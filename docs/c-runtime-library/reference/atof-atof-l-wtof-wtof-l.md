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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 5200b93a5745dfb8e9b31cd5663452b84cb3058a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909110"
---
# <a name="atof-_atof_l-_wtof-_wtof_l"></a>atof, _atof_l, _wtof, _wtof_l

Dizeyi Double 'a Dönüştür.

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

*üstbilgisine*<br/>
Dönüştürülecek dize.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, giriş karakterlerinin sayı olarak yorumlanarak oluşturulan **Double** değeri döndürür. Giriş Bu türden bir değere dönüştürülemiyorsa, dönüş değeri 0,0 ' dir.

Tüm Aralık dışı durumlarda **errno** , **ERANGE**olarak ayarlanır. Geçirilen parametre **null**Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** ' ı **EINVAL** olarak ayarlar ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, bir karakter dizesini çift duyarlıklı, kayan noktalı bir değere dönüştürür.

Giriş dizesi, belirtilen türden sayısal bir değer olarak yorumlanabilen bir karakter dizisidir. İşlev, bir sayının parçası olarak tanıyamadığı ilk karakterde giriş dizesini okumayı durduruyor. Bu karakter, dizeyi sonlandıran null karakteri (' \ 0 ' veya L ' \ 0 ') olabilir.

**Atof** ve **_wtof** *Str* bağımsız değişkeni aşağıdaki biçimdedir:

[*boşluk*] [*imzala*] [*basamaklar*] [__.__ *basamaklar*] [{**e** &#124; **e** } [*oturum açma*]*basamakları*]

*Boşluk* , yoksayılan boşluk veya sekme karakterlerinden oluşur; *imza* artı (+) veya eksi (-); ve *rakamlar* bir veya daha fazla ondalık basamaktır. Ondalık noktadan önce bir basamak görünmezse, ondalık ayırıcıdan sonra en az bir rakam görünmelidir. Ondalık basamakların ardından, bir giriş harfinden (**e**veya **e**) ve isteğe bağlı olarak imzalanmış ondalık tamsayıdan oluşan bir üs gelebilir.

Bu işlevlerin UCRT sürümleri, FORTRAN-Style (**d** veya **d**) üs harflerinin dönüştürülmesini desteklemez. Standart olmayan bu uzantı, CRT 'nin önceki sürümleri tarafından desteklenmiş ve kodunuz için bir ön değişiklik olabilir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli yerel ayar yerine geçirilen *yerel ayar* parametresini kullanmaları dışında aynıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstof**|**atof**|**atof**|**_wtof**|
|**_ttof**|**atof**|**atof**|**_wtof**|

## <a name="requirements"></a>Gereksinimler

|Yordam (ler)|Gerekli başlık|
|------------------|---------------------|
|**atof**, **_atof_l**|C: \<Math. h> veya \<stdlib. h> C++: \<cstdlib>, \<Stdlib. h>, \<cmath> veya \<Math. h>|
|**_wtof**, **_wtof_l**|C: \<Stdlib. h> veya \<wchar. h> C++: \<cstdlib>, \<Stdlib. h> veya \<wchar. h>|

## <a name="example"></a>Örnek

Bu program, dizeler olarak depolanan sayıların, **atof** ve **_atof_l** işlevleri kullanılarak sayısal değerlere nasıl dönüştürülebileceğini gösterir.

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
