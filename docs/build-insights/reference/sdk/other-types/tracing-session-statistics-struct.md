---
title: TRACING_SESSION_STATISTICS yapısı
description: C++ Build Insights SDK TRACING_SESSION_STATISTICS yapısı başvurusu hakkında bilgi edinin.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7135c49bdf95ef5ba39db090c95ad46d266d8f65
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919663"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_STATISTICS`Yapı, toplanan bir izleme üzerinde istatistikleri açıklar. Bir izleme oturumu durdurulduğunda alanları ayarlanır.

## <a name="syntax"></a>Syntax

```cpp
typedef struct TRACING_SESSION_STATISTICS_TAG
{
    unsigned long MSVCEventsLost;
    unsigned long MSVCBuffersLost;
    unsigned long SystemEventsLost;
    unsigned long SystemBuffersLost;

} TRACING_SESSION_STATISTICS;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `MSVCEventsLost` | Bırakılan MSVC olay sayısı. |
| `MSVCBuffersLost` | Bırakılan MSVC olay arabelleklerinin sayısı. |
| `SystemEventsLost` | Bırakılan sistem olaylarının sayısı. |
| `SystemBuffersLost` | Bırakılan sistem olay arabelleklerinin sayısı. |

## <a name="remarks"></a>Açıklamalar

Bu yapı aşağıdaki işlevler çağrılırken doldurulur:

- [StopTracingSession](../functions/stop-tracing-session.md)
- [StopTracingSessionA](../functions/stop-tracing-session-a.md)
- [StopTracingSessionW](../functions/stop-tracing-session-w.md)
- [StopAndAnalyzeTracingSession](../functions/stop-and-analyze-tracing-session.md)
- [StopAndAnalyzeTracingSessionA](../functions/stop-and-analyze-tracing-session-a.md)
- [StopAndAnalyzeTracingSessionW](../functions/stop-and-analyze-tracing-session-w.md)
- [StopAndRelogTracingSession](../functions/stop-and-relog-tracing-session.md)
- [StopAndRelogTracingSessionA](../functions/stop-and-relog-tracing-session-a.md)
- [StopAndRelogTracingSessionW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
