---
title: strtold, _strtold_l, wcstold, _wcstold_l
ms.date: 04/05/2018
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
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
ms.openlocfilehash: fce60775ee1ef6def214e559779004d4de95453c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484584"
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold, _strtold_l, wcstold, _wcstold_l

Dizeleri bir uzun çift duyarlıklı kayan noktalı değere dönüştürür.

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtold** kayan nokta sayı değerini döndürür bir **uzun** **çift**, gösterimin bir taşma neden olduğu zaman dışında — bu durumda, işlev +/-döndürür**HUGE_VALL**. İşaretini **HUGE_VALL** temsil edilemeyen değerin işareti ile eşleşir. **strtold** dönüştürme gerçekleştirilemeyiorsa veya bir Yetersizlik durumu oluşursa 0 döndürür.

**wcstold** çok öğesine değerleri döndürür **strtold**. Her iki işlev için **errno** ayarlanır **ERANGE** taşma veya yetersiz gelme oluşması ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Giriş dizesindeki her işlevi dönüştürür *strSource* için bir **uzun** **çift**. **Strtold** işlevi dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir. Geniş karakter sürümünü **strtold** olduğu **wcstold**; *strSource* geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

**Lc_numerıc** tanıma öğesindeki taban karakterin tanınmasını geçerli yerel ayar kategori ayarı belirler *strSource*. Daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md). İşlevlerin **_l** soneki geçerli yerel ayarı kullanır; **_strtold_l** ve **_wcstold_l** özdeş **_strtold** ve **_wcstold** bunun yerine yerel ayarı kullanmaları dışında bu geçirildi. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

**strtold** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

[*boşluk*] [*oturum*] [*basamak*] [. *basamak*] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*oturum* ]*basamak*]

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir *oturum* ya da artı (**+**) veya eksidir (**-**); ve *basamak* bir veya daha fazla ondalık basamaktır. Herhangi bir basamak taban karakterden önce görünüyorsa, en az bir taban karakterden sonra yer almalıdır. Ondalık basamak bir tanıtıcı harften oluşan bir üs gelebilir (**d**, **D**, **e**, veya **E**) ve isteğe bağlı olarak işaretli tamsayı. Üstel bir parça ya da bir taban karakter görünürse, taban karakterin dizedeki son basamağı izlediği varsayılır. Bu forma uymayan ilk karakter taramayı durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtold**, **_strtold_l**|\<stdlib.h >|
|**wcstold**, **_wcstold_l**|\<stdlib.h > veya \<wchar.h >|

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
