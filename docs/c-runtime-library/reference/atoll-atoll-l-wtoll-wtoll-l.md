---
title: atoll, _atoll_l, _wtoll, _wtoll_l
ms.date: 11/04/2016
apiname:
- _wtoll
- _atoll_l
- _wtoll_l
- atoll
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
ms.openlocfilehash: 7933b3e25185b5abdbd10c1b3fd616742bb28f92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341190"
---
# <a name="atoll-atolll-wtoll-wtolll"></a>atoll, _atoll_l, _wtoll, _wtoll_l

Bir dizeye dönüştürür bir **uzun** **uzun** tamsayı.

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

*str*<br/>
Dönüştürülecek dize.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her işlev **uzun** **uzun** giriş karakterlerinin sayı olarak yorumlanmasıyla üretilen değer. Dönüş değeri **atoll** 0 ise giriş türü bir değere dönüştürülemez.

Büyük pozitif tamsayı değerleri içeren taşma **atoll** döndürür **LLONG_MAX**, ve büyük negatif tam sayı değerleri içeren taşma için döndürür **LLONG_MIN**.

Tüm aralık dışı durumlarda **errno** ayarlanır **ERANGE**. Geçirilen parametre ise **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler bir karakter dizesine dönüştürün bir **uzun** **uzun** tamsayı değeri.

Giriş dizesi belirtilen türde bir sayısal değer olarak yorumlanabilecek bir karakter dizisi ' dir. İşlev bir sayının parçası olarak tanıyamadığı ilk karakterde giriş dizesini okumayı durdurur. Bu karakteri, null dizeyi sonlandıran karakteri ('\0' veya '\0' L) olabilir.

*Str* bağımsız değişkeni **atoll** aşağıdaki biçime sahiptir:

> [*boşluk*] [*oturum*] [*basamak*]

A *boşluk* yoksayılan boşluk veya sekme karakterlerinden oluşur *oturum* ya da artı (+) veya eksidir (–); ve *basamak* bir veya daha fazla rakamdır.

**_wtoll** aynıdır **atoll** dışında parametre olarak geniş karakter dizesi alır.

Sahip bu işlevlerin sürümleri **_l** sonekine buna sahip olmayan sürümleri geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanırlar dışında. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoll**|**atoll**|**atoll**|**_wtoll**|
|**_tstoll_l**|**_atoll_l**|**_atoll_l**|**_wtoll_l**|
|**_ttoll**|**_atoll**|**_atoll**|**_wtoll**|

## <a name="requirements"></a>Gereksinimler

|Rutinleri|Gerekli başlık|
|--------------|---------------------|
|**atoll**, **_atoll_l**|\<stdlib.h >|
|**_wtoll**, **_wtoll_l**|\<stdlib.h > veya \<wchar.h >|

## <a name="example"></a>Örnek

Bu program, nasıl kullanılacağını gösterir. **atoll** sayısal değerleri için dizeler olarak saklanan işlevleri.

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
[locale](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
