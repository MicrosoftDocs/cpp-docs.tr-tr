---
title: strtof, _strtof_l, wcstof, _wcstof_l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e084140b3b220df04859f4ac1bdfe3c1e34ddfc
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strtof-strtofl-wcstof-wcstofl"></a>strtof, _strtof_l, wcstof, _wcstof_l

Dizeleri tek duyarlıklı kayan noktalı değerine dönüştürür.

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
Tarama durdurur karakter işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtof** gösterimi, servis talebi işlevi döndürür +/-taşma, ne zaman neden olacağından dışında kayan noktalı sayı değerini döndürür**HUGE_VALF**. İşaretini **HUGE_VALF** gösterilemez değerini oturum eşleşir. **strtof** dönüştürme gerçekleştirilebilir veya bir underflow oluşur 0 döndürür.

**wcstof** değerleri analogously çok döndürür **strtof**. Her iki işlevler için **errno** ayarlanır **ERANGE** taşması veya yetersiz olursa ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Giriş dizesi her işlevi dönüştürür *strSource* için bir **float**. **Strtof** işlev dönüştürür *strSource* tek duyarlıklı değeri. **strtof** dize okumayı durdurur *strSource* ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir. **wcstof** bir joker karakter sürümü **strtof**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

**Lc_numerıc** geçerli yerel kategori ayarı belirler tanıma taban karakterinin *strSource*; daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). Yok işlevleri **_l** soneki geçerli yerel kullanın; bunun yerine geçirilen yerel kullanmasını dışında son ekine sahip olanlarla aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* işaret ediyor konumunda depolanan *endptr*.

**strtof** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

[*boşluk*] [*oturum*] [*basamak*] [__.__ *basamak*] [{**e** &#124; **E**} [*oturum*] *basamak*]

A *boşluk* , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir *oturum* da artı (**+**) veya eksi (**-**); ve *basamak* bir veya daha fazla ondalık basamakların. Hiç basamak önce taban karakter görünüyorsa, en az bir taban karakter sonra görünmesi gerekir. Ondalık basamak giriş harfini oluşur üs tarafından izlenebilir (**e** veya **E**) ve isteğe bağlı olarak işaretli bir tam sayı. Ne üs bir parçası, ne de bir taban karakter görünürse, bir taban karakter dizesindeki son basamaklı izleyin varsayılır. Bu form sığmayan ilk karakter tarama durdurur.

Bu işlevlerin UCRT sürümleri Fortran stili dönüştürülmesini desteklemez (**d** veya **D**) üs harf. Bu standart uzantısı CRT önceki sürümleri tarafından desteklenen ve kodunuz için önemli bir değişiklik olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtof**, **_strtof_l**|C: \<stdlib.h > C++: &lt;cstdlib > veya \<stdlib.h >|
|**wcstof**, **_wcstof_l**|C: \<stdlib.h > veya \<wchar.h > C++: &lt;cstdlib >, \<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
