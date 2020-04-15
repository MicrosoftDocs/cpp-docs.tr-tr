---
title: ANALYSIS_CALLBACKS yapısı
description: C++ Build Insights SDK yapı referansı ANALYSIS_CALLBACKS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c6de999b19657f999f884075ee53e21a4d2f2b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323500"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `ANALYSIS_CALLBACKS` [bir ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) nesnenin başlatılmasında kullanılır. Windows (ETW) izlemesinin analizi veya yeniden günlüğe kaydedildiği sırada hangi işlevlerin arayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

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

|  |  |
|--|--|
| `OnStartActivity` | Bir etkinlik başlatma olayını işlemek için çağrıldı. |
| `OnStopActivity` | Bir etkinlik durdurma olayını işlemek için çağrıldı. |
| `OnSimpleEvent` | Basit bir olayı işlemek için çağrıldı. |
| `OnTraceInfo` | Analiz oturumları için, her analiz geçişinin başında denir. Oturumları yeniden kaydetmeiçin, her analiz geçişinin başında ve yine yeniden ağaçlama geçişinin başında denir. Bu işlev yalnızca OnBeginAnalysisPass çağrıldıktan sonra çağrılır. |
| `OnBeginAnalysis` | Analiz oturumları için, herhangi bir analiz geçişi başlamadan önce denir. Yeniden ağaçlama oturumları için, analiz aşaması başlamadan önce iki kez çağrılır: bir kez yeniden ağaçlama oturumunun başlangıcını duyurmak ve bir kez daha analiz aşamasının başlangıcını duyurmak için. |
| `OnEndAnalysis` | Çözümleme oturumları için, tüm çözümleme geçişleri sona erdikten sonra bu işlev çağrılır. Oturumları yeniden günleme için, çözümleme aşamasının tüm çözümleme geçişleri sona erdiğinde bu işlev çağrılır. Daha sonra, yeniden ağaçlama geçişi sona erdikten sonra tekrar çağrılır. |
| `OnBeginAnalysisPass` | Herhangi bir olayı işlemeden önce, bir analiz geçişi veya yeniden günleme geçişi başlarken çağrılır. |
| `OnEndAnalysisPass` | Tüm olayları işledikten sonra, bir analiz geçişi veya yeniden günleme geçişi sona ererken çağrılır. |

## <a name="remarks"></a>Açıklamalar

Yeniden günleme oturumunun çözümleme aşaması, yeniden ağaçlama oturumunun bir parçası olarak kabul edilir ve birden çok çözümleme geçişi içerebilir. Bu nedenle, `OnBeginAnalysis` bir yeniden günlüğe kaydetme oturumunun başında üst üste iki kez çağrılır. `OnEndAnalysis`yeniden kaydetme aşamasına başlamadan önce, analiz aşamasının sonunda ve yeniden ağaçlama aşamasının sonunda bir kez daha denir. Yeniden kaydetme aşaması her zaman tek bir yeniden ağaçlama geçişi içerir.

Çözümleyicilerin hem analizin hem de yeniden ağaç kesiminin yeniden günleme aşamasının bir parçası olması mümkündür. Bu çözümleyiciler, OnBeginAnalysis ve `OnEndAnalysis` çağrı çiftlerini izleyerek hangi aşamanın şu anda devam ediyor olduğunu belirleyebilirler. Herhangi `OnBeginAnalysis` bir `OnEndAnalysis` çağrı olmadan iki arama, analiz aşamasının devam olduğu anlamına gelir. İki `OnBeginAnalysis` arama `OnEndAnalysis` ve bir arama, yeniden günlüğe kaydetme aşamasının devam ediyor olduğu anlamına gelir. İki OnBeginAnalysis `OnEndAnalysis` ve iki çağrı, her iki aşamanın da sona ermiş olduğu anlamına gelir.

Yapının `ANALYSIS_CALLBACKS` tüm üyeleri geçerli bir işlevi işaret etmelidir. Kabul edilen işlev imzaları hakkında daha fazla bilgi için [Bkz. OnAnalysisEventFunc](on-analysis-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md), ve [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
