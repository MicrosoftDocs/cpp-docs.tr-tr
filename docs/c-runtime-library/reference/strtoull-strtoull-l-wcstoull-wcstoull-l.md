---
title: strtoull, _strtoull_l, wcstoull, _wcstoull_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _strtoull_l
- _wcstoull_l
- strtoull
- wcstoull
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
- _wcstoull_l
- _tcstoull
- _tcstoull_l
- wcstoull
- _strtoull_l
- strtoull
dev_langs:
- C++
helpviewer_keywords:
- strtoull function
- _tcstoull_l function
- _tcstoull function
- _wcstoull_l function
- _strtoull_l function
- wcstoull function
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d984dc88af4c4029c139d13cfa19a2c4159f4eab
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strtoull-strtoulll-wcstoull-wcstoulll"></a>strtoull, _strtoull_l, wcstoull, _wcstoull_l

Dizeleri imzasız uzun uzun tamsayı değerine dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned long long strtoull(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long long _strtoull_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long long wcstoull(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long long _wcstoull_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Dönüştürülecek null ile sonlandırılmış dize.

*endptr*<br/>
Tarama durdurur karakter işaretçi.

*base*<br/>
Kullanılacak sayı temel.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoull** varsa, dönüştürülen değeri döndürür veya **ULLONG_MAX** taşma. **strtoull** dönüştürme gerçekleştirilebiliyorsa 0 döndürür. **wcstoull** değerleri analogously çok döndürür **strtoull**. Her iki işlevler için **errno** ayarlanır **ERANGE** taşma veya yetersiz olduğunda.

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri giriş dizesi dönüştürür *strSource* için bir **imzasız** **uzun** **uzun** tamsayı değeri.

**strtoull** dize okumayı durdurur *strSource* ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir veya büyük veya eşit ilk sayısal karakter olabilir *temel*. Ayarını **lc_numerıc** yerel kategorisini belirler tanıma taban karakterinin *strSource*; daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). **strtoull** ve **wcstoull** geçerli yerel; kullanın **_strtoull_l** ve **_wcstoull_l** yerine geçirilen yerel ayar ancak özdeş kullanmayacak. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* işaret ediyor konumunda depolanan *endptr*.

**wcstoull** bir joker karakter sürümü **strtoull** ve kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoull**|**strtoull**|**strtoull**|**wcstoull**|
|**_tcstoull_l**|**strtoull_l**|**_strtoull_l**|**_wcstoull_l**|

**strtoull** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerden oluşabilir. *basamak* bir veya daha fazla ondalık basamakların. *harf* 'a' ile 'z' (veya 'A'-'Z') bir veya daha fazla harf şunlardır. Bu form sığmayan ilk karakter tarama durdurur. Varsa *temel* sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa *temel* işaret ediyor dizesinin ilk karakter 0'dır ve *strSource* temel belirlemek için kullanılır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden *temel* izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa *temel* 0'dır ve taranan ilk karakter '0', sekizli tamsayı olduğu varsayılır ve Tarama '8' veya '9' karakteri durdurur. **strtoull** bir artı işareti sağlar (**+**) veya eksi işareti (**-**) öneki; başında eksi işareti dönüş değeri tasarruflarını olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoull**|\<stdlib.h >|
|**wcstoull**|\<stdlib.h > veya \<wchar.h >|
|**_strtoull_l**|\<stdlib.h >|
|**_wcstoull_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Sayısal Değer İşlevleri Dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
