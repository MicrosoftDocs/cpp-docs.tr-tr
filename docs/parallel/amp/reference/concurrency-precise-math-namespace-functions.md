---
title: Concurrency::precise_math ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::precise_math::acos
- amp_math/Concurrency::precise_math::acosh
- amp_math/Concurrency::precise_math::acoshf
- amp_math/Concurrency::precise_math::asinf
- amp_math/Concurrency::precise_math::asinh
- amp_math/Concurrency::precise_math::atan
- amp_math/Concurrency::precise_math::atan2
- amp_math/Concurrency::precise_math::atanf
- amp_math/Concurrency::precise_math::atanh
- amp_math/Concurrency::precise_math::cbrt
- amp_math/Concurrency::precise_math::cbrtf
- amp_math/Concurrency::precise_math::ceilf
- amp_math/Concurrency::precise_math::copysign
- amp_math/Concurrency::precise_math::cos
- amp_math/Concurrency::precise_math::cosf
- amp_math/Concurrency::precise_math::coshf
- amp_math/Concurrency::precise_math::cospi
- amp_math/Concurrency::precise_math::erf
- amp_math/Concurrency::precise_math::erfc
- amp_math/Concurrency::precise_math::erfcinv
- amp_math/Concurrency::precise_math::erfcinvf
- amp_math/Concurrency::precise_math::erfinv
- amp_math/Concurrency::precise_math::erfinvf
- amp_math/Concurrency::precise_math::exp10
- amp_math/Concurrency::precise_math::exp10f
- amp_math/Concurrency::precise_math::exp2f
- amp_math/Concurrency::precise_math::expf
- amp_math/Concurrency::precise_math::expm1f
- amp_math/Concurrency::precise_math::fabs
- amp_math/Concurrency::precise_math::floor
- amp_math/Concurrency::precise_math::fdim
- amp_math/Concurrency::precise_math::floorf
- amp_math/Concurrency::precise_math::fmaf
- amp_math/Concurrency::precise_math::fmaxf
- amp_math/Concurrency::precise_math::fmin
- amp_math/Concurrency::precise_math::fmod
- amp_math/Concurrency::precise_math::fmodf
- amp_math/Concurrency::precise_math::frexp
- amp_math/Concurrency::precise_math::frexpf
- amp_math/Concurrency::precise_math::hypotf
- amp_math/Concurrency::precise_math::ilogb
- amp_math/Concurrency::precise_math::isfinite
- amp_math/Concurrency::precise_math::isinf
- amp_math/Concurrency::precise_math::isnormal
- amp_math/Concurrency::precise_math::ldexp
- amp_math/Concurrency::precise_math::lgamma
- amp_math/Concurrency::precise_math::lgammaf
- amp_math/Concurrency::precise_math::log10
- amp_math/Concurrency::precise_math::log10f
- amp_math/Concurrency::precise_math::log1pf
- amp_math/Concurrency::precise_math::log2
- amp_math/Concurrency::precise_math::logb
- amp_math/Concurrency::precise_math::logbf
- amp_math/Concurrency::precise_math::modf
- amp_math/Concurrency::precise_math::modff
- amp_math/Concurrency::precise_math::nanf
- amp_math/Concurrency::precise_math::nearbyint
- amp_math/Concurrency::precise_math::nextafter
- amp_math/Concurrency::precise_math::nextafterf
- amp_math/Concurrency::precise_math::phif
- amp_math/Concurrency::precise_math::pow
- amp_math/Concurrency::precise_math::probit
- amp_math/Concurrency::precise_math::probitf
- amp_math/Concurrency::precise_math::rcbrtf
- amp_math/Concurrency::precise_math::remainder
- amp_math/Concurrency::precise_math::remquo
- amp_math/Concurrency::precise_math::remquof
- amp_math/Concurrency::precise_math::roundf
- amp_math/Concurrency::precise_math::rsqrt
- amp_math/Concurrency::precise_math::scalb
- amp_math/Concurrency::precise_math::scalbf
- amp_math/Concurrency::precise_math::scalbnf
- amp_math/Concurrency::precise_math::signbit
- amp_math/Concurrency::precise_math::sin
- amp_math/Concurrency::precise_math::sincos
- amp_math/Concurrency::precise_math::sinf
- amp_math/Concurrency::precise_math::sinh
- amp_math/Concurrency::precise_math::sinpi
- amp_math/Concurrency::precise_math::sinpif
- amp_math/Concurrency::precise_math::sqrtf
- amp_math/Concurrency::precise_math::tan
- amp_math/Concurrency::precise_math::tanh
- amp_math/Concurrency::precise_math::tanhf
- amp_math/Concurrency::precise_math::tanpif
- amp_math/Concurrency::precise_math::tgamma
- amp_math/Concurrency::precise_math::trunc
- amp_math/Concurrency::precise_math::truncf
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
ms.openlocfilehash: 53ebaf8d9cc1bca53b1fe51464668d6df8e08424
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126958"
---
# <a name="concurrencyprecise_math-namespace-functions"></a>Concurrency::precise_math ad alanı işlevleri

