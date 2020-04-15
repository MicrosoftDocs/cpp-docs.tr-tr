---
title: Concurrency::fast_math ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math::acos
- amp_math/Concurrency::fast_math::asin
- amp_math/Concurrency::fast_math::asinf
- amp_math/Concurrency::fast_math::atan2
- amp_math/Concurrency::fast_math::atan2f
- amp_math/Concurrency::fast_math::ceil
- amp_math/Concurrency::fast_math::ceilf
- amp_math/Concurrency::fast_math::cosf
- amp_math/Concurrency::fast_math::cosh
- amp_math/Concurrency::fast_math::exp
- amp_math/Concurrency::fast_math::exp2
- amp_math/Concurrency::fast_math::expf
- amp_math/Concurrency::fast_math::fabs
- amp_math/Concurrency::fast_math::floor
- amp_math/Concurrency::fast_math::floorf
- amp_math/Concurrency::fast_math::fmaxf
- amp_math/Concurrency::fast_math::fmin
- amp_math/Concurrency::fast_math::fmod
- amp_math/Concurrency::fast_math::fmodf
- amp_math/Concurrency::fast_math::frexpf
- amp_math/Concurrency::fast_math::isfinite
- amp_math/Concurrency::fast_math::isnan
- amp_math/Concurrency::fast_math::ldexp
- amp_math/Concurrency::fast_math::log
- amp_math/Concurrency::fast_math::log10
- amp_math/Concurrency::fast_math::log2
- amp_math/Concurrency::fast_math::log2f
- amp_math/Concurrency::fast_math::modf
- amp_math/Concurrency::fast_math::modff
- amp_math/Concurrency::fast_math::powf
- amp_math/Concurrency::fast_math::round
- amp_math/Concurrency::fast_math::rsqrt
- amp_math/Concurrency::fast_math::rsqrtf
- amp_math/Concurrency::fast_math::signbitf
- amp_math/Concurrency::fast_math::sin
- amp_math/Concurrency::fast_math::sincosf
- amp_math/Concurrency::fast_math::sinf
- amp_math/Concurrency::fast_math::sinhf
- amp_math/Concurrency::fast_math::sqrt
- amp_math/Concurrency::fast_math::tan
- amp_math/Concurrency::fast_math::tanf
- amp_math/Concurrency::fast_math::tanhf
- amp_math/Concurrency::fast_math::trunc
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
ms.openlocfilehash: cd0882b072cfe26cd83e63024ae6837dc962ebf9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376403"
---
# <a name="concurrencyfast_math-namespace-functions"></a>Concurrency::fast_math ad alanı işlevleri

