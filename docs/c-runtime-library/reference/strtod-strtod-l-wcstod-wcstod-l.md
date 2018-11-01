---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 10/20/2017
apiname:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
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
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
ms.openlocfilehash: c8c2b3b491e2e7265829fa88580529dc757ace8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469335"
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

Dize, çift duyarlıklı bir değere Dönüştür.

## <a name="syntax"></a>Sözdizimi

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
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

**strtod** gösterimi içinde çalışması işlevi döndürür +/-taşmaya neden olduğu zaman dışında kayan nokta sayı değerini döndürür**HUGE_VAL**. İşaretini **HUGE_VAL** temsil edilemeyen değerin işareti ile eşleşir. **strtod** dönüştürme gerçekleştirilemeyiorsa veya bir Yetersizlik durumu oluşursa 0 döndürür.

**wcstod** çok öğesine değerleri döndürür **strtod**. Her iki işlev için **errno** ayarlanır **ERANGE** taşma veya yetersiz gelme oluşması ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer döndürme kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Giriş dizesindeki her işlevi dönüştürür *strSource* için bir **çift**. **Strtod** işlev dönüştürür *strSource* çift duyarlıklı bir değere. **strtod** dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir. **wcstod** geniş karakterli sürümüdür **strtod**; *strSource* geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

**Lc_numerıc** geçerli yerel ayarının kategori ayarı belirler taban karakterin tanınmasını yerel ayarların noktası *strSource*. Daha fazla bilgi için [setlocale](setlocale-wsetlocale.md). İşlevlerin **_l** soneki geçerli yerel ayarı kullanır; **_strtod_l** aynıdır **_strtod_l** kullanmaları hariç, *yerel ayar* geçirilen. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

**strtod** bekliyor *strSource* bir dizeye aşağıdaki biçimlerden birini işaret edecek şekilde:

[*boşluk*] [*oturum*] {*basamak* [*taban* *basamak*] &#124;  *sayı tabanını* *basamak*} [{**e** &#124; **E**} [*oturum*] *basamak*] [*boşluk*] [*oturum*] {**0 x** &#124; **0 X**} {*hexdigits* [ *taban* *hexdigits*] &#124; *taban* *hexdigits*} [{**p** &#124; **P**} [*oturum*] *hexdigits*] [*boşluk*] [*oturum*] { **INF** &#124; **SONSUZ**} [*boşluk*] [*oturum*]  **NAN** [*dizisi*]

İsteğe bağlı önde gelen *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir *oturum* ya da artı (+) veya eksidir (–); *basamak* bir veya daha fazla ondalık basamaktır; *hexdigits* onaltılık basamaktır; bir veya daha fazla *taban* taban noktası karakter ya da bir nokta (.) varsayılan "C" yerel ayarında, ya da yerel ayara özgü değer, geçerli yerel ayarları farklı ise ya da zaman *yerel ayar* belirtilir; bir *dizisi* alfasayısal oluşan bir dizidir veya alt çizgi karakterleri. Herhangi bir basamak taban noktası karakterden önce görünüyorsa ondalık ve onaltılık sayı formlarında en az bir taban noktası karakterden sonra yer almalıdır. Ondalık biçiminde ondalık basamak bir tanıtıcı harften oluşan bir üs gelebilir (**e** veya **E**) ve isteğe bağlı olarak imzalı bir tamsayı. Onaltılık biçimde onaltılık basamak bir tanıtıcı harften oluşan bir üs gelebilir (**p** veya **P**) ve temsil eden bir isteğe bağlı olarak imzalı bir onaltılık tamsayı 2'in kuvveti olarak üs. Üstel bir parça ya da bir taban noktası karakter görünürse, iki biçimden biriyle noktası taban karakterin dizedeki son basamağı izleyin varsayılır. Durum hem de sayılır **INF** ve **NAN** forms. Şu biçimlerden birini uymayan ilk karakter taramayı durdurur.

Bu işlevlerin UCRT sürümleri Fortran stili dönüştürülmesini desteklemez (**d** veya **D**) üs harf. Bu standart olmayan uzantı CRT önceki sürümleri tarafından desteklenen ve kodunuz için bir değişiklik olması olabilir. Onaltılık dizeler ve önceki sürümlerinde desteklenmemiş, INF ve NAN değerlerini gidiş dönüşü engelleyebilecek UCRT sürümleri destekler. Bu aynı zamanda önemli değişiklikler kodunuzda neden olabilir. Örneğin, "0x1a" dizesi olarak yorumlanacağını **strtod** 0,0 önceki sürümlerinde, ancak 26.0 UCRT sürümü.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;stdlib.h > C++: &lt;cstdlib > veya &lt;stdlib.h > |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h > veya &lt;wchar.h > C++: &lt;cstdlib >, &lt;stdlib.h > veya &lt;wchar.h > |

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Sayısal Değer İşlevleri Dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
