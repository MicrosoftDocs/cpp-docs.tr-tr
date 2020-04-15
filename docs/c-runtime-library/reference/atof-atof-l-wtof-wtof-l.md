---
title: atof, _atof_l, _wtof, _wtof_l
ms.date: 4/2/2020
api_name:
- _wtof_l
- atof
- _atof_l
- _wtof
- _o__atof_l
- _o__wtof
- _o__wtof_l
- _o_atof
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
ms.openlocfilehash: 492719a0cc0f8ac079b257ec8d7aa1014c5b2a86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348919"
---
# <a name="atof-_atof_l-_wtof-_wtof_l"></a>atof, _atof_l, _wtof, _wtof_l

Bir dizeyi çifte dönüştürün.

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

*Str*<br/>
Dize dönüştürülecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, giriş karakterlerini bir sayı olarak yorumlayarak üretilen **çift** değeri döndürür. Giriş bu tür bir değere dönüştürülemiyorsa, iade değeri 0,0'dır.

Tüm kapsama alanı dışı durumlarda, **errno** **ERANGE**olarak ayarlanır. Geçirilen parametre **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve 0 döndürün.

## <a name="remarks"></a>Açıklamalar

Bu işlevler bir karakter dizesini çift duyarlıklı, kayan nokta değerine dönüştürür.

Giriş dizesi, belirtilen türün sayısal değeri olarak yorumlanabilecek bir karakter dizisidir. İşlev, bir sayının parçası olarak tanıyamadığı ilk karakterdeki giriş dizesini okumayı durdurur. Bu karakter, dizeyi sonlayan null karakter ('\0' veya L'\0') olabilir.

**Atof** ve **_wtof** str *argümanı* aşağıdaki formu vardır:

[*beyazuzay*] [*işaret*] [*rakamlar*] [__.__ *rakamlar*] [ {**e** &#124; **E** }[*işaret*]*rakamları*]

Bir *boşluk,* yoksayılan boşluk veya sekme karakterlerinden oluşur; *işareti* artı (+) veya eksi (-); ve *basamaklar* bir veya daha fazla ondalık basamakvardır. Ondalık noktadan önce basamak görünmüyorsa, ondalık noktadan sonra en az bir basamak görünmesi gerekir. Ondalık basamakları, giriş harfi **(e**, veya **E)** ve isteğe bağlı olarak imzalanmış ondalık bir dosdoğrudan oluşan bir üs izlenebilir.

Bu işlevlerin UCRT sürümleri Fortran stili **(d** veya **D)** üs harflerinin dönüştürülmesini desteklemez. Bu standart dışı uzantı CRT'nin önceki sürümleri tarafından desteklenmiştir ve kodunuz için bir son değişiklik olabilir.

Bu işlevlerin **_l** soneki olan sürümleri, geçerli yerel alan yerine geçirilen *yerel* parametreyi kullanmaları dışında aynıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstof**|**atof**|**atof**|**_wtof**|
|**_ttof**|**atof**|**atof**|**_wtof**|

## <a name="requirements"></a>Gereksinimler

|Rutin(ler)|Gerekli başlık|
|------------------|---------------------|
|**atof**, **_atof_l**|C: \<math.h \<> veya stdlib.h \<> C++: \<cstdlib>, stdlib.h>, \<cmath> veya \<math.h>|
|**_wtof**, **_wtof_l**|C: \<stdlib.h \<> veya wchar.h \<> C++: \<cstdlib>, stdlib.h> veya \<wchar.h>|

## <a name="example"></a>Örnek

Bu program, dize olarak depolanan **sayıların atof** ve **_atof_l** işlevlerini kullanarak sayısal değerlere nasıl dönüştürülebileceğini gösterir.

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