||||
|-|-|-|
|[acos](#acos)|[acosf](#acosf)|[acosh](#acosh)|
|[acoshf](#acoshf)|[Asin](#asin)|[asinf](#asinf)|
|[ASİNH](#asinh)|[asinhf](#asinhf)|[atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[ATANH](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|
|[cbrtf](#cbrtf)|[Ceil](#ceil)|[ceilf](#ceilf)|
|[copysign](#copysign)|[copysignf](#copysignf)|[cos](#cos)|
|[cosf](#cosf)|[Cosh](#cosh)|[coshf](#coshf)|
|[cospi](#cospi)|[cospif](#cospif)|[işlevi](#erf)|
|[erfc](#erfc)|[erfcf](#erfcf)|[erfcinv](#erfcinv)|
|[erfcinvf](#erfcinvf)|[erff](#erff)|[erfinv](#erfinv)|
|[erfinvf](#erfinvf)|[exp](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[fabs](#fabs)|[fabsf](#fabsf)|[sını](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[FMA](#fma)|[fmaf](#fmaf)|
[Fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[FMOD](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[frexpf](#frexpf)|[hypot](#hypot)|[hypotf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[isFinite](#isfinite)|
|[isinf](#isinf)|[isNaN](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[açmasını](#log)|[log10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[nBir](#nan)|[nanf](#nanf)|
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[nextafter](#nextafter)|
|[nextafterf](#nextafterf)|[Phi](#phi)|[phif](#phif)|
|[POW](#pow)|[powf](#powf)|[probit](#probit)|
|[probitf](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[geri kalanında](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[gidiş](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[scalb](#scalb)|
|[scalbf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[signbitf](#signbitf)|[sin](#sin)|
|[sincos](#sincos)|[sincosf](#sincosf)|[sinf](#sinf)|
|[sinh](#sinh)|[sinhf](#sinhf)|[sinpi](#sinpi)|
|[sinpif](#sinpif)|[k](#sqrt)|[sqrtf](#sqrtf)|
|[Başlangıçtan](#tan)|[tanf](#tanf)|[tanh](#tanh)|
|[tanhf](#tanhf)|[tanpi](#tanpi)|[tanpif](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[TRUNC](#trunc)|
|[truncf](#truncf)|

## <a name="acos"></a>acos

Bağımsız değişkenin arkkosinüsünü hesaplar

```cpp
inline float acos(float _X) restrict(amp);

inline double acos(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin Arkkosinüs değerini döndürür

## <a name="acosf"></a>acosf

Bağımsız değişkenin arkkosinüsünü hesaplar

```cpp
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin Arkkosinüs değerini döndürür

## <a name="acosh"></a>acosh

Bağımsız değişkenin ters hiperbolik kosinüsünü hesaplar

```cpp
inline float acosh(float _X) restrict(amp);

inline double acosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik kosinüs değerini döndürür

## <a name="acoshf"></a>acoshf

Bağımsız değişkenin ters hiperbolik kosinüsünü hesaplar

```cpp
inline float acoshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik kosinüs değerini döndürür

## <a name="asin"></a>Asin

Bağımsız değişkenin arksinüsünü hesaplar

```cpp
inline float asin(float _X) restrict(amp);

inline double asin(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arksinüs değerini döndürür

## <a name="asinf"></a>asinf

Bağımsız değişkenin arksinüsünü hesaplar

```cpp
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arksinüs değerini döndürür

## <a name="asinh"></a>ASİNH

Bağımsız değişkenin ters hiperbolik sinüsünü hesaplar

```cpp
inline float asinh(float _X) restrict(amp);

inline double asinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik sinüs değerini döndürür

## <a name="asinhf"></a>asinhf

Bağımsız değişkenin ters hiperbolik sinüsünü hesaplar

```cpp
inline float asinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik sinüs değerini döndürür

## <a name="atan"></a>atan

Bağımsız değişkenin arktanjantını hesaplar

```cpp
inline float atan(float _X) restrict(amp);

inline double atan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arktanjant değerini döndürür

## <a name="atan2"></a>atan2

_Y/_X arktanjantını hesaplar

```cpp
inline float atan2(
    float _Y,
    float _X) restrict(amp);

inline double atan2(
    double _Y,
    double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Y*<br/>
Kayan nokta değeri

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y/_X arktanjant değerini döndürür

## <a name="atan2f"></a>atan2f

_Y/_X arktanjantını hesaplar

```cpp
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Y*<br/>
Kayan nokta değeri

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y/_X arktanjant değerini döndürür

## <a name="atanf"></a>atanf

Bağımsız değişkenin arktanjantını hesaplar

```cpp
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arktanjant değerini döndürür

## <a name="atanh"></a>ATANH

Bağımsız değişkenin ters hiperbolik tanjantını hesaplar

```cpp
inline float atanh(float _X) restrict(amp);

inline double atanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik tanjant değerini döndürür

## <a name="atanhf"></a>atanhf

Bağımsız değişkenin ters hiperbolik tanjantını hesaplar

```cpp
inline float atanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik tanjant değerini döndürür

## <a name="cbrt"></a>cbrt

Bağımsız değişkenin gerçek Küp kökünü hesaplar

```cpp
inline float cbrt(float _X) restrict(amp);

inline double cbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin gerçek Küp kökünü döndürür

## <a name="cbrtf"></a>cbrtf

Bağımsız değişkenin gerçek Küp kökünü hesaplar

```cpp
inline float cbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin gerçek Küp kökünü döndürür

## <a name="ceil"></a>Ceil

Bağımsız değişkenin tavan sayısını hesaplar

```cpp
inline float ceil(float _X) restrict(amp);

inline double ceil(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tavan sayısını döndürür

## <a name="ceilf"></a>ceilf

Bağımsız değişkenin tavan sayısını hesaplar

```cpp
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tavan sayısını döndürür

## <a name="copysign"></a>copysign

_X büyüklüğü ve _Y işareti ile bir değer üretir

```cpp
inline float copysign(
    float _X,
    float _Y) restrict(amp);

inline double copysign(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X büyüklüğü ve _Y işareti olan bir değer döndürür

## <a name="copysignf"></a>copysignf

_X büyüklüğü ve _Y işareti ile bir değer üretir

```cpp
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X büyüklüğü ve _Y işareti olan bir değer döndürür

## <a name="cos"></a>cos

Bağımsız değişkenin kosinüsünü hesaplar

```cpp
inline float cos(float _X) restrict(amp);

inline double cos(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kosinüs değerini döndürür

## <a name="cosf"></a>cosf

Bağımsız değişkenin kosinüsünü hesaplar

```cpp
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kosinüs değerini döndürür

## <a name="cosh"></a>Cosh

Bağımsız değişkenin hiperbolik kosinüs değerini hesaplar

```cpp
inline float cosh(float _X) restrict(amp);

inline double cosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik kosinüs değerini döndürür

## <a name="coshf"></a>coshf

Bağımsız değişkenin hiperbolik kosinüs değerini hesaplar

```cpp
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik kosinüs değerini döndürür

## <a name="cospi"></a>cospi

PI \* _X kosinüs değerini hesaplar

```cpp
inline float cospi(float _X) restrict(amp);

inline double cospi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

PI \* _X kosinüs değerini döndürür

## <a name="cospif"></a>cospif

PI \* _X kosinüs değerini hesaplar

```cpp
inline float cospif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

PI \* _X kosinüs değerini döndürür

## <a name="erf"></a>işlevi

_X hata işlevini hesaplar

```cpp
inline float erf(float _X) restrict(amp);

inline double erf(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X hata işlevini döndürür

## <a name="erfc"></a>erfc

_X tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfc(float _X) restrict(amp);

inline double erfc(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X tamamlayıcı hata işlevini döndürür

## <a name="erfcf"></a>erfcf

_X tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfcf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X tamamlayıcı hata işlevini döndürür

## <a name="erfcinv"></a>erfcinv

_X ters tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfcinv(float _X) restrict(amp);

inline double erfcinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters tamamlayıcı hata işlevini döndürür

## <a name="erfcinvf"></a>erfcinvf

_X ters tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfcinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters tamamlayıcı hata işlevini döndürür

## <a name="erff"></a>erff

_X hata işlevini hesaplar

```cpp
inline float erff(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X hata işlevini döndürür

## <a name="erfinv"></a>erfinv

_X ters hata işlevini hesaplar

```cpp
inline float erfinv(float _X) restrict(amp);

inline double erfinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters hata işlevini döndürür

## <a name="erfinvf"></a>erfinvf

_X ters hata işlevini hesaplar

```cpp
inline float erfinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters hata işlevini döndürür

## <a name="exp10"></a>exp10

Bağımsız değişkenin 10 tabanında üssünü hesaplar

```cpp
inline float exp10(float _X) restrict(amp);

inline double exp10(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 10 tabanında üstel değerini döndürür

## <a name="exp10f"></a>exp10f

Bağımsız değişkenin 10 tabanında üssünü hesaplar

```cpp
inline float exp10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 10 tabanında üstel değerini döndürür

## <a name="expm1"></a>expm1

Bağımsız değişkenin e tabanında üssü eksi 1 hesaplar.

```cpp
inline float expm1(float exponent) restrict(amp);

inline double expm1(double exponent) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*s*<br/>
`e`<sup>n</sup>, `e` doğal logaritmanın tabanı olan matematiksel ifadenin üstel terimi *n* .

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin e tabanında üssü eksi 1 döndürür.

## <a name="expm1f"></a>expm1f

Bağımsız değişkenin e tabanında üssü eksi 1 hesaplar.

```cpp
inline float expm1f(float exponent) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*s*<br/>
`e`<sup>n</sup>, `e` doğal logaritmanın tabanı olan matematiksel ifadenin üstel terimi *n* .

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin e tabanında üssü eksi 1 döndürür.

## <a name="exp"></a>exp

Bağımsız değişkenin taban-e üssünü hesaplar

```cpp
inline float exp(float _X) restrict(amp);

inline double exp(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-e üssünü döndürür

## <a name="expf"></a>expf

Bağımsız değişkenin taban-e üssünü hesaplar

```cpp
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-e üssünü döndürür

## <a name="exp2"></a>exp2

Bağımsız değişkenin taban 2 üssünü hesaplar

```cpp
inline float exp2(float _X) restrict(amp);

inline double exp2(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban 2 üssel değerini döndürür

## <a name="exp2f"></a>exp2f

Bağımsız değişkenin taban 2 üssünü hesaplar

```cpp
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban 2 üssel değerini döndürür

## <a name="fabs"></a>fabs

Bağımsız değişkenin mutlak değerini döndürür

```cpp
inline float fabs(float _X) restrict(amp);

inline double fabs(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin mutlak değerini döndürür

## <a name="fabsf"></a>fabsf

Bağımsız değişkenin mutlak değerini döndürür

```cpp
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin mutlak değerini döndürür

## <a name="fdim"></a>fdim

Bağımsız değişkenler arasındaki pozitif farkı hesaplar.

```cpp
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri *_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Y daha büyükse _X ve _Y arasındaki fark Aksi halde, + 0.

## <a name="fdimf"></a>fdimf

Bağımsız değişkenler arasındaki pozitif farkı hesaplar.

```cpp
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri *_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Y daha büyükse _X ve _Y arasındaki fark Aksi halde, + 0.

## <a name="floor"></a>sını

Bağımsız değişkenin katsını hesaplar

```cpp
inline float floor(float _X) restrict(amp);

inline double floor(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin katsını döndürür

## <a name="floorf"></a>floorf

Bağımsız değişkenin katsını hesaplar

```cpp
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin katsını döndürür

## <a name="a-namefma-fma"></a><a name="fma"> FMA

Birinci ve ikinci belirtilen bağımsız değişkenlerin çarpımını hesaplar ve ardından üçüncü belirtilen bağımsız değişkeni sonuca ekler; Tüm hesaplama tek bir işlem olarak gerçekleştirilir.

```cpp
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İlk kayan nokta bağımsız değişkeni.
*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.
*_Z*<br/>
Üçüncü kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

İfadenin sonucu (_X \* _Y) + _Z. Tüm hesaplama tek bir işlem olarak gerçekleştirilir; diğer bir deyişle, alt ifadeler sonsuz duyarlığa göre hesaplanır ve yalnızca nihai sonuç yuvarlanır.

## <a name="fmaf"></a>fmaf

Birinci ve ikinci belirtilen bağımsız değişkenlerin çarpımını hesaplar ve ardından üçüncü belirtilen bağımsız değişkeni sonuca ekler; Tüm hesaplama tek bir işlem olarak gerçekleştirilir.

```cpp
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İlk kayan nokta bağımsız değişkeni.
*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.
*_Z*<br/>
Üçüncü kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

İfadenin sonucu (_X \* _Y) + _Z. Tüm hesaplama tek bir işlem olarak gerçekleştirilir; diğer bir deyişle, alt ifadeler sonsuz duyarlığa göre hesaplanır ve yalnızca nihai sonuç yuvarlanır.

## <a name="fmax"></a>Fmax

Bağımsız değişkenlerin en büyük sayısal değerini belirleme

```cpp
inline float fmax(
    float _X,
    float _Y) restrict(amp);

inline double fmax(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en büyük sayısal değerini döndürür

## <a name="fmaxf"></a>fmaxf

Bağımsız değişkenlerin en büyük sayısal değerini belirleme

```cpp
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en büyük sayısal değerini döndürür

## <a name="fmin"></a>fmin

Bağımsız değişkenlerin en küçük sayısal değerini belirleme

```cpp
inline float fmin(
    float _X,
    float _Y) restrict(amp);

inline double fmin(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en küçük sayısal değerini döndürür

## <a name="fminf"></a>fminf

Bağımsız değişkenlerin en küçük sayısal değerini belirleme

```cpp
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en küçük sayısal değerini döndürür

## <a name="fmod"></a>fmod Işlevi (C++ amp)

Belirtilen ilk bağımsız değişkenin kalan kısmını belirtilen ikinci bağımsız değişken ile ayırarak hesaplar.

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);

inline double fmod(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

`_X` kalanı `_Y`bölünür; diğer bir deyişle, `_X`değeri  - `_Y`*n*, burada *n* , `_X` - büyüklüğü `_Y`büyüklüğünün daha *küçük olduğu için* tam bir tamsayıdır.`_Y`

## <a name="fmodf"></a>fmodf

Belirtilen ilk bağımsız değişkenin kalan kısmını belirtilen ikinci bağımsız değişken ile ayırarak hesaplar.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

`_X` kalanı `_Y`bölünür; diğer bir deyişle, `_X`değeri  - `_Y`*n*, burada *n* , `_X` - büyüklüğü `_Y`büyüklüğünün daha *küçük olduğu için* tam bir tamsayıdır.`_Y`

## <a name="fpclassify"></a>fpclassify

Bağımsız değişken değerini NaN, sonsuz, normal, subnormal, sıfır olarak sınıflandırır

```cpp
inline int fpclassify(float _X) restrict(amp);

inline int fpclassify(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin değerine uygun olan sınıflandırma makrosunun sayı değerini döndürür.

## <a name="frexp"></a>frexp

_X Mantis ve üstürünü alır

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);

inline double frexp(
    double _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Exp*<br/>
Kayan nokta değerindeki _X tamsayı üssünü döndürür

### <a name="return-value"></a>Dönüş Değeri

Mantis _X döndürür

## <a name="frexpf"></a>frexpf

_X Mantis ve üstürünü alır

```cpp
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Exp*<br/>
Kayan nokta değerindeki _X tamsayı üssünü döndürür

### <a name="return-value"></a>Dönüş Değeri

Mantis _X döndürür

## <a name="hypot"></a>hypot

_X ve _Y karelerinin toplamının kare kökünü hesaplar

```cpp
inline float hypot(
    float _X,
    float _Y) restrict(amp);

inline double hypot(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ve _Y karelerinin toplamının kare kökünü döndürür

## <a name="hypotf"></a>hypotf

_X ve _Y karelerinin toplamının kare kökünü hesaplar

```cpp
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ve _Y karelerinin toplamının kare kökünü döndürür

## <a name="ilogb"></a>ilogb

_X 'nin üssünü imzalı bir int değeri olarak Ayıkla

```cpp
inline int ilogb(float _X) restrict(amp);

inline int ilogb(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X 'nin üssünü, imzalı bir int değeri olarak döndürür

## <a name="ilogbf"></a>ilogbf

_X 'nin üssünü imzalı bir int değeri olarak Ayıkla

```cpp
inline int ilogbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X 'nin üssünü, imzalı bir int değeri olarak döndürür

## <a name="isfinite"></a>isFinite

Bağımsız değişkenin sonlu bir değere sahip olup olmadığını belirler

```cpp
inline int isfinite(float _X) restrict(amp);

inline int isfinite(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yalnızca bağımsız değişkenin sınırlı bir değeri varsa sıfır olmayan bir değer döndürür

## <a name="isinf"></a>isinf

Bağımsız değişkenin bir sonsuzluk olup olmadığını belirler

```cpp
inline int isinf(float _X) restrict(amp);

inline int isinf(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değer döndürür ve yalnızca bağımsız değişken sonsuz bir değere sahipse

## <a name="isnan"></a>isNaN

Bağımsız değişkenin bir NaN olup olmadığını belirler

```cpp
inline int isnan(float _X) restrict(amp);

inline int isnan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değer döndürür ve yalnızca bağımsız değişkenin bir NaN değeri varsa

## <a name="isnormal"></a>isnormal

Bağımsız değişkenin normal olup olmadığını belirler

```cpp
inline int isnormal(float _X) restrict(amp);

inline int isnormal(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yalnızca bağımsız değişkenin normal bir değeri varsa, sıfır dışında bir değer döndürür

## <a name="ldexp"></a>ldexp

Belirtilen Mantis ve üs öğesinden gerçek bir sayı hesaplar.

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);

inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, Mantis

*_Exp*<br/>
Tamsayı değeri, üs

### <a name="return-value"></a>Dönüş Değeri

_X \* 2 ^ _Exp döndürür

## <a name="ldexpf"></a>ldexpf

Belirtilen Mantis ve üs öğesinden gerçek bir sayı hesaplar.

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, Mantis

*_Exp*<br/>
Tamsayı değeri, üs

### <a name="return-value"></a>Dönüş Değeri

_X \* 2 ^ _Exp döndürür

## <a name="lgamma"></a>lgamma

Bağımsız değişkenin tam Gamma değerinin doğal logaritmasını hesaplar

```cpp
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);

inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Sign*<br/>
İşareti döndürür

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tam gama değeri için doğal logaritmayı döndürür

## <a name="lgammaf"></a>lgammaf

Bağımsız değişkenin tam Gamma değerinin doğal logaritmasını hesaplar

```cpp
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Sign*<br/>
İşareti döndürür

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tam gama değeri için doğal logaritmayı döndürür

## <a name="log"></a>açmasını

Bağımsız değişkenin taban-e logaritmasını hesaplar

```cpp
inline float log(float _X) restrict(amp);

inline double log(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-e logaritmasını döndürür

## <a name="log10"></a>log10

Bağımsız değişkenin 10 tabanında logaritmasını hesaplar

```cpp
inline float log10(float _X) restrict(amp);

inline double log10(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 10 tabanında logaritmasını döndürür

## <a name="log10f"></a>log10f

Bağımsız değişkenin 10 tabanında logaritmasını hesaplar

```cpp
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 10 tabanında logaritmasını döndürür

## <a name="log1p"></a>log1p

1 ve bağımsız değişkenin taban-e logaritmasını hesaplar

```cpp
inline float log1p(float _X) restrict(amp);

inline double log1p(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

1 ve bağımsız değişkenin taban-e logaritmasını döndürür

## <a name="log1pf"></a>log1pf

1 ve bağımsız değişkenin taban-e logaritmasını hesaplar

```cpp
inline float log1pf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

1 ve bağımsız değişkenin taban-e logaritmasını döndürür

## <a name="log2"></a>log2

Bağımsız değişkenin 2 tabanında logaritmasını hesaplar

```cpp
inline float log2(float _X) restrict(amp);

inline double log2(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 10 tabanında logaritmasını döndürür

## <a name="log2f"></a>log2f

Bağımsız değişkenin 2 tabanında logaritmasını hesaplar

```cpp
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 10 tabanında logaritmasını döndürür

## <a name="logb"></a>logb

Kayan nokta biçiminde işaretli bir tamsayı değeri olarak _X üssünü ayıklar

```cpp
inline float logb(float _X) restrict(amp);

inline double logb(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X 'nin imzalı üssünü döndürür

## <a name="logbf"></a>logbf

Kayan nokta biçiminde işaretli bir tamsayı değeri olarak _X üssünü ayıklar

```cpp
inline float logbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X 'nin imzalı üssünü döndürür

## <a name="logf"></a>logf

Bağımsız değişkenin taban-e logaritmasını hesaplar

```cpp
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-e logaritmasını döndürür

## <a name="modf"></a>modf

Belirtilen bağımsız değişkeni kesirli ve tamsayı bölümlerine böler.

```cpp
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);

inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Iptr*<br/>
dışı `_X`tamsayı kısmı, kayan nokta değeri olarak.

### <a name="return-value"></a>Dönüş Değeri

`_X`işaretli kesirli kısmı.

## <a name="modff"></a>modff

Belirtilen bağımsız değişkeni kesirli ve tamsayı bölümlerine böler.

```cpp
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Iptr*<br/>
`_X`tamsayı kısmı, kayan nokta değeri olarak.

### <a name="return-value"></a>Dönüş Değeri

`_X`işaretli kesirli kısmını döndürür.

## <a name="nan"></a>nBir

Sessiz NaN döndürür

```cpp
inline double nan(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Varsa, içerik _X belirtilen içeriğe sahip bir sessiz NaN döndürür

## <a name="nanf"></a>nanf

Sessiz NaN döndürür

```cpp
inline float nanf(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Varsa, içerik _X belirtilen içeriğe sahip bir sessiz NaN döndürür

## <a name="nearbyint"></a>nearbyint

Bağımsız değişkenini, geçerli yuvarlama yönünü kullanarak kayan nokta biçimindeki bir tamsayı değerine yuvarlar.

```cpp
inline float nearbyint(float _X) restrict(amp);

inline double nearbyint(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yuvarlatılmış tamsayı değerini döndürür.

## <a name="nearbyintf"></a>nearbyintf

Bağımsız değişkenini, geçerli yuvarlama yönünü kullanarak kayan nokta biçimindeki bir tamsayı değerine yuvarlar.

```cpp
inline float nearbyintf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yuvarlatılmış tamsayı değerini döndürür.

## <a name="nextafter"></a>nextafter

_Y yönündeki _X sonra işlevin türünde bir sonraki gösterilemeyen değeri belirleme

```cpp
inline float nextafter(
    float _X,
    float _Y) restrict(amp);

inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y yönündeki _X sonra işlevin türünde bir sonraki gösterilemeyen değeri döndürür

## <a name="nextafterf"></a>nextafterf

_Y yönündeki _X sonra işlevin türünde bir sonraki gösterilemeyen değeri belirleme

```cpp
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y yönündeki _X sonra işlevin türünde bir sonraki gösterilemeyen değeri döndürür

## <a name="phi"></a>Phi

Bağımsız değişkenin kümülatif dağıtım işlevini döndürür

```cpp
inline float phi(float _X) restrict(amp);

inline double phi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kümülatif dağıtım işlevini döndürür

## <a name="phif"></a>phif

Bağımsız değişkenin kümülatif dağıtım işlevini döndürür

```cpp
inline float phif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kümülatif dağıtım işlevini döndürür

## <a name="pow"></a>POW

_Y kuvvetine _X hesaplar

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);

inline double pow(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, taban

*_Y*<br/>
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

## <a name="powf"></a>powf

_Y kuvvetine _X hesaplar

```cpp
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, taban

*_Y*<br/>
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

## <a name="probit"></a>probit

Bağımsız değişkenin ters kümülatif dağıtım işlevini döndürür

```cpp
inline float probit(float _X) restrict(amp);

inline double probit(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters kümülatif dağıtım işlevini döndürür

## <a name="probitf"></a>probitf

Bağımsız değişkenin ters kümülatif dağıtım işlevini döndürür

```cpp
inline float probitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters kümülatif dağıtım işlevini döndürür

## <a name="rcbrt"></a>rcbrt

Bağımsız değişkenin küp kökünün tersini döndürür

```cpp
inline float rcbrt(float _X) restrict(amp);

inline double rcbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin küp kökünün tersini döndürür

## <a name="rcbrtf"></a>rcbrtf

Bağımsız değişkenin küp kökünün tersini döndürür

```cpp
inline float rcbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin küp kökünün tersini döndürür

## <a name="remainder"></a>geri kalanında

Kalanı hesaplar: _X REM _Y

```cpp
inline float remainder(
    float _X,
    float _Y) restrict(amp);

inline double remainder(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X REM _Y döndürür

## <a name="remainderf"></a>remainderf

Kalanı hesaplar: _X REM _Y

```cpp
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X REM _Y döndürür

## <a name="remquo"></a>remquo

Belirtilen ilk bağımsız değişkenin kalan kısmını belirtilen ikinci bağımsız değişken ile ayırarak hesaplar. Ayrıca, belirtilen ilk bağımsız değişkenin mantisinin bölümünü, ikinci belirtilen bağımsız değişkenin mantisinin bölünmesiyle hesaplar ve üçüncü bağımsız değişkende belirtilen konumu kullanarak bölümü döndürür.

```cpp
inline float remquo(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);

inline double remquo(
    double _X,
    double _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

*_Quo*<br/>
dışı `_X` kesirli bitlerinin bölümünü döndürmek için kullanılan bir tamsayı adresi, `_Y`kesirli bitleriyle bölünür.

### <a name="return-value"></a>Dönüş Değeri

`_Y`bölünen `_X` kalanı döndürür.

## <a name="remquof"></a>remquof

Belirtilen ilk bağımsız değişkenin kalan kısmını belirtilen ikinci bağımsız değişken ile ayırarak hesaplar. Ayrıca, belirtilen ilk bağımsız değişkenin mantisinin bölümünü, ikinci belirtilen bağımsız değişkenin mantisinin bölünmesiyle hesaplar ve üçüncü bağımsız değişkende belirtilen konumu kullanarak bölümü döndürür.

```cpp
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

*_Quo*<br/>
dışı `_X` kesirli bitlerinin bölümünü döndürmek için kullanılan bir tamsayı adresi, `_Y`kesirli bitleriyle bölünür.

### <a name="return-value"></a>Dönüş Değeri

`_Y`bölünen `_X` kalanı döndürür.

## <a name="round"></a>gidiş

_X en yakın tamsayıya yuvarlar

```cpp
inline float round(float _X) restrict(amp);

inline double round(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

En yakın _X tamsayı döndürür

## <a name="roundf"></a>roundf

_X en yakın tamsayıya yuvarlar

```cpp
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

En yakın _X tamsayı döndürür

## <a name="rsqrt"></a>rsqrt

Bağımsız değişkenin karekökünü döndürür

```cpp
inline float rsqrt(float _X) restrict(amp);

inline double rsqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin karekökünü döndürür

## <a name="rsqrtf"></a>rsqrtf

Bağımsız değişkenin karekökünü döndürür

```cpp
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin karekökünü döndürür

## <a name="scalb"></a>scalb

_X FLT_RADIX güç _Y çarpar

```cpp
inline float scalb(
    float _X,
    float _Y) restrict(amp);

inline double scalb(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* döndürür (FLT_RADIX ^ _Y)

## <a name="scalbf"></a>scalbf

_X FLT_RADIX güç _Y çarpar

```cpp
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* döndürür (FLT_RADIX ^ _Y)

## <a name="scalbn"></a>scalbn

_X FLT_RADIX güç _Y çarpar

```cpp
inline float scalbn(
    float _X,
    int _Y) restrict(amp);

inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* döndürür (FLT_RADIX ^ _Y)

## <a name="scalbnf"></a>scalbnf

_X FLT_RADIX güç _Y çarpar

```cpp
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* döndürür (FLT_RADIX ^ _Y)

## <a name="signbit"></a>signbit

_X işaretinin negatif olup olmadığını belirler

```cpp
inline int signbit(float _X) restrict(amp);

inline int signbit(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değer döndürür ve yalnızca _X işareti negatifse

## <a name="signbitf"></a>signbitf

_X işaretinin negatif olup olmadığını belirler

```cpp
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değer döndürür ve yalnızca _X işareti negatifse

## <a name="sin"></a>sin

Bağımsız değişkenin sinüs değerini hesaplar

```cpp
inline float sin(float _X) restrict(amp);

inline double sin(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin sinüs değerini döndürür

## <a name="sinf"></a>sinf

Bağımsız değişkenin sinüs değerini hesaplar

```cpp
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin sinüs değerini döndürür

## <a name="sincos"></a>sincos

_X sinüsünü ve kosinüs değerini hesaplar

```cpp
inline void sincos(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);

inline void sincos(
    double _X,
    _Out_ double* _S,
    _Out_ double* _C) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_S*<br/>
_X sinüs değerini döndürür

*_C*<br/>
_X kosinüs değerini döndürür

## <a name="sincosf"></a>sincosf

_X sinüsünü ve kosinüs değerini hesaplar

```cpp
inline void sincosf(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_S*<br/>
_X sinüs değerini döndürür

*_C*<br/>
_X kosinüs değerini döndürür

## <a name="sinh"></a>sinh

Bağımsız değişkenin hiperbolik sinüs değerini hesaplar

```cpp
inline float sinh(float _X) restrict(amp);

inline double sinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik sinüs değerini döndürür

## <a name="sinhf"></a>sinhf

Bağımsız değişkenin hiperbolik sinüs değerini hesaplar

```cpp
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik sinüs değerini döndürür

## <a name="sinpi"></a>sinpi

PI \* _X sinüs değerini hesaplar

```cpp
inline float sinpi(float _X) restrict(amp);

inline double sinpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Pi \* 'nin sinüs değerini döndürür _X

## <a name="sinpif"></a>sinpif

PI \* _X sinüs değerini hesaplar

```cpp
inline float sinpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Pi \* 'nin sinüs değerini döndürür _X

## <a name="sqrt"></a>k

Bağımsız değişkenin Squre kökünü hesaplar

```cpp
inline float sqrt(float _X) restrict(amp);

inline double sqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin Squre kökünü döndürür

## <a name="sqrtf"></a>sqrtf

Bağımsız değişkenin Squre kökünü hesaplar

```cpp
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin Squre kökünü döndürür

## <a name="tan"></a>Başlangıçtan

Bağımsız değişkenin tanjant değerini hesaplar

```cpp
inline float tan(float _X) restrict(amp);

inline double tan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tanjant değerini döndürür

## <a name="tanf"></a>tanf

Bağımsız değişkenin tanjant değerini hesaplar

```cpp
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tanjant değerini döndürür

## <a name="tanh"></a>tanh

Bağımsız değişkenin hiperbolik tanjant değerini hesaplar

```cpp
inline float tanh(float _X) restrict(amp);

inline double tanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik tanjant değerini döndürür

## <a name="tanhf"></a>tanhf

Bağımsız değişkenin hiperbolik tanjant değerini hesaplar

```cpp
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik tanjant değerini döndürür

## <a name="tanpi"></a>tanpi

PI \* _X tanjant değerini hesaplar

```cpp
inline float tanpi(float _X) restrict(amp);

inline double tanpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

PI \* _X tanjant değerini döndürür

## <a name="tanpif"></a>tanpif

PI \* _X tanjant değerini hesaplar

```cpp
inline float tanpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

PI \* _X tanjant değerini döndürür

## <a name="tgamma"></a>tgamma

_X gama işlevini hesaplar

```cpp
inline float tgamma(float _X) restrict(amp);

inline double tgamma(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X gama işlevinin sonucunu döndürür

## <a name="tgammaf"></a>tgammaf

_X gama işlevini hesaplar

```cpp
inline float tgammaf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X gama işlevinin sonucunu döndürür

## <a name="trunc"></a>TRUNC

Bağımsız değişkeni tamsayı bileşene kırpar

```cpp
inline float trunc(float _X) restrict(amp);

inline double trunc(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tamsayı bileşenini döndürür

## <a name="truncf"></a>truncf

Bağımsız değişkeni tamsayı bileşene kırpar

```cpp
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tamsayı bileşenini döndürür

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)
