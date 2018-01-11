---
title: strtof, _strtof_l, wcstof, _wcstof_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fdfe3a202d18aa1634a2ef692088264ff8fe188
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strtof-strtofl-wcstof-wcstofl"></a>strtof, _strtof_l, wcstof, _wcstof_l
Dizeleri tek duyarlıklı kayan noktalı değerine dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
float strtof(  
   const char *nptr,  
   char **endptr   
);  
float _strtof_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
float wcstof(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
float wcstof_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `nptr`  
 Dönüştürülecek null ile sonlandırılmış dize.  
  
 `endptr`  
 Tarama durdurur karakter işaretçi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `strtof`gösterimi, servis talebi işlevi döndürür +/-taşma, ne zaman neden olacağından dışında kayan noktalı sayı değerini döndürür`HUGE_VALF`. İşaretini `HUGE_VALF` gösterilemez değerini oturum eşleşir. `strtof`hiçbir dönüştürme gerçekleştirilebilir veya bir underflow oluştuğunda 0 döndürür.  
  
 `wcstof`değerleri analogously çok döndürür `strtof`. Her iki işlevler için `errno` ayarlanır `ERANGE` taşması veya yetersiz olursa ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Giriş dizesi her işlevi dönüştürür `nptr` için bir `float`. `strtof` İşlev dönüştürür `nptr` tek duyarlıklı değeri. `strtof`dize okumayı durdurur `nptr` ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir. `wcstof`bir joker karakter sürümü `strtof`; kendi `nptr` bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstof`|`strtof`|`strtof`|`wcstof`|  
|`_tcstof_l`|`_strtof_l`|`_strtof_l`|`_wcstof_l`|  
  
 `LC_NUMERIC` Geçerli yerel kategori ayarı belirler tanıma taban karakterinin `nptr`; daha fazla bilgi için bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Yok işlevleri `_l` soneki geçerli yerel kullanın; bunun yerine geçirilen yerel kullanmasını dışında son ekine sahip olanlarla aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Varsa `endptr` değil `NULL`, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır `endptr`. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri `nptr` işaret ediyor konumunda depolanan `endptr`.  
  
 `strtof`bekliyor `nptr` aşağıdaki biçimde bir dizeye işaret etmek için:  
  
 [`whitespace`] [`sign`] [`digits`] [`.digits`] [ {`e` &#124; `E`}[`sign`]`digits`]  
  
 A `whitespace` , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir `sign` da artı (`+`) veya eksi (`-`); ve `digits` bir veya daha fazla ondalık basamakların. Hiç basamak önce taban karakter görünüyorsa, en az bir taban karakter sonra görünmesi gerekir. Ondalık basamak giriş harfini oluşur üs tarafından izlenebilir (`e` veya `E`) ve isteğe bağlı olarak işaretli bir tam sayı. Ne üs bir parçası, ne de bir taban karakter görünürse, bir taban karakter dizesindeki son basamaklı izleyin varsayılır. Bu form sığmayan ilk karakter tarama durdurur.  
 
 Bu işlevlerin UCRT sürümleri Fortran stili dönüştürülmesini desteklemez (`d` veya `D`) üs harf. Bu standart uzantısı CRT önceki sürümleri tarafından desteklenen ve kodunuz için önemli bir değişiklik olabilir.
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strtof`, `_strtof_l`|C: \<stdlib.h > C++: &lt;cstdlib > veya \<stdlib.h >|  
|`wcstof`, `_wcstof_l`|C: \<stdlib.h > veya \<wchar.h > C++: &lt;cstdlib >, \<stdlib.h > veya \<wchar.h >|  
  
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