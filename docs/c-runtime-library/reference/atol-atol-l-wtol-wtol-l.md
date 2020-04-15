---
title: atol, _atol_l, _wtol, _wtol_l
ms.date: 4/2/2020
api_name:
- atol
- _wtol_l
- _wtol
- _atol_l
- _o__atol_l
- _o__wtol
- _o__wtol_l
- _o_atol
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
- _atol_l
- _ttol_l
- _tstol_l
- _tstol
- _wtol
- _ttol
- _wtol_l
helpviewer_keywords:
- tstol function
- atol function
- ttol function
- _atol_l function
- _tstol_l function
- string conversion, to integers
- _tstol function
- _ttol function
- _ttol_l function
- atol_l function
- wtol_l function
- _wtol_l function
- wtol function
- _wtol function
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
ms.openlocfilehash: 30f8375814259cac8c3d7216c636b69acbc7e90a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348751"
---
# <a name="atol-_atol_l-_wtol-_wtol_l"></a>atol, _atol_l, _wtol, _wtol_l

Bir dizeyi uzun bir tamsayıya dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
long atol(
   const char *str
);
long _atol_l(
   const char *str,
   _locale_t locale
);
long _wtol(
   const wchar_t *str
);
long _wtol_l(
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

Her işlev, giriş karakterlerini bir sayı olarak yorumlayarak üretilen **uzun** değeri döndürür. Giriş bu tür bir değere dönüştürülemiyorsa, dönüş değeri **atol** için 0L'dir.

Büyük pozitif integral değerleri ile taşma durumunda, **atol** **LONG_MAX**döner; büyük negatif integral değerleri ile taşma durumunda, **LONG_MIN** döndürülür. Tüm kapsama alanı dışı durumlarda, **errno** **ERANGE**olarak ayarlanır. Geçirilen parametre **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve 0 döndürün.

## <a name="remarks"></a>Açıklamalar

Bu işlevler bir karakter dizesini uzun bir tamsayı değerine **(atol)** dönüştürür.

Giriş dizesi, belirtilen türün sayısal değeri olarak yorumlanabilecek bir karakter dizisidir. İşlev, bir sayının parçası olarak tanıyamadığı ilk karakterdeki giriş dizesini okumayı durdurur. Bu karakter, dizeyi sonlayan null karakter ('\0' veya L'\0') olabilir.

**Atol** için *str* argümanaşağıdaki formu vardır:

> [*beyazuzay*] [*işaret*] [*basamak ]]*

Bir *boşluk,* yoksayılan boşluk veya sekme karakterlerinden oluşur; *işareti* artı (+) veya eksi (-); ve *basamaklar* bir veya daha fazla basamakvardır.

**_wtol** geniş bir karakter dize alır dışında **atol** aynıdır.

Bu işlevlerin **_l** soneki olan sürümleri, geçerli yerel alan yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstol**|**Atol**|**Atol**|**_wtol**|
|**_ttol**|**Atol**|**Atol**|**_wtol**|

## <a name="requirements"></a>Gereksinimler

|Rutin|Gerekli başlık|
|--------------|---------------------|
|**Atol**|\<stdlib.h>|
|**_atol_l**, **_wtol**, **_wtol_l**|\<stdlib.h> \<ve wchar.h>|

## <a name="example"></a>Örnek

Bu program, dizeleri olarak depolanan sayıların **atol** işlevini kullanarak sayısal değerlere nasıl dönüştürülebileceğini gösterir.

```C
// crt_atol.c
// This program shows how numbers stored as
// strings can be converted to numeric values
// using the atol functions.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    long    value = 0;

    // An example of the atol function
    // with leading and trailing white spaces.
    str = "  -2309 ";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );

    // Another example of the atol function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );

    // Another example of the atol function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atol( "  -2309 " ) = -2309
Function: atol( "314127.64" ) = 314127
Function: atol( "3336402735171707160320" ) = 2147483647
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
