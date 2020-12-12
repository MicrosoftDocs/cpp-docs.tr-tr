---
description: 'Hakkında daha fazla bilgi edinin: TN059: MFC MBCS/Unicode dönüştürme makrolarını kullanma'
title: 'TN059: MFC MBCS-Unicode dönüştürme makrolarını kullanma'
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
ms.openlocfilehash: c1b767a8d90f2c788a15c9e880056206e7d1326a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214773"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC MBCS/Unicode Dönüştürme Makrolarını Kullanma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, AFXPRıV. H ' de tanımlanan MBCS/Unicode dönüştürme makrolarını kullanma açıklanmaktadır. Bu makrolar en çok yararlı olur çünkü uygulamanız doğrudan OLE API 'siyle veya bir nedenden dolayı, genellikle Unicode ve MBCS arasında dönüştürmelidir.

## <a name="overview"></a>Genel Bakış

MFC 3. x ' te, OLE arabirimleri çağrıldığında Unicode ve MBCS arasında otomatik olarak dönüştürmek için özel bir DLL kullanılmıştır (MFCANS32.DLL). Bu DLL, ole API 'Leri ve arabirimleri, her zaman Unicode (Macintosh dışında) olsalar bile, OLE uygulamalarının ve arabirimlerin MBCS gibi yazılmasına izin veren neredeyse saydam bir katmandır. Bu katman kullanışlı olsa da, izin verilen uygulamaların Win16 'den Win32 'e (MFC, Microsoft Word, Microsoft Excel ve VBA) hızla bir şekilde eklenmesi, bazen önemli bir performans okuması gerekiyordu. Bu nedenle, MFC 4. x bu DLL 'yi kullanmaz ve bunun yerine doğrudan Unicode OLE arabirimlerini kullanır. Bunu yapmak için, MFC 'nin bir OLE arabirimine çağrı yaparken Unicode 'a dönüştürülmesi ve genellikle bir OLE arabirimi uygularken Unicode 'a dönüştürülmesi gerekir. Bunu verimli ve kolay bir şekilde işlemek için, bu dönüştürmeyi kolaylaştırmak için bir dizi makro oluşturulmuştur.

Böyle bir makro kümesi oluşturmanın en büyük sallarından biri bellek ayırdır. Dizeler yerinde dönüştürülemediğinden, dönüştürülen sonuçları tutacak yeni bellek ayrılmalıdır. Bu, aşağıdakine benzer kodla yapılabilir:

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

Bu yaklaşım çok sayıda sorun. Ana sorun, yazma, test ve hata ayıklama için kodun çok büyük olması olabilir. Basit işlev çağrısı olan bir şey artık çok daha karmaşıktır. Ayrıca, bunu yaparken önemli bir çalışma zamanı ek yükü vardır. Bellek, yığın üzerinde ayrılmalıdır ve her dönüştürme tamamlandığında serbest bırakılır. Son olarak, Yukarıdaki kodun `#ifdefs` Unicode ve Macintosh yapılarına (Bu dönüştürmenin gerçekleşmesi gerekmez) uygun şekilde eklenmiş olması gerekir.

Sunduğumuz çözüm, 1 ' in çeşitli platformlar arasındaki farkı maskelemesinin yanı sıra 2) etkin bir bellek ayırma şeması kullanma ve 3) varolan kaynak koda kolayca ekleyebileceğiniz bazı makrolar oluşturmaktır. Tanımlardan birine bir örnek aşağıda verilmiştir:

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

Yukarıdaki kod yerine bu makroyu kullanma ve çok daha basit hale getiriyoruz:

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

Dönüştürmenin gerekli olduğu, ancak makroların kullanılması basit ve etkili olduğu çok fazla çağrı vardır.

Her makronun uygulanması, yığın yerine yığından bellek ayırmak için _alloca () işlevini kullanır. Yığından bellek ayırma, yığında bellek ayırmaya göre çok daha hızlıdır ve işlev çıkıldığında bellek otomatik olarak serbest bırakılır. Ayrıca, makrolar `MultiByteToWideChar` (veya) birden çok kez çağrı yapmaktan kaçınır `WideCharToMultiByte` . Bu, gerekenden biraz daha fazla bellek ayırarak yapılır. MBC 'nin en fazla bir **wchar** 'a dönüştüp her **wchar** IÇIN en fazla iki MBC bayt olacağını biliyoruz. Gerekenden biraz daha fazlasını ayırarak, ancak dönüştürmeyi işlemek için her zaman yeterince, dönüştürme işlevine ikinci çağrı ikinci çağrısı kaçınılmaz. Yardımcı işlevine yapılan çağrı, `AfxA2Whelper` Dönüştürmeyi gerçekleştirmek için yapılması gereken bağımsız değişken gönderimlerin sayısını azaltır (Bu, doğrudan çağrılmadığı gibi daha küçük bir koda neden olur `MultiByteToWideChar` ).

