---
title: strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l
ms.date: 11/04/2016
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
helpviewer_keywords:
- _strtoumax_l function
- conversion functions
- wcstoumax function
- _wcstoumax_l function
- strtoumax function
ms.assetid: 566769f9-495b-4508-b9c6-02217a578897
ms.openlocfilehash: c9c8ca79ed68b23586d9fef979bc8d47b72ca846
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518475"
---
# <a name="strtoumax-strtoumaxl-wcstoumax-wcstoumaxl"></a>strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l

Dizeleri en büyük desteklenen imzasız tamsayı türünün tamsayı değerine dönüştürür.

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
Taramayı durduran karakter işaretçisi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoull** varsa, dönüştürülen değeri döndürür veya **UINTMAX_MAX** taşmada. **strtoull** dönüştürme gerçekleştirilemiyorsa 0 döndürür. **wcstoumax** çok öğesine değerleri döndürür **strtoumax**. Her iki işlev için **errno** ayarlanır **ERANGE** taşma veya yetersiz gelme oluşması durumunda.

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri Giriş dizesinin dönüştürür *strSource* için bir **uintmax_t** tamsayı değeri.

**strtoull** dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir veya büyüktür veya ona eşit olan ilk sayısal karakter olabilir *temel*. **Lc_numerıc** öğesindeki taban karakterin tanınmasını yerel ayarların belirler yerel ayarının kategori ayarına *strSource*. Daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md). **strtoull** ve **wcstoumax** geçerli yerel ayarı kullanır; **_strtoumax_l** ve **_wcstoumax_l** bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

Geniş karakter sürümünü **strtoumax** olduğu **wcstoumax**; *strSource* geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoumax**|**strtoumax**|**strtoumax**|**wcstoumax**|
|**_tcstoumax_l**|**strtoumax_l**|**_strtoumax_l**|**_wcstoumax_l**|

**strtoull** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *basamak* bir veya daha fazla ondalık basamaktır. *harf* 'a' ila 'z' (veya 'A'-'Z') bir veya daha fazla harf olan. Bu forma uymayan ilk karakter taramayı durdurur. Varsa *temel* 2 ile 36 arasındaysa sayının tabanı kullanılır olduğu. Varsa *temel* tarafından işaret edilen dizenin ilk karakterleri 0'dır *strSource* tabanı belirlemek için kullanılır. İlk karakter '0', ikinci karakter 'x' veya 'X' değil ise dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter '0' ise ve ikinci karakter 'x' veya 'X' dize onaltılık bir tamsayı olarak yorumlanır. İlk karakter ' 1'-' 9' ise, dize ondalık bir tamsayı olarak yorumlanır. Harfler 'bir'-'z' (ya da 'A'-'Z'), 10-35 arasında değerler atanır; yalnızca atanan değerleri olan harf küçüktür *temel* izin verilir. Tabanın aralığının dışındaki ilk karakter taramayı durdurur. Örneğin, varsa *temel* 0 ise ve taranan ilk karakter '0' ise, sekizlik bir tamsayı olduğu varsayılır ve bir '8' veya '9' karakteri taramayı durduracaktır. **strtoull** artı işaretine (**+**) ya da eksi işareti (**-**) öneki; baştaki eksi işareti, dönüş değerinin iki tamamlayıcısı olduğunu gösterir Dönüştürülmüş dize mutlak değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoumax**|\<stdlib.h >|
|**wcstoumax**|\<stdlib.h > veya \<wchar.h >|
|**_strtoumax_l**|\<stdlib.h >|
|**_wcstoumax_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

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
