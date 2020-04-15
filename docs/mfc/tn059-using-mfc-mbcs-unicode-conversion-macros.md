---
title: 'TN059: MFC MBCS-Unicode Dönüşüm Makrolarını Kullanma'
ms.date: 11/04/2016
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
ms.openlocfilehash: 0d63a87d0fddde30dd5cbb18207297a345d74b9c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366587"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC MBCS/Unicode Dönüştürme Makrolarını Kullanma

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, AFXPRIV'de tanımlanan MBCS/Unicode dönüştürme makrolarının nasıl kullanılacağını açıklar. H. Bu makrolar, uygulamanız doğrudan OLE API ile veya bir nedenle işlerle ilgileniyorsa, genellikle Unicode ve MBCS arasında dönüştürme yapması gerekiyorsa, en kullanışlı olanlardır.

## <a name="overview"></a>Genel Bakış

MFC 3.x'te özel bir DLL kullanılmıştır (MFCANS32). DLL) OLE arabirimleri çağrıldığında Unicode ve MBCS arasında otomatik olarak dönüştürmek için. Bu DLL, OLE uygulamalarının her zaman Unicode olmasına rağmen (Macintosh hariç) OLE API'leri ve arabirimleri MBCS gibi yazılmasına izin veren neredeyse saydam bir katmandı. Bu katman kullanışlı ve uygulamaların Win16'dan Win32'ye (MFC, Microsoft Word, Microsoft Excel ve VBA) hızlı bir şekilde taşınabilir olmasına izin verirken, bu teknolojiyi kullanan Microsoft uygulamalarından sadece bazılarıdır), bazen önemli bir performans isabeti vardı. Bu nedenle, MFC 4.x bu DLL'yi kullanmaz ve bunun yerine doğrudan Unicode OLE arabirimleriyle konuşur. Bunu yapmak için, MFC'nin OLE arabirimine arama yaparken Unicode'a MBCS'ye dönüştürmesi gerekir ve genellikle OLE arabirimi uygularken Unicode'dan MBCS'ye dönüştürmesi gerekir. Bu etkin ve kolay bir şekilde işlemek için, bu dönüşümü kolaylaştırmak için bir dizi makro oluşturuldu.

Böyle bir makro kümesi oluşturmanın önündeki en büyük engellerden biri bellek ayırmadır. Dizeleri yerine dönüştürülemediğinden, dönüştürülen sonuçları tutmak için yeni bellek ayrılması gerekir. Bu, aşağıdakilere benzer bir kodla yapılmış olabilir:

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

Bu yaklaşım bir takım sorunlar olarak. Temel sorun, yazmak, test etmek ve hata ayıklamak için kod çok olmasıdır. Basit bir işlev çağrısı olan bir şey, şimdi çok daha karmaşıktır. Buna ek olarak, bunu yaparken önemli bir çalışma zamanı yükü vardır. Bellek yığın adamalıdır ve bir dönüştürme yapılır her zaman serbest. Son olarak, yukarıdaki kodun `#ifdefs` Unicode ve Macintosh yapıları için uygun şekilde eklenmesi gerekir (bu dönüştürmenin gerçekleşmesini gerektirmez).

Biz geldi çözüm 1) maske çeşitli platformlar arasındaki farkı bazı makrolar oluşturmak ve 2) verimli bir bellek ayırma düzeni kullanmak ve 3) varolan kaynak kodu na eklemek kolaydır. Tanımlardan birine bir örnek aşağıda verilmiştir:

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

Yukarıdaki kod yerine bu makro kullanarak ve şeyler çok daha basittir:

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

Dönüştürmenin gerekli olduğu ekstra aramalar vardır, ancak makroları kullanmak basit ve etkilidir.

