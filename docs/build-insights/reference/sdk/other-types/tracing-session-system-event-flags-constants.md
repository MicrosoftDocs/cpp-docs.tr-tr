---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitleri
description: C++ Derleme ÖNGÖRÜLERI SDK TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitler başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce0b0ea373ec53f0d5bcf228269299d69b49bb95
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332357"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitleri

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS` sabitler, bir izleme sırasında hangi sistem olaylarının toplanacağını betimleyen kullanılır. [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) yapısının `SystemEventFlags` alanını başlatmak için bunları kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Üyeler

| Adı | Bu bayrak tarafından açık olaylar |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Bu bayrak, C++ açıkça belirtilmediği halde Build Insights SDK 'sı tarafından varsayılan olarak etkinleştirilir. C++ Derleme öngörülerinin düzgün şekilde çalışması için gerekli olan temel sistem olaylarını sağlar. Bu bayrak tarafından etkinleştirilen olaylar, süreçler, iş parçacıkları ve görüntü yükleme hakkında bilgi sağlar. Bu olayları devre dışı bırakamıyorum. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU örnekleri |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Bu bayrak tüm sistem olaylarını etkinleştirir. |

::: moniker-end
