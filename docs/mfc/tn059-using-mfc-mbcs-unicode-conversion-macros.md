---
title: 'TN059: MFC MBCS-Unicode dönüştürme makrolarını kullanma'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.mbcs
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
ms.openlocfilehash: 130b459dc87f36325d0f253181a196bea868856f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399622"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC MBCS/Unicode dönüştürme makrolarını kullanma

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not AFXPRIV içinde tanımlanan MBCS/Unicode dönüştürme makrolarını kullanma açıklanmaktadır. H Bu makrolar, uygulama anlaşmalarınızı doğrudan OLE API'si ile ya da herhangi bir nedenle genellikle gerekiyorsa MBCS ve Unicode arasında dönüştürme ekseriyetle faydalıdır.

## <a name="overview"></a>Genel Bakış

MFC'de özel bir DLL 3.x edildi (MFCANS32. kullanılan DLL) OLE arabirimleri çağrıldığında Unicode ve MBCS arasında otomatik olarak dönüştürmek için kullanılır. OLE uygulamaları MBCS, arabirimleri ve OLE API'leri gibi her zaman Unicode olsalar yazılmasına izin neredeyse saydam bir katmanı bu DLL edildi (Macintosh üzerinde hariç). Bu katman kullanışlı ederken ve izin verilen uygulamaları hızlı bir şekilde Win16 ' Win32 için unity'nin (MFC, Microsoft Word, Microsoft Excel ve VBA bazıları yalnızca bu teknoloji kullanılan Microsoft uygulamalarının), bazen önemli bir performans vardı isabet. Bu nedenle, MFC 4.x bu DLL kullanmaz ve bunun yerine doğrudan Unicode OLE arabirimleri hakkında konuşuyor. Bunu yapmak için MFC MBCS Unicode OLE arayüz için bir arama yaparken dönüştürmek gereken ve genellikle bir OLE arabirimi uygulanırken MBCS'den Unicode dönüştürme gerekiyor. Makrolar sayısı bu verimli ve kolay bir şekilde işlemek için bu dönüştürme kolaylaştırmak için oluşturuldu.

Bu tür makroları kümesi oluşturmanın en büyük üstesinden bellek ayırma biridir. Dizeler yerinde dönüştürülemediğinden, dönüştürülen sonuçlar tutmak için yeni bellek ayrılması gerekir. Bu kod aşağıdaki gibi ile yapılmış:

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

Bu yaklaşım olarak çeşitli sorunlar. Temel sorun kod yazma, test ve hata ayıklama için çok fazla olmasıdır. Bir şey, bir basit işlev çağrı artık çok daha karmaşıktır. Ayrıca, bunu yaparken ek yükünü önemli bir çalışma zamanı yoktur. Yığında ayrılmış ve bir dönüştürme yapılır her zaman serbest bellek var. Son olarak, yukarıdaki kod uygun gereklidir `#ifdefs` (hangi gerçekleşmesi için bu dönüştürme gerektirmeyen) Unicode ve Macintosh yapılar için eklendi.

Biz birlikte gelen yedekleme çözümü hangi 1) maskesi çeşitli platformlara ve (2) kullanımı bir verimli bellek ayırma şeması arasındaki farkı ve 3) olan mevcut eklemek kolay kaynak kodu bazı makrolar oluşturmaktır. Tanımlarının bir örneği aşağıda verilmiştir:

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

Bu makro, yukarıdaki kod yerine ve şeyleri kullanarak çok daha kolaydır:

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

Burada dönüştürme gereklidir, ancak makroları kullanarak basit ve etkili ek çağrıları vardır.

Her makrosu uygulamasını _alloca() işlev yığın yerine yığından bellek ayırmak için kullanır. Yığında bellek ayırma daha çok daha hızlı yığından bellek ayırma ve bellek işlevi çıkıldı olduğunda otomatik olarak serbest bırakılır. Ayrıca, makroları çağırmaktan kaçınmanız `MultiByteToWideChar` (veya `WideCharToMultiByte`) birden fazla kez. Bu, gerekli olandan biraz daha fazla bellek ayırma tarafından gerçekleştirilir. En fazla birine dönüştürecek bir MBC biliyoruz **WCHAR** ve her **WCHAR** en fazla iki MBC bayt sahibiz. Ancak her zaman yeterince biraz daha fazla gerekli ayırarak ikinci çağrı, ikinci dönüştürme işlemek için dönüştürme işlevine çağrı önlenmiş olur. Yardımcı işlevi çağrısını `AfxA2Whelper` azaltır dönüştürme gerçekleştirmek için gerçekleştirilmesi gereken bağımsız değişken gönderim sayısı (adlı bu daha küçük kod içinde daha sonuçlarını `MultiByteToWideChar` doğrudan).

