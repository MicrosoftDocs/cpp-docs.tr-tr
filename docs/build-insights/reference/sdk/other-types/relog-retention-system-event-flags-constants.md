---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitleri
description: C++ Build Insights SDK sabitler referansı RELOG_RETENTION_SYSTEM_EVENT_FLAGS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7110f809a819357b31951c203c1fa6ac9fb9f42e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323467"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS sabitleri

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sabitler, `RELOG_RETENTION_SYSTEM_EVENT_FLAGS` hangi sistem olaylarının yeniden kaydedilmiş bir izde tutulmasıgerektiğini açıklamak için kullanılır. [RELOG_DESCRIPTOR](relog-descriptor-struct.md) yapının `SystemEventsRetentionFlags` alanını başlatmak için bunları kullanın.

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
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU örnek sistem olaylarını yeniden kaydedilmiş bir izlemede tutun. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Tüm sistem olaylarını yeniden kaydedilmiş bir izlemede tutun. |

## <a name="remarks"></a>Açıklamalar

::: moniker-end
