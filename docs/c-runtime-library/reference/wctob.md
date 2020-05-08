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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: f402b090409c2eb5dc8db457776140a27f8f820e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910483"
---
# <a name="wctob"></a>wctob

Geniş bir karakterin çok baytlı bir karaktere karşılık geldiğini ve çok baytlı karakter gösterimini döndürüp döndürmeyeceğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Parametreler

*wchar*<br/>
Çevrilecek değer.

## <a name="return-value"></a>Dönüş Değeri

**Wctob** , geniş bir karakteri başarıyla dönüştürdüğünde, yalnızca çok baytlı karakter tam olarak bir bayt uzunluğunda ise çok baytlı karakter gösterimini döndürür. **Wctob** çok baytlı bir karaktere dönüştüremediği veya çok baytlı karakter tam olarak bir bayt uzunluğunda değilse,-1 döndürür.

## <a name="remarks"></a>Açıklamalar

**Wctob** işlevi, çok baytlı karakter tam olarak bir bayt uzunsa, *wchar* içindeki bir geniş karakteri Return **Int** değeri ile geçirilen karşılık gelen çok baytlı karaktere dönüştürür.

**Wctob** başarısız olduysa ve karşılık gelen çok baytlı karakter bulunmazsa, işlev **errno** ' ı **eilseq** olarak ayarlar ve-1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctob**|\<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu program **wcstombs** işlevinin davranışını gösterir.

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[Widechartoçok baytlı](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
