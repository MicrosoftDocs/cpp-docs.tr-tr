---
title: strtoul, _strtoul_l, wcstoul, _wcstoul_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a75833dedc988e1cd39ed318ca6729f579e90008
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strtoul-strtoull-wcstoul-wcstoull"></a>strtoul, _strtoul_l, wcstoul, _wcstoul_l

Dizeleri imzasız uzun tamsayı değerine dönüştürmek.

## <a name="syntax"></a>Sözdizimi

```C
unsigned long strtoul(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long _strtoul_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long wcstoul(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long _wcstoul_l(
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

**strtoul** varsa, dönüştürülen değeri döndürür veya **ULONG_MAX** taşma. **strtoul** dönüştürme gerçekleştirilebiliyorsa 0 döndürür. **wcstoul** değerleri analogously çok döndürür **strtoul**. Her iki işlevler için **errno** ayarlanır **ERANGE** taşma veya yetersiz olduğunda.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri giriş dizesi dönüştürür *strSource* için bir **imzasız** **uzun**.

**strtoul** dize okumayı durdurur *strSource* ilk karakterinde onu bir sayı bir parçası olarak tanıyabilmesi olamaz. Bu sonlandırma null karakter olabilir ya da sıfırdan büyük veya eşit ilk sayısal karakter olabilir *temel*. **Lc_numerıc** yerel kategori ayarı belirler tanıma taban karakterinin *strSource*; daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). **strtoul** ve **wcstoul** geçerli yerel; kullanın **_strtoul_l** ve **_wcstoul_l** yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakteri gösteren bir işaretçi işaret konumunda depolanan *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* gösterdiği konumunda depolanan *endptr*.

**wcstoul** bir joker karakter sürümü **strtoul**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoul**|**strtoul**|**strtoul**|**wcstoul**|
|**_tcstoul_l**|**strtoul_l**|**_strtoul_l**|**_wcstoul_l**|

**strtoul** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerden oluşabilir. *basamak* bir veya daha fazla ondalık basamakların. *harf* 'a' ile 'z' (veya 'A'-'Z') bir veya daha fazla harf şunlardır. Bu form sığmayan ilk karakter tarama durdurur. Varsa *temel* sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa *temel* gösterdiği dizenin ilk karakter 0'dır ve *strSource* temel belirlemek için kullanılır. İlk karakter 0 ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden *temel* izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa *temel* 0'dır ve taranan ilk karakter '0', tamsayı sekizli kabul edilir ve bir '8' veya '9' karakter tarama durdurur. **strtoul** artı sağlar (**+**) veya eksi (**-**) oturum önek; önüne eksi işareti dönüş değeri tasarruflarını olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoul**|\<stdlib.h >|
|**wcstoul**|\<stdlib.h > veya \<wchar.h >|
|**_strtoul_l**|\<stdlib.h >|
|**_wcstoul_l**|\<stdlib.h > veya \<wchar.h >|

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
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
