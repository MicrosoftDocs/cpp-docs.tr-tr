---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l
ms.date: 4/2/2020
api_name:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
- _o__strtoll_l
- _o__wcstoll_l
- _o_strtoll
- _o_wcstoll
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: d5a0ce8cb2c1d5f88d5439b99047609b32c8d2ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365186"
---
# <a name="strtoll-_strtoll_l-wcstoll-_wcstoll_l"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l

Bir dizeyi **uzun** bir **değere** dönüştürür.

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
Dönüştürme için null-sonlandırılan dize.

*endptr*<br/>
Tazyimi durduran karaktere işaretçi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtoll,** temsilciliğin bir taşmaya neden olacağı durumlar *dışında,* LLONG_MAX **veya** **LLONG_MIN**döndürür. Dönüşüm yapılamazsa işlev 0 döndürür. **wcstoll** benzer şekilde **strtoll**değerleri döndürür.

**LLONG_MAX** ve **LLONG_MIN** LIMITS olarak tanımlanır. H.

*strSource* **NULL** ise veya *taban* sıfırsız ve 2'den az veya 36'dan büyükse, **errno** **EINVAL**olarak ayarlanır.

İade kodları hakkında daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Açıklamalar

**Strtoll** fonksiyonu *strSource'u* **uzun** bir uzuna **dönüştürür.** Her iki işlev de bir sayının parçası olarak tanıyamayacakları ilk karakterdeki *string strSource'u* okumayı durdurur. Bu sonlandırıcı null karakter olabilir veya *tabandan*daha büyük veya taban eşit ilk sayısal karakter olabilir. **wcstoll** **strtoll**geniş karakterli bir sürümüdür ; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

Yerel LC_NUMERIC **kategori** ayarı *strSource*radix karakterinin tanınmasını belirler; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md)bakın. **_l** sonek olmayan işlevler geçerli yerel durumu kullanır; **_strtoll_l** ve **_wcstoll_l,** sonek olmayan karşılık gelen işlevlerle aynıdır, ancak bunun yerine geçirilen yerel alanı kullanırlar. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Endptr* **NULL**değilse, saramayı durduran karaktere işaretçi *endptr*tarafından işaret edilen konumda depolanır. Dönüşüm gerçekleştirilemezse (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtoll** *strSource* aşağıdaki formu bir dize işaret bekliyor:

> [*beyazuzay*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **X** }]] [ *&#124; harflerin**basamakları* ]

Bir *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir; *basamaklar* bir veya daha fazla ondalık basamak; *harfler* 'a' ile 'z' (veya 'A' ile 'Z' harfleri) harfleridir. Bu forma uymayan ilk karakter tazyimi durdurur. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, temeli belirlemek için *strSource* tarafından işaret edilen dizenin ilk karakterleri kullanılır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' değilse, dize sekizli bir sonda olarak yorumlanır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' ise, dize hexadecimal tamsayı olarak yorumlanır. İlk karakter '1' ile '9' arasındaysa, dize ondalık tamsayı olarak yorumlanır. 'a' ile 'z' (veya 'A' ile 'Z' arasında) harfleri 10 ile 35 arasında atanır; yalnızca atanan değerleri *tabandan* daha az olan harflere izin verilir. Taban aralığının dışındaki ilk karakter tazyimeyi durdurur. Örneğin, *taban* 0 ise ve taranan ilk karakter '0' ise, bir sekizli sonda varsayar ve '8' veya '9' karakteri taranması nı durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoll**, **_strtoll_l**|\<stdlib.h>|
|**wcstoll**, **_wcstoll_l**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Dizeden Sayısal Değer Fonksiyonlarına](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
