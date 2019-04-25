---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l
ms.date: 11/04/2016
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
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
ms.openlocfilehash: 53ae4ab1d482478c50aa257acdc974569bfc05f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269156"
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
Taramayı durduran karakter işaretçisi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoll** dizesinde temsil edilen değeri döndürür *strSource*, gösterimin bir taşma neden olduğu zaman dışında — bu durumda, döndürür **LLONG_MAX** veya **LLONG_MIN**. Dönüştürme gerçekleştirilemiyorsa işlev 0 döndürür. **wcstoll** çok öğesine değerleri döndürür **strtoll**.

**LLONG_MAX** ve **LLONG_MIN** SINIRLARI tanımlanır. H

Varsa *strSource* olduğu **NULL** veya *temel* sıfır dışında olan ve 2'den küçük veya 36'dan büyük ya da daha az **errno** ayarlanır **EINVAL** .

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Strtoll** işlev dönüştürür *strSource* için bir **uzun** **uzun**. Her iki işlev dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir veya büyüktür veya ona eşit olan ilk sayısal karakter olabilir *temel*. **wcstoll** geniş karakterli sürümüdür **strtoll**; *strSource* geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

Yerel **lc_numerıc** kategori ayarı belirler taban karakterin tanınmasını yerel ayarların *strSource*; daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). Sahip olmayan işlevler **_l** soneki geçerli yerel ayarı kullanır; **_strtoll_l** ve **_wcstoll_l** bunun yerine geçirilen yerel ayarı kullanmaları dışında soneki olmayan ilgili işlevlerle aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

**strtoll** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir *basamak* bir veya daha fazla ondalık basamaktır; *harf* 'a' ila 'z' (veya 'A'-'Z') bir veya daha fazla harf olan. Bu forma uymayan ilk karakter taramayı durdurur. Varsa *temel* 2 ile 36 arasındaysa sayının tabanı kullanılır olduğu. Varsa *temel* tarafından işaret edilen dizenin ilk karakterleri 0'dır *strSource* tabanı belirlemek için kullanılır. İlk karakter '0', ikinci karakter 'x' veya 'X' değil ise dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter '0' ise ve ikinci karakter 'x' veya 'X' dize onaltılık bir tamsayı olarak yorumlanır. İlk karakter ' 1'-' 9' ise, dize ondalık bir tamsayı olarak yorumlanır. Harfler 'bir'-'z' (ya da 'A'-'Z'), 10-35 arasında değerler atanır; yalnızca atanan değerleri olan harf küçüktür *temel* izin verilir. Tabanın aralığının dışındaki ilk karakter taramayı durdurur. Örneğin, varsa *temel* 0 ise ve taranan ilk karakter '0' ise, sekizlik bir tamsayı olduğu varsayılır ve bir '8' veya '9' karakteri taramayı durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoll**, **_strtoll_l**|\<stdlib.h >|
|**wcstoll**, **_wcstoll_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
