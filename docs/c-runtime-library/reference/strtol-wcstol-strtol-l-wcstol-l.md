---
title: strtol, wcstol, _strtol_l, _wcstol_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
dev_langs:
- C++
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fd2d3a78138ca4c6f94cf77bb33de9fda89743d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol, wcstol, _strtol_l, _wcstol_l
Dizeleri uzun tamsayı değerine dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long strtol(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long wcstol(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long _strtol_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long _wcstol_l(  
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
 `strtol` dizede gösterilen değerini verir `nptr`, temsili taşma neden olacağından, içinde bu döndürür durumda dışında `LONG_MAX` veya `LONG_MIN`. `strtol` hiçbir dönüştürme gerçekleştirilebiliyorsa 0 döndürür. `wcstol` değerleri analogously çok döndürür `strtol`. Her iki işlevler için `errno` ayarlanır `ERANGE` taşma veya yetersiz olduğunda.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer dönüş kodları hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 `strtol` İşlev dönüştürür `nptr` için bir `long`. `strtol` dize okumayı durdurur `nptr` ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir ya da sıfırdan büyük veya eşit ilk sayısal karakter olabilir `base`.  
  
 `wcstol` bir joker karakter sürümü `strtol`; kendi `nptr` bağımsız değişkeni olan bir joker karakter dizesi. Bu işlevler aynı şekilde aksi davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstol`|`strtol`|`strtol`|`wcstol`|  
|`_tcstol_l`|`_strtol_l`|`_strtol_l`|`_wcstol_l`|  
  
 Geçerli yerel `LC_NUMERIC` kategori ayarı belirler tanıma taban karakterinin `nptr` *;* daha fazla bilgi için bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Olmadan çalışır `_l` sonekini kullan geçerli yerel; `_strtol_l` ve `_wcstol_l` ilgili işlevleri aynıdır `_l` yerine geçirilen yerel ayar kullanmasını dışında soneki. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Varsa `endptr` değil `NULL`, tarama durduruldu karakteri gösteren bir işaretçi işaret konumunda depolanan `endptr`. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri `nptr` gösterdiği konumunda depolanan `endptr`.  
  
 `strtol` bekliyor `nptr` aşağıdaki biçimde bir dizeye işaret etmek için:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 A `whitespace` , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir `digits` bir veya daha fazla ondalık basamakların. Bu form sığmayan ilk karakter tarama durdurur. Varsa `base` sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa `base` gösterdiği dizenin ilk karakter 0'dır ve `nptr` temel belirlemek için kullanılır. İlk karakter 0 ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden `base` izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa `base` 0'dır ve taranan ilk karakter '0', tamsayı sekizli kabul edilir ve bir '8' veya '9' karakter tarama durdurur.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strtol`|\<stdlib.h>|  
|`wcstol`|\<stdlib.h > veya \<wchar.h >|  
|`_strtol_l`|\<stdlib.h>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Sayısal değer işlevleri dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)