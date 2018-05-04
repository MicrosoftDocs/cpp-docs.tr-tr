---
title: atof, _atof_l, _wtof, _wtof_l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wtof_l
- atof
- _atof_l
- _wtof
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
- _tstof
- _ttof
- atof
- stdlib/atof
- math/atof
- _atof_l
- stdlib/_atof_l
- math/_atof_l
- _wtof
- corecrt_wstdlib/_wtof
- _wtof_l
- corecrt_wstdlib/_wtof_l
dev_langs:
- C++
helpviewer_keywords:
- tstof function
- atof_l function
- _atof_l function
- atof function
- _tstof function
- _ttof function
- wtof function
- _wtof_l function
- ttof function
- wtof_l function
- _wtof function
- string conversion, to floating point values
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78fe14783200e1e145c39b9b274d9e7e3ddb6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atof-atofl-wtof-wtofl"></a>atof, _atof_l, _wtof, _wtof_l

Bir dize çift dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
double atof(
   const char *str
);
double _atof_l(
   const char *str,
   _locale_t locale
);
double _wtof(
   const wchar_t *str
);
double _wtof_l(
   const wchar_t *str,
   _locale_t locale
);
```

## <a name="parameters"></a>Parametreler

*str*<br/>
Dönüştürülecek dizesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür **çift** değeri bir sayı olarak giriş karakter yorumlama tarafından üretilen. Dönüş değeri 0,0 ise giriş türü değerine dönüştürülemiyor.

Tüm aralık dışı durumlarda **errno** ayarlanır **ERANGE**. Geçirilen parametre ise **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin bir karakter dizesi çift duyarlıklı, kayan nokta değerine dönüştürür.

Giriş dizesi belirtilen türde bir sayısal değer yorumlanan karakterden oluşan bir dizidir. İşlevi, giriş dizesi bir sayı bir parçası olarak tanıyamıyor ilk karakterinde okuma durdurur. Bu karakteri ('\0' veya '\0' L) null karakter olabilir dize sonlandırılıyor.

*Str* bağımsız değişkeni **atof** ve **_wtof** aşağıdaki biçime sahiptir:

[*boşluk*] [*oturum*] [*basamak*] [__.__ *basamak*] [{**e** &#124; **E** } [*oturum*]*basamak*]

A *boşluk* , göz ardı edilir; boşluk veya sekmesinde karakterlerden oluşur *oturum* da artı (+) veya eksi (-); ve *basamak* bir veya daha fazla ondalık basamakların. Hiç basamak ondalık ayırıcıdan önce görünüyorsa, en az bir ondalık ayırıcıdan sonra görünmesi gerekir. Ondalık basamak giriş harfini oluşur üs tarafından takip edilebilir (**e**, veya **E**) ve isteğe bağlı olarak imzalanmış bir ondalık tamsayı.

Bu işlevlerin UCRT sürümleri Fortran stili dönüştürülmesini desteklemez (**d** veya **D**) üs harf. Bu standart uzantısı CRT önceki sürümleri tarafından desteklenen ve kodunuz için önemli bir değişiklik olabilir.

Bu işlevleri sürümlerini **_l** kullandıkları dışında sonek aynı *yerel* parametresi geçirilen yerine geçerli yerel ayar.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstof**|**atof**|**atof**|**_wtof**|
|**_ttof**|**atof**|**atof**|**_wtof**|

## <a name="requirements"></a>Gereksinimler

|Routine(s)|Gerekli başlık|
|------------------|---------------------|
|**atof**, **_atof_l**|C: \<math.h > veya \<stdlib.h > C++: \<cstdlib >, \<stdlib.h >, \<cmath > veya \<math.h >|
|**_wtof**, **_wtof_l**|C: \<stdlib.h > veya \<wchar.h > C++: \<cstdlib >, \<stdlib.h > veya \<wchar.h >|

## <a name="example"></a>Örnek

Bu program, dize olarak depolanan sayılar kullanarak sayısal değerleri nasıl dönüştürülebilir gösterir **atof** ve **_atof_l** işlevleri.

```C
// crt_atof.c
//
// This program shows how numbers stored as
// strings can be converted to numeric
// values using the atof and _atof_l functions.

#include <stdlib.h>
#include <stdio.h>
#include <locale.h>

int main(void)
{
    char    *str = NULL;
    double value = 0;
    _locale_t fr = _create_locale(LC_NUMERIC, "fr-FR");

    // An example of the atof function
    // using leading and training spaces.
    str = "  3336402735171707160320 ";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);

    // Another example of the atof function
    // using the 'E' exponential formatting keyword.
    str = "3.1412764583E210";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);

    // An example of the atof and _atof_l functions
    // using the 'e' exponential formatting keyword
    // and showing different decimal point interpretations.
    str = "  -2,309e-25";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);
    value = _atof_l(str, fr);
    printf("Function: _atof_l(\"%s\", fr)) = %e\n", str, value);
}
```

```Output
Function: atof("  3336402735171707160320 ") = 3.336403e+21
Function: atof("3.1412764583E210") = 3.141276e+210
Function: atof("  -2,309e-25") = -2.000000e+00
Function: _atof_l("  -2,309e-25", fr)) = -2.309000e-25
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
