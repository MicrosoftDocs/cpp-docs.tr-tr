---
title: wctob
ms.date: 11/04/2016
apiname:
- wctob
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
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: c40fd6a6094aa6f0c8c153bb00420d1e990dbbb2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635493"
---
# <a name="wctob"></a>wctob

Bir geniş karakter karşılık gelen çok baytlı bir karakter ve çok baytlı karakterin gösterimine döndürür belirler.

## <a name="syntax"></a>Sözdizimi

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Parametreler

*wchar*<br/>
Çevrilecek değeri.

## <a name="return-value"></a>Dönüş Değeri

Varsa **wctob** başarıyla bir geniş karakter dönüştürür, çok baytlı karakter gösterimi yalnızca çok baytlı karakter tam olarak bir bayt uzunluğunda olup olmadığını döndürür. Varsa **wctob** karşılaşıyorsa, dönüştüremiyor bir çok baytlı karakter veya çok baytlı karakterin bir geniş karakterse tam olarak bir bayt uzunluğunda, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Wctob** işlevi dönüştürür bulunan bir geniş karakter *wchar* dönüş tarafından geçirilen çok baytlı karaktere karşılık gelen **int** değerini ise çok baytlı tam olarak bir bayt uzunluğunda karakterdir.

Varsa **wctob** başarısız oldu ve karşılık gelen hiçbir çok baytlı karakter bulundu, işlev ayarlar **errno** için **EILSEQ** ve -1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctob**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program davranışlarını gösterir **wcstombs** işlevi.

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}

```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
