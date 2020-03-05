---
title: TRACING_SESSION_STATISTICS yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK TRACING_SESSION_OPTIONS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9aa7c0a861d80fd3ebff85eb7ecb17dd05ae869e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332203"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_STATISTICS` yapısı, toplanan bir izlemede istatistikleri açıklar. Bir izleme oturumu durdurulduğunda alanları ayarlanır.

## <a name="syntax"></a>Sözdizimi

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

|  |  |
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
- [Stopandçözümleyicileri Etracingsession](../functions/stop-and-analyze-tracing-session.md)
- [Stopandçözümleyiciler Etracingsessiona](../functions/stop-and-analyze-tracing-session-a.md)
- [Stopandçözümleyiciler Etracingsessionw](../functions/stop-and-analyze-tracing-session-w.md)
- [StopAndRelogTracingSession](../functions/stop-and-relog-tracing-session.md)
- [StopAndRelogTracingSessionA](../functions/stop-and-relog-tracing-session-a.md)
- [StopAndRelogTracingSessionW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
