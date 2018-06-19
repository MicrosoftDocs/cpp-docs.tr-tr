---
title: 'TN059: MFC MBCS Unicode dönüştürme makrolarını kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.mbcs
dev_langs:
- C++
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 379c5b4fb9ed302ad1ea0167f2b32c30e48ab2bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384296"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC MBCS/Unicode Dönüştürme Makrolarını Kullanma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not AFXPRIV içinde tanımlanan MBCS/Unicode dönüştürme makrolarını kullanma açıklanır. H. Bu makroları uygulama anlaşmalar doğrudan OLE API ile ya da herhangi bir nedenle genellikle gerekiyorsa Unicode ve MBCS arasında dönüştürme çok kullanışlıdır.  
  
## <a name="overview"></a>Genel Bakış  
 MFC'de özel DLL 3.x oluştu (MFCANS32. kullanılan OLE arabirimleri çağrıldığında Unicode ve MBCS arasında otomatik olarak dönüştürmek için DLL). OLE uygulamaları OLE API ve arabirimler MBCS, değilmiş gibi her zaman Unicode olsalar yazılmasına izin neredeyse saydam bir katman bu DLL oluştu (Macintosh üzerinde hariç). Bu katman uygun ederken ve izin verilen uygulamalarını hızla Win16 Win32 öğesine bağlantı noktası kurulmuş (MFC, Microsoft Word, Microsoft Excel ve VBA, bazıları yalnızca bu teknoloji kullanılan Microsoft uygulamalarını), bazen önemli bir performans vardı ulaştı. Bu nedenle, MFC 4.x bu DLL kullanmaz ve bunun yerine doğrudan Unicode OLE arabirimleri ettiği. Bunu yapmak için MFC MBCS Unicode'a OLE arabirimi için bir arama yaparken dönüştürmek gereken ve genellikle bir OLE arabirimi uygularken MBCS'den Unicode dönüştürmek gereken. Bu verimli bir şekilde ve kolayca işlemek amacıyla makroları sayısı bu dönüştürme kolaylaştırmak için oluşturuldu.  
  
 Bu tür makroları kümesi oluşturma en büyük zorluklardan bellek ayırma biridir. Dizeleri yerinde dönüştürülemediği için dönüştürülen sonuçları tutmak için yeni bellek tahsis edilmelidir. Bu aşağıdakine benzer bir kod ile yapılmış:  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP,
    0,   
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string  
delete[] lpszW;  
```  
  
 Bu yaklaşım sorunları sayısı. Ana sorunu çok sayıda yazma, test ve hata ayıklamak için kod olmasıdır. Bir şey basit işlev çağrısı oluştu, artık çok daha karmaşıktır. Ayrıca, bunu yaparken yükü önemli bir çalışma zamanı yok. Bellek yığında ayrılmış ve bir dönüştürme yapılan her zaman serbest bulunur. Son olarak, yukarıdaki kod olması uygun gerekir `#ifdefs` (hangi gerçekleşmesi için bu dönüştürme gerektirmeyen) Unicode ve Macintosh yapıları için eklenmiştir.  
  
 Biz ile gelen çözüm hangi 1) maskesi çeşitli platformlar ve 2) kullanım verimli bellek ayırma şeması arasındaki farkı ve 3) olan mevcut eklemek kolay kaynak kodu bazı makrolar oluşturmaktır. Tanımları bir örneği burada verilmiştir:  
  
