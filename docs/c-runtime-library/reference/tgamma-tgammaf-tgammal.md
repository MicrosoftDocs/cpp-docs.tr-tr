---
title: tgamma, tgammaf, tgammal
ms.date: 4/2/2020
api_name:
- tgamma
- tgammaf
- tgammal
- _o_tgamma
- _o_tgammaf
- _o_tgammal
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: d7e27e8b818a16cb0c18f58e2f40c0090dd13ecf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362500"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Belirtilen değerin gama işlevini belirler.

## <a name="syntax"></a>Sözdizimi

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Gama bulmak için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*gama döndürür.

*X'in* büyüklüğü veri türü için çok büyük veya çok küçükse bir aralık hatası oluşabilir. *X* <= 0 ise etki alanı hatası veya aralık hatası oluşabilir.

|Sorun|Dönüş|
|-----------|------------|
|x = ±0|±SONSUZLUK|
|x = negatif toplam|NaN|
|x = -SONSUZLUK|NaN|
|x = +SONSUZLUK|+SONSUZLUK|
|x = NaN|NaN|
|etki alanı hatası|NaN|
|kutup hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|taşma aralığı hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|akış aralığı hatası|yuvarlama sonra doğru değer.|

Hatalar [_matherr](matherr.md)belirtildiği gibi bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** türleri alan ve döndüren aşırı **tgamma** yüklerini arayabilirsiniz. Bir C programında, **tgamma** her zaman alır ve bir **çift**döndürür.

X doğal bir sayı ise, bu fonksiyon faktöriyel (x-1) döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**, **tgammal**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
