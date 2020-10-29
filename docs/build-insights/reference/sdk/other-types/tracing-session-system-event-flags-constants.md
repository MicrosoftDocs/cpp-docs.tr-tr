---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitleri
description: C++ derleme öngörüleri SDK TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitler başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 346c955355ffbc6c062a34bf928f16ccd3940154
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922379"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitleri

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS`Sabitler, bir izleme sırasında toplanacak sistem olaylarını tanımlamakta kullanılır. [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) yapısının alanını başlatmak için bunları kullanın `SystemEventFlags` .

## <a name="syntax"></a>Syntax

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Üyeler

| Ad | Bu bayrak tarafından açık olaylar |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Bu bayrak, açıkça belirtilmediği halde C++ Build Insights SDK 'Sı tarafından varsayılan olarak etkinleştirilir. C++ derleme öngörülerinin düzgün çalışması için gerekli olan temel sistem olaylarını sağlar. Bu bayrak tarafından etkinleştirilen olaylar, süreçler, iş parçacıkları ve görüntü yükleme hakkında bilgi sağlar. Bu olayları devre dışı bırakamıyorum. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU örnekleri |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Bu bayrak tüm sistem olaylarını etkinleştirir. |

::: moniker-end
