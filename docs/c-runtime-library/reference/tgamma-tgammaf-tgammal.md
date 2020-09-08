---
title: tgamma, tgammaf, tgammal
description: Tgama, tgamaf ve tgammal; için API başvurusu belirtilen değerin gama işlevini belirleyen.
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b49020ca0697e920dccf188df4ad024820966571
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555182"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Belirtilen değerin gama işlevini belirler.

## <a name="syntax"></a>Söz dizimi

```C
double tgamma(
   double x
);

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

#define tgamma(X) // Requires C11 or higher

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only
```

### <a name="parameters"></a>Parametreler

*sayı*\
Gamasını bulmak için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *x*'in gamasını döndürür.

*X* büyüklüğü çok büyükse veya veri türü için çok küçük olduğunda Aralık hatası oluşabilir. *X* <= 0 olduğunda bir etki alanı hatası veya Aralık hatası oluşabilir.

|Sorun|Döndürülmesini|
|-----------|------------|
|x = ± 0|± INFINITY|
|x = negatif tamsayı|NaN|
|x =-sonsuzluk|NaN|
|x = + sonsuzluk|+ SONSUZLUK|
|x = NaN|NaN|
|etki alanı hatası|NaN|
|direk hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|
|taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|
|yetersiz yer aralığı hatası|yuvarlama sonrasında doğru değer.|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türündeki **tgama** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **tgama** her zaman alır ve döndürür **`double`** .

\<tgmath.h> `tgamma()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

X doğal bir sayı ise, bu işlev (x-1) faktöriyelini döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**tgama**, **tgamaf**,  **tgammal**|\<math.h>|\<cmath>|
|**tgama** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
