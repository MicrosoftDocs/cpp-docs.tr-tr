---
title: wcrtomb_s
ms.date: 11/04/2016
apiname:
- wcrtomb_s
apilocation:
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
apitype: DLLExport
f1_keywords:
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: 7fe7fba861eecec562928cf381973f62a4db60fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155478"
---
# <a name="wcrtombs"></a>wcrtomb_s

Bir geniş karakter çok baytlı karakterin gösterimine dönüştürür. Bir sürümünü [wcrtomb](wcrtomb.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*pReturnValue*<br/>
Bir hata oluşursa, yazılan bayt sayısı veya -1 döndürür.

*mbchar*<br/>
Sonuçta elde edilen çok baytlı karakter dönüştürülür.

*sizeOfmbchar*<br/>
Boyutu *mbchar* bayt değişken.

*wchar*<br/>
Dönüştürülecek bir geniş karakter.

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** nesne.

## <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür veya bir **errno** bir hata oluşursa değeri.

## <a name="remarks"></a>Açıklamalar

**Wcrtomb_s** işlevi dönüştürür bir geniş karakter içerdiği belirtilen dönüşüm durumu başlayarak *mbstate*, bulunan değerden *wchar*, içine adresi temsil ettiği *mbchar*. *PReturnValue* değerinin dönüştürülmüş bayt, ancak Hayır sayısını olması birden fazla **MB_CUR_MAX** bayt veya bir hata oluştu, -1.

Varsa *mbstate* null, iç **mbstate_t** dönüştürme durumu kullanılır. Karakter içeriyorsa *wchar* karşılık gelen çok baytlı bir karakter olan değerini yok *pReturnValue* -1 olur ve işlev döndürür **errno** değerini **EILSEQ**.

**Wcrtomb_s** işlevi farklıdır [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md) kendi restartability tarafından. Dönüştürme durumunu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır. Örneğin, bir uygulama kullanırsınız **wcsrlen** yerine **wcslen**sonraki çağrı, **wcsrtombs_s** yerine kullanılan **wcstombs_s**.

C++'da, bu işlevi kullanmak şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Wcrtomb_s** işlevi, geçerli iş parçacığındaki hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlev yürütülürken ve *mbstate* null.

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
|**wcrtomb_s**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
