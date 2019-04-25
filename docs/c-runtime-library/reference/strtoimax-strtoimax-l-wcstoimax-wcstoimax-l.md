---
title: strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
ms.date: 11/04/2016
apiname:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
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
- wcstoimax
- _tcstoimax
- strtoimax
- _wcstoimax_l
- _strtoimax_l
- _tcstoimax_l
helpviewer_keywords:
- strtoimax funciton
- conversion functions
- _strtoimax_l function
- _wcstoimax_l function
- wcstoimax function
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
ms.openlocfilehash: e0a320f90b2c0f8653109a6ae0056c4c0cdd7455
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176297"
---
# <a name="strtoimax-strtoimaxl-wcstoimax-wcstoimaxl"></a>strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l

Bir dizeyi en büyük desteklenen imzalı tamsayı türünün tamsayı değerine dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
intmax_t strtoimax(
   const char *strSource,
   char **endptr,
   int base
);
intmax_t wcstoimax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
intmax_t _strtoimax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
intmax_t _wcstoimax_l(
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

**strtoimax** dizesinde temsil edilen değeri döndürür *strSource*, gösterimin bir taşma neden olduğu zaman dışında — bu durumda, döndürür **INTMAX_MAX** veya **INTMAX_MIN**, ve **errno** ayarlanır **ERANGE**. Dönüştürme gerçekleştirilemiyorsa işlev 0 döndürür. **wcstoimax** çok öğesine değerleri döndürür **strtoimax**.

**INTMAX_MAX** ve **INTMAX_MIN** stdint.h. içinde tanımlanır.

Varsa *strSource* olduğu **NULL** veya *temel* sıfır dışında olan ve 2'den küçük veya 36'dan büyük ya da daha az **errno** ayarlanır **EINVAL** .

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Strtoimax** işlev dönüştürür *strSource* için bir **intmax_t**. Geniş karakter sürümünü **strtoimax** olduğu **wcstoimax**; *strSource* geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır. Her iki işlev dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir veya büyüktür veya ona eşit olan ilk sayısal karakter olabilir *temel*.

Yerel **lc_numerıc** kategori ayarı belirler taban karakterin tanınmasını yerel ayarların *strSource*; daha fazla bilgi için bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md). Sahip olmayan işlevler **_l** soneki geçerli yerel ayarı kullanır; **_strtoimax_l** ve **_wcstoimax_l** sahip olmayan ilgili işlevlerle aynıdır **_l** bunun yerine yerel ayarı kullanmaları dışında soneki o geçirildi. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoimax**|**strtoimax**|**strtoimax**|**wcstoimax**|
|**_tcstoimax_l**|**strtoimax_l**|**_strtoimax_l**|**_wcstoimax_l**|

**strtoimax** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir *basamak* bir veya daha fazla ondalık basamaktır; *harf* 'a' ila 'z' (veya 'A'-'Z') bir veya daha fazla harf olan. Bu forma uymayan ilk karakter taramayı durdurur. Varsa *temel* 2 ile 36 arasındaysa sayının tabanı kullanılır olduğu. Varsa *temel* tarafından işaret edilen dizenin ilk karakterleri 0'dır *strSource* tabanı belirlemek için kullanılır. İlk karakter '0', ikinci karakter 'x' veya 'X' değil ise dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter '0' ise ve ikinci karakter 'x' veya 'X' dize onaltılık bir tamsayı olarak yorumlanır. İlk karakter ' 1'-' 9' ise, dize ondalık bir tamsayı olarak yorumlanır. Harfler 'bir'-'z' (ya da 'A'-'Z'), 10-35 arasında değerler atanır; yalnızca atanan değerleri olan harf küçüktür *temel* izin verilir. Tabanın aralığının dışındaki ilk karakter taramayı durdurur. Örneğin, varsa *temel* 0 ise ve taranan ilk karakter '0' ise, sekizlik bir tamsayı olduğu varsayılır ve bir '8' veya '9' karakteri taramayı durduracaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoimax**, **_strtoimax_l**, **wcstoimax**, **_wcstoimax_l**|\<inttypes.h >|

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
[strtoull, _strtoull_l, wcstoull, _wcstoull_l](strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
