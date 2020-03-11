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
ms.openlocfilehash: 3652e02d9f3ff7b09ee7334dba20188e40344cb5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865476"
---
# <a name="concurrencyfast_math-namespace-functions"></a>Concurrency::fast_math ad alanı işlevleri

||||
|-|-|-|
|[acos](#acos)|[acosf](#acosf)|[Asin](#asin)|
|[asinf](#asinf)|[atan](#atan)|[atan2](#atan2)|
|[atan2f](#atan2f)|[atanf](#atanf)|[Ceil](#ceil)|
|[ceilf](#ceilf)|[cos](#cos)|[cosf](#cosf)|
|[Cosh](#cosh)|[coshf](#coshf)|[exp](#exp)|
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|
|[fabs](#fabs)|[fabsf](#fabsf)|[sını](#floor)|
|[floorf](#floorf)|[Fmax](#fmax)|[fmaxf](#fmaxf)|
|[fmin](#fmin)|[fminf](#fminf)|[FMOD](#fmod)|
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|
|[isFinite](#isfinite)|[isinf](#isinf)|[isNaN](#isnan)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[açmasını](#log)|
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[POW](#pow)|[powf](#powf)|
|[gidiş](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|
|[sin](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|
|[sinf](#sinf)|[sinh](#sinh)|[sinhf](#sinhf)|
|[k](#sqrt)|[sqrtf](#sqrtf)|[Başlangıçtan](#tan)|
|[tanf](#tanf)|[tanh](#tanh)|[tanhf](#tanhf)|
|[TRUNC](#trunc)|[truncf](#truncf)|

## <a name="acos"></a>acos

Bağımsız değişkenin arkkosinüsünü hesaplar

```cpp
inline float acos(float _X) restrict(amp);
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

## <a name="asin"></a>Asin

Bağımsız değişkenin arksinüsünü hesaplar

```cpp
inline float asin(float _X) restrict(amp);
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

## <a name="atan"></a>atan

Bağımsız değişkenin arktanjantını hesaplar

```cpp
inline float atan(float _X) restrict(amp);
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

## <a name="ceil"></a>Ceil

Bağımsız değişkenin tavan sayısını hesaplar

```cpp
inline float ceil(float _X) restrict(amp);
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

## <a name="cos"></a>cos

Bağımsız değişkenin kosinüsünü hesaplar

```cpp
inline float cos(float _X) restrict(amp);
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
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin hiperbolik kosinüs değerini döndürür

## <a name="exp"></a>exp

Bağımsız değişkenin taban-e üssünü hesaplar

```cpp
inline float exp(float _X) restrict(amp);
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

## <a name="fabs"></a>fabs

Bağımsız değişkenin mutlak değerini döndürür

```cpp
inline float fabs(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

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

## <a name="floor"></a>sını

Bağımsız değişkenin katsını hesaplar

```cpp
inline float floor(float _X) restrict(amp);
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

## <a name="fmax"></a>Fmax

Bağımsız değişkenlerin en büyük sayısal değerini belirleme

```cpp
inline float max(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

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
inline float min(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

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

## <a name="fmod"></a>FMOD

_X/_Y kayan nokta kalanını hesaplar

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X/_Y kayan nokta kalanını döndürür

## <a name="fmodf"></a>fmodf

_X/_Y kayan nokta kalanını hesaplar.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Y*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X/_Y kayan nokta kalanını döndürür

## <a name="frexp"></a>frexp

_X Mantis ve üstürünü alır

```cpp
inline float frexp(
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

## <a name="isfinite"></a>isFinite

Bağımsız değişkenin sonlu bir değere sahip olup olmadığını belirler

```cpp
inline int isfinite(float _X) restrict(amp);
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
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değer döndürür ve yalnızca bağımsız değişkenin bir NaN değeri varsa

## <a name="ldexp"></a>ldexp

Mantis ve üs öğesinden gerçek bir sayıyı hesaplar

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, mentissa

*_Exp*<br/>
Tamsayı üssü

### <a name="return-value"></a>Dönüş Değeri

_X \* 2 ^ _Exp döndürür

## <a name="ldexpf"></a>ldexpf

Mantis ve üs öğesinden gerçek bir sayıyı hesaplar

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, mentissa

*_Exp*<br/>
Tamsayı üssü

### <a name="return-value"></a>Dönüş Değeri

_X \* 2 ^ _Exp döndürür

## <a name="log"></a>açmasını

Bağımsız değişkenin taban-e logaritmasını hesaplar

```cpp
inline float log(float _X) restrict(amp);
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

## <a name="log2"></a>log2

Bağımsız değişkenin 2 tabanında logaritmasını hesaplar

```cpp
inline float log2(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin 2 tabanında logaritmasını döndürür

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

_X kesirli ve tamsayı bölümlerine böler.

```cpp
inline float modf(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Ip*<br/>
Değerin tamsayı kısmını alır

### <a name="return-value"></a>Dönüş Değeri

_X işaretli kesirli kısmını döndürür

## <a name="modff"></a>modff

_X kesirli ve tamsayı bölümlerine böler.

```cpp
inline float modff(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

*_Ip*<br/>
Değerin tamsayı kısmını alır

### <a name="return-value"></a>Dönüş Değeri

_X işaretli kesirli kısmını döndürür

## <a name="pow"></a>POW

_Y kuvvetine _X hesaplar

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri, taban

*_Y*<br/>
Kayan nokta değeri, üs

### <a name="return-value"></a>Dönüş Değeri

_X, _Y kuvvetinin değerini döndürür

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

## <a name="round"></a>gidiş

_X en yakın tamsayıya yuvarlar

```cpp
inline float round(float _X) restrict(amp);
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

## <a name="signbit"></a>signbit

_X işaretinin negatif olup olmadığını belirler

```cpp
inline int signbit(float _X) restrict(amp);
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
    float* _S,
    float* _C) restrict(amp);
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
    float* _S,
    float* _C) restrict(amp);
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

## <a name="sqrt"></a>k

Bağımsız değişkenin Squre kökünü hesaplar

```cpp
inline float sqrt(float _X) restrict(amp);
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

## <a name="trunc"></a>TRUNC

Bağımsız değişkeni tamsayı bileşene kırpar

```cpp
inline float trunc(float _X) restrict(amp);
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

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp_math. h **ad alanı:** concurrency:: fast_math

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)
