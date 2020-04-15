---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitleri
description: C++ Build Insights SDK sabitler referansı TRACING_SESSION_SYSTEM_EVENT_FLAGS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 264d697cc905eb6b44c8ec7de835a552976f0eb8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323281"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS sabitleri

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sabitler, `TRACING_SESSION_SYSTEM_EVENT_FLAGS` izleme sırasında hangi sistem olaylarının toplandığını açıklamak için kullanılır. [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) yapının `SystemEventFlags` alanını başlatmak için bunları kullanın.

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

| Adı | Bu bayrak tarafından açık olan olaylar |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Bu bayrak, açıkça belirtilmese bile C++ Build Insights SDK tarafından varsayılan olarak etkinleştirilir. C++ Build Insights tarafından gerekli olan temel sistem olaylarının düzgün çalışmasını sağlar. Bu bayrağın etkinleştiren olayları işlemler, iş parçacıkları ve görüntü yükleme hakkında bilgi sağlar. Bu olayları devre dışı kalamazsınız. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU örnekleri |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Bu bayrak tüm sistem olaylarını açar. |

::: moniker-end
