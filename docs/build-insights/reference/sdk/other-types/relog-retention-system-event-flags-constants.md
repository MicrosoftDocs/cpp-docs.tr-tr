---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitleri
description: C++ Derleme ÖNGÖRÜLERI SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitler başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 74afc10faa26ba39a669a05aa3e3cabd1a211293
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332322"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitleri

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS` sabitler, yeniden günlüğe kaydedilen bir izlemede tutulacak sistem olaylarını tanımlamakta kullanılır. [RELOG_DESCRIPTOR](relog-descriptor-struct.md) yapısının `SystemEventsRetentionFlags` alanını başlatmak için bunları kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU örnek sistem olaylarını yeniden günlüğe kaydedilmiş bir izlemede saklayın. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Tüm sistem olaylarını yeniden günlüğe kaydedilmiş bir izlemede saklayın. |

## <a name="remarks"></a>Açıklamalar

::: moniker-end
