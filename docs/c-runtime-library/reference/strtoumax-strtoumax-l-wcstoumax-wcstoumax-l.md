---
description: ': Strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l hakkında daha fazla bilgi edinin'
title: strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l
ms.date: 11/04/2016
api_name:
- _wcstoumax_l
- _strtoumax_l
- wcstoumax
- strtoumax
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
ms.openlocfilehash: fe3ef3efe19f6b75ff949362876a2004932e9d14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117256"
---
# <a name="strtoumax-_strtoumax_l-wcstoumax-_wcstoumax_l"></a>strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l

Dizeleri desteklenen en büyük işaretsiz tamsayı türünün tamsayı değerine dönüştürür.

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
Kullanılacak sayı temeli.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoull** , varsa dönüştürülmüş değeri, varsa veya taşma üzerinde **UINTMAX_MAX** döndürür. **strtoull** , hiçbir dönüştürme gerçekleştirilemiyorsa 0 döndürür. **wcstoull** , **strtoull**'a anormal değerler döndürür. Her iki işlev için de **errno** , taşma veya yetersiz kalması durumunda **ERANGE** olarak ayarlanır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, *strSource* giriş dizesini bir **uintmax_t** tamsayı değerine dönüştürür.

**strtoull** , bir sayının parçası olarak tanıyamadığı ilk karakterde *strSource* dize okumasını durduruyor. Bu, Sonlandırıcı null karakteri olabilir veya *tabandan* büyük veya buna eşit olan ilk sayısal karakter olabilir. Yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*'ta taban karakterinin tanınmasını belirler. Daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). **strtoull** ve **wcstoull** geçerli yerel ayarı kullanır; **_strtoumax_l** ve **_wcstoumax_l** , bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null** değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr* tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr* tarafından işaret edilen konumda depolanır.

**Strtoull** öğesinin geniş karakterli sürümü **wcstoull**; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoumax**|**strtoull**|**strtoull**|**wcstoull**|
|**_tcstoumax_l**|**strtoumax_l**|**_strtoumax_l**|**_wcstoumax_l**|

**strtoull** , *strSource* 'un aşağıdaki biçimdeki bir dizeyi işaret etmek istiyor:

> [*boşluk*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*rakam*  &#124; *harf*]

Boşluk ve sekme karakterlerinden oluşan bir *boşluk* , yok sayılır. *rakamlar* bir veya daha fazla ondalık basamaklıdır. *harfler* , ' a '-' z ' (veya ' a '-' z ') harflerinden biridir. Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Base* 0 Ise, *strSource* tarafından işaret edilen dizenin ilk karakterleri temeli belirlemede kullanılır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arasında değerler atanır; yalnızca atanmış değerlerine *tabandan* küçük olan harflerine izin verilir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *Base* 0 ise ve taranan ilk karakter ' 0 ' ise, sekizlik bir tamsayı varsayılır ve ' 8 ' veya ' 9 ' karakteri taramayı durduracaktır. **strtoull** , bir artı işareti ( **+** ) ya da eksi işareti ( **-** ) ön ekine izin verir; baştaki eksi işareti, dönüş değerinin, dönüştürülmüş dizenin mutlak değerinin tamamlamada elde olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoull**|\<stdlib.h>|
|**wcstoull**|\<stdlib.h> veya \<wchar.h>|
|**_strtoumax_l**|\<stdlib.h>|
|**_wcstoumax_l**|\<stdlib.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Strtod](strtod-strtod-l-wcstod-wcstod-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Sayısal değer Işlevlerine dize](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l](strtoimax-strtoimax-l-wcstoimax-wcstoimax-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
