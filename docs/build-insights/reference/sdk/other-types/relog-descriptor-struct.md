---
title: RELOG_DESCRIPTOR yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK RELOG_DESCRIPTOR yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f6f20835ed6535dd05def629200c113772e8f077
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332329"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_DESCRIPTOR` yapısı, [Reloga](../functions/relog-a.md) ve [relogw](../functions/relog-w.md) işlevleriyle birlikte kullanılır. Windows için olay Izleme (ETW) izlemenin nasıl yeniden günlüğe kaydedileceğini açıklar.

## <a name="syntax"></a>Sözdizimi

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

|  |  |
|--|--|
| `NumberOfAnalysisPasses` | Yeniden günlüğe kaydetme oturumunun çözümleme aşamasında ETW izlemesi üzerinden gerçekleştirilmesi gereken analiz geçişlerinin sayısı. |
| `AnalysisCallbacks` | Yeniden günlüğe kaydetme oturumunun çözümleme aşamasında hangi işlevlerin çağrılacağını belirten [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) nesne. |
| `RelogCallbacks` | Yeniden günlüğe kaydetme oturumunun yeniden günlüğe kaydetme aşamasında hangi işlevlerin çağrılacağını belirten [RELOG_CALLBACKS](relog-callbacks-struct.md) nesne. |
| `SystemEventsRetentionFlags` | Yeniden günlüğe kaydedilen izlemede hangi sistem ETW olaylarını tutacağız belirten [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) bir bit maskesi. |
| `AnalysisContext` | `AnalysisCallbacks` ' de belirtilen tüm geri çağırma işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanmış bir bağlam |
| `RelogContext` | `RelogCallbacks` ' de belirtilen tüm geri çağırma işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanmış bir bağlam |

## <a name="remarks"></a>Açıklamalar

Yeniden günlüğe kaydetme oturumu sırasında ETW olaylarının yeniden günlüğe kaydedilmesi, Kullanıcı tarafından `RelogCallbacks`' de belirtilen geri çağırma işlevleri aracılığıyla denetlenir. Ancak, CPU örnekleri gibi sistem ETW olayları bu geri arama işlevlerine iletilmez. Sistem ETW olaylarının yeniden günlüğe kaydedilmesini denetlemek için `SystemEventsRetentionFlags` alanını kullanın.

`AnalysisCallbacks` ve `RelogCallbacks` yapıları yalnızca üye olmayan işlevlere yönelik işaretçileri kabul eder. Bir nesne işaretçisine ayarlayarak bu sınırlamayı çözebilirsiniz. Bu nesne işaretçisi, tüm üye olmayan geri çağırma işlevleriniz için bir bağımsız değişken olarak geçirilir. Üye olmayan geri çağırma işlevlerinizin içinden üye işlevleri çağırmak için bu işaretçiyi kullanın.

Yeniden günlüğe kaydetme oturumunun analiz aşaması her zaman yeniden günlüğe kaydetme aşamasından önce yürütülür.

::: moniker-end
