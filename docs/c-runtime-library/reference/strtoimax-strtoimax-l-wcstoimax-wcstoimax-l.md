---
description: 'Daha fazla bilgi edinin: strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l'
title: strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
ms.date: 11/04/2016
api_name:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
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
ms.openlocfilehash: 9de1e03ef54b65d321e38f86a6f39bc014df7bf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288756"
---
# <a name="strtoimax-_strtoimax_l-wcstoimax-_wcstoimax_l"></a>strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l

Dizeyi en büyük desteklenen işaretli tamsayı türünün tamsayı değerine dönüştürür.

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
Kullanılacak sayı temeli.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoimax** , *strSource* dizesinde temsil edilen değeri döndürür; bu durumda, gösterim bir taşmaya neden olabilir. Bu durumda, **INTMAX_MAX** veya **INTMAX_MIN** döndürür ve **errno** , **ERANGE** olarak ayarlanır. Dönüştürme gerçekleştirilemiyorsa işlev 0 döndürür. **wcstoimax** , **strtoimax**'e anormal olarak değer döndürür.

**INTMAX_MAX** ve **INTMAX_MIN** , stdint. h içinde tanımlanır.

*StrSource* **null** ise veya *taban* sıfır değilse ve 2 ' den küçük ya da 36 ' den büyükse **errno** , **EINVAL** olarak ayarlanır.

Dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Strtoimax** Işlevi, *strSource* 'u bir **intmax_t** dönüştürür. **Strtoimax** 'in geniş karakterli sürümü **wcstoimax**; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde davranır. Her iki işlev de bir sayının parçası olarak tanıyamadığı ilk karakterde *strSource* dize okumasını durdurur. Bu, Sonlandırıcı null karakteri olabilir veya *tabandan* büyük veya buna eşit olan ilk sayısal karakter olabilir.

Yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*; içindeki taban karakterinin tanınmasını belirler. daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). **_L** sonekine sahip olmayan işlevler geçerli yerel ayarı kullanır; **_strtoimax_l** ve **_wcstoimax_l** , **_l** sonekine sahip olmayan ilgili işlevlerle aynıdır, bunun yerine geçirilen yerel ayarı kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null** değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr* tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr* tarafından işaret edilen konumda depolanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoimax**|**strtoimax**|**strtoimax**|**wcstoimax**|
|**_tcstoimax_l**|**strtoimax_l**|**_strtoimax_l**|**_wcstoimax_l**|

**strtoimax** , *strSource* 'un aşağıdaki biçimdeki bir dizeyi işaret etmek istiyor:

> [*boşluk*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*rakam*  &#124; *harf*]

Boşluk ve sekme karakterlerinden oluşan bir *boşluk* , yok sayılır; *rakamlar* bir veya daha fazla ondalık basamaklıdır; *harfler* , ' a '-' z ' (veya ' a '-' z ') harflerinden biridir. Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Base* 0 Ise, *strSource* tarafından işaret edilen dizenin ilk karakterleri, temeli belirlemede kullanılır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arasında değerler atanır; yalnızca atanmış değerlerine *tabandan* küçük olan harflerine izin verilir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *Base* 0 ise ve taranan ilk karakter ' 0 ' ise, sekizlik bir tamsayı varsayılır ve ' 8 ' veya ' 9 ' karakteri taramayı durduracaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoimax**, **_strtoimax_l**, **wcstoimax**, **_wcstoimax_l**|\<inttypes.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Sayısal değer Işlevlerine dize](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l](strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
