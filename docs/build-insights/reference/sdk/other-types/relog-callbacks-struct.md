---
title: RELOG_CALLBACKS yapısı
description: C++ Yapı Öngörüleri SDK yapı referansı RELOG_CALLBACKS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 60e7db81a48731090a23b82332704a79a51e97df
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328968"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `RELOG_CALLBACKS` [RELOG_DESCRIPTOR](relog-descriptor-struct.md) bir nesneyi başharflediğinde kullanılır. Windows için Olay İzleme (ETW) izlemenin yeniden günlüğe kaydedildiği sırada hangi işlevlerin arayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `OnStartActivity` | Bir etkinlik başlatma olayını işlemek için çağrıldı. |
| `OnStopActivity` | Bir etkinlik durdurma olayını işlemek için çağrıldı. |
| `OnSimpleEvent` | Basit bir olayı işlemek için çağrıldı. |
| `OnTraceInfo` | Yeniden ağaçlandırılanın başında bir `OnBeginReloggingPass` kez çağrılır, sonra çağrıldı. |
| `OnBeginRelogging` | Yeniden günlüğe kaydetme oturumu başlarken, yeniden ağaçlama geçişi başlamadan önce çağrılır. |
| `OnEndRelogging` | Yeniden günlüğe kaydetme oturumu sona erdiğinde, yeniden ağaçlama geçişi sona erdikten sonra çağrılır. |
| `OnBeginReloggingPass` | Herhangi bir olayı işlemeden önce, yeniden günlüğe kaydetme işlemine başlarken çağrılır. |
| `OnEndReloggingPass` | Tüm olayları işledikten sonra, yeniden günlüğe kaydetme geçişini sona erdirirken çağrılır. |

## <a name="remarks"></a>Açıklamalar

Yapının `RELOG_CALLBACKS` tüm üyeleri geçerli bir işlevi işaret etmelidir. Kabul edilen işlev imzaları hakkında daha fazla bilgi için [OnRelogEventFunc](on-relog-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md)ve [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)adresine bakın.

::: moniker-end
