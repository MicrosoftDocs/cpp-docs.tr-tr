---
title: CONCURRENCY::fast_math Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: amp_math/Concurrency::fast_math
dev_langs: C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 047eee60eb409e86d77faf6f637a88a56f271094
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math Ad Alanı
İşlevlerini `fast_math` ad alanına sahip alt doğruluğu, tek tek duyarlıklı desteği (`float`) ve DirectX iç bilgileri çağırın. İki sürümü vardır her işlev örneğin `cos` ve `cosf`. Her iki sürümünü alın ve dönüş bir `float`, ancak her aynı DirectX iç çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Bağımsız değişken arkkosinüsünü hesaplar|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Bağımsız değişken arkkosinüsünü hesaplar|  
|[asin](concurrency-fast-math-namespace-functions.md#asin)|Bağımsız değişken arksinüsünü hesaplar|  
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Bağımsız değişken arksinüsünü hesaplar|  
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Bağımsız değişken tanjantını hesaplar|  
|[ATAN2](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_X tanjantını hesaplar|  
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_X tanjantını hesaplar|  
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Bağımsız değişken tanjantını hesaplar|  
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Bağımsız değişken tavan hesaplar|  
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Bağımsız değişken tavan hesaplar|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Bağımsız değişken kosinüsünü hesaplar|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Bağımsız değişken kosinüsünü hesaplar|  
|[COSH](concurrency-fast-math-namespace-functions.md#cosh)|Bağımsız değişkenin hiperbolik kosinüsünü değeri hesaplar|  
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Bağımsız değişkenin hiperbolik kosinüsünü değeri hesaplar|  
|[exp](concurrency-fast-math-namespace-functions.md#exp)|E tabanında bağımsız değişkeni üstel hesaplar|  
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|Base-2 bağımsız değişkeni üstel hesaplar|  
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Base-2 bağımsız değişkeni üstel hesaplar|  
|[expf](concurrency-fast-math-namespace-functions.md#expf)|E tabanında bağımsız değişkeni üstel hesaplar|  
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Bağımsız değişken mutlak değerini döndürür|  
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Bağımsız değişken mutlak değerini döndürür|  
|[Kat](concurrency-fast-math-namespace-functions.md#floor)|Bağımsız değişken kat hesaplar|  
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Bağımsız değişken kat hesaplar|  
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Bağımsız değişkenler en büyük sayısal değerini belirleme|  
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Bağımsız değişkenler en büyük sayısal değerini belirleme|  
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Bağımsız değişkenler en küçük sayısal değeri belirleme|  
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Bağımsız değişkenler en küçük sayısal değeri belirleme|  
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Kayan nokta _X/_Y kalanı hesaplar|  
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Kayan nokta _X/_Y kalanı hesaplar|  
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Mantis ve üs _X, alır|  
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|Mantis ve üs _X, alır|  
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|Bağımsız değişken sınırlı bir değere sahip olup olmadığını belirler|  
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Bağımsız değişkeni bir sonsuzluk olup olmadığını belirler|  
|[isNaN](concurrency-fast-math-namespace-functions.md#isnan)|Bağımsız değişkeni bir NaN olup olmadığını belirler|  
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Mantis ve üs arasında bir gerçek sayı hesaplar|  
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Mantis ve üs arasında bir gerçek sayı hesaplar|  
|[Günlük](concurrency-fast-math-namespace-functions.md#log)|Bağımsız değişken e tabanında logaritmasını hesaplar|  
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Bağımsız değişken 10 tabanında logaritmasını hesaplar|  
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Bağımsız değişken 10 tabanında logaritmasını hesaplar|  
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Bağımsız değişken 2 tabanındaki logaritmasını hesaplar|  
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Bağımsız değişken 2 tabanındaki logaritmasını hesaplar|  
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Bağımsız değişken e tabanında logaritmasını hesaplar|  
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Kesirli içine _X ve tamsayı bölümleri böler.|  
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Kesirli içine _X ve tamsayı bölümleri böler.|  
|[POW](concurrency-fast-math-namespace-functions.md#pow)|Üssü _Y _X hesaplar|  
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Üssü _Y _X hesaplar|  
|[yuvarlamak](concurrency-fast-math-namespace-functions.md#round)|_X en yakın tamsayıya yuvarlar|  
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|_X en yakın tamsayıya yuvarlar|  
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Devrik değerlerin bağımsız değişkeni'nin kare kökünü döndürür|  
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Devrik değerlerin bağımsız değişkeni'nin kare kökünü döndürür|  
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Bağımsız değişken işaretini döndürür|  
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Bağımsız değişken işaretini döndürür|  
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Bağımsız değişkenin sinüsünü değeri hesaplar|  
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|_X Sinüs ve Kosinüs değerini hesaplar|  
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|_X Sinüs ve Kosinüs değerini hesaplar|  
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Bağımsız değişkenin sinüsünü değeri hesaplar|  
|[SİNH](concurrency-fast-math-namespace-functions.md#sinh)|Bağımsız değişkenin hiperbolik sinüsünü değeri hesaplar|  
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Bağımsız değişkenin hiperbolik sinüsünü değeri hesaplar|  
|[Sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|Bağımsız değişken'in kare kökünü hesaplar|  
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Bağımsız değişken'in kare kökünü hesaplar|  
|[tan](concurrency-fast-math-namespace-functions.md#tan)|Bağımsız değişkenin Eğim değeri hesaplar|  
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Bağımsız değişkenin Eğim değeri hesaplar|  
|[TANH](concurrency-fast-math-namespace-functions.md#tanh)|Bağımsız değişkenin hiperbolik tanjant değeri hesaplar|  
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Bağımsız değişkenin hiperbolik tanjant değeri hesaplar|  
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Tamsayı bileşen bağımsız değişkeni tamsayıya dönüştürür|  
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Tamsayı bileşen bağımsız değişkeni tamsayıya dönüştürür|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_math.h  
  
 **Namespace:** Concurrency::fast_math  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
