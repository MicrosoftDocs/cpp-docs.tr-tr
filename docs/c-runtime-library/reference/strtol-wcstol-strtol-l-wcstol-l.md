---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 11/04/2016
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
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
ms.openlocfilehash: b40362e93a41730e46ad0911b5a633118d024e9c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957632"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Dizeleri uzun tamsayı değerine dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
long strtol(
   const char *strSource,
   char **endptr,
   int base
);
long wcstol(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long _strtol_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
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
Kullanılacak sayı temeli.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtol** , *strSource*dizesinde temsil edilen değeri döndürür, bu, temsilin taşmaya neden olduğu durumlar dışında **LONG_MAX** veya **LONG_MIN**döndürür. Hiçbir dönüştürme gerçekleştirilemiyorsa **strtol** 0 değerini döndürür. **wcstol** , **strtol**'e anormal olarak değer döndürür. Her iki işlev için de **errno** , taşma veya yetersiz kalması durumunda **ERANGE** olarak ayarlanır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Strtol** Işlevi, *strSource* 'u **Long**olarak dönüştürür. **strtol** , bir sayının parçası olarak tanıyamadığı Ilk karakterde *strSource* dize okumasını durduruyor. Bu, Sonlandırıcı null karakteri olabilir veya *tabandan*büyük veya buna eşit ilk sayısal karakter olabilir.

**wcstol** , **strtol**; öğesinin geniş karakterli bir sürümüdür. *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

Geçerli yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*; içindeki taban karakterinin tanınmasını belirler. daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). **_L** soneki olmayan işlevler geçerli yerel ayarı kullanır; **_strtol_l** ve **_wcstol_l** , yerine geçirilen yerel ayarı kullanmaları dışında, **_l** soneki olmadan ilgili işlevlerle aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null**değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr*tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtol** , *strSource* 'un aşağıdaki biçimdeki bir dizeye işaret etmek bekler:

> [*boşluk*] [{ **+** &#124; &#124; &#124; }] [0 [{x x}]] [basamak harfleri] **-**

Boşluk ve sekme karakterlerinden oluşan bir *boşluk* , yok sayılır; *rakamlar* bir veya daha fazla ondalık basamaklıdır; *harfler* , ' a '-' z ' (veya ' a '-' z ') harflerinden biridir.  Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Base* 0 Ise, *strSource* tarafından işaret edilen dizenin ilk karakterleri, temeli belirlemede kullanılır. İlk karakter 0 ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arasında değerler atanır; yalnızca atanmış değerlerine *tabandan* küçük olan harflerine izin verilir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *Base* 0 ise ve taranan ilk karakter ' 0 ' ise, sekizlik bir tamsayı varsayılır ve ' 8 ' veya ' 9 ' karakteri taramayı durduracaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtol**|\<Stdlib. h >|
|**wcstol**|\<Stdlib. h > veya \<wchar. h >|
|**_strtol_l**|\<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Strtod](strtod-strtod-l-wcstod-wcstod-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Sayısal Değer İşlevleri Dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
