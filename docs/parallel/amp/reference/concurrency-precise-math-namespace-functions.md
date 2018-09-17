---
title: CONCURRENCY::precise_math ad alanı işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60c2b85c3a5c1ca5e2da9b0ef3b42148510b59e1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711070"
---
# <a name="concurrencyprecisemath-namespace-functions"></a>CONCURRENCY::precise_math ad alanı işlevleri
||||
|-|-|-|
|[acos](#acos)|[acosf](#acosf)|[ACOSH](#acosh)|
|[acoshf](#acoshf)|[asin](#asin)|[asinf](#asinf)|
|[ASİNH](#asinh)|[asinhf](#asinhf)|[atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[ATANH](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|
|[cbrtf](#cbrtf)|[ceil](#ceil)|[ceilf](#ceilf)|
|[copysign](#copysign)|[copysignf](#copysignf)|[cos](#cos)|
|[cosf](#cosf)|[COSH](#cosh)|[coshf](#coshf)|
|[cospi](#cospi)|[cospif](#cospif)|[erf](#erf)|
|[erfc](#erfc)|[erfcf](#erfcf)|[erfcinv](#erfcinv)|
|[erfcinvf](#erfcinvf)|[erff](#erff)|[erfinv](#erfinv)|
|[erfinvf](#erfinvf)|[exp](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[fabs](#fabs)|[fabsf](#fabsf)|[Kat](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[FMA](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[frexpf](#frexpf)|[hypot](#hypot)|[hypotf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[isfinite](#isfinite)|
|[isinf](#isinf)|[isnan](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[log](#log)|[log10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[NaN](#nan)|[nanf](#nanf)|
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[nextafter](#nextafter)|
|[nextafterf](#nextafterf)|[phı](#phi)|[phif](#phif)|
|[POW](#pow)|[powf](#powf)|[probit](#probit)|
|[probitf](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[Kalan](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[Yuvarlak](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[scalb](#scalb)|
|[scalbf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[signbitf](#signbitf)|[sin](#sin)|
|[sincos](#sincos)|[sincosf](#sincosf)|[sinf](#sinf)|
|[SİNH](#sinh)|[sinhf](#sinhf)|[sinpi](#sinpi)|
|[sinpif](#sinpif)|[sqrt](#sqrt)|[sqrtf](#sqrtf)|
|[tan](#tan)|[tanf](#tanf)|[TANH](#tanh)|
|[tanhf](#tanhf)|[tanpi](#tanpi)|[tanpif](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[trunc](#trunc)|
|[truncf](#truncf)|

##  <a name="acos"></a>  ACOS
Bağımsız değişkenin ark kosinüsünü hesaplar.

```  
inline float acos(float _X) restrict(amp);


inline double acos(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ark kosinüsünü değerini döndürür

##  <a name="acosf"></a>  acosf
Bağımsız değişkenin ark kosinüsünü hesaplar.

```  
inline float acosf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ark kosinüsünü değerini döndürür

##  <a name="acosh"></a>  ACOSH
Bağımsız değişkenin ters hiperbolik kosinüsünü hesaplar.

```  
inline float acosh(float _X) restrict(amp);


inline double acosh(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ters hiperbolik Kosinüs değerini döndürür

##  <a name="acoshf"></a>  acoshf
Bağımsız değişkenin ters hiperbolik kosinüsünü hesaplar.

```  
inline float acoshf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ters hiperbolik Kosinüs değerini döndürür

##  <a name="asin"></a>  asin
Bağımsız değişkenin ark sinüsünü hesaplar

```  
inline float asin(float _X) restrict(amp);


inline double asin(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ark sinüsünü değerini döndürür

##  <a name="asinf"></a>  asinf
Bağımsız değişkenin ark sinüsünü hesaplar

```  
inline float asinf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ark sinüsünü değerini döndürür

##  <a name="asinh"></a>  ASİNH
Bağımsız değişkenin ters hiperbolik sinüsünü hesaplar.

```  
inline float asinh(float _X) restrict(amp);


inline double asinh(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ters hiperbolik sinüs değerini döndürür

##  <a name="asinhf"></a>  asinhf
Bağımsız değişkenin ters hiperbolik sinüsünü hesaplar.

```  
inline float asinhf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ters hiperbolik sinüs değerini döndürür

##  <a name="atan"></a>  atan
Bağımsız değişkenin ark tanjantını hesaplar.

```  
inline float atan(float _X) restrict(amp);


inline double atan(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ark tanjantını değerini döndürür

##  <a name="atan2"></a>  ATAN2
_Y/_x'in ark tanjantını hesaplar.

```  
inline float atan2(
    float _Y,
    float _X) restrict(amp);


inline double atan2(
    double _Y,
    double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_Y`  
Kayan nokta değeri

`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_Y/_x'in ark tanjantını değerini döndürür

##  <a name="atan2f"></a>  atan2f
_Y/_x'in ark tanjantını hesaplar.

```  
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_Y`  
Kayan nokta değeri

`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_Y/_x'in ark tanjantını değerini döndürür

##  <a name="atanf"></a>  atanf
Bağımsız değişkenin ark tanjantını hesaplar.

```  
inline float atanf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ark tanjantını değerini döndürür

##  <a name="atanh"></a>  ATANH
Bağımsız değişkenin ters hiperbolik tanjantı hesaplar.

```  
inline float atanh(float _X) restrict(amp);


inline double atanh(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişken ters hiperbolik tanjant değerini döndürür

##  <a name="atanhf"></a>  atanhf
Bağımsız değişkenin ters hiperbolik tanjantı hesaplar.

```  
inline float atanhf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişken ters hiperbolik tanjant değerini döndürür

##  <a name="cbrt"></a>  cbrt
Bağımsız değişkenin gerçek Küp kökünü hesaplar.

```  
inline float cbrt(float _X) restrict(amp);


inline double cbrt(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin gerçek Küp kökünü döndürür

##  <a name="cbrtf"></a>  cbrtf
Bağımsız değişkenin gerçek Küp kökünü hesaplar.

```  
inline float cbrtf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin gerçek Küp kökünü döndürür

##  <a name="ceil"></a>  Ceil
Bağımsız değişkenin tavanını hesaplar.

```  
inline float ceil(float _X) restrict(amp);


inline double ceil(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin tavanını döndürür

##  <a name="ceilf"></a>  ceilf
Bağımsız değişkenin tavanını hesaplar.

```  
inline float ceilf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin tavanını döndürür

##  <a name="copysign"></a>  copysign
Büyüklüğünü _X ve _Y'in bir değer üretir.

```  
inline float copysign(
    float _X,
    float _Y) restrict(amp);


inline double copysign(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Büyüklüğünü _X ve _Y'in bir değer döndürür

##  <a name="copysignf"></a>  copysignf
Büyüklüğünü _X ve _Y'in bir değer üretir.

```  
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Büyüklüğünü _X ve _Y'in bir değer döndürür

##  <a name="cos"></a>  Cos
Bağımsız değişkenin kosinüsünü hesaplar.

```  
inline float cos(float _X) restrict(amp);


inline double cos(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin Kosinüs değerini döndürür

##  <a name="cosf"></a>  cosf
Bağımsız değişkenin kosinüsünü hesaplar.

```  
inline float cosf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin Kosinüs değerini döndürür

##  <a name="cosh"></a>  COSH
Bağımsız değişkenin hiperbolik Kosinüs değerini hesaplar.

```  
inline float cosh(float _X) restrict(amp);


inline double cosh(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin hiperbolik Kosinüs değerini döndürür

##  <a name="coshf"></a>  coshf
Bağımsız değişkenin hiperbolik Kosinüs değerini hesaplar.

```  
inline float coshf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin hiperbolik Kosinüs değerini döndürür

##  <a name="cospi"></a>  cospi
Pi Kosinüs değerini hesaplar \* _X

```  
inline float cospi(float _X) restrict(amp);


inline double cospi(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Pi Kosinüs değerini döndürür \* _X

##  <a name="cospif"></a>  cospif
Pi Kosinüs değerini hesaplar \* _X

```  
inline float cospif(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Pi Kosinüs değerini döndürür \* _X

##  <a name="erf"></a>  erf
_X hata işlevini hesaplar.

```  
inline float erf(float _X) restrict(amp);


inline double erf(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X hata işlevini döndürür

##  <a name="erfc"></a>  erfc
_X Tümleyici hata işlevini hesaplar.

```  
inline float erfc(float _X) restrict(amp);


inline double erfc(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X Tümleyici hata işlevini döndürür

##  <a name="erfcf"></a>  erfcf
_X Tümleyici hata işlevini hesaplar.

```  
inline float erfcf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X Tümleyici hata işlevini döndürür

##  <a name="erfcinv"></a>  erfcinv
_X ters Tümleyici hata işlevini hesaplar.

```  
inline float erfcinv(float _X) restrict(amp);


inline double erfcinv(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ters Tümleyici hata işlevini döndürür

##  <a name="erfcinvf"></a>  erfcinvf
_X ters Tümleyici hata işlevini hesaplar.

```  
inline float erfcinvf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ters Tümleyici hata işlevini döndürür

##  <a name="erff"></a>  erff
_X hata işlevini hesaplar.

```  
inline float erff(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X hata işlevini döndürür

##  <a name="erfinv"></a>  erfinv
_X ters hata işlevini hesaplar.

```  
inline float erfinv(float _X) restrict(amp);


inline double erfinv(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ters hata işlevini döndürür

##  <a name="erfinvf"></a>  erfinvf
_X ters hata işlevini hesaplar.

```  
inline float erfinvf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ters hata işlevini döndürür

##  <a name="exp10"></a>  exp10
10 tabanında bağımsız değişkeni üssünü hesaplar.

```  
inline float exp10(float _X) restrict(amp);


inline double exp10(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
10 tabanında üssünü bağımsız değişkenin döndürür

##  <a name="exp10f"></a>  exp10f
10 tabanında bağımsız değişkeni üssünü hesaplar.

```  
inline float exp10f(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
10 tabanında üssünü bağımsız değişkenin döndürür

##  <a name="expm1"></a>  expm1
Bağımsız değişkenin e tabanında üssü eksi 1 hesaplar.

```  
inline float expm1(float exponent) restrict(amp);


inline double expm1(double exponent) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`exponent`  
Üstel terimi *n* matematik ifadesindeki `e` <sup>n</sup>burada `e` ve Doğal logaritmanın tabanıdır.

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin e tabanında üssü eksi 1 döndürür.

##  <a name="expm1f"></a>  expm1f
Bağımsız değişkenin e tabanında üssü eksi 1 hesaplar.

```  
inline float expm1f(float exponent) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`exponent`  
Üstel terimi *n* matematik ifadesindeki `e` <sup>n</sup>burada `e` ve Doğal logaritmanın tabanıdır.

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin e tabanında üssü eksi 1 döndürür.

##  <a name="exp"></a>  exp
Tabanında üssü bağımsız değişkeni hesaplar.

```  
inline float exp(float _X) restrict(amp);


inline double exp(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Üstel bağımsız değişkenin e tabanında döndürür

##  <a name="expf"></a>  expf
Tabanında üssü bağımsız değişkeni hesaplar.

```  
inline float expf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Üstel bağımsız değişkenin e tabanında döndürür

##  <a name="exp2"></a>  exp2
2 tabanında üssünü bağımsız değişkeni hesaplar.

```  
inline float exp2(float _X) restrict(amp);


inline double exp2(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Üstel bağımsız değişkenin 2 tabanında döndürür

##  <a name="exp2f"></a>  exp2f
2 tabanında üssünü bağımsız değişkeni hesaplar.

```  
inline float exp2f(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Üstel bağımsız değişkenin 2 tabanında döndürür

##  <a name="fabs"></a>  fabs
Bağımsız değişkenin mutlak değerini döndürür

```  
inline float fabs(float _X) restrict(amp);


inline double fabs(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin mutlak değerini döndürür

##  <a name="fabsf"></a>  fabsf
Bağımsız değişkenin mutlak değerini döndürür

```  
inline float fabsf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin mutlak değerini döndürür

## <a name="fdim"></a> fdim
Bağımsız değişkenler arasındaki pozitif farkı hesaplar.
```  
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
*_X'İ*<br/>
Kayan nokta değeri *_Y*<br/>
Kayan nokta değeri


### <a name="return-value"></a>Dönüş Değeri
_X ve _Y _X ardından _Y büyükse arasındaki fark; Aksi takdirde, + 0.

## <a name="fdimf"></a> fdimf
Bağımsız değişkenler arasındaki pozitif farkı hesaplar.
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```
### <a name="parameters"></a>Parametreler
*_X'İ*<br/>
Kayan nokta değeri *_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ve _Y _X ardından _Y büyükse arasındaki fark; Aksi takdirde, + 0.

##  <a name="floor"></a>  Kat
Bağımsız değişkenin tabanını hesaplar.

```  
inline float floor(float _X) restrict(amp);


inline double floor(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Tam bir bağımsız değişken değerini döndürür

##  <a name="floorf"></a>  floorf
Bağımsız değişkenin tabanını hesaplar.

```  
inline float floorf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Tam bir bağımsız değişken değerini döndürür

## <a name="a-namefma-fma"></a><a name="fma"> FMA
Birinci ve ikinci belirtilen bağımsız değişken ürününü hesaplar, ardından sonuca üçüncü belirtilen bağımsız değişken ekler; Hesaplamanın tamamı tek bir işlem olarak gerçekleştirilir.
```
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
*_X'İ*<br/>
İlk kayan noktalı bağımsız değişken.
*_Y*<br/>
İkinci kayan noktalı bağımsız değişken.
*_Z*<br/>
Üçüncü kayan noktalı bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri
İfadenin sonucu (_X \* _Y) + _Z. Hesaplamanın tamamı tek bir işlem olarak gerçekleştirilir; diğer bir deyişle, alt ifadeler sonsuz duyarlık için hesaplanır ve yalnızca Nihai sonuç yuvarlanır.

## <a name="fmaf"></a> fmaf
Birinci ve ikinci belirtilen bağımsız değişken ürününü hesaplar, ardından sonuca üçüncü belirtilen bağımsız değişken ekler; Hesaplamanın tamamı tek bir işlem olarak gerçekleştirilir.
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```  
### <a name="parameters"></a>Parametreler
*_X'İ*<br/>
İlk kayan noktalı bağımsız değişken.
*_Y*<br/>
İkinci kayan noktalı bağımsız değişken.
*_Z*<br/>
Üçüncü kayan noktalı bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri
İfadenin sonucu (_X \* _Y) + _Z. Hesaplamanın tamamı tek bir işlem olarak gerçekleştirilir; diğer bir deyişle, alt ifadeler sonsuz duyarlık için hesaplanır ve yalnızca Nihai sonuç yuvarlanır.

##  <a name="fmax"></a>  fmax
Bağımsız değişkenlerin en büyük sayısal değerini belirler

```  
inline float fmax(
    float _X,
    float _Y) restrict(amp);


inline double fmax(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en büyük sayısal değerini döndürür

##  <a name="fmaxf"></a>  fmaxf
Bağımsız değişkenlerin en büyük sayısal değerini belirler

```  
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en büyük sayısal değerini döndürür

##  <a name="fmin"></a>  fmin
Bağımsız değişkenlerin en küçük sayısal değerini belirler

```  
inline float fmin(
    float _X,
    float _Y) restrict(amp);


inline double fmin(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en düşük sayısal değerini döndürür

##  <a name="fminf"></a>  fminf
Bağımsız değişkenlerin en küçük sayısal değerini belirler

```  
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en düşük sayısal değerini döndürür

##  <a name="fmod"></a>  fmod işlevi (C++ AMP)  
İlk belirtilen bağımsız ikinci belirtilen bağımsız değişkene bölünmesinden kalanı hesaplar.

```  
inline float fmod(
    float _X,
    float _Y) restrict(amp);


inline double fmod(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
İlk kayan noktalı bağımsız değişken.

`_Y`  
İkinci kayan noktalı bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri
Geri kalanında `_X` bölü `_Y`; diğer bir deyişle, değerini `_X`  -  `_Y` *n*burada *n* bir tamsayı olduğu gibi büyüklüğünü `_X`  -  `_Y` *n* büyüklüğünü'dan küçük `_Y`.

##  <a name="fmodf"></a>  fmodf
İlk belirtilen bağımsız ikinci belirtilen bağımsız değişkene bölünmesinden kalanı hesaplar.

```  
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
İlk kayan noktalı bağımsız değişken.

`_Y`  
İkinci kayan noktalı bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri
Geri kalanında `_X` bölü `_Y`; diğer bir deyişle, değerini `_X`  -  `_Y` *n*burada *n* bir tamsayı olduğu gibi büyüklüğünü `_X`  -  `_Y` *n* büyüklüğünü'dan küçük `_Y`.

##  <a name="fpclassify"></a>  fpclassify
Bağımsız değişken değeri NaN, sonsuz, normal, subnormal, sıfır olarak sınıflandırır

```  
inline int fpclassify(float _X) restrict(amp);


inline int fpclassify(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin değerini uygun sayı sınıflandırma makronun değerini döndürür.

##  <a name="frexp"></a>  frexp
_X'in Mantis ve alır.

```  
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);


inline double frexp(
    double _X,
    _Out_ int* _Exp) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Exp`  
_X'in tam sayı üssü kayan nokta değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri
Mantis _x'i döndürür

##  <a name="frexpf"></a>  frexpf
_X'in Mantis ve alır.

```  
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Exp`  
_X'in tam sayı üssü kayan nokta değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri
Mantis _x'i döndürür

##  <a name="hypot"></a>  hypot
_X ve _Y kareler toplamı karekökünü hesaplar.

```  
inline float hypot(
    float _X,
    float _Y) restrict(amp);


inline double hypot(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ve _Y kareler toplamı kare kökünü döndürür

##  <a name="hypotf"></a>  hypotf
_X ve _Y kareler toplamı karekökünü hesaplar.

```  
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ve _Y kareler toplamı kare kökünü döndürür

##  <a name="ilogb"></a>  ilogb
_X üs imzalı bir tamsayı ayıklayın.

```  
inline int ilogb(float _X) restrict(amp);


inline int ilogb(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X üs imzalı bir tamsayı döndürür.

##  <a name="ilogbf"></a>  ilogbf
_X üs imzalı bir tamsayı ayıklayın.

```  
inline int ilogbf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X üs imzalı bir tamsayı döndürür.

##  <a name="isfinite"></a>  isfinite
Bağımsız değişkenin sınırlı bir değer olup olmadığını belirler

```  
inline int isfinite(float _X) restrict(amp);


inline int isfinite(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Sınırlı bir değeri bağımsız değişkene sahiptir ve yalnızca, sıfır olmayan bir değer döndürür.

##  <a name="isinf"></a>  isinf
Bağımsız değişkenin bir sonsuzluk olup olmadığını belirler

```  
inline int isinf(float _X) restrict(amp);


inline int isinf(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişken sonsuz bir değere sahip ve yalnızca, sıfır olmayan bir değer döndürür.

##  <a name="isnan"></a>  isNaN
Bağımsız değişkenin bir NaN olup olmadığını belirler

```  
inline int isnan(float _X) restrict(amp);


inline int isnan(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin bir NaN değerini sahiptir ve yalnızca, sıfır olmayan bir değer döndürür.

##  <a name="isnormal"></a>  isnormal
Bağımsız değişken bir normal olup olmadığını belirler

```  
inline int isnormal(float _X) restrict(amp);


inline int isnormal(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Normal bir değeri bağımsız değişkene sahiptir ve yalnızca, sıfır olmayan bir değer döndürür.

##  <a name="ldexp"></a>  ldexp
Belirtilen Mantis ve üst değerinden bir gerçek sayı hesaplar.

```  
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);


inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri, Mantis

`_Exp`  
Tamsayı değeri, üs

### <a name="return-value"></a>Dönüş Değeri
_X'i döndürür \* 2 ^ _Exp

##  <a name="ldexpf"></a>  ldexpf
Belirtilen Mantis ve üst değerinden bir gerçek sayı hesaplar.

```  
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri, Mantis

`_Exp`  
Tamsayı değeri, üs

### <a name="return-value"></a>Dönüş Değeri
_X'i döndürür \* 2 ^ _Exp

##  <a name="lgamma"></a>  lgamma
Gama bağımsız değişkenin mutlak değerini doğal logaritmasını hesaplar.

```  
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);


inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Sign`  
İşaretini döndürür

### <a name="return-value"></a>Dönüş Değeri
Gama bağımsız değişkenin mutlak değerini doğal logaritmasını döndürür

##  <a name="lgammaf"></a>  lgammaf
Gama bağımsız değişkenin mutlak değerini doğal logaritmasını hesaplar.

```  
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Sign`  
İşaretini döndürür

### <a name="return-value"></a>Dönüş Değeri
Gama bağımsız değişkenin mutlak değerini doğal logaritmasını döndürür

##  <a name="log"></a>  Günlük
Bağımsız değişkenin e tabanında logaritmasını hesaplar.

```  
inline float log(float _X) restrict(amp);


inline double log(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin e tabanında logaritmasını döndürür

##  <a name="log10"></a>  log10
Bağımsız değişkenin 10 tabanında logaritmasını hesaplar.

```  
inline float log10(float _X) restrict(amp);


inline double log10(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin 10 tabanında logaritmasını döndürür

##  <a name="log10f"></a>  log10f
Bağımsız değişkenin 10 tabanında logaritmasını hesaplar.

```  
inline float log10f(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin 10 tabanında logaritmasını döndürür

##  <a name="log1p"></a>  log1p
1 ek bağımsız değişkenin e tabanında logaritmasını hesaplar.

```  
inline float log1p(float _X) restrict(amp);


inline double log1p(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
1 artı bağımsız değişkenin e tabanında logaritmasını döndürür

##  <a name="log1pf"></a>  log1pf
1 ek bağımsız değişkenin e tabanında logaritmasını hesaplar.

```  
inline float log1pf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
1 artı bağımsız değişkenin e tabanında logaritmasını döndürür

##  <a name="log2"></a>  log2
Bağımsız değişkenin 2 tabanlı logaritmasını hesaplar.

```  
inline float log2(float _X) restrict(amp);


inline double log2(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin 10 tabanında logaritmasını döndürür

##  <a name="log2f"></a>  log2f
Bağımsız değişkenin 2 tabanlı logaritmasını hesaplar.

```  
inline float log2f(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin 10 tabanında logaritmasını döndürür

##  <a name="logb"></a>  logb
_X üs kayan nokta biçiminde bir işaretli tamsayı değeri olarak ayıklar

```  
inline float logb(float _X) restrict(amp);


inline double logb(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X imzalı üssünü döndürür

##  <a name="logbf"></a>  logbf
_X üs kayan nokta biçiminde bir işaretli tamsayı değeri olarak ayıklar

```  
inline float logbf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X imzalı üssünü döndürür

##  <a name="logf"></a>  logf
Bağımsız değişkenin e tabanında logaritmasını hesaplar.

```  
inline float logf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin e tabanında logaritmasını döndürür

##  <a name="modf"></a>  modf
Belirtilen bağımsız değişkeni kesirli ve tamsayı bölümlere böler.

```  
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);


inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Iptr`  
[out] Tamsayı kısmını `_X`, kayan nokta değeri olarak.

### <a name="return-value"></a>Dönüş Değeri
İşaretli kesirli kısmını `_X`.

##  <a name="modff"></a>  modff
Belirtilen bağımsız değişkeni kesirli ve tamsayı bölümlere böler.

```  
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Iptr`  
Tamsayı kısmını `_X`, kayan nokta değeri olarak.

### <a name="return-value"></a>Dönüş Değeri
İşaretli kesirli kısmını döndürür `_X`.

##  <a name="nan"></a>  NaN
Sessiz bir NaN döndürür

```  
inline double nan(int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Kullanılabilir içeriğe sahip _X belirtilmişse sessiz bir NaN döndürür.

##  <a name="nanf"></a>  nanf
Sessiz bir NaN döndürür

```  
inline float nanf(int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Kullanılabilir içeriğe sahip _X belirtilmişse sessiz bir NaN döndürür.

##  <a name="nearbyint"></a>  nearbyint
Bağımsız değişken geçerli yuvarlama yönünü kullanarak kayan nokta biçiminde bir tamsayı değerine yuvarlanır.

```  
inline float nearbyint(float _X) restrict(amp);


inline double nearbyint(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Yuvarlak bir Integer değeri döndürür.

##  <a name="nearbyintf"></a>  nearbyintf
Bağımsız değişken geçerli yuvarlama yönünü kullanarak kayan nokta biçiminde bir tamsayı değerine yuvarlanır.

```  
inline float nearbyintf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Yuvarlak bir Integer değeri döndürür.

##  <a name="nextafter"></a>  nextafter
_X ardından _Y yönünde işlevin türü içinde sonraki gösterilebilir değeri belirlemek

```  
inline float nextafter(
    float _X,
    float _Y) restrict(amp);


inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ardından _Y yönünde işlevin türü içinde gösterilebilir sıradaki değerini döndürür

##  <a name="nextafterf"></a>  nextafterf
_X ardından _Y yönünde işlevin türü içinde sonraki gösterilebilir değeri belirlemek

```  
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X ardından _Y yönünde işlevin türü içinde gösterilebilir sıradaki değerini döndürür

##  <a name="phi"></a>  phı
Bağımsız değişkenin kümülatif dağılım fonksiyonunu döndürür

```  
inline float phi(float _X) restrict(amp);


inline double phi(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin kümülatif dağılım fonksiyonunu döndürür

##  <a name="phif"></a>  phif
Bağımsız değişkenin kümülatif dağılım fonksiyonunu döndürür

```  
inline float phif(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin kümülatif dağılım fonksiyonunu döndürür

##  <a name="pow"></a>  POW
_X ardından _Y üssünü hesaplar.

```  
inline float pow(
    float _X,
    float _Y) restrict(amp);


inline double pow(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri, temel

`_Y`  
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

##  <a name="powf"></a>  powf
_X ardından _Y üssünü hesaplar.

```  
inline float powf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri, temel

`_Y`  
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

##  <a name="probit"></a>  probit
Bağımsız değişkenin ters kümülatif dağılım fonksiyonunu döndürür

```  
inline float probit(float _X) restrict(amp);


inline double probit(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ters kümülatif dağılım fonksiyonunu döndürür

##  <a name="probitf"></a>  probitf
Bağımsız değişkenin ters kümülatif dağılım fonksiyonunu döndürür

```  
inline float probitf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin ters kümülatif dağılım fonksiyonunu döndürür

##  <a name="rcbrt"></a>  rcbrt
Bağımsız değişkenin küp kökünün karşıtını döndürür

```  
inline float rcbrt(float _X) restrict(amp);


inline double rcbrt(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin küp kökünün karşıtını döndürür

##  <a name="rcbrtf"></a>  rcbrtf
Bağımsız değişkenin küp kökünün karşıtını döndürür

```  
inline float rcbrtf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin küp kökünün karşıtını döndürür

##  <a name="remainder"></a>  Kalan
Kalanı hesaplar: _X REM _Y

```  
inline float remainder(
    float _X,
    float _Y) restrict(amp);


inline double remainder(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X REM _Y döndürür

##  <a name="remainderf"></a>  remainderf
Kalanı hesaplar: _X REM _Y

```  
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X REM _Y döndürür

##  <a name="remquo"></a>  remquo
İlk belirtilen bağımsız ikinci belirtilen bağımsız değişkene bölünmesinden kalanı hesaplar. Ayrıca mantisinin ikinci belirtilen bağımsız değişken bölünmüş ilk belirtilen bağımsız değişkenin mantisinin kalanını hesaplar ve üçüncü bağımsız değişkende belirtilen konumu kullanarak bölümü döndürür.

```  
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
`_X`  
İlk kayan noktalı bağımsız değişken.

`_Y`  
İkinci kayan noktalı bağımsız değişken.

`_Quo`  
[out] Kesirli bitlerinin kalanını döndürmek için kullanılan bir tamsayı adresi `_X` kesirli bitleri tarafından ayrılmış `_Y`.

### <a name="return-value"></a>Dönüş Değeri
Kalanı döndürür `_X` bölü `_Y`.

##  <a name="remquof"></a>  remquof
İlk belirtilen bağımsız ikinci belirtilen bağımsız değişkene bölünmesinden kalanı hesaplar. Ayrıca mantisinin ikinci belirtilen bağımsız değişken bölünmüş ilk belirtilen bağımsız değişkenin mantisinin kalanını hesaplar ve üçüncü bağımsız değişkende belirtilen konumu kullanarak bölümü döndürür.

```  
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
İlk kayan noktalı bağımsız değişken.

`_Y`  
İkinci kayan noktalı bağımsız değişken.

`_Quo`  
[out] Kesirli bitlerinin kalanını döndürmek için kullanılan bir tamsayı adresi `_X` kesirli bitleri tarafından ayrılmış `_Y`.

### <a name="return-value"></a>Dönüş Değeri
Kalanı döndürür `_X` bölü `_Y`.

##  <a name="round"></a>  Yuvarlak
_X'i en yakın tamsayıya yuvarlar

```  
inline float round(float _X) restrict(amp);


inline double round(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'ın en yakın tamsayıyı döndürür

##  <a name="roundf"></a>  roundf
_X'i en yakın tamsayıya yuvarlar

```  
inline float roundf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'ın en yakın tamsayıyı döndürür

##  <a name="rsqrt"></a>  rsqrt
Bağımsız değişkenin kare kökünün karşıtını döndürür

```  
inline float rsqrt(float _X) restrict(amp);


inline double rsqrt(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin kare kökünün karşıtını döndürür

##  <a name="rsqrtf"></a>  rsqrtf
Bağımsız değişkenin kare kökünün karşıtını döndürür

```  
inline float rsqrtf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin kare kökünün karşıtını döndürür

##  <a name="scalb"></a>  scalb
Flt_radıx tarafından _x'i güç _Y çarpar.

```  
inline float scalb(
    float _X,
    float _Y) restrict(amp);


inline double scalb(
    double _X,
    double _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'i döndürür \* (flt_radıx ^ _Y)  

##  <a name="scalbf"></a>  scalbf
Flt_radıx tarafından _x'i güç _Y çarpar.

```  
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'i döndürür \* (flt_radıx ^ _Y)  

##  <a name="scalbn"></a>  scalbn
Flt_radıx tarafından _x'i güç _Y çarpar.

```  
inline float scalbn(
    float _X,
    int _Y) restrict(amp);


inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
_X'i döndürür \* (flt_radıx ^ _Y)  

##  <a name="scalbnf"></a>  scalbnf
Flt_radıx tarafından _x'i güç _Y çarpar.

```  
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_Y`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
_X'i döndürür \* (flt_radıx ^ _Y)  

##  <a name="signbit"></a>  signbit
_X'in işaretini negatif olup olmadığını belirler

```  
inline int signbit(float _X) restrict(amp);


inline int signbit(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'in işaretini negatif ise ve yalnızca, sıfır olmayan bir değer döndürür.

##  <a name="signbitf"></a>  signbitf
_X'in işaretini negatif olup olmadığını belirler

```  
inline int signbitf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'in işaretini negatif ise ve yalnızca, sıfır olmayan bir değer döndürür.

##  <a name="sin"></a>  Sin
Bağımsız değişkenin sinüs değeri hesaplar

```  
inline float sin(float _X) restrict(amp);


inline double sin(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin sinüs değerini döndürür

##  <a name="sinf"></a>  sinf
Bağımsız değişkenin sinüs değeri hesaplar

```  
inline float sinf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin sinüs değerini döndürür

##  <a name="sincos"></a>  sincos
_X'in Sinüs ve Kosinüs değerini hesaplar.

```  
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
`_X`  
Kayan nokta değeri

`_S`  
_X'in sinüs değerini döndürür

`_C`  
_X Kosinüs değerini döndürür

##  <a name="sincosf"></a>  sincosf
_X'in Sinüs ve Kosinüs değerini hesaplar.

```  
inline void sincosf(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

`_S`  
_X'in sinüs değerini döndürür

`_C`  
_X Kosinüs değerini döndürür

##  <a name="sinh"></a>  SİNH
Bağımsız değişkenin hiperbolik sinüs değerini hesaplar.

```  
inline float sinh(float _X) restrict(amp);


inline double sinh(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin hiperbolik sinüs değerini döndürür

##  <a name="sinhf"></a>  sinhf
Bağımsız değişkenin hiperbolik sinüs değerini hesaplar.

```  
inline float sinhf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin hiperbolik sinüs değerini döndürür

##  <a name="sinpi"></a>  sinpi
Pi sinüs değerini hesaplar \* _X

```  
inline float sinpi(float _X) restrict(amp);


inline double sinpi(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Pi sinüs değerini döndürür \* _X

##  <a name="sinpif"></a>  sinpif
Pi sinüs değerini hesaplar \* _X

```  
inline float sinpif(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Pi sinüs değerini döndürür \* _X

##  <a name="sqrt"></a>  Sqrt
Bağımsız değişkenin squre kök hesaplar

```  
inline float sqrt(float _X) restrict(amp);


inline double sqrt(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin squre kökünü döndürür

##  <a name="sqrtf"></a>  sqrtf
Bağımsız değişkenin squre kök hesaplar

```  
inline float sqrtf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin squre kökünü döndürür

##  <a name="tan"></a>  tan
Bağımsız değişkenin tanjant değerini hesaplar.

```  
inline float tan(float _X) restrict(amp);


inline double tan(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin tanjant değerini döndürür

##  <a name="tanf"></a>  tanf
Bağımsız değişkenin tanjant değerini hesaplar.

```  
inline float tanf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin tanjant değerini döndürür

##  <a name="tanh"></a>  TANH
Bağımsız değişkenin hiperbolik tanjant değerini hesaplar.

```  
inline float tanh(float _X) restrict(amp);


inline double tanh(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin hiperbolik tanjant değerini döndürür

##  <a name="tanhf"></a>  tanhf
Bağımsız değişkenin hiperbolik tanjant değerini hesaplar.

```  
inline float tanhf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin hiperbolik tanjant değerini döndürür

##  <a name="tanpi"></a>  tanpi
Pi tanjant değerini hesaplar \* _X

```  
inline float tanpi(float _X) restrict(amp);


inline double tanpi(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Pi tanjant değerini döndürür \* _X

##  <a name="tanpif"></a>  tanpif
Pi tanjant değerini hesaplar \* _X

```  
inline float tanpif(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Pi tanjant değerini döndürür \* _X

##  <a name="tgamma"></a>  tgamma
Gama fonksiyonu _x hesaplar

```  
inline float tgamma(float _X) restrict(amp);


inline double tgamma(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Gama fonksiyonu _x sonucunu döndürür

##  <a name="tgammaf"></a>  tgammaf
Gama fonksiyonu _x hesaplar

```  
inline float tgammaf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Gama fonksiyonu _x sonucunu döndürür

##  <a name="trunc"></a>  trunc
Bağımsız değişkeni tam sayı bileşenine keser

```  
inline float trunc(float _X) restrict(amp);


inline double trunc(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişken tamsayı bileşenini döndürür

##  <a name="truncf"></a>  truncf
Bağımsız değişkeni tam sayı bileşenine keser

```  
inline float truncf(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişken tamsayı bileşenini döndürür

## <a name="see-also"></a>Ayrıca Bkz.
[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)