```  
#define A2W(lpa) (\  
 ((LPCSTR)lpa == NULL) NULL : (\  
    _convert = (strnlen(lpa)+1),\  
    AfxA2WHelper((LPWSTR) alloca(_convert*2),   
    lpa,
    _convert)\)\)  
```  
  
 Bu Yukarıdaki kod yerine makrosu ve şeyler kullanarak çok daha kolaydır:  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```  
  
 Burada dönüştürme gereklidir, ancak makrolarını kullanarak basit ve etkili ek çağrıları vardır.  
  
 Her makrosu uyarlamasını _alloca() işlevi öbek yerine yığından bellek ayırmak için kullanır. Yığından bellek ayırma yığınındaki bellek ayırma daha hızlıdır ve işlev çıkıldı zaman bellek boşaltılır. Ayrıca, arama makroları kaçının **MultiByteToWideChar** (veya **WideCharToMultiByte**) birden fazla kez. Bu, gerekli olandan biraz daha fazla bellek ayırarak gerçekleştirilir. Bir MBC en fazla bir dönüştürecek biliyoruz **WCHAR** ve her **WCHAR** en çok iki MBC bayt sahip olur. Ancak her zaman yeterli biraz daha fazla gerekli ayırarak dönüştürme ikinci çağrı ikinci işlemek için dönüştürme işlevi çağrısı önlenmiş olur. Yardımcı işlevi çağrısı **AfxA2Whelper** dönüştürme gerçekleştirmek için yapılması gereken bağımsız değişkeni gönderim sayısını azaltır (adlı varsa bu küçük kodda daha sonuçları **MultiByteToWideChar**doğrudan).  
  
 Sırada depolamak için makrolar alanınız için geçici bir uzunluk her işlev, bu mu _mantıksal adlı bir yerel değişken kullanan dönüşüm makroları bildirmek gerekli değildir. Bu çağırarak yapılır **USES_CONVERSION** yukarıdaki örnekte görüldüğü gibi makrosu.  
  
 Genel dönüştürme makrolarını ve OLE belirli makroları vardır. Bu iki farklı makrosu kümeleri aşağıda ele alınmıştır. Tüm makroları AFXPRIV içinde bulunur. H.  
  
## <a name="generic-conversion-macros"></a>Genel dönüşüm makroları  
 Genel dönüştürme makrolarını temel mekanizma oluşturur. Makro örneğini ve A2W, önceki bölümde gösterilen uygulama var. böyle bir "Genel" makrosu Bunun için OLE özellikle ilgili değildir. Genel makroları kümesi aşağıda listelenmiştir:  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 Metin dönüşümleri yapılması yanı sıra da vardır makrolar ve dönüştürmek için yardımcı işlevleri `TEXTMETRIC`, `DEVMODE`, `BSTR`ve OLE dizeleri ayrılmış. Bu tartışma kapsamı dışındadır Bu makrolar olduğunu - için AFXPRIV bakın. H makroları hakkında daha fazla bilgi için.  
  
## <a name="ole-conversion-macros"></a>OLE dönüşüm makroları  
 OLE dönüşüm makroları beklediğiniz işlevleri işlemek için özellikle tasarlanmış **OLESTR** karakter. OLE üstbilgileri incelemek, birçok başvurular görürsünüz **LPCOLESTR** ve **OLECHAR**. Bu tür OLE arabirimleri platforma özgü değildir şekilde kullanılan karakter türünü belirtmek için kullanılır. **OLECHAR** eşlendiği `char` Win16 ve Macintosh platformlarda ve **WCHAR** Win32 içinde.  
  
 Sayısı tutmak için **#ifdef** yönergeleri MFC'de kod minimumda her dönüştürme için benzer bir makro sahibiz, OLE dizeleri söz konusu olduğu. Aşağıdaki makroları en yaygın olarak kullanılır:  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 Yeniden, bunu yapmak için benzer makrolar vardır `TEXTMETRIC`, `DEVMODE`, `BSTR`ve OLE dizeleri ayrılmış. İçin AFXPRIV bakın. Daha fazla bilgi için H.  
  
## <a name="other-considerations"></a>Diğer Konular  
 Makrolar sıkı bir döngüde kullanmayın. Örneğin, aşağıdaki tür kodu yazmak istediğinizde değil:  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
```  
  
 Yukarıdaki kod megabayt bellek hangi dize içeriğine bağlı olarak yığınındaki ayırma sonuçlanabilir `lpsz` değil! Ayrıca, her döngü tekrarında dizesi dönüştürmek için zaman alır. Bunun yerine, döngü dışında sabit tür dönüşümleri Taşı:  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, lpszT);

}  
```  
  
 Dize sabit değilse, bir işlev yöntemi çağrısına kapsüller. Bu, her zaman boşaltılacak dönüştürme arabellek olanak tanır. Örneğin:  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
 
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
    for (int ii = 0; ii <10000; ii++)  
    CallSomeMethod(ii, lpszArray[ii]);

}  
```  
  
 Dönüş değeri dönüş önce verilerin bir kopyasını hale gelir sürece hiçbir zaman makroları birinin sonucu döndürür. Örneğin, bu kodu bozuk.:  
  
```  
LPTSTR BadConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // bad! returning alloca memory  
}  
```  
  
 Yukarıdaki kod değeri kopyalayan bir şey için dönüş değerini değiştirerek sabit:  
  
```  
CString BetterConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // CString makes copy  
}  
```  
  
 Makrolar kodunuza eklemek kolay ve kullanımı kolay, ancak yukarıdaki uyarılar anlayabilirsiniz gibi bunları kullanırken dikkatli olmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

