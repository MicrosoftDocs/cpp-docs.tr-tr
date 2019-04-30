---
title: strtof, _strtof_l, wcstof, _wcstof_l
ms.date: 04/05/2018
apiname:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
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
ms.openlocfilehash: 10a50a175685f3e8f7f1241683c7705fd9a9b142
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376438"
---
# <a name="strtof-strtofl-wcstof-wcstofl"></a>strtof, _strtof_l, wcstof, _wcstof_l

Dizeleri bir tek duyarlıklı kayan noktalı değere dönüştürür.

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtof** gösterimi içinde çalışması işlevi döndürür +/-taşmaya neden olduğu zaman dışında kayan nokta sayı değerini döndürür**HUGE_VALF**. İşaretini **HUGE_VALF** temsil edilemeyen değerin işareti ile eşleşir. **strtof** dönüştürme gerçekleştirilemeyiorsa veya bir Yetersizlik durumu oluşursa 0 döndürür.

**wcstof** çok öğesine değerleri döndürür **strtof**. Her iki işlev için **errno** ayarlanır **ERANGE** taşma veya yetersiz gelme oluşması ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Giriş dizesindeki her işlevi dönüştürür *strSource* için bir **float**. **Strtof** işlev dönüştürür *strSource* tek duyarlıklı bir değere. **strtof** dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir. **wcstof** geniş karakterli sürümüdür **strtof**; *strSource* geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

**Lc_numerıc** taban karakterin tanınmasını geçerli yerel ayar kategori ayarı belirler *strSource*; daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). Sahip olmayan işlevler **_l** soneki geçerli yerel ayarı kullanır; bunun yerine geçirilen yerel ayarı kullanmaları dışında son ekine sahip olanları aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

**strtof** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

[*whitespace*] [*sign*] [*digits*] [__.__*digits*] [{**e** &#124; **E**} [*sign*] *digits*]

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir *oturum* ya da artı (**+**) veya eksidir (**-**); ve *basamak* bir veya daha fazla ondalık basamaktır. Herhangi bir basamak taban karakterden önce görünüyorsa, en az bir taban karakterden sonra yer almalıdır. Ondalık basamak bir tanıtıcı harften oluşan bir üs gelebilir (**e** veya **E**) ve isteğe bağlı olarak imzalı bir tamsayı. Üstel bir parça ya da bir taban karakter görünürse, taban karakterin dizedeki son basamağı izlediği varsayılır. Bu forma uymayan ilk karakter taramayı durdurur.

Bu işlevlerin UCRT sürümleri Fortran stili dönüştürülmesini desteklemez (**d** veya **D**) üs harf. Bu standart olmayan uzantı CRT önceki sürümleri tarafından desteklenen ve kodunuz için bir değişiklik olması olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtof**, **_strtof_l**|C: \<stdlib.h > C++: &lt;cstdlib > veya \<stdlib.h >|
|**wcstof**, **_wcstof_l**|C: \<stdlib.h > veya \<wchar.h > C++: &lt;cstdlib >, \<stdlib.h > veya \<wchar.h >|

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