||||
|-|-|-|
|[Acos](#acos)|[acosf](#acosf)|[Asin](#asin)|
|[asinf](#asinf)|[atan](#atan)|[atan2](#atan2)|
|[atan2f](#atan2f)|[atanf](#atanf)|[Ceil](#ceil)|
|[ceilf](#ceilf)|[Çünkü](#cos)|[cosf](#cosf)|
|[Cosh](#cosh)|[coşf](#coshf)|[Exp](#exp)|
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|
|[Faruk](#fabs)|[fabsf](#fabsf)|[Kat](#floor)|
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|
|[fmin](#fmin)|[fminf](#fminf)|[Fmod](#fmod)|
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|
|[Isfinite](#isfinite)|[isinf](#isinf)|[ısnan](#isnan)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[Günlük](#log)|
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[Pow](#pow)|[powf](#powf)|
|[Yuvarlak](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|
|[Günah](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|
|[sinf](#sinf)|[Sinh](#sinh)|[sinhf](#sinhf)|
|[Karekök](#sqrt)|[sqrtf](#sqrtf)|[tan](#tan)|
|[tanf](#tanf)|[Tanh](#tanh)|[tanhf](#tanhf)|
|[Trunc](#trunc)|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>Acos

Bağımsız değişkenin arccosine hesaplar

```cpp
inline float acos(float _X) restrict(amp);
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

## <a name="asin"></a><a name="asin"></a>Asin

Bağımsız değişkenin arcsine hesaplar

```cpp
inline float asin(float _X) restrict(amp);
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

## <a name="atan"></a><a name="atan"></a>atan

Bağımsız değişkenin arctantını hesaplar

```cpp
inline float atan(float _X) restrict(amp);
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

## <a name="ceil"></a><a name="ceil"></a>Ceil

Bağımsız değişkenin tavanını hesaplar

```cpp
inline float ceil(float _X) restrict(amp);
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

## <a name="cos"></a><a name="cos"></a>Çünkü

Bağımsız değişkenin kosinüsünün hesaplar

```cpp
inline float cos(float _X) restrict(amp);
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
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik kosinüs değerini verir

## <a name="exp"></a><a name="exp"></a>Exp

Bağımsız değişkenin taban-e üstel değerini hesaplar

```cpp
inline float exp(float _X) restrict(amp);
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

## <a name="fabs"></a><a name="fabs"></a>Faruk

Bağımsız değişkenin mutlak değerini verir

```cpp
inline float fabs(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

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

## <a name="floor"></a><a name="floor"></a>Kat

Bağımsız değişkenin zeminini hesaplar

```cpp
inline float floor(float _X) restrict(amp);
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

## <a name="fmax"></a><a name="fmax"></a>fmax

Bağımsız değişkenlerin maksimum sayısal değerini belirleme

```cpp
inline float max(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

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
inline float min(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

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

## <a name="fmod"></a><a name="fmod"></a>Fmod

_X/_Y kayan nokta kalanını hesaplar

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X/_Y kayan nokta kalanını verir

## <a name="fmodf"></a><a name="fmodf"></a>fmodf

_X/_Y kayan nokta kalanını hesaplar.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X/_Y kayan nokta kalanını verir

## <a name="frexp"></a><a name="frexp"></a>frexp

mantisve üs alır _X

```cpp
inline float frexp(
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

## <a name="isfinite"></a><a name="isfinite"></a>Isfinite

Bağımsız değişkenin sonlu bir değeri olup olmadığını belirler

```cpp
inline int isfinite(float _X) restrict(amp);
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
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin NaN değeri varsa ve yalnızca sıfır olmayan bir değer verir

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

Mantisve üsden gerçek bir sayıyı hesaplar

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, mentissa

*_Exp*<br/>
İnteger üs

### <a name="return-value"></a>Dönüş Değeri

2^_Exp_X \* döndürür

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

Mantisve üsden gerçek bir sayıyı hesaplar

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, mentissa

*_Exp*<br/>
İnteger üs

### <a name="return-value"></a>Dönüş Değeri

2^_Exp_X \* döndürür

## <a name="log"></a><a name="log"></a>Günlük

Bağımsız değişkenin temel-e logaritmasını hesaplar

```cpp
inline float log(float _X) restrict(amp);
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

## <a name="log2"></a><a name="log2"></a>log2

Bağımsız değişkenin taban-2 logaritmasını hesaplar

```cpp
inline float log2(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin taban-2 logaritmasını verir

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

_X kesirli ve tamsayı parçalarına böler.

```cpp
inline float modf(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Ip*<br/>
Değerin bir kısmını alıcı

### <a name="return-value"></a>Dönüş Değeri

_X'nin imzalı kesirli kısmını verir

## <a name="modff"></a><a name="modff"></a>modff

_X kesirli ve tamsayı parçalarına böler.

```cpp
inline float modff(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

*_Ip*<br/>
Değerin bir kısmını alıcı

### <a name="return-value"></a>Dönüş Değeri

_X'nin imzalı kesirli kısmını verir

## <a name="pow"></a><a name="pow"></a>Pow

_Y gücüne yükseltilen _X hesaplar

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri, taban

*_Y*<br/>
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

_Y gücüne yükseltilen _X değerini verir

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

## <a name="round"></a><a name="round"></a>Yuvarlak

_X en yakın tamsayıya yuvarlar

```cpp
inline float round(float _X) restrict(amp);
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

## <a name="signbit"></a><a name="signbit"></a>signbit

_X işaretinin negatif olup olmadığını belirler

```cpp
inline int signbit(float _X) restrict(amp);
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
    float* _S,
    float* _C) restrict(amp);
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
    float* _S,
    float* _C) restrict(amp);
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

## <a name="sqrt"></a><a name="sqrt"></a>Karekök

Bağımsız değişkenin squre kökünü hesaplar

```cpp
inline float sqrt(float _X) restrict(amp);
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

## <a name="trunc"></a><a name="trunc"></a>Trunc

Bağımsız değişkeni sonda bileşenine truncates

```cpp
inline float trunc(float _X) restrict(amp);
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

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp_math.h **Ad alanı:** Eşzamanlılık::fast_math

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)
