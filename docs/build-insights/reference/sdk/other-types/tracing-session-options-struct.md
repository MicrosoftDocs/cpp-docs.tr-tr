---
title: TRACING_SESSION_OPTIONS yapısı
description: C++ Build Insights SDK TRACING_SESSION_OPTIONS yapısı başvurusu hakkında bilgi edinin.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3147debbfe1ea7ab4bcb4fa3bb8a803e66163557
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922385"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_OPTIONS`Yapı, bir [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) yapısı başlatırken kullanılır. Bir izlemenin toplanması sırasında hangi olayların yakalanacağını açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `SystemEventFlags` | Yakalanacak sistem olaylarını açıklayan bir bit maskesi. Daha fazla bilgi için bkz. [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md). |
| `MsvcEventFlags` | Yakalanacak MSVC olaylarını açıklayan bir bit maskesi. Daha fazla bilgi için bkz. [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md). |

::: moniker-end
