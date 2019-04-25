---
title: strtoul, _strtoul_l, wcstoul, _wcstoul_l
ms.date: 11/04/2016
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- strtoul
- _tcstoul
- wcstoul
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
ms.openlocfilehash: d4d974084c9249740d565f879f471bc7dfc697bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269214"
---
# <a name="strtoul-strtoull-wcstoul-wcstoull"></a>strtoul, _strtoul_l, wcstoul, _wcstoul_l

Dizeleri bir işaretsiz uzun tamsayı değerine dönüştürün.

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
Taramayı durduran karakter işaretçisi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoul** varsa, dönüştürülen değeri döndürür veya **ULONG_MAX** taşmada. **strtoul** dönüştürme gerçekleştirilemiyorsa 0 döndürür. **wcstoul** çok öğesine değerleri döndürür **strtoul**. Her iki işlev için **errno** ayarlanır **ERANGE** taşma veya yetersiz gelme oluşması durumunda.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri Giriş dizesinin dönüştürür *strSource* için bir **işaretsiz** **uzun**.

**strtoul** dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir veya daha büyük veya eşit ilk sayısal karakter olabilir *temel*. **Lc_numerıc** yerel ayarının kategori ayarı belirler taban karakterin tanınmasını yerel ayarların *strSource*; daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). **strtoul** ve **wcstoul** geçerli yerel ayarı kullanır; **_strtoul_l** ve **_wcstoul_l** bunun yerine iletilmiş yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

**wcstoul** geniş karakterli sürümüdür **strtoul**; *strSource* geniş karakterli bir dizedir. Aksi takdirde bu işlevleri aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoul**|**strtoul**|**strtoul**|**wcstoul**|
|**_tcstoul_l**|**strtoul_l**|**_strtoul_l**|**_wcstoul_l**|

**strtoul** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *basamak* bir veya daha fazla ondalık basamaktır. *harf* 'a' ila 'z' (veya 'A'-'Z') bir veya daha fazla harf olan. Bu forma uymayan ilk karakter taramayı durdurur. Varsa *temel* 2 ile 36 arasındaysa sayının tabanı kullanılır olduğu. Varsa *temel* tarafından işaret edilen dizenin ilk karakterleri 0'dır *strSource* tabanı belirlemek için kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter '0' ise ve ikinci karakter 'x' veya 'X' dize onaltılık bir tamsayı olarak yorumlanır. İlk karakter ' 1'-' 9' ise, dize ondalık bir tamsayı olarak yorumlanır. Harfler 'bir'-'z' (ya da 'A'-'Z'), 10-35 arasında değerler atanır; yalnızca atanan değerleri olan harf küçüktür *temel* izin verilir. Tabanın aralığının dışındaki ilk karakter taramayı durdurur. Örneğin, varsa *temel* 0 ise ve taranan ilk karakter '0' ise, sekizlik bir tamsayı olduğu varsayılır ve bir '8' veya '9' karakteri taramayı durduracaktır. **strtoul** artı sağlar (**+**) veya eksidir (**-**) oturum önekinin; baştaki eksi işareti dönüş değerine değilleme uygulandığını gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoul**|\<stdlib.h >|
|**wcstoul**|\<stdlib.h > veya \<wchar.h >|
|**_strtoul_l**|\<stdlib.h >|
|**_wcstoul_l**|\<stdlib.h > veya \<wchar.h >|

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
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
