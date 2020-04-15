---
title: _strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l
ms.date: 4/2/2020
api_name:
- _strtoi64
- _strtoi64_l
- _wcstoi64_l
- _wcstoi64
- _o__strtoi64
- _o__strtoi64_l
- _o__wcstoi64
- _o__wcstoi64_l
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
- _strtoi64
- strtoi64
- _stroi64_l
- _wcstoi64_l
- wcstoi64_l
- _wcstoi64
- wcstoi64
- strtoi64_l
helpviewer_keywords:
- _strtoi64 function
- _wcstoi64 function
- _strtoi64_l function
- string conversion, to integers
- _wcstoi64_l function
- strtoi64_l function
- wcstoi64 function
- strtoi64 function
- wcstoi64_l function
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
ms.openlocfilehash: 8dcdff4cf6f3eff191dc126583c1ca8290133e02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365125"
---
# <a name="_strtoi64-_wcstoi64-_strtoi64_l-_wcstoi64_l"></a>_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l

Dizeyi **__int64** değerine dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
__int64 _strtoi64(
   const char *strSource,
   char **endptr,
   int base
);
__int64 _wcstoi64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
__int64 _strtoi64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
__int64 _wcstoi64_l(
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
Tçalışmayı durduran karakter işaretçisi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_strtoi64,** gösterimin bir taşmaya neden olacağı durumlar *dışında,* **_I64_MAX** veya **_I64_MIN**döndürür. Dönüştürme yapılamazsa işlev 0 döndürecek. **_wcstoi64** benzer şekilde **strtoi64**değerleri döndürür.

**_I64_MAX** ve **_I64_MIN** LIMITS olarak tanımlanır. H.

*strSource* **NULL** ise veya *taban* sıfırsız ve 2'den az veya 36'dan büyükse, **errno** **EINVAL**olarak ayarlanır.

Bunlar ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**_strtoi64** işlevi *strSource'u* **bir __int64**dönüştürür. Her iki işlev de bir sayının parçası olarak tanıyamayacakları ilk karakterdeki *string strSource'u* okumayı durdurur. Bu sonlandırıcı null karakter olabilir veya ilk sayısal karakter daha büyük veya *baz*eşit olabilir. **_wcstoi64** **_strtoi64**geniş karakterli bir sürümüdür; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler aynı şekilde başka türlü çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoi64**|**_strtoi64**|**_strtoi64**|**_wcstoi64**|
|**_tcstoi64_l**|**_strtoi64_l**|**_strtoi64_l**|**_wcstoi64_l**|

Yerel LC_NUMERIC **kategori** ayarı *strSource*radix karakterinin tanınmasını belirler; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. _l sonek olmayan işlevler geçerli yerel durumu kullanır; **_strtoi64_l** ve **_wcstoi64_l,** bunun yerine geçirilen yerelliği kullanmaları **dışında, _l** soneki olmadan karşılık gelen işlek ile aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Endptr* **NULL**değilse, saramayı durduran karaktere işaretçi *endptr*tarafından işaret edilen konumda depolanır. Dönüşüm gerçekleştirilemezse (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**_strtoi64** *strSource* aşağıdaki formu bir dize işaret bekliyor:

> [*beyazuzay*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **X** }]] [ *&#124; harflerin**basamakları* ]

Bir *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir; *basamaklar* bir veya daha fazla ondalık basamak; *harfler* 'a' ile 'z' (veya 'A' ile 'Z' harfleri) harfleridir.  Bu forma uymayan ilk karakter tazyimi durdurur. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, temeli belirlemek için *strSource* tarafından işaret edilen dizeilk karakterleri kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizli bir sonda olarak yorumlanır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' ise, dize hexadecimal tamsayı olarak yorumlanır. İlk karakter '1' ile '9' arasındaysa, dize ondalık tamsayı olarak yorumlanır. 'a' ile 'z' (veya 'A' ile 'Z' arasında) harfleri 10 ile 35 arasında atanır; yalnızca atanan değerleri *tabandan* daha az olan harflere izin verilir. Taban aralığının dışındaki ilk karakter tazyimeyi durdurur. Örneğin, *taban* 0 ise ve taranan ilk karakter '0' ise, bir sekizli sonda varsayar ve '8' veya '9' karakteri taranmasını durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtoi64**, **_strtoi64_l**|\<stdlib.h>|
|**_wcstoi64**, **_wcstoi64_l**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Dizeden Sayısal Değer Fonksiyonlarına](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
