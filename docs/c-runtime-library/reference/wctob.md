---
title: wctob | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cff2dcb8d6b0ad3756a8a0047fcc9b982fb7bb8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="wctob"></a>wctob

Geniş karakter için birden çok baytlı karakter karşılık gelir ve çok baytlı karakter gösterimini döndürür belirler.

## <a name="syntax"></a>Sözdizimi

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Parametreler

*wchar*<br/>
Çevirmek için değer.

## <a name="return-value"></a>Dönüş Değeri

Varsa **wctob** başarıyla geniş karakter dönüştürür yalnızca birden çok baytlı karakter tam olarak bir bayt uzun olması durumunda, birden çok baytlı karakter gösterim döndürür. Varsa **wctob** karşılaştığı onu dönüştüremiyor birden çok baytlı karakter veya birden çok baytlı karakter geniş karakter olan tam bir bayt uzun, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Wctob** işlevi içinde yer alan geniş karakter dönüştürür *wchar* dönüş tarafından geçirilen karşılık gelen birden çok baytlı karakter **int** , değeri çok baytlı tam olarak bir bayt uzun karakterdir.

Varsa **wctob** başarısız oldu ve karşılık gelen hiçbir birden çok baytlı karakter bulundu, işlevi ayarlar **errno** için **EILSEQ** ve -1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctob**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu programın davranışını gösterilmektedir **wcstombs** işlevi.

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
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
