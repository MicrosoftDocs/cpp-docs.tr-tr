---
title: Concurrency::fast_math Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
ms.openlocfilehash: 6ed8dcfa2faff49e8811769b76aad9df15b2fe7b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226756"
---
# <a name="concurrencyfast_math-namespace"></a>Concurrency::fast_math Ad Alanı

`fast_math`Ad alanındaki işlevlerin doğruluğu daha düşüktür, yalnızca tek duyarlıklı () desteği sağlar **`float`** ve DirectX iç sayısını çağırır. Her bir işlevin iki sürümü vardır, örneğin `cos` ve `cosf` . Her iki sürüm de alır ve döndürür **`float`** , ancak her biri aynı DirectX iç öğesini çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace fast_math;
```

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Bağımsız değişkenin arkkosinüsünü hesaplar|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Bağımsız değişkenin arkkosinüsünü hesaplar|
|[Asin](concurrency-fast-math-namespace-functions.md#asin)|Bağımsız değişkenin arksinüsünü hesaplar|
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Bağımsız değişkenin arksinüsünü hesaplar|
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Bağımsız değişkenin arktanjantını hesaplar|
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_X arktanjantını hesaplar|
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_X arktanjantını hesaplar|
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Bağımsız değişkenin arktanjantını hesaplar|
|[Ceil](concurrency-fast-math-namespace-functions.md#ceil)|Bağımsız değişkenin tavan sayısını hesaplar|
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Bağımsız değişkenin tavan sayısını hesaplar|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Bağımsız değişkenin kosinüsünü hesaplar|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Bağımsız değişkenin kosinüsünü hesaplar|
|[Cosh](concurrency-fast-math-namespace-functions.md#cosh)|Bağımsız değişkenin hiperbolik kosinüs değerini hesaplar|
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Bağımsız değişkenin hiperbolik kosinüs değerini hesaplar|
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Bağımsız değişkenin taban-e üssünü hesaplar|
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|Bağımsız değişkenin taban 2 üssünü hesaplar|
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Bağımsız değişkenin taban 2 üssünü hesaplar|
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Bağımsız değişkenin taban-e üssünü hesaplar|
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Bağımsız değişkenin mutlak değerini döndürür|
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Bağımsız değişkenin mutlak değerini döndürür|
|[sını](concurrency-fast-math-namespace-functions.md#floor)|Bağımsız değişkenin katsını hesaplar|
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Bağımsız değişkenin katsını hesaplar|
|[Fmax](concurrency-fast-math-namespace-functions.md#fmax)|Bağımsız değişkenlerin en büyük sayısal değerini belirleme|
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Bağımsız değişkenlerin en büyük sayısal değerini belirleme|
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Bağımsız değişkenlerin en küçük sayısal değerini belirleme|
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Bağımsız değişkenlerin en küçük sayısal değerini belirleme|
|[FMOD](concurrency-fast-math-namespace-functions.md#fmod)|_X/_Y kayan nokta kalanını hesaplar|
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|_X/_Y kayan nokta kalanını hesaplar|
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|_X Mantis ve üstürünü alır|
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|_X Mantis ve üstürünü alır|
|[isFinite](concurrency-fast-math-namespace-functions.md#isfinite)|Bağımsız değişkenin sonlu bir değere sahip olup olmadığını belirler|
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Bağımsız değişkenin bir sonsuzluk olup olmadığını belirler|
|[isNaN](concurrency-fast-math-namespace-functions.md#isnan)|Bağımsız değişkenin bir NaN olup olmadığını belirler|
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Mantis ve üs öğesinden gerçek bir sayıyı hesaplar|
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Mantis ve üs öğesinden gerçek bir sayıyı hesaplar|
|[açmasını](concurrency-fast-math-namespace-functions.md#log)|Bağımsız değişkenin taban-e logaritmasını hesaplar|
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Bağımsız değişkenin 10 tabanında logaritmasını hesaplar|
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Bağımsız değişkenin 10 tabanında logaritmasını hesaplar|
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Bağımsız değişkenin 2 tabanında logaritmasını hesaplar|
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Bağımsız değişkenin 2 tabanında logaritmasını hesaplar|
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Bağımsız değişkenin taban-e logaritmasını hesaplar|
|[modf](concurrency-fast-math-namespace-functions.md#modf)|_X kesirli ve tamsayı bölümlerine böler.|
|[modff](concurrency-fast-math-namespace-functions.md#modff)|_X kesirli ve tamsayı bölümlerine böler.|
|[POW](concurrency-fast-math-namespace-functions.md#pow)|_Y kuvvetine _X hesaplar|
|[powf](concurrency-fast-math-namespace-functions.md#powf)|_Y kuvvetine _X hesaplar|
|[gidiş](concurrency-fast-math-namespace-functions.md#round)|_X en yakın tamsayıya yuvarlar|
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|_X en yakın tamsayıya yuvarlar|
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Bağımsız değişkenin karekökünü döndürür|
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Bağımsız değişkenin karekökünü döndürür|
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Bağımsız değişkenin işaretini döndürür|
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Bağımsız değişkenin işaretini döndürür|
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Bağımsız değişkenin sinüs değerini hesaplar|
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|_X sinüsünü ve kosinüs değerini hesaplar|
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|_X sinüsünü ve kosinüs değerini hesaplar|
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Bağımsız değişkenin sinüs değerini hesaplar|
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|Bağımsız değişkenin hiperbolik sinüs değerini hesaplar|
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Bağımsız değişkenin hiperbolik sinüs değerini hesaplar|
|[k](concurrency-fast-math-namespace-functions.md#sqrt)|Bağımsız değişkenin kare kökünü hesaplar|
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Bağımsız değişkenin kare kökünü hesaplar|
|[Başlangıçtan](concurrency-fast-math-namespace-functions.md#tan)|Bağımsız değişkenin tanjant değerini hesaplar|
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Bağımsız değişkenin tanjant değerini hesaplar|
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|Bağımsız değişkenin hiperbolik tanjant değerini hesaplar|
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Bağımsız değişkenin hiperbolik tanjant değerini hesaplar|
|[TRUNC](concurrency-fast-math-namespace-functions.md#trunc)|Bağımsız değişkeni tamsayı bileşene kırpar|
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Bağımsız değişkeni tamsayı bileşene kırpar|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_math. h

**Ad alanı:** Eşzamanlılık:: fast_math

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
