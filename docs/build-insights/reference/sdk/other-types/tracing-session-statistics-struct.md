---
title: TRACING_SESSION_STATISTICS yapısı
description: C++ derleme öngörüleri SDK TRACING_SESSION_OPTIONS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5f6126fb469dc13b814b91942fe9f7bc480ba3f1
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041191"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

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
