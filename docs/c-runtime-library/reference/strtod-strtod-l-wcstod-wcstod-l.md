---
title: strtod, _strtod_l, wcstod, _wcstod_l
description: Strtod, _strtod_l, wcstod ve _wcstod_l için API başvurusu dizeleri çift duyarlıklı bir değere dönüştürür.
ms.date: 08/27/2020
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
ms.openlocfilehash: 1e75fe39c8ab7020a088307421926327d4043ba8
ms.sourcegitcommit: efed9ed109862c6c2a042f2663b680e8ca4e16a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89933833"
---
# <a name="strtod-_strtod_l-wcstod-_wcstod_l"></a>strtod, _strtod_l, wcstod, _wcstod_l

Dizeleri çift duyarlıklı bir değere dönüştürür.

## <a name="syntax"></a>Söz dizimi

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

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtod** , kayan noktalı sayının değerini döndürür; bu durumda, işlevin bir taşmaya neden olacağı durumlar hariç, işlev +/-**HUGE_VAL**döndürür. **HUGE_VAL** işareti, gösterilemeyen değerin işaretiyle eşleşir. **strtod** , `0` hiçbir dönüştürme gerçekleştirilemiyorsa veya bir yetersiz yer oluşması durumunda geri döner.

**wcstod** , **strtod**'ye anormal bir değer döndürür:

- Her iki işlev için de **errno** , taşma veya yetersiz kalması durumunda **ERANGE** olarak ayarlanır.
- Geçersiz parametreler varsa, **errno** **EINVAL** olarak ayarlanır ve [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Her işlev, *strSource* giriş dizesini öğesine dönüştürür **`double`** . **Strtod** Işlevi, *strSource* 'u çift duyarlıklı bir değere dönüştürür. **strtod** , bir sayının parçası olarak tanıyamadığı Ilk karakterde *strSource* dize okumasını durduruyor. Bu karakter, Sonlandırıcı null karakteri olabilir. **wcstod** , **strtod**; öğesinin geniş karakterli bir sürümüdür. *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

Geçerli yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*içindeki taban noktası karakterinin tanınmasını belirler. Daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). **_L** soneki olmayan işlevler geçerli yerel ayarı kullanır; **_strtod_l** , ilki bunun yerine geçirilen *yerel ayarı* kullandığından **_strtod** aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null**değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr*tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtod** , *strSource* 'un aşağıdaki formlardan birine işaret olmasını bekler:

[*boşluk*] [*imzala*] {*digits* [*taban* *rakamları*] &#124; *taban* *rakamları*} [{**e** &#124; **e**} [*oturum açma*] *basamaklar*] [*boşluk*]*[imzala*]**{0x** &#124; **0x**} {*onaltıbasamaklar* [*taban* *onaltıbasamaklar*] &#124; *taban* *onaltıbasamaklar*} [{**p** &#124; **p**} [*oturum açma*] *basamaklar*] [*boşluk*] [imzala] {**INF** &#124; **Infinity**} [*boşluk*] [*imzala*] **Nan** [*Sequence*]*sign*

İsteğe bağlı öndeki *boşluk* , yoksayılan boşluk ve sekme karakterlerinden oluşabilir. \
*imza* artı (+) veya eksi (-). \
*rakamlar* bir veya daha fazla ondalık basamaklıdır. \
*onaltılıbasamaklar* bir veya daha fazla onaltılık rakamdan oluşur. \
*taban* , varsayılan "C" yerel ayarında nokta (.) veya geçerli yerel ayar farklıysa ya da *Yerel* ayar belirtildiğinde yerel ayara özgü değeri olan taban nokta karakterdir. \
 *Dizi* , alfasayısal veya alt çizgi karakterlerinden oluşan bir dizidir.

Hem ondalık hem de onaltılık sayı formlarında, taban nokta karakterinden önce bir basamak görünmezse, en az bir sayı, taban nokta karakterinden sonra görünmelidir. 

Ondalık biçimde, ondalık basamakların ardından, bir giriş harfinden (**e** veya **e**) ve isteğe bağlı olarak işaretli bir tamsayıdan oluşan bir üs gelebilir. 

Onaltılık biçimde, onaltılık basamakların ardından, bir giriş harfinden (**p** veya **p**) oluşan bir üs ve 2 ' nin üssü olarak üs değeri temsil eden isteğe bağlı olarak imzalanmış bir ondalık tamsayı ile izlenebilir.

Herhangi bir biçimde, bir üs bölümü veya bir taban nokta karakteri yoksa, bir sayı karakteri, dizedeki son basamağı izleyecek şekilde kabul edilir.

Hem **INF** hem de **Nan** formlarında durum yoksayılır. Bu formlardan birine uymayan ilk karakter taramayı durduruyor.

Bu işlevlerin UCRT sürümleri, FORTRAN-Style (**d** veya **d**) üs harflerinin dönüştürülmesini desteklemez. Standart olmayan bu uzantı, CRT 'nin önceki sürümleri tarafından desteklenmiş ve kodunuz için bir ön değişiklik olabilir. UıCRT sürümleri, önceki sürümlerde desteklenmeyen, INF ve NAN değerlerinin onaltılık dizelerini ve gidiş dönüşü destekler. Bu ayrıca kodunuzda önemli değişikliklere neden olabilir. Örneğin, "0x1A" dizesi önceki sürümlerde 0,0 olarak **strtod** ve UCRT sürümünde 26,0 olarak yorumlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt; Stdlib. h> C++: &lt; cstdlib> veya &lt; stdlib. h> |
|**wcstod**, **_wcstod_l**|C: &lt; Stdlib. h> veya &lt; wchar. h> C++: &lt; cstdlib>, &lt; stdlib. h> veya &lt; wchar. h> |

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
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Çok baytlı karakter dizilerinin yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Sayısal değer Işlevlerine dize](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
