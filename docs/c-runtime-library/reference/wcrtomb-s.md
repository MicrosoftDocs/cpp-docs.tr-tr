---
title: wcrtomb_s
ms.date: 11/04/2016
api_name:
- wcrtomb_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: c1612e7fc4e40e05c46f06d8a29b69534c359421
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945841"
---
# <a name="wcrtomb_s"></a>wcrtomb_s

Geniş bir karakteri çok baytlı karakter gösterimine dönüştürür. [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi, güvenlik geliştirmeleriyle [wcrtomb](wcrtomb.md) sürümü.

## <a name="syntax"></a>Sözdizimi

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Ön kapatma değeri*<br/>
Bir hata oluştuysa, yazılan bayt sayısını veya-1 değerini döndürür.

*mbchar*<br/>
Elde edilen çok baytlı karakter dönüştürülmüş karakteri.

*sizeOfmbchar*<br/>
*Mbchar* değişkeninin bayt cinsinden boyutu.

*wchar*<br/>
Dönüştürülecek geniş bir karakter.

*mbstate*<br/>
**Mbstate_t** nesnesine yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa sıfır veya **errno** değeri döndürür.

## <a name="remarks"></a>Açıklamalar

**Wcrtomb_s** işlevi, belirtilen dönüştürme durumundan itibaren, *wchar*içinde bulunan değerden *mbchar*tarafından temsil edilen adrese *kadar olan bir*geniş karakteri dönüştürür. *PReturnValue* değeri, dönüştürülen bayt sayısı, ancak en fazla **MB_CUR_MAX** bayt veya bir hata oluştuysa-1 olacaktır.

*Mbstate* null ise, iç **mbstate_t** dönüştürme durumu kullanılır. *Wchar* içinde yer alan karakterin karşılık gelen bir çok baytlı karakteri yoksa, *pReturnValue* değeri-1 olur ve Işlev **errno** değeri **eilseq**' i döndürür.

**Wcrtomb_s** işlevi, [wctomb_s, _wc^ s_l](wctomb-s-wctomb-s-l.md) öğesinden yeniden startability 'a göre farklılık gösterir. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır. Örneğin, **wcstombs_s**yerine **wcsrtombs_s** için sonraki bir çağrı kullanıldıysa, bir uygulama **wcslen**yerine **wcsrlen** kullanır.

' C++De, bu işlevin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

Geçerli iş parçacığında hiçbir işlev bu işlev yürütülürken ve *mbstate* null olduğunda, **wcrtomb_s** işlevi çoklu iş parçacığı güvenlidir.

## <a name="example"></a>Örnek

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar. h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
