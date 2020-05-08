---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 4/2/2020
api_name:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
- _o__strtod_l
- _o__wcstod_l
- _o_strtod
- _o_wcstod
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
ms.openlocfilehash: 410d339789ef4a29a6760a4118f967b22f4f3a8c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910887"
---
# <a name="strtod-_strtod_l-wcstod-_wcstod_l"></a>strtod, _strtod_l, wcstod, _wcstod_l

Dizeleri çift duyarlıklı bir değere dönüştürür.

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

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtod** , kayan noktalı sayının değerini döndürür; bu durumda, işlevin bir taşmaya neden olacağı durumlar hariç, işlev +/-**HUGE_VAL**döndürür. **HUGE_VAL** işareti, gösterilemeyen değerin işaretiyle eşleşir. **strtod** , hiçbir dönüştürme gerçekleştirilemiyorsa veya bir yetersiz bir durum oluşursa 0 değerini döndürür.

**wcstod** , **strtod**'ye anormal olarak değer döndürür. Her iki işlev için de **errno** , taşma veya yetersiz kalması durumunda ve [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrıldığında **ERANGE** olarak ayarlanır. Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

Her işlev, *strSource* giriş dizesini **Double**olarak dönüştürür. **Strtod** Işlevi, *strSource* 'u çift duyarlıklı bir değere dönüştürür. **strtod** , bir sayının parçası olarak tanıyamadığı Ilk karakterde *strSource* dize okumasını durduruyor. Bu, Sonlandırıcı null karakteri olabilir. **wcstod** , **strtod**; öğesinin geniş karakterli bir sürümüdür. *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

Geçerli yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*içindeki taban noktası karakterinin tanınmasını belirler. Daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). **_L** soneki olmayan işlevler geçerli yerel ayarı kullanır; **_strtod_l** , bunun yerine geçirilen *yerel ayarı* kullanmaları hariç **_strtod_l** aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null**değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr*tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtod** , *strSource* 'un aşağıdaki formlardan birine işaret olmasını bekler:

[*boşluk*] [*imzala*] {*digits* [*taban* *rakamları*] &#124; *taban* *rakamları*} [{**e** &#124; **e**} [*oturum açma*] *basamaklar*] [*boşluk*] [*imzala*] {**0x** &#124; **0x**} {*onaltıbasamaklar* [*taban* *onaltıbasamaklar*] &#124; *taban* *onaltıbasamaklar*} [{**p** &#124; **p**} [*işareti*] *onaltılık basamaklar*] **NAN** *sequence***[&#124;** boşluk *] [**oturum]**whitespace* **INFINITY***sign*

İsteğe bağlı öndeki *boşluk* , yoksayılan boşluk ve sekme karakterlerinden oluşabilir; *imza* artı (+) veya eksi (-); *rakamlar* bir veya daha fazla ondalık basamaklıdır; *onaltılıbasamaklar* bir veya daha fazla onaltılı basamaktan oluşur; *taban* , varsayılan "C" yerel ayarında nokta (.) veya geçerli yerel ayar farklıysa ya da *Yerel* ayar belirtildiğinde yerel ayara özgü değeri olan taban nokta karakterdir; *dizi* , alfasayısal veya alt çizgi karakterlerinden oluşan bir dizidir. Hem ondalık hem de onaltılık sayı formlarında, taban nokta karakterinden önce bir basamak görünmezse, en az bir sayı, taban nokta karakterinden sonra görünmelidir. Ondalık biçimde, ondalık basamakların ardından, bir giriş harfinden (**e** veya **e**) ve isteğe bağlı olarak işaretli bir tamsayıdan oluşan bir üs gelebilir. Onaltılık biçimde, onaltılık basamakların ardından, bir giriş harfinden (**p** veya **p**) oluşan bir üs ve 2 ' nin üssü olarak üs değeri temsil eden isteğe bağlı olarak imzalanmış bir onaltılık tamsayı gelebilir. Her iki biçimde de bir üs bölümü veya bir taban nokta karakteri görünmüyorsa, bir taban noktası karakterinin, dizedeki son basamağı izleyecek varsayılır. Hem **INF** hem de **Nan** formlarında durum yoksayılır. Bu formlardan birine uymayan ilk karakter taramayı durduruyor.

Bu işlevlerin UCRT sürümleri, FORTRAN-Style (**d** veya **d**) üs harflerinin dönüştürülmesini desteklemez. Standart olmayan bu uzantı, CRT 'nin önceki sürümleri tarafından desteklenmiş ve kodunuz için bir ön değişiklik olabilir. UıCRT sürümleri, önceki sürümlerde desteklenmeyen, INF ve NAN değerlerinin onaltılık dizelerini ve gidiş dönüşü destekler. Bu ayrıca kodunuzda önemli değişikliklere neden olabilir. Örneğin, "0x1A" dizesi önceki sürümlerde 0,0 olarak **strtod** ve UCRT sürümünde 26,0 olarak yorumlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;Stdlib. h> C++: &lt;cstdlib> veya &lt;Stdlib. h> |
|**wcstod**, **_wcstod_l**|C: &lt;Stdlib. h> veya &lt;wchar. h> C++: &lt;cstdlib>, &lt;Stdlib. h> veya &lt;wchar. h> |

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Sayısal değer Işlevlerine dize](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
