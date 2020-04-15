---
title: atoi, _atoi_l, _wtoi, _wtoi_l
ms.date: 4/2/2020
api_name:
- _wtoi
- _wtoi_l
- atoi
- _atoi_l
- _o__atoi_l
- _o__wtoi
- _o__wtoi_l
- _o_atoi
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tstoi
- _wtoi
- _ttoi
- atoi
- _atoi_l
- _wtoi_l
helpviewer_keywords:
- _atoi_l function
- ttoi function
- atoi_l function
- string conversion, to integers
- _wtoi function
- wtoi_l function
- tstoi function
- _ttoi function
- _tstoi function
- _wtoi_l function
- atoi function
- wtoi function
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
ms.openlocfilehash: ef65f8986cf02b6385cbce71e5e81fa690b38b2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348862"
---
# <a name="atoi-_atoi_l-_wtoi-_wtoi_l"></a>atoi, _atoi_l, _wtoi, _wtoi_l

Bir dizeyi tamsayıya dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
int atoi(
   const char *str
);
int _wtoi(
   const wchar_t *str
);
int _atoi_l(
   const char *str,
   _locale_t locale
);
int _wtoi_l(
   const wchar_t *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Dize dönüştürülecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, giriş karakterlerini bir sayı olarak yorumlayarak üretilen **int** değerini döndürür. Giriş bu tür bir değere dönüştürülemiyorsa, **atoi** ve **_wtoi**için dönüş değeri 0'dır.

Büyük negatif integral değerleri ile taşma durumunda, **LONG_MIN** döndürülür. **atoi** ve **_wtoi** bu koşullarda **INT_MAX** ve **INT_MIN** dönerler. Tüm kapsama alanı dışı durumlarda, **errno** **ERANGE**olarak ayarlanır. Geçirilen parametre **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve 0 döndürün.

## <a name="remarks"></a>Açıklamalar

Bu işlevler bir karakter dizesini tamsayı değerine **(atoi** ve **_wtoi)** dönüştürür. Giriş dizesi, belirtilen türün sayısal değeri olarak yorumlanabilecek bir karakter dizisidir. İşlev, bir sayının parçası olarak tanıyamadığı ilk karakterdeki giriş dizesini okumayı durdurur. Bu karakter, dizeyi sonlayan null karakter ('\0' veya L'\0') olabilir.

**atoi** ve **_wtoi** *str* argümanı aşağıdaki formu vardır:

> [*beyazuzay*] [*işaret*] [*basamak ]]*

Bir *boşluk,* yoksayılan boşluk veya sekme karakterlerinden oluşur; *işareti* artı (+) veya eksi (-); ve *basamaklar* bir veya daha fazla basamakvardır.

Bu işlevlerin **_l** soneki olan sürümleri, geçerli yerel alan yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstoi**|**atoi**|**atoi**|**_wtoi**|
|**_ttoi**|**atoi**|**atoi**|**_wtoi**|

## <a name="requirements"></a>Gereksinimler

|Rutin|Gerekli başlık|
|--------------|---------------------|
|**atoi**|\<stdlib.h>|
|**_atoi_l**, **_wtoi**, **_wtoi_l**|\<stdlib.h> \<veya wchar.h>|

## <a name="example"></a>Örnek

Bu program, dizeleri olarak depolanan **sayıların atoi** işlevlerini kullanarak sayısal değerlere nasıl dönüştürülebileceğini gösterir.

```C
// crt_atoi.c
// This program shows how numbers
// stored as strings can be converted to
// numeric values using the atoi functions.

#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    int     value = 0;

    // An example of the atoi function.
    str = "  -2309 ";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );

    // Another example of the atoi function.
    str = "31412764";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );

    // Another example of the atoi function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atoi( "  -2309 " ) = -2309
Function: atoi( "31412764" ) = 31412764
Function: atoi( "3336402735171707160320" ) = 2147483647
Overflow condition occurred.
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
