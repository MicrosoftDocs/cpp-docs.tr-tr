---
title: strtod, _strtod_l, wcstod, _wcstod_l | Microsoft Docs
ms.custom: ''
ms.date: 10/20/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b1e9971b4e4287b9a7578cf1295ed3c6f5cca1e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

Dizeleri çift duyarlıklı değerine dönüştürür.

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
Tarama durdurur karakter işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtod** gösterimi, servis talebi işlevi döndürür +/-taşma, ne zaman neden olacağından dışında kayan noktalı sayı değerini döndürür**HUGE_VAL**. İşaretini **HUGE_VAL** gösterilemez değerini oturum eşleşir. **strtod** dönüştürme gerçekleştirilebilir veya bir underflow oluşur 0 döndürür.

**wcstod** değerleri analogously çok döndürür **strtod**. Her iki işlevler için **errno** ayarlanır **ERANGE** taşması veya yetersiz olursa ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer dönüş kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Giriş dizesi her işlevi dönüştürür *strSource* için bir **çift**. **Strtod** işlev dönüştürür *strSource* çift duyarlıklı değeri. **strtod** dize okumayı durdurur *strSource* ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir. **wcstod** bir joker karakter sürümü **strtod**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Bu işlevler aynı şekilde aksi davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

**Lc_numerıc** geçerli yerel kategori ayarı belirler tanıma taban noktası karakterinin *strSource*. Daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). Olmadan çalışır **_l** sonekini kullan geçerli yerel; **_strtod_l** aynıdır **_strtod_l** kullandıkları dışında *yerel* yerine geçilen. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakteri gösteren bir işaretçi işaret konumunda depolanan *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* gösterdiği konumunda depolanan *endptr*.

**strtod** bekliyor *strSource* bir dizeye aşağıdaki biçimlerden birini işaret edecek şekilde:

[*boşluk*] [*oturum*] {*basamak* [*taban* *basamak*] &#124;  *sayı tabanını* *basamak*} [{**e** &#124; **E**} [*oturum*] *basamak*] [*boşluk*] [*oturum*] {**0 x** &#124; **0 X**} {*hexdigits* [ *taban* *hexdigits*] &#124; *taban* *hexdigits*} [{**p** &#124; **P**} [*oturum*] *hexdigits*] [*boşluk*] [*oturum*] {} **INF** &#124; **SONSUZ**} [*boşluk*] [*oturum*]  **NAN** [*dizisi*]

İsteğe bağlı başında *boşluk* , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir *oturum* da artı (+) veya eksi (-); *basamak* bir veya daha fazla ondalık basamakların; *hexdigits* onaltılık basamak; bir veya daha fazla olan *taban* taban noktasını karakter ya da bir nokta (.) varsayılan "C" yerel ya da yerel ayarlara özgü değeri geçerli yerel farklıysa veya zaman *yerel* belirtilir; bir *dizisi* alfasayısal dizisini veya alt çizgi karakteri. Sayı tabanını noktasını karakter önce hiç basamak görünüyorsa, ondalık ve onaltılık sayı formlarında en az bir taban noktasını karakter sonra görünmesi gerekir. Ondalık biçiminde bir tanıtım harfini oluşur üs tarafından ondalık basamak izlenebilir (**e** veya **E**) ve isteğe bağlı olarak işaretli bir tam sayı. Onaltılık biçimde bir tanıtım harfini oluşur üs tarafından onaltılık basamak izlenebilir (**p** veya **P**) ve temsil eden bir isteğe bağlı olarak imzalanmış onaltılık tamsayı 2'in üssü olarak üs. Ne üs bir parçası, ne de bir taban noktası karakter görüntülenirse, ya da formunda dizedeki son basamaklı izlemek için bir taban noktası karakter varsayılır. Durum göz ardı edilir hem de **INF** ve **NAN** forms. Şu biçimlerden birini sığmayan ilk karakter tarama durdurur.

Bu işlevlerin UCRT sürümleri Fortran stili dönüştürülmesini desteklemez (**d** veya **D**) üs harf. Bu standart uzantısı CRT önceki sürümleri tarafından desteklenen ve kodunuz için önemli bir değişiklik olabilir. Onaltılık dizeler ve önceki sürümlerinde desteklenmemiş INF ve NAN değerler gidiş UCRT sürümlerini destekler. Bu da önemli değişiklikler kodunuzda neden olabilir. Örneğin, "0x1a" dizesi tarafından yorumlanacağını **strtod** 0,0 önceki sürümlerinde, ancak 26.0 UCRT sürümünde.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;stdlib.h > C++: &lt;cstdlib > veya &lt;stdlib.h > |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h > veya &lt;wchar.h > C++: &lt;cstdlib >, &lt;stdlib.h > veya &lt;wchar.h > |

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
