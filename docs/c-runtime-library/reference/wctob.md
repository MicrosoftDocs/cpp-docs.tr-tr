---
title: wctob
ms.date: 4/2/2020
api_name:
- wctob
- _o_wctob
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: 420071680c3dc273f6df637cf44273f2c24bd64c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320439"
---
# <a name="wctob"></a>wctob

Geniş bir karakterin çok bayt karaktere karşılık gelip olmadığını belirler ve çok bayt karakter gösterimini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Parametreler

*Wchar*<br/>
Çevrilecek değer.

## <a name="return-value"></a>Dönüş Değeri

**Wctob** geniş bir karakteri başarıyla dönüştürürse, çok bayt karakter gösterimini, yalnızca çok bayt karakteri tam olarak bir bayt uzunluğundaysa döndürür. **Wctob** geniş bir karakterle karşılaşırsa çok bayt karaktere dönüştürülemez veya çok bayt karakteri tam olarak bir bayt uzunluğunda değildir, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Wctob** işlevi, çok bayt karakteri tam olarak bir bayt uzunluğundaysa, *wchar'da* bulunan geniş bir karakteri return **int** değeri tarafından geçirilen karşılık gelen çok bayt karaktere dönüştürür.

**Wctob** başarısız olduysa ve karşılık gelen çok bayt karakteri bulunamadıysa, fonksiyon **errno'yu** **EILSEQ'ya** ayarlar ve -1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program **wcstombs** işlevinin davranışını göstermektedir.

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
