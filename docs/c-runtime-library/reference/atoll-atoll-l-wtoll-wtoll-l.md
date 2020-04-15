---
title: atoll, _atoll_l, _wtoll, _wtoll_l
ms.date: 4/2/2020
api_name:
- _wtoll
- _atoll_l
- _wtoll_l
- atoll
- _o__atoll_l
- _o__wtoll
- _o__wtoll_l
- _o_atoll
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
- _tstoll_l
- _wtoll
- _atoll_l
- _ttoll
- _tstoll
- _wtoll_l
- atoll
helpviewer_keywords:
- atoll function
- _wtoll_l function
- _wtoll function
- _atoll_l function
ms.assetid: 5e85fcac-b351-4882-bff2-6e7c469b7fa8
ms.openlocfilehash: 34b7d0fdedb55241452f9a7f9937b64c58f7772c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348707"
---
# <a name="atoll-_atoll_l-_wtoll-_wtoll_l"></a>atoll, _atoll_l, _wtoll, _wtoll_l

Bir dizeyi **uzun** **bir** tamsayıya dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
long long atoll(
   const char *str
);
long long _wtoll(
   const wchar_t *str
);
long long _atoll_l(
   const char *str,
   _locale_t locale
);
long long _wtoll_l(
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

Her işlev, giriş karakterlerini bir sayı olarak yorumlayarak üretilen **uzun** **uzun** değeri döndürür. Giriş bu tür bir değere dönüştürülemiyorsa **mercan adasının** dönüş değeri 0'dır.

Büyük pozitif integral değerleri ile taşma için, **mercan** **LLONG_MAX**döndürür ve büyük negatif integral değerleri ile taşma **için, LLONG_MIN**döndürür.

Tüm kapsama alanı dışı durumlarda, **errno** **ERANGE**olarak ayarlanır. Geçirilen parametre **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve 0 döndürün.

## <a name="remarks"></a>Açıklamalar

Bu işlevler bir karakter dizesini **uzun** **bir** tamsayı değerine dönüştürür.

Giriş dizesi, belirtilen türün sayısal değeri olarak yorumlanabilecek bir karakter dizisidir. İşlev, bir sayının parçası olarak tanıyamadığı ilk karakterdeki giriş dizesini okumayı durdurur. Bu karakter, dizeyi sonlandıran null karakter ('\0' veya L'\0') olabilir.

**Mercan adasıiçin** *str* bağımsız değişkeni aşağıdaki formu vardır:

> [*beyazuzay*] [*işaret*] [*rakamlar*]

Bir *boşluk,* yoksayılan boşluk veya sekme karakterlerinden oluşur; *işareti* artı (+) veya eksi (-); ve *basamaklar* bir veya daha fazla basamakvardır.

**_wtoll** bir parametre olarak geniş bir karakter dize alır dışında **mercan adası** ile aynıdır.

**_l** sonek olan bu işlevlerin sürümleri, geçerli yerel yerine geçirilen yerel parametreyi kullanmaları dışında, bu tür olmayan sürümlerle aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoll**|**Atoll**|**Atoll**|**_wtoll**|
|**_tstoll_l**|**_atoll_l**|**_atoll_l**|**_wtoll_l**|
|**_ttoll**|**_atoll**|**_atoll**|**_wtoll**|

## <a name="requirements"></a>Gereksinimler

|Rutin|Gerekli başlık|
|--------------|---------------------|
|**mercan adası**, **_atoll_l**|\<stdlib.h>|
|**_wtoll**, **_wtoll_l**|\<stdlib.h> \<veya wchar.h>|

## <a name="example"></a>Örnek

Bu program, dize olarak depolanan sayıları sayısal değerlere dönüştürmek için **mercan adası** işlevlerinin nasıl kullanılacağını gösterir.

```C
// crt_atoll.c
// Build with: cl /W4 /Tc crt_atoll.c
// This program shows how to use the atoll
// functions to convert numbers stored as
// strings to numeric values.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main(void)
{
    char *str = NULL;
    long long value = 0;

    // An example of the atoll function
    // with leading and trailing white spaces.
    str = "  -27182818284 ";
    value = atoll(str);
    printf("Function: atoll(\"%s\") = %lld\n", str, value);

    // Another example of the atoll function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = atoll(str);
    printf("Function: atoll(\"%s\") = %lld\n", str, value);

    // Another example of the atoll function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atoll(str);
    printf("Function: atoll(\"%s\") = %lld\n", str, value);
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atoll("  -27182818284 ") = -27182818284
Function: atoll("314127.64") = 314127
Function: atoll("3336402735171707160320") = 9223372036854775807
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
