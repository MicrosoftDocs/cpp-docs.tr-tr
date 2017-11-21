---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
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
- _strtoll_l
- _tcstoll_l
- _tcstoll
- _wcstoll_l
- strtoll
- wcstoll
dev_langs: C++
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c0528427216f08723d67cb56018a3379562cf32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="strtoll-strtolll-wcstoll-wcstolll"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l
Bir dizeye dönüştürür bir `long long` değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long long strtoll(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long long wcstoll(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long long _strtoll_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long long _wcstoll_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nptr`  
 Dönüştürülecek null ile sonlandırılmış dize.  
  
 `endptr`  
 Tarama durdurur karakter işaretçi.  
  
 `base`  
 Kullanılacak sayı temel.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `strtoll`dizeyi temsil edilen değeri döndürür `nptr`, temsili taşma zaman neden olacağından dışında — bu durumda, döndürür `LLONG_MAX` veya `LLONG_MIN`. Hiçbir dönüştürme gerçekleştirilebiliyorsa işlevi 0 değerini döndürür. `wcstoll`değerleri analogously çok döndürür `strtoll`.  
  
 `LLONG_MAX`ve `LLONG_MIN` SINIRLARI tanımlanır. H.  
  
 Varsa `nptr` olan `NULL` veya `base` sıfır dışında olan ve 2 veya 36, büyüktür ya da daha az `errno` ayarlanır `EINVAL`.  
  
 Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `strtoll` İşlev dönüştürür `nptr` için bir `long long`. Her iki işlevleri Durdur dize okuma `nptr` ilk karakterinde bunlar bir sayı bir parçası olarak tanımak olamaz. Bu sonlandırma null karakter olabilir veya büyük veya eşit ilk sayısal karakter olabilir `base`. `wcstoll`bir joker karakter sürümü `strtoll`; kendi `nptr` bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoll`|`strtoll`|`strtoll`|`wcstoll`|  
|`_tcstoll_l`|`_strtoll_l`|`_strtoll_l`|`_wcstoll_l`|  
  
 Yerel `LC_NUMERIC` kategori ayarı belirler tanıma taban karakterinin `nptr`; daha fazla bilgi için bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Yok işlevleri `_l` sonekini kullan geçerli yerel; `_strtoll_l` ve `_wcstoll_l` yerine geçirilen yerel kullandıkları dışında sonek yok ilgili işlevleri için aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Varsa `endptr` değil `NULL`, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır `endptr`. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri `nptr` işaret ediyor konumunda depolanan `endptr`.  
  
 `strtoll`bekliyor `nptr` aşağıdaki biçimde bir dizeye işaret etmek için:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; `letters`]  
  
 A `whitespace` , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir `digits` bir veya daha fazla ondalık basamakların; `letters` 'a' ile 'z' (veya 'A'-'Z') bir veya daha fazla harf şunlardır. Bu form sığmayan ilk karakter tarama durdurur. Varsa `base` sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa `base` işaret ediyor dizesinin ilk karakter 0'dır ve `nptr` temel belirlemek için kullanılır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden `base` izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa `base` 0'dır ve taranan ilk karakter '0', sekizli tamsayı olduğu varsayılır ve Tarama '8' veya '9' karakteri durdurur.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strtoll`, `_strtoll_l`|\<stdlib.h >|  
|`wcstoll`, `_wcstoll_l`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Sayısal değer işlevleri dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)