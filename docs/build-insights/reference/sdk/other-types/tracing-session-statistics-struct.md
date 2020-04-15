---
title: TRACING_SESSION_STATISTICS yapısı
description: C++ Yapı Öngörüleri SDK TRACING_SESSION_OPTIONS yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 96cff3a231fd515ec1c52a048b8350a63ba46a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323378"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `TRACING_SESSION_STATISTICS` toplanan bir iz üzerindeki istatistikleri açıklar. Bir izleme oturumu durdurulurken alanları ayarlanır.

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
| `MSVCEventsLost` | Bırakılan MSVC olaylarının sayısı. |
| `MSVCBuffersLost` | Bırakılan MSVC olay arabelleklerinin sayısı. |
| `SystemEventsLost` | Bırakılan sistem olaylarının sayısı. |
| `SystemBuffersLost` | Bırakılan sistem olay arabelleklerinin sayısı. |

## <a name="remarks"></a>Açıklamalar

Bu yapı, aşağıdaki işlevleri çağırArak doldurulur:

- [StopTracingSession](../functions/stop-tracing-session.md)
- [StopTracingSessionA](../functions/stop-tracing-session-a.md)
- [StopTracingSessionW](../functions/stop-tracing-session-w.md)
- [StopAndAnalyzeTracingSession](../functions/stop-and-analyze-tracing-session.md)
- [StopAndAnalyzeTracingSessionA](../functions/stop-and-analyze-tracing-session-a.md)
- [StopAndAnalyzeTracingSessionW](../functions/stop-and-analyze-tracing-session-w.md)
- [StopAndRelogTracingOturum](../functions/stop-and-relog-tracing-session.md)
- [StopAndRelogTracingSessionA](../functions/stop-and-relog-tracing-session-a.md)
- [StopAndRelogTracingSessionW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
