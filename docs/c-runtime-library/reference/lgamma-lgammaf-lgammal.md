---
title: lgamma, lgammaf, lgammal
description: Lgama, lgamaf ve lgammal; için API başvurusu belirtilen değerin gama işlevinin mutlak logaritmasını belirleyen bir değer.
ms.date: 9/1/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 202250f3575f61fcef1cf29a687b8fdf36e6db33
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555403"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Belirtilen değerin gama işlevinin mutlak logaritmasına ilişkin doğal logaritmayı belirler.

## <a name="syntax"></a>Söz dizimi

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
#define lgammal(X) // Requires C11 or higher

float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*sayı*\
Hesaplama değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*'in gama işlevinin mutlak logaritmasını döndürün.

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* = Nan|NaN|
|*x* = ± 0|+ SONSUZLUK|
|*x*= negatif tamsayı|+ SONSUZLUK|
|± INFINITY|+ SONSUZLUK|
|direk hatası|+ HUGE_VAL, + HUGE_VALF veya + HUGE_VALL|
|taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **lgamma** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **lgama** her zaman alır ve döndürür **`double`** .

\<tgmath.h> `lgamma()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

X bir Rational Number ise, bu işlev (x-1) faktöriyelini logaritmasını döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**lgamma**, **lgamaf**, **lgammal**|\<math.h>|\<cmath>|
|**lgama** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
