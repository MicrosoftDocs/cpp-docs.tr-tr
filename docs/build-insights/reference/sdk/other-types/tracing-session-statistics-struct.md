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
ms.openlocfilehash: c1db302d9e816591624f0fc63633351d32684097
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742768"
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
