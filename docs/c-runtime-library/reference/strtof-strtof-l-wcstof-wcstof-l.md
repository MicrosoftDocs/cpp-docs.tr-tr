---
title: strtof, _strtof_l, wcstof, _wcstof_l
ms.date: 04/05/2018
api_name:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
ms.openlocfilehash: b2b2e7d230074b5a464260d36b41c28b9951d65b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957758"
---
# <a name="strtof-_strtof_l-wcstof-_wcstof_l"></a>strtof, _strtof_l, wcstof, _wcstof_l

Dizeleri tek duyarlıklı kayan noktalı değere dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
float strtof(
   const char *strSource,
   char **endptr
);
float _strtof_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
float wcstof(
   const wchar_t *strSource,
   wchar_t **endptr
);
float wcstof_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

## <a name="parameters"></a>Parametreler

*strSource*<br/>
Dönüştürülecek null ile sonlandırılmış dize.

*endptr*<br/>
Taramayı durduran karakter işaretçisi.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtof** , kayan noktalı sayının değerini döndürür; bu durumda, işlevin bir taşmaya neden olacağı durumlar hariç, işlev +/-**HUGE_VALF**döndürür. **HUGE_VALF** işareti, gösterilemeyen değerin işaretiyle eşleşir. **strtof** , hiçbir dönüştürme gerçekleştirilemiyorsa veya bir yetersiz bir durum oluşursa 0 değerini döndürür.

**wcstof** , **strtof**'e anormal olarak değer döndürür. Her iki işlev için de **errno** , taşma veya yetersiz kalması durumunda ve [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrıldığında **ERANGE** olarak ayarlanır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Her işlev, *strSource* giriş dizesini bir **float**öğesine dönüştürür. **Strtof** Işlevi, *strSource* 'u tek duyarlıklı bir değere dönüştürür. **strtof** , bir sayının parçası olarak tanıyamadığı Ilk karakterde *strSource* dize okumasını durduruyor. Bu, Sonlandırıcı null karakteri olabilir. **wcstof** , **strtof**öğesinin geniş karakterli bir sürümüdür. *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

Geçerli yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*; içindeki taban karakterinin tanınmasını belirler. daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). **_L** sonekine sahip olmayan işlevler geçerli yerel ayarı kullanır; sonekine sahip olanlar, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null**değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr*tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtof** , *strSource* 'un aşağıdaki biçimdeki bir dizeyi işaret etmek bekler:

[*boşluk*] [*imzala*] [*basamaklar*] [ __.__ *basamaklar*] [{**e** &#124; **e**} [*oturum*] *basamakları*]

Boşluk ve sekme karakterlerinden oluşan bir *boşluk* , yok sayılır; *işareti* artı ( **+** ) ya da eksi ( **-** ); *rakamlar* bir veya daha fazla ondalık basamak. Taban karakterinden önce bir basamak görünmezse, en az bir sayı, taban karakterinden sonra görünmelidir. Ondalık basamakların ardından, bir giriş harfinden (**e** veya **e**) ve isteğe bağlı olarak işaretli bir tamsayıdan oluşan bir üs gelebilir. Ne bir üs bölümü ne de bir taban karakteri görünmüyorsa, dizedeki son basamağı izlemek için bir taban karakteri varsayılır. Bu forma uymayan ilk karakter taramayı durduruyor.

Bu işlevlerin UCRT sürümleri, FORTRAN-Style (**d** veya **d**) üs harflerinin dönüştürülmesini desteklemez. Standart olmayan bu uzantı, CRT 'nin önceki sürümleri tarafından desteklenmiş ve kodunuz için bir ön değişiklik olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtof**, **_strtof_l**|C: \<Stdlib. h > C++: &lt;cstdlib > veya \<Stdlib. h >|
|**wcstof**, **_wcstof_l**|C: \<Stdlib. h > veya \<wchar. h > C++: &lt;cstdlib >, \<Stdlib. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtof.c
// This program uses strtof to convert a
// string to a single-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   float x;

   string = "3.14159This stopped it";
   x = strtof(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtof = %f\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.14159This stopped it
   strtof = 3.141590
   Stopped scan at: This stopped it
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Sayısal Değer İşlevleri Dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
