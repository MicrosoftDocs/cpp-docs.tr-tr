---
title: TRACING_SESSION_OPTIONS yapısı
description: C++ Yapı Öngörüleri SDK TRACING_SESSION_OPTIONS yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5aeb6299aea8dc0661b9469ee524e7aa4d010aca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323436"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `TRACING_SESSION_OPTIONS` [bir ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) yapının başlatılmasında kullanılır. Bir izlemenin toplanması sırasında hangi olayların yakalandığı açıklanır.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `SystemEventFlags` | Yakalamak için sistem olaylarını açıklayan bir bitmaskesi. Daha fazla bilgi için [TRACING_SESSION_SYSTEM_EVENT_FLAGS.](tracing-session-system-event-flags-constants.md) |
| `MsvcEventFlags` | Yakalamak için MSVC olaylarını açıklayan bir bitmask. Daha fazla bilgi için [TRACING_SESSION_MSVC_EVENT_FLAGS.](tracing-session-msvc-event-flags-constants.md) |

::: moniker-end
