---
description: 'Daha fazla bilgi edinin: strsöyle, _strtold_l, wcstold, _wcstold_l'
title: strtold, _strtold_l, wcstold, _wcstold_l
ms.date: 4/2/2020
api_name:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
- _o__strtold_l
- _o__wcstold_l
- _o_strtold
- _o_wcstold
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
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
ms.openlocfilehash: c20550e93d45838c39e799a2ebf2f2cd368d059c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288665"
---
# <a name="strtold-_strtold_l-wcstold-_wcstold_l"></a>strtold, _strtold_l, wcstold, _wcstold_l

Dizeleri uzun çift duyarlıklı kayan noktalı değere dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
long double strtold(
   const char *strSource,
   char **endptr
);
long double _strtold_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
long double wcstold(
   const wchar_t *strSource,
   wchar_t **endptr
);
long double wcstold_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Dönüştürülecek null ile sonlandırılmış dize.

*endptr*<br/>
Taramayı durduran karakter işaretçisi.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtend** , kayan noktalı sayının değerini olarak döndürür **`long double`** ; Bu durumda, işlevin bir taşmaya neden olacağı durumlar dışında, işlev +/-**HUGE_VALL** döndürür. **HUGE_VALL** işareti, gösterilemeyen değerin işaretiyle eşleşir. Hiçbir dönüştürme gerçekleştirilemiyorsa veya bir yetersiz kalması durumunda **strbildirilir** 0 döndürür.

**wcstold** , **strıse**'ye bir değer döndürür. Her iki işlev için de **errno** , taşma veya yetersiz kalması durumunda ve [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrıldığında **ERANGE** olarak ayarlanır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Her işlev, *strSource* giriş dizesini öğesine dönüştürür **`long double`** . **Strsöylefunction** , bir sayının parçası olarak tanıyamadığı Ilk karakterde *strSource* dize okumasını durduruyor. Bu, Sonlandırıcı null karakteri olabilir. **Stristeninin** geniş karakterli sürümü **wcstold**; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strsöylemi**|**strsöylemi**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

Geçerli yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*'ta taban karakterinin tanınmasını belirler. Daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). **_L** soneki olmayan işlevler geçerli yerel ayarı kullanır; **_strtold_l** ve **_wcstold_l** , **_strtold** ve **_wcstold** aynıdır, bunun yerine geçirilen yerel ayarı kullanmaları dışında. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null** değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr* tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr* tarafından işaret edilen konumda depolanır.

**strbildirilir** , *strSource* 'un aşağıdaki biçimdeki bir dizeyi işaret edilmesini bekler:

[*boşluk*] [*imzala*] [*basamaklar*] [. *basamaklar*] [{**d** &#124; **d** &#124; **e** &#124; **e**} [*oturum açma*]*basamakları*]

Boşluk ve sekme karakterlerinden oluşan bir *boşluk* , yok sayılır; *işareti* artı ( **+** ) ya da eksi ( **-** ); *rakamlar* bir veya daha fazla ondalık basamak. Taban karakterinden önce bir basamak görünmezse, en az bir sayı, taban karakterinden sonra görünmelidir. Ondalık basamakların ardından, giriş harfinden (**d**, **d**, **e** veya **e**) ve isteğe bağlı olarak işaretli bir tamsayıdan oluşan bir üs gelebilir. Ne bir üs bölümü ne de bir taban karakteri görünmüyorsa, dizedeki son basamağı izlemek için bir taban karakteri varsayılır. Bu forma uymayan ilk karakter taramayı durduruyor.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strsöyle,** **_strtold_l**|\<stdlib.h>|
|**wcstold**, **_wcstold_l**|\<stdlib.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtold.c
// Build with: cl /W4 /Tc crt_strtold.c
// This program uses strtold to convert a
// string to a long double-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   long double x;

   string = "3.1415926535898This stopped it";
   x = strtold(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtold = %.13Lf\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.1415926535898This stopped it
   strtold = 3.1415926535898
   Stopped scan at: This stopped it
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Sayısal değer Işlevlerine dize](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
