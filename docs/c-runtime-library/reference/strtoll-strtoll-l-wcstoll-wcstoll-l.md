---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd469bcab9e64de070484ce6774e7449eda8d167
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strtoll-strtolll-wcstoll-wcstolll"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l

Bir dizeye dönüştürür bir **uzun** **uzun** değeri.

## <a name="syntax"></a>Sözdizimi

```C
long long strtoll(
   const char *strSource,
   char **endptr,
   int base
);
long long wcstoll(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long long _strtoll_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long long _wcstoll_l(
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

**strtoll** dizesini temsil edilen değeri döndürür *strSource*, temsili taşma zaman neden olacağından dışında — bu durumda, döndürür **LLONG_MAX** veya **LLONG_MIN**. Hiçbir dönüştürme gerçekleştirilebiliyorsa işlevi 0 değerini döndürür. **wcstoll** değerleri analogously çok döndürür **strtoll**.

**LLONG_MAX** ve **LLONG_MIN** SINIRLARI tanımlanır. H.

Varsa *strSource* olan **NULL** veya *temel* sıfır dışında olan ve 2 veya 36, büyüktür ya da daha az **errno** ayarlanır **EINVAL** .

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Strtoll** işlev dönüştürür *strSource* için bir **uzun** **uzun**. Her iki işlevleri Durdur dize okuma *strSource* ilk karakterinde bunlar bir sayı bir parçası olarak tanımak olamaz. Bu sonlandırma null karakter olabilir veya büyük veya eşit ilk sayısal karakter olabilir *temel*. **wcstoll** bir joker karakter sürümü **strtoll**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

Yerel **lc_numerıc** kategori ayarı belirler tanıma taban karakterinin *strSource*; daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). Yok işlevleri **_l** sonekini kullan geçerli yerel; **_strtoll_l** ve **_wcstoll_l** yerine geçirilen yerel kullandıkları dışında sonek yok ilgili işlevleri için aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakter işaretçisi işaret ediyor konumda depolanır *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* işaret ediyor konumunda depolanan *endptr*.

**strtoll** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* , göz ardı edilir; boşluk ve sekme karakterlerden oluşabilir *basamak* bir veya daha fazla ondalık basamakların; *harf* 'a' ile 'z' (veya 'A'-'Z') bir veya daha fazla harf şunlardır. Bu form sığmayan ilk karakter tarama durdurur. Varsa *temel* sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa *temel* işaret ediyor dizesinin ilk karakter 0'dır ve *strSource* temel belirlemek için kullanılır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden *temel* izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa *temel* 0'dır ve taranan ilk karakter '0', sekizli tamsayı olduğu varsayılır ve Tarama '8' veya '9' karakteri durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoll**, **_strtoll_l**|\<stdlib.h >|
|**wcstoll**, **_wcstoll_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Sayısal Değer İşlevleri Dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