Sırada depolamak için makroları alanınız için bir geçici uzunluğu, her işlev yapan _csv'ye Dönüştür adlı bir yerel değişken dönüşüm makroları kullanacağını belirtmeniz gerekli. Bu işlem, yukarıdaki örnekte görüldüğü gibi USES_CONVERSION makrosu çağrılarak gerçekleştirilir.

Genel dönüşüm makroları hem OLE belirli makroları vardır. Bu iki farklı makrosu kümesi aşağıda ele alınmıştır. Tüm makroları AFXPRIV içinde yer alır. H

## <a name="generic-conversion-macros"></a>Genel dönüşüm makroları

Genel dönüşüm makroları temel mekanizması oluşturur. Makro örneği A2W, önceki bölümde gösterilen uygulama olduğundan, bu tür bir "Genel" makrosu. Bunun için OLE özellikle ilgili değildir. Genel makrolar kümesini aşağıda verilmiştir:

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

Metin dönüştürmeleri yapmak yanı sıra, ayrıca vardır makroları ve dönüştürmek için yardımcı işlevleri `TEXTMETRIC`, `DEVMODE`, `BSTR`ve ayrılan dizeleri OLE. Bu makrolar bu tartışma kapsamı dışındadır - AFXPRIV için bakın. Bu makrolar hakkında daha fazla bilgi için H.

## <a name="ole-conversion-macros"></a>OLE dönüşüm makroları

OLE dönüşüm makroları beklediğiniz işlevleri işlemek için özel olarak tasarlanmış **OLESTR** karakter. OLE üstbilgileri incelemek, birçok başvuruları görürsünüz **LPCOLESTR** ve **OLECHAR**. Bu tür, platforma özgü olmayan bir yolla OLE arabirimleri kullanılan karakter türü belirtmek için kullanılır. **OLECHAR** eşlendiği **char** Win16 ve Macintosh platformlarda ve **WCHAR** Win32'de.

Sayısı tutulabilmesi için **#ifdef** MFC'de yönergeleri için en az kod her dönüştürme için benzer bir makro sahibiz, OLE dizeleri söz konusu burada. Aşağıdaki makroları en yaygın olarak kullanılır:

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

Yeniden TEXTMETRIC, DEVMODE BSTR ve dizeleri ayrılan OLE yapmak için benzer makroları vardır. AFXPRIV için bakın. Daha fazla bilgi için H.

## <a name="other-considerations"></a>Diğer Konular

Makrolar, sıkı bir döngüde kullanmayın. Örneğin, aşağıdaki türde bir kod yazmak istiyor musunuz:

```
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

Yukarıdaki kod, megabayt hangi dize içeriğine bağlı olarak yığında bellek ayırma sonuçlanabilir `lpsz` olan! Ayrıca döngünün her yinelemesinden için dize dönüştürmek için zaman alır. Bunun yerine, sabit tür dönüştürmeler döngü dışına taşıyın:

```
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

Dize sabit değil, bir işlev uygulamasına yöntem çağrısının ardından kapsüller. Bu, her zaman serbest bırakılacak dönüştürme arabellek olanak tanır. Örneğin:

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

Dönüş değeri, dönüş önce verileri kopyalayarak gelir sürece hiçbir zaman makroları birinin sonucu döndürür. Örneğin, bu kodu bozuk:

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

Yukarıdaki kod, dönüş değeri, değerin kopyalayan bir değiştirerek sabit:

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

Makroları, kullanımı kolay ve kodunuza eklemek kolaydır, ancak uyarılar yukarıdaki söyleyebilirsiniz gibi bunları kullanırken dikkatli olmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
