---
title: strtoul, _strtoul_l, wcstoul, _wcstoul_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
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
- strtoul
- _tcstoul
- wcstoul
dev_langs: C++
helpviewer_keywords:
- _wcstoul_l function
- _tcstoul function
- _strtoul_l function
- string conversion, to integers
- wcstoul function
- strtoul function
- wcstoul_l function
- strtoul_l function
- tcstoul function
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32bc9c63ec148d8e5c39d2aa6a38da974bfc6d96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strtoul-strtoull-wcstoul-wcstoull"></a>strtoul, _strtoul_l, wcstoul, _wcstoul_l
Dizeleri imzasız uzun tamsayı değerine dönüştürmek.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned long strtoul(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long _strtoul_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long wcstoul(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long _wcstoul_l(  
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
 `strtoul`varsa, dönüştürülen değeri döndürür veya `ULONG_MAX` taşma. `strtoul`hiçbir dönüştürme gerçekleştirilebiliyorsa 0 döndürür. `wcstoul`değerleri analogously çok döndürür `strtoul`. Her iki işlevler için `errno` ayarlanır `ERANGE` taşma veya yetersiz olduğunda.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri giriş dizesi dönüştürür `nptr` için bir `unsigned` `long`.  
  
 `strtoul`dize okumayı durdurur `nptr` ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir ya da sıfırdan büyük veya eşit ilk sayısal karakter olabilir `base`. `LC_NUMERIC` Yerel kategori ayarı belirler tanıma taban karakterinin `nptr`; daha fazla bilgi için bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). `strtoul`ve `wcstoul` geçerli yerel; kullanın `_strtoul_l` ve `_wcstoul_l` yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Varsa `endptr` değil `NULL`, tarama durduruldu karakteri gösteren bir işaretçi işaret konumunda depolanan `endptr`. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri `nptr` gösterdiği konumunda depolanan `endptr`.  
  
 `wcstoul`bir joker karakter sürümü `strtoul`; kendi `nptr` bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde bu işlevler aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoul`|`strtoul`|`strtoul`|`wcstoul`|  
|`_tcstoul_l`|`strtoul_l`|`_strtoul_l`|`_wcstoul_l`|  
  
 `strtoul`bekliyor `nptr` aşağıdaki biçimde bir dizeye işaret etmek için:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 A `whitespace` , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir `digits` bir veya daha fazla ondalık basamakların. Bu form sığmayan ilk karakter tarama durdurur. Varsa `base` sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa `base` gösterdiği dizenin ilk karakter 0'dır ve `nptr` temel belirlemek için kullanılır. İlk karakter 0 ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden `base` izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa `base` 0'dır ve taranan ilk karakter '0', tamsayı sekizli kabul edilir ve bir '8' veya '9' karakter tarama durdurur. `strtoul`artı sağlar (`+`) veya eksi (`-`) oturum önek; önüne eksi işareti dönüş değeri tasarruflarını olduğunu gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strtoul`|\<stdlib.h >|  
|`wcstoul`|\<stdlib.h > veya \<wchar.h >|  
|`_strtoul_l`|\<stdlib.h >|  
|`_wcstoul_l`|\<stdlib.h > veya \<wchar.h >|  
  
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
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)