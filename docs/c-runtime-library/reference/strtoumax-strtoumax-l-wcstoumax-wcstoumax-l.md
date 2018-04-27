---
title: strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wcstoumax_l
- _strtoumax_l
- wcstoumax
- strtoumax
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
- wcstoumax
- _tcstoumax
- _strtoumax_l
- _wcstoumax_l
- _tcstoumax_l
- strtoumax
dev_langs:
- C++
helpviewer_keywords:
- _strtoumax_l function
- conversion functions
- wcstoumax function
- _wcstoumax_l function
- strtoumax function
ms.assetid: 566769f9-495b-4508-b9c6-02217a578897
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e57298c9f3c4d2ef20e679abf7d7da3c75f1ec52
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strtoumax-strtoumaxl-wcstoumax-wcstoumaxl"></a>strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l

Dizeleri büyük desteklenen imzasız Tamsayı türünde tamsayı değerine dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
uintmax_t strtoumax(
   const char *strSource,
   char **endptr,
   int base
);
uintmax_t _strtoumax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
uintmax_t wcstoumax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
uintmax_t _wcstoumax_l(
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

**strtoumax** varsa, dönüştürülen değeri döndürür veya **UINTMAX_MAX** taşma. **strtoumax** dönüştürme gerçekleştirilebiliyorsa 0 döndürür. **wcstoumax** değerleri analogously çok döndürür **strtoumax**. Her iki işlevler için **errno** ayarlanır **ERANGE** taşma veya yetersiz olduğunda.

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri giriş dizesi dönüştürür *strSource* için bir **uintmax_t** tamsayı değeri.

**strtoumax** dize okumayı durdurur *strSource* ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir veya büyük veya eşit ilk sayısal karakter olabilir *temel*. **Lc_numerıc** yerel kategori ayarı belirler taban karakterinin tanıma *strSource*. Daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). **strtoumax** ve **wcstoumax** geçerli yerel; kullanın **_strtoumax_l** ve **_wcstoumax_l** yerine geçirilen yerel kullandıkları dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* işaret ediyor konumunda depolanan *endptr*.

Joker karakter sürümü **strtoumax** olan **wcstoumax**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoumax**|**strtoumax**|**strtoumax**|**wcstoumax**|
|**_tcstoumax_l**|**strtoumax_l**|**_strtoumax_l**|**_wcstoumax_l**|

**strtoumax** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerden oluşabilir. *basamak* bir veya daha fazla ondalık basamakların. *harf* 'a' ile 'z' (veya 'A'-'Z') bir veya daha fazla harf şunlardır. Bu form sığmayan ilk karakter tarama durdurur. Varsa *temel* sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa *temel* işaret ediyor dizesinin ilk karakter 0'dır ve *strSource* temel belirlemek için kullanılır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden *temel* izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa *temel* 0'dır ve taranan ilk karakter '0', tamsayı sekizli kabul edilir ve bir '8' veya '9' karakter tarama durdurur. **strtoumax** bir artı işareti sağlar (**+**) veya eksi işareti (**-**) öneki; önüne eksi işareti dönüş değerini iki kişinin tamamlayıcı olduğunu gösterir Dönüştürülmüş dizeyi mutlak değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoumax**|\<stdlib.h >|
|**wcstoumax**|\<stdlib.h > veya \<wchar.h >|
|**_strtoumax_l**|\<stdlib.h >|
|**_wcstoumax_l**|\<stdlib.h > veya \<wchar.h >|

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
[strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l](strtoimax-strtoimax-l-wcstoimax-wcstoimax-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
