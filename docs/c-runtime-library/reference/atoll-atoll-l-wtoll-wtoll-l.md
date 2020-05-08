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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 89a4d94a98e58f4ef5489554e02866a8471ade20
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913517"
---
# <a name="atoll-_atoll_l-_wtoll-_wtoll_l"></a>atoll, _atoll_l, _wtoll, _wtoll_l

Bir dizeyi **uzun** **uzun** tamsayıya dönüştürür.

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

*üstbilgisine*<br/>
Dönüştürülecek dize.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, giriş karakterlerinin sayı olarak yorumlanarak üretilen **uzun** **uzun** değeri döndürür. Giriş Bu türden bir değere dönüştürülemiyorsa, **aücretli** için dönüş değeri 0 ' dır.

Büyük pozitif tamsayı değerleriyle taşma için, **aücretli** **LLONG_MAX**döndürür ve büyük negatif tamsayı değerleriyle taşma için **LLONG_MIN**döndürür.

Tüm Aralık dışı durumlarda **errno** , **ERANGE**olarak ayarlanır. Geçirilen parametre **null**Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** ' ı **EINVAL** olarak ayarlar ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, bir karakter dizesini **uzun** **uzun** bir tamsayı değerine dönüştürür.

Giriş dizesi, belirtilen türden sayısal bir değer olarak yorumlanabilen bir karakter dizisidir. İşlev, bir sayının parçası olarak tanıyamadığı ilk karakterde giriş dizesini okumayı durduruyor. Bu karakter, dizeyi sonlandıran null karakteri (' \ 0 ' veya L ' \ 0 ') olabilir.

**Aücretli** *dize* bağımsız değişkeni aşağıdaki biçimdedir:

> [*boşluk*] [*imzala*] [*basamaklar*]

*Boşluk* , yoksayılan boşluk veya sekme karakterlerinden oluşur; *imza* artı (+) veya eksi (-); ve *rakamlar* bir veya daha fazla basamaktan oluşur.

**_wtoll** , bir parametre olarak geniş bir karakter dizesi almak dışında, **aücretli** ile aynıdır.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanmaları dışında, sahip olmayan sürümlerle aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoll**|**Atoll**|**Atoll**|**_wtoll**|
|**_tstoll_l**|**_atoll_l**|**_atoll_l**|**_wtoll_l**|
|**_ttoll**|**_atoll**|**_atoll**|**_wtoll**|

## <a name="requirements"></a>Gereksinimler

|Çalıştırmasını|Gerekli başlık|
|--------------|---------------------|
|**aücretli**, **_atoll_l**|\<Stdlib. h>|
|**_wtoll**, **_wtoll_l**|\<Stdlib. h> veya \<wchar. h>|

## <a name="example"></a>Örnek

Bu program, dize olarak depolanan sayıları sayısal değerlere dönüştürmek için **alü** işlevlerinin nasıl kullanılacağını gösterir.

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
