---
title: "CONCURRENCY::fast_math ad alanı işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 406f92d4a13502ed784936398070f1b4a7b4eb95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="concurrencyfastmath-namespace-functions"></a>CONCURRENCY::fast_math ad alanı işlevleri
||||  
|-|-|-|  
|[ACOS](#acos)|[acosf](#acosf)|[asin](#asin)|  
|[asinf](#asinf)|[atan](#atan)|[ATAN2](#atan2)|  
|[atan2f](#atan2f)|[atanf](#atanf)|[ceil](#ceil)|  
|[ceilf](#ceilf)|[cos](#cos)|[cosf](#cosf)|  
|[COSH](#cosh)|[coshf](#coshf)|[exp](#exp)|  
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|  
|[fabs](#fabs)|[fabsf](#fabsf)|[Kat](#floor)|  
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|  
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|  
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|  
|[isfinite](#isfinite)|[isinf](#isinf)|[isNaN](#isnan)|  
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[Günlük](#log)|  
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|  
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|  
|[modff](#modff)|[POW](#pow)|[powf](#powf)|  
|[yuvarlamak](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|  
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|  
|[sin](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|  
|[sinf](#sinf)|[SİNH](#sinh)|[sinhf](#sinhf)|  
|[Sqrt](#sqrt)|[sqrtf](#sqrtf)|[tan](#tan)|  
|[tanf](#tanf)|[TANH](#tanh)|[tanhf](#tanhf)|  
|[trunc](#trunc)|[truncf](#truncf)|  
  
##  <a name="acos"></a>ACOS  
 Bağımsız değişken arkkosinüsünü hesaplar  
  
```  
inline float acos(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken arkkosinüsünü değerini döndürür  
  
##  <a name="acosf"></a>acosf  
 Bağımsız değişken arkkosinüsünü hesaplar  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken arkkosinüsünü değerini döndürür  
  
##  <a name="asin"></a>asin  
 Bağımsız değişken arksinüsünü hesaplar  
  
```  
inline float asin(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken arksinüsünü değerini döndürür  
  
##  <a name="asinf"></a>asinf  
 Bağımsız değişken arksinüsünü hesaplar  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken arksinüsünü değerini döndürür  
  
##  <a name="atan"></a>atan  
 Bağımsız değişken tanjantını hesaplar  
  
```  
inline float atan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken arktanjantını değerini döndürür  
  
##  <a name="atan2"></a>ATAN2  
 _Y/_X tanjantını hesaplar  
  
```  
inline float atan2(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Y`  
 Kayan nokta değeri  
  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 _Y/_X arktanjantını değerini döndürür  
  
##  <a name="atan2f"></a>atan2f  
 _Y/_X tanjantını hesaplar  
  
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
 _Y/_X arktanjantını değerini döndürür  
  
##  <a name="atanf"></a>atanf  
 Bağımsız değişken tanjantını hesaplar  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken arktanjantını değerini döndürür  
  
##  <a name="ceil"></a>ceil  
 Bağımsız değişken tavan hesaplar  
  
```  
inline float ceil(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken tavan döndürür  
  
##  <a name="ceilf"></a>ceilf  
 Bağımsız değişken tavan hesaplar  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken tavan döndürür  
  
##  <a name="cosf"></a>cosf  
 Bağımsız değişken kosinüsünü hesaplar  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken kosinüsünü değerini döndürür  
  
##  <a name="coshf"></a>coshf  
 Bağımsız değişkenin hiperbolik kosinüsünü değeri hesaplar  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken hiperbolik kosinüsünü değerini döndürür  
  
##  <a name="cos"></a>cos  
 Bağımsız değişken kosinüsünü hesaplar  
  
```  
inline float cos(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken kosinüsünü değerini döndürür  
  
##  <a name="cosh"></a>COSH  
 Bağımsız değişkenin hiperbolik kosinüsünü değeri hesaplar  
  
```  
inline float cosh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken hiperbolik kosinüsünü değerini döndürür  
  
##  <a name="exp"></a>exp  
 E tabanında bağımsız değişkeni üstel hesaplar  
  
```  
inline float exp(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 E tabanında bağımsız değişkenin üstel döndürür  
  
##  <a name="exp2"></a>exp2  
 Base-2 bağımsız değişkeni üstel hesaplar  
  
```  
inline float exp2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Base-2 bağımsız değişkeni üstel döndürür  
  
##  <a name="exp2f"></a>exp2f  
 Base-2 bağımsız değişkeni üstel hesaplar  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Base-2 bağımsız değişkeni üstel döndürür  
  
##  <a name="expf"></a>expf  
 E tabanında bağımsız değişkeni üstel hesaplar  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 E tabanında bağımsız değişkenin üstel döndürür  
  
##  <a name="fabs"></a>fabs  
 Bağımsız değişken mutlak değerini döndürür  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken mutlak değerini döndürür  
  
##  <a name="fabsf"></a>fabsf  
 Bağımsız değişken mutlak değerini döndürür  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken mutlak değerini döndürür  
  
##  <a name="floor"></a>Kat  
 Bağımsız değişken kat hesaplar  
  
```  
inline float floor(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken kat döndürür  
  
##  <a name="floorf"></a>floorf  
 Bağımsız değişken kat hesaplar  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken kat döndürür  
  
##  <a name="fmax"></a>fmax  
 Bağımsız değişkenler en büyük sayısal değerini belirleme  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
 `_Y`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkenler en büyük sayısal değeri döndürür  
  
##  <a name="fmaxf"></a>fmaxf  
 Bağımsız değişkenler en büyük sayısal değerini belirleme  
  
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
 Bağımsız değişkenler en büyük sayısal değeri döndürür  
  
##  <a name="fmin"></a>fmin  
 Bağımsız değişkenler en küçük sayısal değeri belirleme  
  
```  
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
 `_Y`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkenler en küçük sayısal değeri döndürür  
  
##  <a name="fminf"></a>fminf  
 Bağımsız değişkenler en küçük sayısal değeri belirleme  
  
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
 Bağımsız değişkenler en küçük sayısal değeri döndürür  
  
##  <a name="fmod"></a>fmod  
 Kayan nokta _X/_Y kalanı hesaplar  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_Y`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayan nokta _X/_Y kalanı döndürür  
  
##  <a name="fmodf"></a>fmodf  
 Kayan nokta _X/_Y kalanı hesaplar.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_Y`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayan nokta _X/_Y kalanı döndürür  
  
##  <a name="frexp"></a>frexp  
 Mantis ve üs _X, alır  
  
```  
inline float frexp(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_Exp`  
 Kayan nokta değeri _X tamsayı üs döndürür  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mantis _X döndürür  
  
##  <a name="frexpf"></a>frexpf  
 Mantis ve üs _X, alır  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_Exp`  
 Kayan nokta değeri _X tamsayı üs döndürür  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mantis _X döndürür  
  
##  <a name="isfinite"></a>isfinite  
 Bağımsız değişken sınırlı bir değere sahip olup olmadığını belirler  
  
```  
inline int isfinite(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken sınırlı bir değere sahip ve yalnızca, sıfır olmayan bir değer döndürür  
  
##  <a name="isinf"></a>isinf  
 Bağımsız değişkeni bir sonsuzluk olup olmadığını belirler  
  
```  
inline int isinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken sonsuz bir değere sahip ve yalnızca, sıfır olmayan bir değer döndürür  
  
##  <a name="isnan"></a>isNaN  
 Bağımsız değişkeni bir NaN olup olmadığını belirler  
  
```  
inline int isnan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken NaN değerine sahip ve yalnızca, sıfır olmayan bir değer döndürür  
  
##  <a name="ldexp"></a>ldexp  
 Mantis ve üs arasında bir gerçek sayı hesaplar  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri, mentissa  
  
 `_Exp`  
 Tamsayı üs  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür _X * 2 ^ _Exp  
  
##  <a name="ldexpf"></a>ldexpf  
 Mantis ve üs arasında bir gerçek sayı hesaplar  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri, mentissa  
  
 `_Exp`  
 Tamsayı üs  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür _X * 2 ^ _Exp  
  
##  <a name="log"></a>Günlük  
 Bağımsız değişken e tabanında logaritmasını hesaplar  
  
```  
inline float log(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken e tabanında logaritmasını döndürür  
  
##  <a name="log10"></a>log10  
 Bağımsız değişken 10 tabanında logaritmasını hesaplar  
  
```  
inline float log10(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken 10 tabanında logaritmasını döndürür  
  
##  <a name="log10f"></a>log10f  
 Bağımsız değişken 10 tabanında logaritmasını hesaplar  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken 10 tabanında logaritmasını döndürür  
  
##  <a name="log2"></a>log2  
 Bağımsız değişken 2 tabanındaki logaritmasını hesaplar  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken 2 tabanındaki logaritmasını döndürür  
  
##  <a name="log2f"></a>log2f  
 Bağımsız değişken 2 tabanındaki logaritmasını hesaplar  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken 10 tabanında logaritmasını döndürür  
  
##  <a name="logf"></a>logf  
 Bağımsız değişken e tabanında logaritmasını hesaplar  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken e tabanında logaritmasını döndürür  
  
##  <a name="modf"></a>modf  
 Kesirli içine _X ve tamsayı bölümleri böler.  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_Ip`  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X imzalı kesirli kısmını döndürür  
  
##  <a name="modff"></a>modff  
 Kesirli içine _X ve tamsayı bölümleri böler.  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_Ip`  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X imzalı kesirli kısmını döndürür  
  
##  <a name="pow"></a>POW  
 Üssü _Y _X hesaplar  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri, taban  
  
 `_Y`  
 Kayan nokta değeri, üs  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X _Y üssüne yükseltilmiş değerini döndürür  
  
##  <a name="powf"></a>powf  
 Üssü _Y _X hesaplar  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri, taban  
  
 `_Y`  
 Kayan nokta değeri, üs  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="round"></a>yuvarlamak  
 _X en yakın tamsayıya yuvarlar  
  
```  
inline float round(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X'en yakın tamsayıya döndürür  
  
##  <a name="roundf"></a>roundf  
 _X en yakın tamsayıya yuvarlar  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X'en yakın tamsayıya döndürür  
  
##  <a name="rsqrt"></a>rsqrt  
 Devrik değerlerin bağımsız değişkeni'nin kare kökünü döndürür  
  
```  
inline float rsqrt(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Devrik değerlerin bağımsız değişkeni'nin kare kökünü döndürür  
  
##  <a name="rsqrtf"></a>rsqrtf  
 Devrik değerlerin bağımsız değişkeni'nin kare kökünü döndürür  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Devrik değerlerin bağımsız değişkeni'nin kare kökünü döndürür  
  
##  <a name="signbit"></a>signbit  
 _X oturum negatif olup olmadığını belirler  
  
```  
inline int signbit(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X oturum varsa ve yalnızca negatifse sıfır olmayan bir değer döndürür  
  
##  <a name="signbitf"></a>signbitf  
 _X oturum negatif olup olmadığını belirler  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X oturum varsa ve yalnızca negatifse sıfır olmayan bir değer döndürür  
  
##  <a name="sin"></a>sin  
 Bağımsız değişkenin sinüsünü değeri hesaplar  
  
```  
inline float sin(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken sinüsünü değerini döndürür  
  
##  <a name="sinf"></a>sinf  
 Bağımsız değişkenin sinüsünü değeri hesaplar  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken sinüsünü değerini döndürür  
  
##  <a name="sincos"></a>sincos  
 _X Sinüs ve Kosinüs değerini hesaplar  
  
```  
inline void sincos(
    float _X,  
    float* _S,  
    float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_S`  
 _X sinüsünü değerini döndürür  
  
 `_C`  
 _X kosinüsünü değerini döndürür  
  
##  <a name="sincosf"></a>sincosf  
 _X Sinüs ve Kosinüs değerini hesaplar  
  
```  
inline void sincosf(
    float _X,  
    float* _S,  
    float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
 `_S`  
 _X sinüsünü değerini döndürür  
  
 `_C`  
 _X kosinüsünü değerini döndürür  
  
##  <a name="sinh"></a>SİNH  
 Bağımsız değişkenin hiperbolik sinüsünü değeri hesaplar  
  
```  
inline float sinh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken hiperbolik sinüsünü değerini döndürür  
  
##  <a name="sinhf"></a>sinhf  
 Bağımsız değişkenin hiperbolik sinüsünü değeri hesaplar  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken hiperbolik sinüsünü değerini döndürür  
  
##  <a name="sqrt"></a>Sqrt  
 Bağımsız değişken squre kökündeki hesaplar  
  
```  
inline float sqrt(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken squre kökünü döndürür  
  
##  <a name="sqrtf"></a>sqrtf  
 Bağımsız değişken squre kökündeki hesaplar  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken squre kökünü döndürür  
  
##  <a name="tan"></a>tan  
 Bağımsız değişkenin Eğim değeri hesaplar  
  
```  
inline float tan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken Eğim değerini döndürür  
  
##  <a name="tanf"></a>tanf  
 Bağımsız değişkenin Eğim değeri hesaplar  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken Eğim değerini döndürür  
  
##  <a name="tanh"></a>TANH  
 Bağımsız değişkenin hiperbolik tanjant değeri hesaplar  
  
```  
inline float tanh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken hiperbolik tanjant değerini döndürür  
  
##  <a name="tanhf"></a>tanhf  
 Bağımsız değişkenin hiperbolik tanjant değeri hesaplar  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken hiperbolik tanjant değerini döndürür  
  
##  <a name="trunc"></a>trunc  
 Tamsayı bileşen bağımsız değişkeni tamsayıya dönüştürür  
  
```  
inline float trunc(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken tamsayı bileşenini döndürür  
  
##  <a name="truncf"></a>truncf  
 Tamsayı bileşen bağımsız değişkeni tamsayıya dönüştürür  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken tamsayı bileşenini döndürür  

## <a name="requirements"></a>Gereksinimler
**Başlık:** amp_math.h **Namespace:** Concurrency::fast_math
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)
