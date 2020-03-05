---
title: ANALYSIS_CALLBACKS yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK ANALYSIS_CALLBACKS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8c35e740d97488969a6b69467d54412297e49227
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332532"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`ANALYSIS_CALLBACKS` yapısı, bir [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) nesnesi başlatılırken kullanılır. Windows için olay Izleme (ETW) izlemenin analiz veya yeniden günlüğe kaydedilmesi sırasında hangi işlevlerin çağrılacağını belirtir.

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
| `OnStartActivity` | Etkinlik başlangıç olayını işlemek için çağırılır. |
| `OnStopActivity` | Etkinlik durdurma olayını işlemek için çağırılır. |
| `OnSimpleEvent` | Basit bir olayı işlemek için çağırılır. |
| `OnTraceInfo` | Analiz oturumları için, her analiz geçişinin başlangıcında çağırılır. Her analiz geçişinin başlangıcında çağrılan ve yeniden günlüğe kaydetme geçişinin başlangıcında bulunan yeniden günlüğe kaydetme oturumları için. Bu işlev yalnızca OnBeginAnalysisPass çağrıldıktan sonra çağrılır. |
| `OnBeginAnalysis` | Analiz oturumları için, herhangi bir analiz geçişinin başlatılmadan önce çağırılır. Yeniden günlüğe kaydetme oturumları için, çözümleme aşaması başlamadan iki kez çağrılır: yeniden günlüğe kaydetme oturumunun başlangıcını duyurduktan sonra ve analiz aşamasının başlangıcını duyurduktan sonra. |
| `OnEndAnalysis` | Analiz oturumlarında, bu işlev tüm analiz geçişleri sona erdikten sonra çağrılır. Yeniden günlüğe kaydetme oturumlarında, analiz aşamasının tüm analiz geçişleri bittiğinde bu işlev çağrılır. Ardından, yeniden oturum açma geçişi bittikten sonra tekrar çağırılır. |
| `OnBeginAnalysisPass` | Bir çözümleme geçişine veya yeniden oturum açma geçişine Başlarken, herhangi bir olayı işlemeden önce çağırılır. |
| `OnEndAnalysisPass` | Bir analiz geçişinin sonlandırılabilmesi veya yeniden günlüğe kaydetme geçişi sırasında, tüm olaylar işlendikten sonra çağırılır. |

## <a name="remarks"></a>Açıklamalar

Yeniden günlüğe kaydetme oturumunun analiz aşaması, yeniden günlüğe kaydetme oturumunun bir parçası olarak değerlendirilir ve birden çok analiz geçişi içerebilir. Bu nedenle, `OnBeginAnalysis` yeniden günlüğe kaydetme oturumunun başındaki bir satırda iki kez çağrılır. `OnEndAnalysis`, yeniden günlüğe kaydetme aşamasına başlamadan önce ve yeniden günlüğe kaydetme aşamasının sonunda bir kez daha önce analiz aşamasının sonunda çağırılır. Yeniden günlüğe kaydetme aşaması her zaman tek bir yeniden günlüğe kaydetme geçişi içerir.

Çözümleyicilerin, yeniden günlüğe kaydetme oturumunun hem analizin hem de yeniden günlüğe kaydetme aşamasının bir parçası olması mümkündür. Bu çözümleyiciler, OnBeginAnalysis ve `OnEndAnalysis` çağrı çiftlerini izleyerek Şu anda hangi aşamanın devam etmekte olduğunu tespit edebilir. `OnEndAnalysis` çağrısı olmadan iki `OnBeginAnalysis` çağrısı, çözümleme aşamasının devam etmektedir anlamına gelir. İki `OnBeginAnalysis` çağrı ve bir `OnEndAnalysis` çağrısı, yeniden günlüğe kaydetme aşamasının devam ettiğinden anlamına gelir. İki OnBeginAnalysis ve iki `OnEndAnalysis` çağrısı, her iki aşamaların de bitmediği anlamına gelir.

`ANALYSIS_CALLBACKS` yapısının tüm üyeleri geçerli bir işleve işaret etmelidir. Kabul edilen işlev imzaları hakkında daha fazla bilgi için bkz. [Onanalyzer Sıseventfunc](on-analysis-event-func-typedef.md), [ontraceinfofunc](on-trace-info-func-typedef.md)ve [onbeginendpassfunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
