---
title: strtold, _strtold_l, wcstold, _wcstold_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ff8aa3f62a50ae544de61953054bd8906ed5971
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold, _strtold_l, wcstold, _wcstold_l
Dizeleri uzun çift duyarlıklı kayan noktalı değerine dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long double strtold(  
   const char *nptr,  
   char **endptr   
);  
long double _strtold_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
long double wcstold(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
long double wcstold_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nptr`  
 Dönüştürülecek null ile sonlandırılmış dize.  
  
 `endptr`  
 Tarama durdurur karakter işaretçi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `strtold`kayan noktalı sayı olarak değerini döndürür bir `long double`, temsili taşma zaman neden olacağından dışında — bu durumda, işlevi döndürür`HUGE_VALL`. İşaretini `HUGE_VALL` gösterilemez değerini oturum eşleşir. `strtold`hiçbir dönüştürme gerçekleştirilebilir veya bir underflow oluştuğunda 0 döndürür.  
  
 `wcstold`değerleri analogously çok döndürür `strtold`. Her iki işlevler için `errno` ayarlanır `ERANGE` taşması veya yetersiz olursa ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Giriş dizesi her işlevi dönüştürür `nptr` için bir `long double`. `strtold` İşlev dönüştürür `nptr` uzun çift duyarlıklı değeri. `strtold`dize okumayı durdurur `nptr` ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir. Joker karakter sürümü `strtold` olan `wcstold`; kendi `nptr` bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstold`|`strtold`|`strtold`|`wcstold`|  
|`_tcstold_l`|`_strtold_l`|`_strtold_l`|`_wcstold_l`|  
  
 `LC_NUMERIC` Geçerli yerel kategori ayarı belirler taban karakterinin tanıma `nptr`. Daha fazla bilgi için bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Olmadan çalışır `_l` sonekini kullan geçerli yerel; `_strtold_l` ve `_wcstold_l` özdeş `_strtold` ve `_wcstold` dışında bunun yerine geçirilen yerel kullanırlar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Varsa `endptr` değil `NULL`, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır `endptr`. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri `nptr` işaret ediyor konumunda depolanan `endptr`.  
  
 `strtold`bekliyor `nptr` aşağıdaki biçimde bir dizeye işaret etmek için:  
  
 [`whitespace`] [`sign`] [`digits`] [`.digits`] [ {`d` &#124; `D` &#124; `e` &#124; `E`}[`sign`]`digits`]  
  
 A `whitespace` , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir `sign` da artı (`+`) veya eksi (`-`); ve `digits` bir veya daha fazla ondalık basamakların. Hiç basamak önce taban karakter görünüyorsa, en az bir taban karakter sonra görünmesi gerekir. Ondalık basamak giriş harfini oluşur üs tarafından izlenebilir (`d`, `D`, `e`, veya `E`) ve isteğe bağlı olarak işaretli bir tam sayı. Ne üs bir parçası, ne de bir taban karakter görünürse, bir taban karakter dizesindeki son basamaklı izleyin varsayılır. Bu form sığmayan ilk karakter tarama durdurur.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strtold`, `_strtold_l`|\<stdlib.h >|  
|`wcstold`, `_wcstold_l`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Sayısal değer işlevleri dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)