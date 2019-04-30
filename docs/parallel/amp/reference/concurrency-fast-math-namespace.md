---
title: Concurrency::fast_math Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
ms.openlocfilehash: e774c2d8e4431960e796ee1e6cc87b924d04174b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405605"
---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math Ad Alanı

İçindeki işlevler `fast_math` ad alanına sahip düşük doğruluk derecesine, tek tek duyarlıklı desteği (`float`) ve DirectX iç bilgilerini çağırın. İki sürümü vardır her işlev için örneğin `cos` ve `cosf`. Her iki sürümü alan ve getiren bir `float`, ancak her iç aynı DirectX'i çağırır.

## <a name="syntax"></a>Sözdizimi

```
namespace fast_math;
```

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Bağımsız değişkenin ark kosinüsünü hesaplar.|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Bağımsız değişkenin ark kosinüsünü hesaplar.|
|[asin](concurrency-fast-math-namespace-functions.md#asin)|Bağımsız değişkenin ark sinüsünü hesaplar|
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Bağımsız değişkenin ark sinüsünü hesaplar|
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Bağımsız değişkenin ark tanjantını hesaplar.|
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_x'in ark tanjantını hesaplar.|
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_x'in ark tanjantını hesaplar.|
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Bağımsız değişkenin ark tanjantını hesaplar.|
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Bağımsız değişkenin tavanını hesaplar.|
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Bağımsız değişkenin tavanını hesaplar.|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Bağımsız değişkenin kosinüsünü hesaplar.|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Bağımsız değişkenin kosinüsünü hesaplar.|
|[COSH](concurrency-fast-math-namespace-functions.md#cosh)|Bağımsız değişkenin hiperbolik Kosinüs değerini hesaplar.|
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Bağımsız değişkenin hiperbolik Kosinüs değerini hesaplar.|
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Tabanında üssü bağımsız değişkeni hesaplar.|
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|2 tabanında üssünü bağımsız değişkeni hesaplar.|
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|2 tabanında üssünü bağımsız değişkeni hesaplar.|
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Tabanında üssü bağımsız değişkeni hesaplar.|
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Bağımsız değişkenin mutlak değerini döndürür|
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Bağımsız değişkenin mutlak değerini döndürür|
|[Kat](concurrency-fast-math-namespace-functions.md#floor)|Bağımsız değişkenin tabanını hesaplar.|
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Bağımsız değişkenin tabanını hesaplar.|
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Bağımsız değişkenlerin en büyük sayısal değerini belirler|
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Bağımsız değişkenlerin en büyük sayısal değerini belirler|
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Bağımsız değişkenlerin en küçük sayısal değerini belirler|
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Bağımsız değişkenlerin en küçük sayısal değerini belirler|
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|_X/_Y'in kayan nokta kalanını hesaplar.|
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|_X/_Y'in kayan nokta kalanını hesaplar.|
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|_X'in Mantis ve alır.|
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|_X'in Mantis ve alır.|
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|Bağımsız değişkenin sınırlı bir değer olup olmadığını belirler|
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Bağımsız değişkenin bir sonsuzluk olup olmadığını belirler|
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|Bağımsız değişkenin bir NaN olup olmadığını belirler|
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Mantis ve bir gerçek sayı hesaplar.|
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Mantis ve bir gerçek sayı hesaplar.|
|[log](concurrency-fast-math-namespace-functions.md#log)|Bağımsız değişkenin e tabanında logaritmasını hesaplar.|
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Bağımsız değişkenin 10 tabanında logaritmasını hesaplar.|
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Bağımsız değişkenin 10 tabanında logaritmasını hesaplar.|
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Bağımsız değişkenin 2 tabanlı logaritmasını hesaplar.|
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Bağımsız değişkenin 2 tabanlı logaritmasını hesaplar.|
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Bağımsız değişkenin e tabanında logaritmasını hesaplar.|
|[modf](concurrency-fast-math-namespace-functions.md#modf)|_X'i kesirli ve tamsayı bölümlere böler.|
|[modff](concurrency-fast-math-namespace-functions.md#modff)|_X'i kesirli ve tamsayı bölümlere böler.|
|[POW](concurrency-fast-math-namespace-functions.md#pow)|_X ardından _Y üssünü hesaplar.|
|[powf](concurrency-fast-math-namespace-functions.md#powf)|_X ardından _Y üssünü hesaplar.|
|[Yuvarlak](concurrency-fast-math-namespace-functions.md#round)|_X'i en yakın tamsayıya yuvarlar|
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|_X'i en yakın tamsayıya yuvarlar|
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Bağımsız değişkenin kare kökünün karşıtını döndürür|
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Bağımsız değişkenin kare kökünün karşıtını döndürür|
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Bağımsız değişkenin işaretini döndürür|
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Bağımsız değişkenin işaretini döndürür|
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Bağımsız değişkenin sinüs değeri hesaplar|
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|_X'in Sinüs ve Kosinüs değerini hesaplar.|
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|_X'in Sinüs ve Kosinüs değerini hesaplar.|
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Bağımsız değişkenin sinüs değeri hesaplar|
|[SİNH](concurrency-fast-math-namespace-functions.md#sinh)|Bağımsız değişkenin hiperbolik sinüs değerini hesaplar.|
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Bağımsız değişkenin hiperbolik sinüs değerini hesaplar.|
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|Bağımsız değişkenin kare kökünü hesaplar.|
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Bağımsız değişkenin kare kökünü hesaplar.|
|[tan](concurrency-fast-math-namespace-functions.md#tan)|Bağımsız değişkenin tanjant değerini hesaplar.|
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Bağımsız değişkenin tanjant değerini hesaplar.|
|[TANH](concurrency-fast-math-namespace-functions.md#tanh)|Bağımsız değişkenin hiperbolik tanjant değerini hesaplar.|
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Bağımsız değişkenin hiperbolik tanjant değerini hesaplar.|
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Bağımsız değişkeni tam sayı bileşenine keser|
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Bağımsız değişkeni tam sayı bileşenine keser|

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_math.h

**Namespace:** CONCURRENCY::fast_math

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
