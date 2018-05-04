---
title: wcrtomb | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcrtomb
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
- wcrtomb
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eca27e81cbb1df26d04059974cdc1ce5313bafa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="wcrtomb"></a>wcrtomb

Geniş karakter, birden çok baytlı karakter gösterimine dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [wcrtomb_s](wcrtomb-s.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*mbchar*<br/>
Sonuçta elde edilen çok baytlı karakter dönüştürülür.

*wchar*<br/>
Dönüştürülecek geniş karakter.

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa dönüştürülen birden çok baytlı karakter yoksa -1 göstermek için gereken bayt sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**Wcrtomb** işlevi dönüştürür bulunan belirtilen dönüşüm durumunu'den başlayarak bir geniş karakter *mbstate*, içerdiği değerinden *wchar*, içine Adres temsil ettiği *mbchar*. Dönüş değeri karşılık gelen birden çok baytlı karakter temsil etmek için gereken bayt sayısıdır. ancak değil döndürülecek birden fazla **MB_CUR_MAX** bayt sayısı.

Varsa *mbstate* null, iç **mbstate_t** dönüştürme durumunu içeren bir nesne *mbchar* kullanılır. Varsa bir karakter dizisi *wchar* karşılık gelen çok baytlı yok karakter gösterimi, -1 döndürülür ve **errno** ayarlanır **EILSEQ**.

**Wcrtomb** işlevi farklı olarak [wctomb, _wctomb_l](wctomb-wctomb-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan *mbstate* sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanırsınız **wcsrlen** yerine **wcsnlen**, bir sonraki çağrı, **wcsrtombs** yerine kullanılan **wcstombs**.

C++'da, bu işlev bu işlevin yeni, güvenli ortaklarınıza çağıran bir şablon aşırı sahiptir. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Wcrtomb** işlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu **setlocale** bu işlev yürütülürken ve sırasında *mbstate* null.

## <a name="example"></a>Örnek

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
