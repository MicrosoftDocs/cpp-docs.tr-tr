---
title: RELOG_DESCRIPTOR yapısı
description: C++ derleme öngörüleri SDK RELOG_DESCRIPTOR yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9b3c870998ce4f9ca55fb5bcc23ba66a1af46558
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922436"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_DESCRIPTOR`Yapı, [reloga](../functions/relog-a.md) ve [relogw](../functions/relog-w.md) işlevleriyle birlikte kullanılır. Windows için olay Izleme (ETW) izlemenin nasıl yeniden günlüğe kaydedileceğini açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `NumberOfAnalysisPasses` | Yeniden günlüğe kaydetme oturumunun çözümleme aşamasında ETW izlemesi üzerinden gerçekleştirilmesi gereken analiz geçişlerinin sayısı. |
| `AnalysisCallbacks` | Yeniden günlüğe kaydetme oturumunun çözümleme aşamasında hangi işlevlerin çağrılacağını belirten [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) nesne. |
| `RelogCallbacks` | Yeniden günlüğe kaydetme oturumunun yeniden günlüğe kaydetme aşamasında hangi işlevlerin çağrılacağını belirten [RELOG_CALLBACKS](relog-callbacks-struct.md) nesne. |
| `SystemEventsRetentionFlags` | Yeniden günlüğe kaydedilen izlemede hangi sistem ETW olaylarını tutacağız belirten [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) bir bit maskesi. |
| `AnalysisContext` | İçinde belirtilen tüm geri çağırma işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanmış bir bağlam `AnalysisCallbacks` |
| `RelogContext` | İçinde belirtilen tüm geri çağırma işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanmış bir bağlam `RelogCallbacks` |

## <a name="remarks"></a>Açıklamalar

Yeniden günlüğe kaydetme sırasında ETW olaylarının yeniden günlüğe kaydedilmesi, ' de belirtilen geri çağırma işlevleri aracılığıyla Kullanıcı tarafından denetlenir `RelogCallbacks` . Ancak, CPU örnekleri gibi sistem ETW olayları bu geri arama işlevlerine iletilmez. `SystemEventsRetentionFlags`SISTEM ETW olaylarının yeniden günlüğe kaydedilmesini denetlemek için alanını kullanın.

`AnalysisCallbacks`Ve `RelogCallbacks` yapıları yalnızca üye olmayan işlevlere yönelik işaretçileri kabul eder. Bir nesne işaretçisine ayarlayarak bu sınırlamayı çözebilirsiniz. Bu nesne işaretçisi, tüm üye olmayan geri çağırma işlevleriniz için bir bağımsız değişken olarak geçirilir. Üye olmayan geri çağırma işlevlerinizin içinden üye işlevleri çağırmak için bu işaretçiyi kullanın.

Yeniden günlüğe kaydetme oturumunun analiz aşaması her zaman yeniden günlüğe kaydetme aşamasından önce yürütülür.

::: moniker-end
