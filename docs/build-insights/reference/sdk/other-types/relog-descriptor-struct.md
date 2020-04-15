---
title: RELOG_DESCRIPTOR yapısı
description: C++ Yapı Öngörüleri SDK yapı referansı RELOG_DESCRIPTOR.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c3aee49fe9f609ca37082693ddcfd5e838cc96a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328945"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `RELOG_DESCRIPTOR` [RelogA](../functions/relog-a.md) ve [RelogW](../functions/relog-w.md) işlevleri ile kullanılır. Windows için Olay İzleme (ETW) izlemenin nasıl yeniden günlüğe kaydedilmesi gerektiğini açıklar.

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
| `NumberOfAnalysisPasses` | Yeniden kaydetme oturumunun analiz aşamasında ETW izleme üzerinden yapılması gereken analiz geçişlerinin sayısı. |
| `AnalysisCallbacks` | Yeniden günleme oturumunun çözümleme aşamasında hangi işlevlerin çağrılmasını belirten [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) bir nesnedir. |
| `RelogCallbacks` | Yeniden günlüğe kaydetme oturumunun yeniden günlüğe kaydetme aşamasında hangi işlevlerin arayacağını belirten [RELOG_CALLBACKS](relog-callbacks-struct.md) bir nesnedir. |
| `SystemEventsRetentionFlags` | Hangi sistem ETW olayları relogged izleme tutmak için belirtir [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) bir bitmask. |
| `AnalysisContext` | Belirtilen tüm geri arama işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanan bağlam`AnalysisCallbacks` |
| `RelogContext` | Belirtilen tüm geri arama işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanan bağlam`RelogCallbacks` |

## <a name="remarks"></a>Açıklamalar

Bir yeniden günlük oturumu sırasında ETW olaylarının yeniden günlüğe kaydedilmesini, `RelogCallbacks`kullanıcı tarafından . Ancak, CPU örnekleri gibi sistem ETW olayları bu geri arama işlevlerine iletilir değildir. Sistem `SystemEventsRetentionFlags` ETW olaylarının yeniden günlüğe kaydedilmesini denetlemek için alanı kullanın.

Ve `AnalysisCallbacks` `RelogCallbacks` yapıları yalnızca üye olmayan işlevler için işaretçileri kabul eder. Bu sınırlamayı bir nesne işaretçisine ayarlayarak atlatabilirsiniz. Bu nesne işaretçisi, üye olmayan tüm geri arama işlevlerinize bağımsız değişken olarak geçirilir. Üye olmayan geri arama işlevleriniz içinden üye işlevleri çağırmak için bu işaretçiyi kullanın.

Yeniden günleme oturumunun çözümleme aşaması her zaman yeniden kaydetme aşamasından önce yürütülür.

::: moniker-end
