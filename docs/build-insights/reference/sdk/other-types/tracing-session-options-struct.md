---
title: TRACING_SESSION_OPTIONS yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK TRACING_SESSION_OPTIONS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3f02552d5df4ffe71bc4be5c46e4b5239f25d73c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332210"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_OPTIONS` yapısı, bir [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) yapısı başlatırken kullanılır. Bir izlemenin toplanması sırasında hangi olayların yakalanacağını açıklar.

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
| `SystemEventFlags` | Yakalanacak sistem olaylarını açıklayan bir bit maskesi. Daha fazla bilgi için bkz. [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md). |
| `MsvcEventFlags` | Yakalanacak MSVC olaylarını açıklayan bir bit maskesi. Daha fazla bilgi için bkz. [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md). |

::: moniker-end
