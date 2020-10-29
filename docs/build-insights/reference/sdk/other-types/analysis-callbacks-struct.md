---
title: ANALYSIS_CALLBACKS yapısı
description: C++ derleme öngörüleri SDK ANALYSIS_CALLBACKS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3fae97370ff9366ffc2fbd8d046a73c30125e554
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919936"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`ANALYSIS_CALLBACKS` [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) nesnesi başlatılırken yapı kullanılır. Windows için olay Izleme (ETW) izlemenin analiz veya yeniden günlüğe kaydedilmesi sırasında hangi işlevlerin çağrılacağını belirtir.

## <a name="syntax"></a>Syntax

```cpp
typedef struct ANALYSIS_CALLBACKS_TAG
{
    OnAnalysisEventFunc     OnStartActivity;
    OnAnalysisEventFunc     OnStopActivity;
    OnAnalysisEventFunc     OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginAnalysis;
    OnBeginEndPassFunc      OnEndAnalysis;
    OnBeginEndPassFunc      OnBeginAnalysisPass;
    OnBeginEndPassFunc      OnEndAnalysisPass;
} ANALYSIS_CALLBACKS;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `OnStartActivity` | Etkinlik başlangıç olayını işlemek için çağırılır. |
| `OnStopActivity` | Etkinlik durdurma olayını işlemek için çağırılır. |
| `OnSimpleEvent` | Basit bir olayı işlemek için çağırılır. |
| `OnTraceInfo` | Analiz oturumları için, her analiz geçişinin başlangıcında çağırılır. Her analiz geçişinin başlangıcında çağrılan ve yeniden günlüğe kaydetme geçişinin başlangıcında bulunan yeniden günlüğe kaydetme oturumları için. Bu işlev yalnızca OnBeginAnalysisPass çağrıldıktan sonra çağrılır. |
| `OnBeginAnalysis` | Analiz oturumları için, herhangi bir analiz geçişinin başlatılmadan önce çağırılır. Yeniden günlüğe kaydetme oturumları için, çözümleme aşaması başlamadan iki kez çağrılır: yeniden günlüğe kaydetme oturumunun başlangıcını duyurduktan sonra ve analiz aşamasının başlangıcını duyurduktan sonra. |
| `OnEndAnalysis` | Analiz oturumlarında, bu işlev tüm analiz geçişleri sona erdikten sonra çağrılır. Yeniden günlüğe kaydetme oturumlarında, analiz aşamasının tüm analiz geçişleri bittiğinde bu işlev çağrılır. Ardından, yeniden oturum açma geçişi bittikten sonra tekrar çağırılır. |
| `OnBeginAnalysisPass` | Bir çözümleme geçişine veya yeniden oturum açma geçişine Başlarken, herhangi bir olayı işlemeden önce çağırılır. |
| `OnEndAnalysisPass` | Bir analiz geçişinin sonlandırılabilmesi veya yeniden günlüğe kaydetme geçişi sırasında, tüm olaylar işlendikten sonra çağırılır. |

## <a name="remarks"></a>Açıklamalar

Yeniden günlüğe kaydetme oturumunun analiz aşaması, yeniden günlüğe kaydetme oturumunun bir parçası olarak değerlendirilir ve birden çok analiz geçişi içerebilir. Bu nedenle, `OnBeginAnalysis` yeniden günlüğe kaydetme oturumunun başındaki bir satırda iki kez çağrılır. `OnEndAnalysis` Çözümleme aşamasının sonunda, yeniden günlüğe kaydetme aşamasına başlamadan önce ve yeniden günlüğe kaydetme aşamasının sonunda tekrar bir kez çağrılır. Yeniden günlüğe kaydetme aşaması her zaman tek bir yeniden günlüğe kaydetme geçişi içerir.

Çözümleyicilerin, yeniden günlüğe kaydetme oturumunun hem analizin hem de yeniden günlüğe kaydetme aşamasının bir parçası olması mümkündür. Bu çözümleyiciler, OnBeginAnalysis ve Call çiftlerini izleyerek Şu anda hangi aşamanın devam etmekte olduğunu tespit edebilir `OnEndAnalysis` . `OnBeginAnalysis`Herhangi bir çağrı olmadan iki çağrı `OnEndAnalysis` , çözümleme aşamasının devam etmektedir anlamına gelir. İki `OnBeginAnalysis` çağrı ve bir `OnEndAnalysis` çağrı, yeniden günlüğe kaydetme aşamasının devam etmekte olduğu anlamına gelir. İki OnBeginAnalysis ve iki `OnEndAnalysis` çağrı, her iki aşamaların de bitmediği anlamına gelir.

Yapının tüm üyeleri `ANALYSIS_CALLBACKS` geçerli bir işleve işaret etmelidir. Kabul edilen işlev imzaları hakkında daha fazla bilgi için bkz. [Onanalyzer Sıseventfunc](on-analysis-event-func-typedef.md), [ontraceinfofunc](on-trace-info-func-typedef.md)ve [onbeginendpassfunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
