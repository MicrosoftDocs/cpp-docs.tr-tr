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
ms.openlocfilehash: ee6ab2313fbdc288ebba1b3fdacf192b7b578eb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321839"
---
# <a name="concurrencyprecise_math-namespace-functions"></a>Concurrency::precise_math ad alanı işlevleri

||||
|-|-|-|
|[Acos](#acos)|[acosf](#acosf)|[acosh](#acosh)|
|[acoşf](#acoshf)|[Asin](#asin)|[asinf](#asinf)|
|[asinh](#asinh)|[asinhf](#asinhf)|[atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[atanh](#atanh)|[atanhf](#atanhf)|[Tcmb](#cbrt)|
|[cbrtf](#cbrtf)|[Ceil](#ceil)|[ceilf](#ceilf)|
|[copysign](#copysign)|[copysignf](#copysignf)|[Çünkü](#cos)|
|[cosf](#cosf)|[Cosh](#cosh)|[coşf](#coshf)|
|[cospi](#cospi)|[cospif](#cospif)|[Erf](#erf)|
|[erfc](#erfc)|[erfcf](#erfcf)|[erfcinv](#erfcinv)|
|[erfcinvf](#erfcinvf)|[erff](#erff)|[erfinv](#erfinv)|
|[erfinvf](#erfinvf)|[Exp](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[Faruk](#fabs)|[fabsf](#fabsf)|[Kat](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[Fma](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[Fmod](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[frexpf](#frexpf)|[hipot](#hypot)|[hipotf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[Isfinite](#isfinite)|
|[isinf](#isinf)|[ısnan](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[Günlük](#log)|[log10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[Nan](#nan)|[nanf](#nanf)|
|[yakın](#nearbyint)|[nearbyintf](#nearbyintf)|[sonraki sonra](#nextafter)|
|[nextafterf](#nextafterf)|[Phi](#phi)|[phif](#phif)|
|[Pow](#pow)|[powf](#powf)|[probit](#probit)|
|[probitf](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[Geri kalanı](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[Yuvarlak](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[scalb](#scalb)|
|[scalbf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[signbitf](#signbitf)|[Günah](#sin)|
|[sincos](#sincos)|[sincosf](#sincosf)|[sinf](#sinf)|
|[Sinh](#sinh)|[sinhf](#sinhf)|[sinpi](#sinpi)|
|[sinpif](#sinpif)|[Karekök](#sqrt)|[sqrtf](#sqrtf)|
|[tan](#tan)|[tanf](#tanf)|[Tanh](#tanh)|
|[tanhf](#tanhf)|[tanpi](#tanpi)|[tanpif](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[Trunc](#trunc)|
|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>Acos

Bağımsız değişkenin arccosine hesaplar

```cpp
inline float acos(float _X) restrict(amp);

inline double acos(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arccosine değerini verir

## <a name="acosf"></a><a name="acosf"></a>acosf

Bağımsız değişkenin arccosine hesaplar

```cpp
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arccosine değerini verir

## <a name="acosh"></a><a name="acosh"></a>acosh

Bağımsız değişkenin ters hiperbolik kosinüshesaplar

```cpp
inline float acosh(float _X) restrict(amp);

inline double acosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik kosinüs değerini verir

## <a name="acoshf"></a><a name="acoshf"></a>acoşf

Bağımsız değişkenin ters hiperbolik kosinüshesaplar

```cpp
inline float acoshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik kosinüs değerini verir

## <a name="asin"></a><a name="asin"></a>Asin

Bağımsız değişkenin arcsine hesaplar

```cpp
inline float asin(float _X) restrict(amp);

inline double asin(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arcsine değerini verir

## <a name="asinf"></a><a name="asinf"></a>asinf

Bağımsız değişkenin arcsine hesaplar

```cpp
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arcsine değerini verir

## <a name="asinh"></a><a name="asinh"></a>asinh

Bağımsız değişkenin ters hiperbolik sinüshesaplar

```cpp
inline float asinh(float _X) restrict(amp);

inline double asinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik sinüs değerini verir

## <a name="asinhf"></a><a name="asinhf"></a>asinhf

Bağımsız değişkenin ters hiperbolik sinüshesaplar

```cpp
inline float asinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik sinüs değerini verir

## <a name="atan"></a><a name="atan"></a>atan

Bağımsız değişkenin arctantını hesaplar

```cpp
inline float atan(float _X) restrict(amp);

inline double atan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arctanjant değerini verir

## <a name="atan2"></a><a name="atan2"></a>atan2

_Y/_X'nin arktjantını hesaplar

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

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y/_X'nin arctanjant değerini verir

## <a name="atan2f"></a><a name="atan2f"></a>atan2f

_Y/_X'nin arktjantını hesaplar

```cpp
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Y*<br/>
Kayan nokta değeri

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y/_X'nin arctanjant değerini verir

## <a name="atanf"></a><a name="atanf"></a>atanf

Bağımsız değişkenin arctantını hesaplar

```cpp
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin arctanjant değerini verir

## <a name="atanh"></a><a name="atanh"></a>atanh

Bağımsız değişkenin ters hiperbolik teğetini hesaplar

```cpp
inline float atanh(float _X) restrict(amp);

inline double atanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik teğet değerini verir

## <a name="atanhf"></a><a name="atanhf"></a>atanhf

Bağımsız değişkenin ters hiperbolik teğetini hesaplar

```cpp
inline float atanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters hiperbolik teğet değerini verir

## <a name="cbrt"></a><a name="cbrt"></a>Tcmb

Bağımsız değişkenin gerçek küp kökünü hesaplar

```cpp
inline float cbrt(float _X) restrict(amp);

inline double cbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin gerçek küp kökünü verir

## <a name="cbrtf"></a><a name="cbrtf"></a>cbrtf

Bağımsız değişkenin gerçek küp kökünü hesaplar

```cpp
inline float cbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin gerçek küp kökünü verir

## <a name="ceil"></a><a name="ceil"></a>Ceil

Bağımsız değişkenin tavanını hesaplar

```cpp
inline float ceil(float _X) restrict(amp);

inline double ceil(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tavanını verir

## <a name="ceilf"></a><a name="ceilf"></a>ceilf

Bağımsız değişkenin tavanını hesaplar

```cpp
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin tavanını verir

## <a name="copysign"></a><a name="copysign"></a>copysign

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

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X büyüklüğü ve _Y işareti ile bir değer verir

## <a name="copysignf"></a><a name="copysignf"></a>copysignf

_X büyüklüğü ve _Y işareti ile bir değer üretir

```cpp
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X büyüklüğü ve _Y işareti ile bir değer verir

## <a name="cos"></a><a name="cos"></a>Çünkü

Bağımsız değişkenin kosinüsünün hesaplar

```cpp
inline float cos(float _X) restrict(amp);

inline double cos(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kosinüs değerini verir

## <a name="cosf"></a><a name="cosf"></a>cosf

Bağımsız değişkenin kosinüsünün hesaplar

```cpp
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kosinüs değerini verir

## <a name="cosh"></a><a name="cosh"></a>Cosh

Bağımsız değişkenin hiperbolik kosinüs değerini hesaplar

```cpp
inline float cosh(float _X) restrict(amp);

inline double cosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik kosinüs değerini verir

## <a name="coshf"></a><a name="coshf"></a>coşf

Bağımsız değişkenin hiperbolik kosinüs değerini hesaplar

```cpp
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik kosinüs değerini verir

## <a name="cospi"></a><a name="cospi"></a>cospi

Pi \* _X kosinüs değerini hesaplar

```cpp
inline float cospi(float _X) restrict(amp);

inline double cospi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Pi \* _X kosinüs değerini verir

## <a name="cospif"></a><a name="cospif"></a>cospif

Pi \* _X kosinüs değerini hesaplar

```cpp
inline float cospif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Pi \* _X kosinüs değerini verir

## <a name="erf"></a><a name="erf"></a>Erf

_X hata işlevini hesaplar

```cpp
inline float erf(float _X) restrict(amp);

inline double erf(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X hata işlevini verir

## <a name="erfc"></a><a name="erfc"></a>erfc

_X tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfc(float _X) restrict(amp);

inline double erfc(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X tamamlayıcı hata işlevini verir

## <a name="erfcf"></a><a name="erfcf"></a>erfcf

_X tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfcf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X tamamlayıcı hata işlevini verir

## <a name="erfcinv"></a><a name="erfcinv"></a>erfcinv

_X ters tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfcinv(float _X) restrict(amp);

inline double erfcinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters tamamlayıcı hata işlevini verir

## <a name="erfcinvf"></a><a name="erfcinvf"></a>erfcinvf

_X ters tamamlayıcı hata işlevini hesaplar

```cpp
inline float erfcinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters tamamlayıcı hata işlevini verir

## <a name="erff"></a><a name="erff"></a>erff

_X hata işlevini hesaplar

```cpp
inline float erff(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X hata işlevini verir

## <a name="erfinv"></a><a name="erfinv"></a>erfinv

_X ters hata işlevini hesaplar

```cpp
inline float erfinv(float _X) restrict(amp);

inline double erfinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters hata işlevini verir

## <a name="erfinvf"></a><a name="erfinvf"></a>erfinvf

_X ters hata işlevini hesaplar

```cpp
inline float erfinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters hata işlevini verir

## <a name="exp10"></a><a name="exp10"></a>exp10

Bağımsız değişkenin taban-10 üstel değerini hesaplar

```cpp
inline float exp10(float _X) restrict(amp);

inline double exp10(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-10 üstel sini verir

## <a name="exp10f"></a><a name="exp10f"></a>exp10f

Bağımsız değişkenin taban-10 üstel değerini hesaplar

```cpp
inline float exp10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-10 üstel sini verir

## <a name="expm1"></a><a name="expm1"></a>expm1

Bağımsız değişkenin e tabanında üssü eksi 1 hesaplar.

```cpp
inline float expm1(float exponent) restrict(amp);

inline double expm1(double exponent) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*Üs*<br/>
Matematiksel `e` <sup>ifaden</sup>n üstel terimi *n* , `e` doğal logaritma tabanı nerede.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin e tabanında üssü eksi 1 döndürür.

## <a name="expm1f"></a><a name="expm1f"></a>expm1f

Bağımsız değişkenin e tabanında üssü eksi 1 hesaplar.

```cpp
inline float expm1f(float exponent) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*Üs*<br/>
Matematiksel `e` <sup>ifaden</sup>n üstel terimi *n* , `e` doğal logaritma tabanı nerede.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin e tabanında üssü eksi 1 döndürür.

## <a name="exp"></a><a name="exp"></a>Exp

Bağımsız değişkenin taban-e üstel değerini hesaplar

```cpp
inline float exp(float _X) restrict(amp);

inline double exp(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-e üstel sini verir

## <a name="expf"></a><a name="expf"></a>expf

Bağımsız değişkenin taban-e üstel değerini hesaplar

```cpp
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-e üstel sini verir

## <a name="exp2"></a><a name="exp2"></a>exp2

Bağımsız değişkenin taban-2 üstel değerini hesaplar

```cpp
inline float exp2(float _X) restrict(amp);

inline double exp2(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-2 üstel sini verir

## <a name="exp2f"></a><a name="exp2f"></a>exp2f

Bağımsız değişkenin taban-2 üstel değerini hesaplar

```cpp
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-2 üstel sini verir

## <a name="fabs"></a><a name="fabs"></a>Faruk

Bağımsız değişkenin mutlak değerini verir

```cpp
inline float fabs(float _X) restrict(amp);

inline double fabs(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin mutlak değerini verir

## <a name="fabsf"></a><a name="fabsf"></a>fabsf

Bağımsız değişkenin mutlak değerini verir

```cpp
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin mutlak değerini verir

## <a name="fdim"></a><a name="fdim"></a>fdim

Bağımsız değişkenler arasındaki olumlu farkı hesaplar.

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

*_x*<br/>
Kayan nokta değeri *_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Y büyükse _X ile _Y arasındaki fark; aksi takdirde, +0.

## <a name="fdimf"></a><a name="fdimf"></a>fdimf

Bağımsız değişkenler arasındaki olumlu farkı hesaplar.

```cpp
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri *_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Y büyükse _X ile _Y arasındaki fark; aksi takdirde, +0.

## <a name="floor"></a><a name="floor"></a>Kat

Bağımsız değişkenin zeminini hesaplar

```cpp
inline float floor(float _X) restrict(amp);

inline double floor(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin zeminini döndürür

## <a name="floorf"></a><a name="floorf"></a>floorf

Bağımsız değişkenin zeminini hesaplar

```cpp
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin zeminini döndürür

## <a name="a-namefma-fma"></a><a name="fma">Fma

Birinci ve ikinci belirtilen bağımsız değişkenlerin ürünlerini hesaplar, ardından üçüncü belirtilen bağımsız değişkeni sonuca ekler; tüm hesaplama tek bir işlem olarak gerçekleştirilir.

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

*_x*<br/>
İlk kayan nokta bağımsız değişkeni.
*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.
*_Z*<br/>
Üçüncü kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

İfadenin sonucu (_X \* _Y) + _Z. Tüm hesaplama tek bir işlem olarak gerçekleştirilir; diğer bir şey, alt ifadeler sonsuz kesinlik için hesaplanır ve yalnızca nihai sonuç yuvarlanır.

## <a name="fmaf"></a><a name="fmaf"></a>fmaf

Birinci ve ikinci belirtilen bağımsız değişkenlerin ürünlerini hesaplar, ardından üçüncü belirtilen bağımsız değişkeni sonuca ekler; tüm hesaplama tek bir işlem olarak gerçekleştirilir.

```cpp
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
İlk kayan nokta bağımsız değişkeni.
*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.
*_Z*<br/>
Üçüncü kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

İfadenin sonucu (_X \* _Y) + _Z. Tüm hesaplama tek bir işlem olarak gerçekleştirilir; diğer bir şey, alt ifadeler sonsuz kesinlik için hesaplanır ve yalnızca nihai sonuç yuvarlanır.

## <a name="fmax"></a><a name="fmax"></a>fmax

Bağımsız değişkenlerin maksimum sayısal değerini belirleme

```cpp
inline float fmax(
    float _X,
    float _Y) restrict(amp);

inline double fmax(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin maksimum sayısal değerini döndürme

## <a name="fmaxf"></a><a name="fmaxf"></a>fmaxf

Bağımsız değişkenlerin maksimum sayısal değerini belirleme

```cpp
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin maksimum sayısal değerini döndürme

## <a name="fmin"></a><a name="fmin"></a>fmin

Bağımsız değişkenlerin minimum sayısal değerini belirleme

```cpp
inline float fmin(
    float _X,
    float _Y) restrict(amp);

inline double fmin(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin minimum sayısal değerini döndürme

## <a name="fminf"></a><a name="fminf"></a>fminf

Bağımsız değişkenlerin minimum sayısal değerini belirleme

```cpp
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin minimum sayısal değerini döndürme

## <a name="fmod-function-c-amp"></a><a name="fmod"></a>fmod Fonksiyonu (C++ AMP)

Belirtilen ilk belirtinen bağımsız değişkenin geri kalanını ikinci belirtilen bağımsız değişkene bölünür.

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);

inline double fmod(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

Geri kalan `_X` bölünerek; `_Y` yani, `_X`  -  `_Y` *n*değeri , *n* bir bütün tamsayı gibi n `_X`  -  `_Y`büyüklüğü daha *azdır* `_Y`.

## <a name="fmodf"></a><a name="fmodf"></a>fmodf

Belirtilen ilk belirtinen bağımsız değişkenin geri kalanını ikinci belirtilen bağımsız değişkene bölünür.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

Geri kalan `_X` bölünerek; `_Y` yani, `_X`  -  `_Y` *n*değeri , *n* bir bütün tamsayı gibi n `_X`  -  `_Y`büyüklüğü daha *azdır* `_Y`.

## <a name="fpclassify"></a><a name="fpclassify"></a>fpclassify

Bağımsız değişken değerini NaN, sonsuz, normal, normal, subnormal, sıfır olarak sınıflandırıyor

```cpp
inline int fpclassify(float _X) restrict(amp);

inline int fpclassify(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin değerine uygun sayı sınıflandırma makrosu değerini verir.

## <a name="frexp"></a><a name="frexp"></a>frexp

mantisve üs alır _X

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);

inline double frexp(
    double _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Exp*<br/>
Kayan nokta değerindeki _X tamsayı üstesini verir

### <a name="return-value"></a>Dönüş Değeri

Mantisa _X döndürür

## <a name="frexpf"></a><a name="frexpf"></a>frexpf

mantisve üs alır _X

```cpp
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Exp*<br/>
Kayan nokta değerindeki _X tamsayı üstesini verir

### <a name="return-value"></a>Dönüş Değeri

Mantisa _X döndürür

## <a name="hypot"></a><a name="hypot"></a>hipot

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

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ve _Y karelerinin toplamının kare kökünü verir

## <a name="hypotf"></a><a name="hypotf"></a>hipotf

_X ve _Y karelerinin toplamının kare kökünü hesaplar

```cpp
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X ve _Y karelerinin toplamının kare kökünü verir

## <a name="ilogb"></a><a name="ilogb"></a>ilogb

İmzalanmış bir int değeri olarak _X üstünü ayıklayın

```cpp
inline int ilogb(float _X) restrict(amp);

inline int ilogb(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

İmzalanmış int değeri olarak _X üst değerini verir

## <a name="ilogbf"></a><a name="ilogbf"></a>ilogbf

İmzalanmış bir int değeri olarak _X üstünü ayıklayın

```cpp
inline int ilogbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

İmzalanmış int değeri olarak _X üst değerini verir

## <a name="isfinite"></a><a name="isfinite"></a>Isfinite

Bağımsız değişkenin sonlu bir değeri olup olmadığını belirler

```cpp
inline int isfinite(float _X) restrict(amp);

inline int isfinite(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin sonlu bir değeri varsa ve yalnızca sıfır olmayan bir değer verir

## <a name="isinf"></a><a name="isinf"></a>isinf

Bağımsız değişkenin sonsuz olup olmadığını belirler

```cpp
inline int isinf(float _X) restrict(amp);

inline int isinf(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin sonsuz bir değeri varsa ve yalnızca sıfır olmayan bir değer verir

## <a name="isnan"></a><a name="isnan"></a>ısnan

Bağımsız değişkenin NaN olup olmadığını belirler

```cpp
inline int isnan(float _X) restrict(amp);

inline int isnan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin NaN değeri varsa ve yalnızca sıfır olmayan bir değer verir

## <a name="isnormal"></a><a name="isnormal"></a>normal

Bağımsız değişkenin normal olup olmadığını belirler

```cpp
inline int isnormal(float _X) restrict(amp);

inline int isnormal(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin normal bir değeri varsa ve yalnızca sıfır olmayan bir değer verir

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

Belirtilen mantis ve üsgerçek bir sayı yı hesaplar.

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);

inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, mantissa

*_Exp*<br/>
İntesayı değeri, üs

### <a name="return-value"></a>Dönüş Değeri

2^_Exp_X \* döndürür

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

Belirtilen mantis ve üsgerçek bir sayı yı hesaplar.

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, mantissa

*_Exp*<br/>
İntesayı değeri, üs

### <a name="return-value"></a>Dönüş Değeri

2^_Exp_X \* döndürür

## <a name="lgamma"></a><a name="lgamma"></a>lgamma

Bağımsız değişkenin gama mutlak değerinin doğal logaritma sını hesaplar

```cpp
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);

inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Sign*<br/>
İşareti döndürür

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin gama mutlak değerinin doğal logaritma verir

## <a name="lgammaf"></a><a name="lgammaf"></a>lgammaf

Bağımsız değişkenin gama mutlak değerinin doğal logaritma sını hesaplar

```cpp
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Sign*<br/>
İşareti döndürür

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin gama mutlak değerinin doğal logaritma verir

## <a name="log"></a><a name="log"></a>Günlük

Bağımsız değişkenin temel-e logaritmasını hesaplar

```cpp
inline float log(float _X) restrict(amp);

inline double log(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-e logaritmasını verir

## <a name="log10"></a><a name="log10"></a>log10

Bağımsız değişkenin taban-10 logaritmasını hesaplar

```cpp
inline float log10(float _X) restrict(amp);

inline double log10(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-10 logaritmasını verir

## <a name="log10f"></a><a name="log10f"></a>log10f

Bağımsız değişkenin taban-10 logaritmasını hesaplar

```cpp
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-10 logaritmasını verir

## <a name="log1p"></a><a name="log1p"></a>log1p

1'in baz-e logaritmasını ve bağımsız değişkeni hesaplar

```cpp
inline float log1p(float _X) restrict(amp);

inline double log1p(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

1 artı bağımsız değişkenin temel-e logaritma sını verir

## <a name="log1pf"></a><a name="log1pf"></a>log1pf

1'in baz-e logaritmasını ve bağımsız değişkeni hesaplar

```cpp
inline float log1pf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

1 artı bağımsız değişkenin temel-e logaritma sını verir

## <a name="log2"></a><a name="log2"></a>log2

Bağımsız değişkenin taban-2 logaritmasını hesaplar

```cpp
inline float log2(float _X) restrict(amp);

inline double log2(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-10 logaritmasını verir

## <a name="log2f"></a><a name="log2f"></a>log2f

Bağımsız değişkenin taban-2 logaritmasını hesaplar

```cpp
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-10 logaritmasını verir

## <a name="logb"></a><a name="logb"></a>logb

Kayan nokta biçiminde imzalı bir tamsayı değeri olarak _X üstünü ayıklar

```cpp
inline float logb(float _X) restrict(amp);

inline double logb(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

İmzalanan üs _X verir

## <a name="logbf"></a><a name="logbf"></a>logbf

Kayan nokta biçiminde imzalı bir tamsayı değeri olarak _X üstünü ayıklar

```cpp
inline float logbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

İmzalanan üs _X verir

## <a name="logf"></a><a name="logf"></a>logf

Bağımsız değişkenin temel-e logaritmasını hesaplar

```cpp
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin temel-e logaritmasını verir

## <a name="modf"></a><a name="modf"></a>modf

Belirtilen bağımsız değişkeni kesirli ve sondaparçalarına böler.

```cpp
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);

inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Iptr*<br/>
[çıkış] Kayan nokta değeri `_X`olarak tamsayı bölümü.

### <a name="return-value"></a>Dönüş Değeri

İmzalanmış kesirli `_X`kısmı.

## <a name="modff"></a><a name="modff"></a>modff

Belirtilen bağımsız değişkeni kesirli ve sondaparçalarına böler.

```cpp
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Iptr*<br/>
Kayan nokta değeri `_X`olarak tamsayı bölümü.

### <a name="return-value"></a>Dönüş Değeri

İmzalanan kesirli `_X`bölümünü verir.

## <a name="nan"></a><a name="nan"></a>Nan

Sessiz bir NaN verir

```cpp
inline double nan(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Varsa, içeriği _X belirtilen sessiz bir NaN verir

## <a name="nanf"></a><a name="nanf"></a>nanf

Sessiz bir NaN verir

```cpp
inline float nanf(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Varsa, içeriği _X belirtilen sessiz bir NaN verir

## <a name="nearbyint"></a><a name="nearbyint"></a>yakın

Geçerli yuvarlama yönünü kullanarak bağımsız değişkeni kayan nokta biçiminde bir sonda değerine yuvarlar.

```cpp
inline float nearbyint(float _X) restrict(amp);

inline double nearbyint(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yuvarlatılmış tümsedo değerini döndürür.

## <a name="nearbyintf"></a><a name="nearbyintf"></a>nearbyintf

Geçerli yuvarlama yönünü kullanarak bağımsız değişkeni kayan nokta biçiminde bir sonda değerine yuvarlar.

```cpp
inline float nearbyintf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yuvarlatılmış tümsedo değerini döndürür.

## <a name="nextafter"></a><a name="nextafter"></a>sonraki sonra

_Y yönünde _X sonra, işlevin türünde bir sonraki temsil edilebilir değeri belirleyin

```cpp
inline float nextafter(
    float _X,
    float _Y) restrict(amp);

inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y yönünde _X sonra, işlevtüründe bir sonraki temsil edilebilir değeri verir_Y

## <a name="nextafterf"></a><a name="nextafterf"></a>nextafterf

_Y yönünde _X sonra, işlevin türünde bir sonraki temsil edilebilir değeri belirleyin

```cpp
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_Y yönünde _X sonra, işlevtüründe bir sonraki temsil edilebilir değeri verir_Y

## <a name="phi"></a><a name="phi"></a>Phi

Bağımsız değişkenin kümülatif dağılım işlevini verir

```cpp
inline float phi(float _X) restrict(amp);

inline double phi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kümülatif dağılım işlevini verir

## <a name="phif"></a><a name="phif"></a>phif

Bağımsız değişkenin kümülatif dağılım işlevini verir

```cpp
inline float phif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kümülatif dağılım işlevini verir

## <a name="pow"></a><a name="pow"></a>Pow

_Y gücüne yükseltilen _X hesaplar

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);

inline double pow(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, taban

*_Y*<br/>
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

## <a name="powf"></a><a name="powf"></a>powf

_Y gücüne yükseltilen _X hesaplar

```cpp
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, taban

*_Y*<br/>
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

## <a name="probit"></a><a name="probit"></a>probit

Bağımsız değişkenin ters kümülatif dağılım işlevini verir

```cpp
inline float probit(float _X) restrict(amp);

inline double probit(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters kümülatif dağılım işlevini verir

## <a name="probitf"></a><a name="probitf"></a>probitf

Bağımsız değişkenin ters kümülatif dağılım işlevini verir

```cpp
inline float probitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin ters kümülatif dağılım işlevini verir

## <a name="rcbrt"></a><a name="rcbrt"></a>rcbrt

Bağımsız değişkenin küp kökünün karşıtlığı verir

```cpp
inline float rcbrt(float _X) restrict(amp);

inline double rcbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin küp kökünün karşıtlığı verir

## <a name="rcbrtf"></a><a name="rcbrtf"></a>rcbrtf

Bağımsız değişkenin küp kökünün karşıtlığı verir

```cpp
inline float rcbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin küp kökünün karşıtlığı verir

## <a name="remainder"></a><a name="remainder"></a>Geri kalanı

Geri kalanını hesaplar: _X REM _Y

```cpp
inline float remainder(
    float _X,
    float _Y) restrict(amp);

inline double remainder(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

REM _X _Y döndürür

## <a name="remainderf"></a><a name="remainderf"></a>remainderf

Geri kalanını hesaplar: _X REM _Y

```cpp
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

REM _X _Y döndürür

## <a name="remquo"></a><a name="remquo"></a>remquo

Belirtilen ilk belirtinen bağımsız değişkenin geri kalanını ikinci belirtilen bağımsız değişkene bölünür. Ayrıca, belirtilen ikinci bağımsız değişkenin önemine bölünen ilk belirtilen bağımsız değişkenin öneminin katkını da hesaplar ve üçüncü bağımsız değişkende belirtilen konumu kullanarak bölümü döndürür.

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

*_x*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

*_Quo*<br/>
[çıkış] Kesirli bitlere `_X` bölünen kesirli bitlerin bölümlerini döndürmek için kullanılan bir karşılayıcının `_Y`adresi

### <a name="return-value"></a>Dönüş Değeri

Bölünen geri `_X` kalanını `_Y`verir.

## <a name="remquof"></a><a name="remquof"></a>remquof

Belirtilen ilk belirtinen bağımsız değişkenin geri kalanını ikinci belirtilen bağımsız değişkene bölünür. Ayrıca, belirtilen ikinci bağımsız değişkenin önemine bölünen ilk belirtilen bağımsız değişkenin öneminin katkını da hesaplar ve üçüncü bağımsız değişkende belirtilen konumu kullanarak bölümü döndürür.

```cpp
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
İlk kayan nokta bağımsız değişkeni.

*_Y*<br/>
İkinci kayan nokta bağımsız değişkeni.

*_Quo*<br/>
[çıkış] Kesirli bitlere `_X` bölünen kesirli bitlerin bölümlerini döndürmek için kullanılan bir karşılayıcının `_Y`adresi

### <a name="return-value"></a>Dönüş Değeri

Bölünen geri `_X` kalanını `_Y`verir.

## <a name="round"></a><a name="round"></a>Yuvarlak

_X en yakın tamsayıya yuvarlar

```cpp
inline float round(float _X) restrict(amp);

inline double round(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X en yakın tamsayıyı döndürür

## <a name="roundf"></a><a name="roundf"></a>roundf

_X en yakın tamsayıya yuvarlar

```cpp
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X en yakın tamsayıyı döndürür

## <a name="rsqrt"></a><a name="rsqrt"></a>rsqrt

Bağımsız değişkenin kare kökünün karşıtlığı verir

```cpp
inline float rsqrt(float _X) restrict(amp);

inline double rsqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kare kökünün karşıtlığı verir

## <a name="rsqrtf"></a><a name="rsqrtf"></a>rsqrtf

Bağımsız değişkenin kare kökünün karşıtlığı verir

```cpp
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin kare kökünün karşıtlığı verir

## <a name="scalb"></a><a name="scalb"></a>scalb

Güç _Y FLT_RADIX _X çarpar

```cpp
inline float scalb(
    float _X,
    float _Y) restrict(amp);

inline double scalb(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* Döndürür (FLT_RADIX ^ _Y)

## <a name="scalbf"></a><a name="scalbf"></a>scalbf

Güç _Y FLT_RADIX _X çarpar

```cpp
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* Döndürür (FLT_RADIX ^ _Y)

## <a name="scalbn"></a><a name="scalbn"></a>scalbn

Güç _Y FLT_RADIX _X çarpar

```cpp
inline float scalbn(
    float _X,
    int _Y) restrict(amp);

inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* Döndürür (FLT_RADIX ^ _Y)

## <a name="scalbnf"></a><a name="scalbnf"></a>scalbnf

Güç _Y FLT_RADIX _X çarpar

```cpp
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

_X \* Döndürür (FLT_RADIX ^ _Y)

## <a name="signbit"></a><a name="signbit"></a>signbit

_X işaretinin negatif olup olmadığını belirler

```cpp
inline int signbit(float _X) restrict(amp);

inline int signbit(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yalnızca _X işareti negatifse sıfır olmayan bir değer verir

## <a name="signbitf"></a><a name="signbitf"></a>signbitf

_X işaretinin negatif olup olmadığını belirler

```cpp
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Yalnızca _X işareti negatifse sıfır olmayan bir değer verir

## <a name="sin"></a><a name="sin"></a>Günah

Bağımsız değişkenin sinüs değerini hesaplar

```cpp
inline float sin(float _X) restrict(amp);

inline double sin(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin sinüs değerini verir

## <a name="sinf"></a><a name="sinf"></a>sinf

Bağımsız değişkenin sinüs değerini hesaplar

```cpp
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin sinüs değerini verir

## <a name="sincos"></a><a name="sincos"></a>sincos

_X sinüs ve kosinüs değerini hesaplar

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

*_x*<br/>
Kayan nokta değeri

*_s*<br/>
_X sinüs değerini verir

*_C*<br/>
_X kosinüs değerini verir

## <a name="sincosf"></a><a name="sincosf"></a>sincosf

_X sinüs ve kosinüs değerini hesaplar

```cpp
inline void sincosf(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_s*<br/>
_X sinüs değerini verir

*_C*<br/>
_X kosinüs değerini verir

## <a name="sinh"></a><a name="sinh"></a>Sinh

Bağımsız değişkenin hiperbolik sinüs değerini hesaplar

```cpp
inline float sinh(float _X) restrict(amp);

inline double sinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik sinüs değerini verir

## <a name="sinhf"></a><a name="sinhf"></a>sinhf

Bağımsız değişkenin hiperbolik sinüs değerini hesaplar

```cpp
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik sinüs değerini verir

## <a name="sinpi"></a><a name="sinpi"></a>sinpi

pi \* _X sinüs değerini hesaplar

```cpp
inline float sinpi(float _X) restrict(amp);

inline double sinpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Pi \* _X sinüs değerini verir

## <a name="sinpif"></a><a name="sinpif"></a>sinpif

pi \* _X sinüs değerini hesaplar

```cpp
inline float sinpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Pi \* _X sinüs değerini verir

## <a name="sqrt"></a><a name="sqrt"></a>Karekök

Bağımsız değişkenin squre kökünü hesaplar

```cpp
inline float sqrt(float _X) restrict(amp);

inline double sqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin squre kökünü verir

## <a name="sqrtf"></a><a name="sqrtf"></a>sqrtf

Bağımsız değişkenin squre kökünü hesaplar

```cpp
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin squre kökünü verir

## <a name="tan"></a><a name="tan"></a>tan

Bağımsız değişkenin teğet değerini hesaplar

```cpp
inline float tan(float _X) restrict(amp);

inline double tan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin teğet değerini verir

## <a name="tanf"></a><a name="tanf"></a>tanf

Bağımsız değişkenin teğet değerini hesaplar

```cpp
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin teğet değerini verir

## <a name="tanh"></a><a name="tanh"></a>Tanh

Bağımsız değişkenin hiperbolik teğet değerini hesaplar

```cpp
inline float tanh(float _X) restrict(amp);

inline double tanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik teğet değerini verir

## <a name="tanhf"></a><a name="tanhf"></a>tanhf

Bağımsız değişkenin hiperbolik teğet değerini hesaplar

```cpp
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik teğet değerini verir

## <a name="tanpi"></a><a name="tanpi"></a>tanpi

pi \* _X teğet değerini hesaplar

```cpp
inline float tanpi(float _X) restrict(amp);

inline double tanpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

pi \* _X teğet değerini verir

## <a name="tanpif"></a><a name="tanpif"></a>tanpif

pi \* _X teğet değerini hesaplar

```cpp
inline float tanpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

pi \* _X teğet değerini verir

## <a name="tgamma"></a><a name="tgamma"></a>tgamma

_X gama işlevini hesaplar

```cpp
inline float tgamma(float _X) restrict(amp);

inline double tgamma(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X gama fonksiyonunun sonucunu verir

## <a name="tgammaf"></a><a name="tgammaf"></a>tgammaf

_X gama işlevini hesaplar

```cpp
inline float tgammaf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X gama fonksiyonunun sonucunu verir

## <a name="trunc"></a><a name="trunc"></a>Trunc

Bağımsız değişkeni sonda bileşenine truncates

```cpp
inline float trunc(float _X) restrict(amp);

inline double trunc(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin insa bileşenini döndürür

## <a name="truncf"></a><a name="truncf"></a>truncf

Bağımsız değişkeni sonda bileşenine truncates

```cpp
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin insa bileşenini döndürür

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)
