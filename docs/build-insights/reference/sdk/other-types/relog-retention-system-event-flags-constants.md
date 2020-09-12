---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitleri
description: C++ derleme öngörüleri SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitler başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5444c1a6b8799b1de8eea228211a5f2d6de638f8
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041412"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitleri

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS`Sabitler, yeniden günlüğe kaydedilen bir izlemede tutulacak sistem olaylarını tanımlamakta kullanılır. [RELOG_DESCRIPTOR](relog-descriptor-struct.md) yapısının alanını başlatmak için bunları kullanın `SystemEventsRetentionFlags` .

## <a name="syntax"></a>Syntax

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU örnek sistem olaylarını yeniden günlüğe kaydedilmiş bir izlemede saklayın. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Tüm sistem olaylarını yeniden günlüğe kaydedilmiş bir izlemede saklayın. |

## <a name="remarks"></a>Açıklamalar

::: moniker-end
