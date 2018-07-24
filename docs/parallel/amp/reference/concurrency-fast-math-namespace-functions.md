---
title: CONCURRENCY::fast_math ad alanı işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4fad0d6f5823a205490038755f9de4eef10eae8
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208516"
---
# <a name="concurrencyfastmath-namespace-functions"></a>CONCURRENCY::fast_math ad alanı işlevleri
||||  
|-|-|-|  
|[acos](#acos)|[acosf](#acosf)|[asin](#asin)|  
|[asinf](#asinf)|[atan](#atan)|[atan2](#atan2)|  
|[atan2f](#atan2f)|[atanf](#atanf)|[ceil](#ceil)|  
|[ceilf](#ceilf)|[cos](#cos)|[cosf](#cosf)|  
|[COSH](#cosh)|[coshf](#coshf)|[exp](#exp)|  
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|  
|[fabs](#fabs)|[fabsf](#fabsf)|[Kat](#floor)|  
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|  
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|  
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|  
|[isfinite](#isfinite)|[isinf](#isinf)|[isnan](#isnan)|  
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[log](#log)|  
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|  
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|  
|[modff](#modff)|[POW](#pow)|[powf](#powf)|  
|[Yuvarlak](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|  
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|  
|[sin](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|  
|[sinf](#sinf)|[SİNH](#sinh)|[sinhf](#sinhf)|  
|[sqrt](#sqrt)|[sqrtf](#sqrtf)|[tan](#tan)|  
|[tanf](#tanf)|[TANH](#tanh)|[tanhf](#tanhf)|  
|[trunc](#trunc)|[truncf](#truncf)|  
  
##  <a name="acos"></a>  ACOS  
 Bağımsız değişkenin ark kosinüsünü hesaplar.  
  
```  
inline float acos(float _X) restrict(amp);
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
  
##  <a name="asin"></a>  asin  
 Bağımsız değişkenin ark sinüsünü hesaplar  
  
```  
inline float asin(float _X) restrict(amp);
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
  
##  <a name="atan"></a>  atan  
 Bağımsız değişkenin ark tanjantını hesaplar.  
  
```  
inline float atan(float _X) restrict(amp);
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
  
##  <a name="ceil"></a>  Ceil  
 Bağımsız değişkenin tavanını hesaplar.  
  
```  
inline float ceil(float _X) restrict(amp);
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
  
##  <a name="cos"></a>  Cos  
 Bağımsız değişkenin kosinüsünü hesaplar.  
  
```  
inline float cos(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkenin hiperbolik Kosinüs değerini döndürür  
  
##  <a name="exp"></a>  exp  
 Tabanında üssü bağımsız değişkeni hesaplar.  
  
```  
inline float exp(float _X) restrict(amp);
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
  
##  <a name="fabs"></a>  fabs  
 Bağımsız değişkenin mutlak değerini döndürür  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
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
  
##  <a name="floor"></a>  Kat  
 Bağımsız değişkenin tabanını hesaplar.  
  
```  
inline float floor(float _X) restrict(amp);
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
  
##  <a name="fmax"></a>  fmax  
 Bağımsız değişkenlerin en büyük sayısal değerini belirler  
  
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
  
##  <a name="fmod"></a>  Fmod  
 _X/_Y'in kayan nokta kalanını hesaplar.  
  
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
 _X/_Y'in kayan nokta kalanını döndürür  
  
##  <a name="fmodf"></a>  fmodf  
 _X/_Y'in kayan nokta kalanını hesaplar.  
  
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
 _X/_Y'in kayan nokta kalanını döndürür  
  
##  <a name="frexp"></a>  frexp  
 _X'in Mantis ve alır.  
  
```  
inline float frexp(
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
  
##  <a name="isfinite"></a>  isfinite  
 Bağımsız değişkenin sınırlı bir değer olup olmadığını belirler  
  
```  
inline int isfinite(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkenin bir NaN değerini sahiptir ve yalnızca, sıfır olmayan bir değer döndürür.  
  
##  <a name="ldexp"></a>  ldexp  
 Mantis ve bir gerçek sayı hesaplar.  
  
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
 _X'i döndürür \* 2 ^ _Exp  
  
##  <a name="ldexpf"></a>  ldexpf  
 Mantis ve bir gerçek sayı hesaplar.  
  
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
 _X'i döndürür \* 2 ^ _Exp  
  
##  <a name="log"></a>  Günlük  
 Bağımsız değişkenin e tabanında logaritmasını hesaplar.  
  
```  
inline float log(float _X) restrict(amp);
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
  
##  <a name="log2"></a>  log2  
 Bağımsız değişkenin 2 tabanlı logaritmasını hesaplar.  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkenin 2 tabanında logaritmasını döndürür  
  
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
 _X'i kesirli ve tamsayı bölümlere böler.  
  
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
 _X'in işaretli kesirli kısmını döndürür.  
  
##  <a name="modff"></a>  modff  
 _X'i kesirli ve tamsayı bölümlere böler.  
  
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
 _X'in işaretli kesirli kısmını döndürür.  
  
##  <a name="pow"></a>  POW  
 _X ardından _Y üssünü hesaplar.  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri, temel  
  
 `_Y`  
 Kayan nokta değeri, üs  
  
### <a name="return-value"></a>Dönüş Değeri  
 _X ardından _Y üssüne yükseltilmiş değerini döndürür  
  
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
  
##  <a name="round"></a>  Yuvarlak  
 _X'i en yakın tamsayıya yuvarlar  
  
```  
inline float round(float _X) restrict(amp);
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
  
##  <a name="signbit"></a>  signbit  
 _X'in işaretini negatif olup olmadığını belirler  
  
```  
inline int signbit(float _X) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
  
##  <a name="sqrt"></a>  Sqrt  
 Bağımsız değişkenin squre kök hesaplar  
  
```  
inline float sqrt(float _X) restrict(amp);
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
  
##  <a name="trunc"></a>  trunc  
 Bağımsız değişkeni tam sayı bileşenine keser  
  
```  
inline float trunc(float _X) restrict(amp);
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

## <a name="requirements"></a>Gereksinimler
**Başlık:** amp_math.h **Namespace:** Concurrency::fast_math
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)