Her makronun uygulanması, yığın yerine yığından bellek ayırmak için _alloca() işlevini kullanır. Bellek yığınından ayırmak yığındaki belleği ayırmaktan çok daha hızlıdır ve işlev çıkarıldığında bellek otomatik olarak serbest bırakılır. Ayrıca, makrolar birden `MultiByteToWideChar` fazla `WideCharToMultiByte`kez aramayapmaktan (veya) kaçınmak. Bu, gerekenden biraz daha fazla bellek ayırarak yapılır. Bir MBC'nin en fazla bir **WCHAR'a** dönüşeceğini ve her **WCHAR** için en fazla iki MBC bayt'a sahip olacağımızı biliyoruz. Gerekli olandan biraz daha fazlasını tahsis ederek, ancak her zaman dönüştürmeyi işlemek için yeterli olan dönüşüm işlevine ikinci çağrı yapılması önlenir. Yardımcı işlevine `AfxA2Whelper` yapılan çağrı, dönüştürmeyi gerçekleştirmek için yapılması gereken bağımsız değişken itme sayısını azaltır (bu, `MultiByteToWideChar` doğrudan çağrıldığına göre daha küçük kodla sonuçlanır).

Makroların geçici bir uzunluğu depolamak için alana sahip olması için, dönüşüm makrolarını kullanan her işlevde bunu yapan _convert adlı yerel bir değişkenin bildirilmesi gerekir. Bu, örnekte yukarıda görüldüğü gibi USES_CONVERSION makrosu çağırılarak yapılır.

Hem genel dönüşüm makroları hem de OLE'ye özgü makrolar vardır. Bu iki farklı makro kümesi aşağıda ele alınmıştır. Makroların tümü AFXPRIV'de yer eder. H.

## <a name="generic-conversion-macros"></a>Genel Dönüşüm Makroları

Genel dönüşüm makroları altta yatan mekanizmayı oluşturur. Makro örneği ve önceki bölümde gösterilen uygulama, A2W, böyle bir "genel" makrodur. Özellikle OLE ile ilgili değildir. Genel makrolar kümesi aşağıda listelenmiştir:

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

Metin dönüştürmeleri yapmanın yanı sıra, dönüştürme için makrolar `TEXTMETRIC` `DEVMODE`ve `BSTR`yardımcı işlevleri de vardır , , ve OLE ayrılmış dizeleri. Bu makrolar bu tartışmanın kapsamı dışındadır - AFXPRIV bakın. Bu makrolar hakkında daha fazla bilgi için H.

## <a name="ole-conversion-macros"></a>OLE Dönüşüm Makroları

OLE dönüştürme makroları, **OLESTR** karakterlerini bekleyen işlevleri işlemek için özel olarak tasarlanmıştır. OLE üstbilgilerini incelerseniz, **LPCOLESTR** ve **OLECHAR'a**birçok başvuru görürsünüz. Bu türler, OLE arabirimlerinde kullanılan karakter türlerini platforma özgü olmayan bir şekilde ifade etmek için kullanılır. Win16 ve Macintosh platformlarında **Char** **OLECHAR** haritaları ve **WCHAR** Win32 içinde.

MFC kodundaki **#ifdef** yönergelerinin sayısını en aza tutmak için, OLE dizelerinin dahil olduğu her dönüşüm için benzer bir makromuz vardır. Aşağıdaki makrolar en sık kullanılan makrolar şunlardır:

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

Yine, TEXTMETRIC, DEVMODE, BSTR ve OLE ayrılmış dizeleri yapmak için benzer makrolar vardır. AFXPRIV'e bakın. Daha fazla bilgi için H.

## <a name="other-considerations"></a>Diğer Konular

Makroları sıkı bir döngü içinde kullanmayın. Örneğin, aşağıdaki tür kod yazmak istemiyorum:

```
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

Yukarıdaki kod, dize `lpsz` içeriğine bağlı olarak yığınüzerinde bellek megabayt ayırma neden olabilir! Ayrıca döngü her yineleme için dize dönüştürmek için zaman alır. Bunun yerine, bu tür sabit dönüşümleri döngüdışına taşıyın:

```
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

Dize sabit değilse, yöntem çağrısını bir işleve kapsülle. Bu, dönüşüm arabelleği her zaman serbest bırakılacak izin verir. Örneğin:

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

İade değeri, iadeden önce verilerin bir kopyasının yapılması anlamına gelmediği sürece makrolardan birinin sonucunu asla döndürmeyin. Örneğin, bu kod kötü:

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

Yukarıdaki kod, iade değerini değeri kopyalayan bir şeyle değiştirilerek düzeltilebilir:

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

Makroların kullanımı ve kodunuza eklenmesi kolaydır, ancak yukarıdaki uyarılardan da anlayabileceğiniz gibi, bunları kullanırken dikkatli olmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