Makroların geçici bir uzunluğu depolaması için alana sahip olması için, dönüştürme makrolarını kullanan her işlevde bunu yapan _convert adlı bir yerel değişken bildirmek gerekir. Bu, örnekte görüldüğü gibi USES_CONVERSION makrosunu çağırarak yapılır.

Hem genel dönüştürme makroları hem de OLE 'ye özgü makrolar vardır. Bu iki farklı makro kümesi aşağıda ele alınmıştır. Tüm makrolar AFXPRıV. H içinde bulunur.

## <a name="generic-conversion-macros"></a>Genel dönüştürme makroları

Genel dönüştürme makroları temel mekanizmayı oluşturur. Önceki bölümde gösterilen makro örneği ve uygulama A2W, bu tür "genel" bir makrodur. Özellikle OLE ile ilgili değildir. Genel makrolar kümesi aşağıda listelenmiştir:

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

Metin dönüştürmeleri yapmanın yanı sıra,,, `TEXTMETRIC` `DEVMODE` ve OLE tarafından ayrılan dizeleri dönüştürmek için makrolar ve yardımcı işlevler de vardır `BSTR` . Bu makrolar, bu tartışma kapsamının ötesinde-AFXPRıV 'e başvurun. Bu makrolar hakkında daha fazla bilgi için H.

## <a name="ole-conversion-macros"></a>OLE dönüştürme makroları

OLE dönüştürme makroları, **olestr** karakter bekleyen işlevleri işlemek için özel olarak tasarlanmıştır. OLE üst bilgilerini incelerseniz, **Lpcolonstr** ve **olechar** için çok sayıda başvuru görürsünüz. Bu türler, OLE arabirimlerinde kullanılan karakterlerin türüne, platforma özgü olmayan bir şekilde başvurmak için kullanılır. **Olechar** , **`char`** Win16 ve Macintosh platformları ve Win32 'teki **wchar** ile eşlenir.

MFC kodundaki **#ifdef** yönergelerinin sayısını en düşük düzeyde tutmak için OLE dizelerinin bulunduğu her dönüştürme için benzer bir makroya sahipsiniz. En yaygın olarak kullanılan makrolar şunlardır:

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

Daha sonra, TEXTMETRIC, DEVMODE, BSTR ve OLE tarafından ayrılan dizeler için de benzer makrolar vardır. AFXPRıV 'e bakın. Daha fazla bilgi için.

## <a name="other-considerations"></a>Diğer Konular

Makroları sıkı bir döngüde kullanmayın. Örneğin, aşağıdaki kod türünü yazmak istemezsiniz:

```cpp
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

Yukarıdaki kod, dizenin içeriklerinin ne olduğuna bağlı olarak yığında belleğin megabayt olarak ayrılmasına neden olabilir `lpsz` ! Ayrıca, her döngü yinelemesi için dizeyi dönüştürmek zaman alır. Bunun yerine, bu tür sabit dönüştürmeleri döngüden dışarı taşıyın:

```cpp
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

Dize sabit değilse, yöntem çağrısını bir işleve kapsülleyebilirsiniz. Bu, dönüştürme arabelleğinin her seferinde serbest bırakılmış olmasını sağlar. Örneğin:

```cpp
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

Dönüş değeri, döndürmeden önce verilerin bir kopyasını yapmayı belirtmedikçe, makrolardan birinin sonucunu hiçbir şekilde geri döndürün. Örneğin, bu kod hatalı:

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

Yukarıdaki kod, dönüş değeri değeri kopyalayan bir şeye değiştirilerek düzeltilebilir:

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

Makroların kullanımı kolaydır, ancak yukarıdaki uyarılarla, yukarıdaki uyarılarla söylemek gerekirse, bunları kullanırken dikkatli olmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
