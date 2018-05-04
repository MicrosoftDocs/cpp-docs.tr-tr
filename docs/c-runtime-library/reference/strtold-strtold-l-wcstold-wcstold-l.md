---
title: strtold, _strtold_l, wcstold, _wcstold_l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
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
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
dev_langs:
- C++
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a5018f9245da77fbadb301a8fa45d1f0f7b4117
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold, _strtold_l, wcstold, _wcstold_l

Dizeleri uzun çift duyarlıklı kayan noktalı değerine dönüştürür.

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
Tarama durdurur karakter işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtold** kayan noktalı sayı değerini döndürür bir **uzun** **çift**, temsili taşma zaman neden olacağından dışında — bu durumda,+/-işlevidöndürür**HUGE_VALL**. İşaretini **HUGE_VALL** gösterilemez değerini oturum eşleşir. **strtold** dönüştürme gerçekleştirilebilir veya bir underflow oluşur 0 döndürür.

**wcstold** değerleri analogously çok döndürür **strtold**. Her iki işlevler için **errno** ayarlanır **ERANGE** taşması veya yetersiz olursa ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Giriş dizesi her işlevi dönüştürür *strSource* için bir **uzun** **çift**. **Strtold** işlevi durdurur dize okuma *strSource* ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir. Joker karakter sürümü **strtold** olan **wcstold**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

**Lc_numerıc** geçerli yerel kategori ayarı belirler taban karakterinin tanıma *strSource*. Daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). Olmadan çalışır **_l** sonekini kullan geçerli yerel; **_strtold_l** ve **_wcstold_l** özdeş **_strtold** ve **_wcstold** bunun yerine yerel kullandıkları dışında bu geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* işaret ediyor konumunda depolanan *endptr*.

**strtold** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

[*boşluk*] [*oturum*] [*basamak*] [. *basamak*] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*oturum* ]*basamak*]

A *boşluk* , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir *oturum* da artı (**+**) veya eksi (**-**); ve *basamak* bir veya daha fazla ondalık basamakların. Hiç basamak önce taban karakter görünüyorsa, en az bir taban karakter sonra görünmesi gerekir. Ondalık basamak giriş harfini oluşur üs tarafından izlenebilir (**d**, **D**, **e**, veya **E**) ve bir isteğe bağlı olarak İmzalı tam sayı. Ne üs bir parçası, ne de bir taban karakter görünürse, bir taban karakter dizesindeki son basamaklı izleyin varsayılır. Bu form sığmayan ilk karakter tarama durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtold**, **_strtold_l**|\<stdlib.h >|
|**wcstold**, **_wcstold_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
