---
title: _atoi64, _atoi64_l, _wtoi64, _wtoi64_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _atoi64_l
- _wtoi64
- _atoi64
- _wtoi64_l
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
- _atoi64
- _tstoi64
- _ttoi64
- wtoi64
- _tstoi64_l
- atoi64
- _wtoi64_l
- _wtoi64
- wtoi64_l
- _atoi64_l
- atoi64_l
dev_langs:
- C++
helpviewer_keywords:
- tstoi64 function
- wtoi64 function
- atoi64_l function
- _ttoi64 function
- string conversion, to integers
- wtoi64_l function
- atoi64 function
- _tstoi64 function
- _atoi64_l function
- _wtoi64_l function
- ttoi64 function
- _wtoi64 function
- _atoi64 function
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69afae8702d707395b09c4848d62aebf6b24aa8f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="atoi64-atoi64l-wtoi64-wtoi64l"></a>_atoi64, _atoi64_l, _wtoi64, _wtoi64_l

Bir dizeyi bir 64-bit tamsayıya dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
__int64 _atoi64(
   const char *str
);
__int64 _wtoi64(
   const wchar_t *str
);
__int64 _atoi64_l(
   const char *str,
   _locale_t locale
);
__int64 _wtoi64_l(
   const wchar_t *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Dönüştürülecek dizesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür **__int64** değeri bir sayı olarak giriş karakter yorumlama tarafından üretilen. Dönüş değeri için 0'dır **_atoi64** giriş türü değerine döndürülemezse.

Taşma büyük pozitif tamsayı değer ile söz konusu olduğunda **_atoi64** döndürür **I64_MAX** ve **I64_MIN** taşma negatif büyük tam sayı değerleri ile söz konusu olduğunda.

Tüm aralık dışı durumlarda **errno** ayarlanır **ERANGE**. Geçirilen parametre ise **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin bir karakter dizesi 64-bit tamsayı değerine dönüştürür.

Giriş dizesi belirtilen türde bir sayısal değer yorumlanan karakterden oluşan bir dizidir. İşlevi, giriş dizesi bir sayı bir parçası olarak tanıyamıyor ilk karakterinde okuma durdurur. Bu karakteri ('\0' veya '\0' L) null karakter olabilir dize sonlandırılıyor.

*Str* bağımsız değişkeni **_atoi64** aşağıdaki biçime sahiptir:

> [*boşluk*] [*oturum*] [*basamak*]

A *boşluk* , göz ardı edilir; boşluk veya sekmesinde karakterlerden oluşur *oturum* da artı (+) veya eksi (-); ve *basamak* bir veya daha fazla basamakların.

**_wtoi64** aynıdır **_atoi64** dışında geniş karakter dizesi bir parametre olarak alır.

Bu işlevleri sürümlerini **_l** soneki, geçerli yerel yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoi64**|**_atoi64**|**_atoi64**|**_wtoi64**|
|**_ttoi64**|**_atoi64**|**_atoi64**|**_wtoi64**|

## <a name="requirements"></a>Gereksinimler

|Yordamları|Gerekli başlık|
|--------------|---------------------|
|**_atoi64**, **_atoi64_l**|\<stdlib.h >|
|**_wtoi64**, **_wtoi64_l**|\<stdlib.h > veya \<wchar.h >|

## <a name="example"></a>Örnek

Bu program, dize olarak depolanan sayılar kullanarak sayısal değerleri nasıl dönüştürülebilir gösterir **_atoi64** işlevleri.

```C
// crt_atoi64.c
// This program shows how numbers stored as
// strings can be converted to numeric values
// using the _atoi64 functions.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    __int64 value = 0;

    // An example of the _atoi64 function
    // with leading and trailing white spaces.
    str = "  -2309 ";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );

    // Another example of the _atoi64 function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );

    // Another example of the _atoi64 function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: _atoi64( "  -2309 " ) = -2309
Function: _atoi64( "314127.64" ) = 314127
Function: _atoi64( "3336402735171707160320" ) = -1
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
