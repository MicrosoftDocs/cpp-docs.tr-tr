---
title: RELOG_CALLBACKS yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK RELOG_CALLBACKS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c5dbed196e6cafaa301b6e07cd0f5546a0f4d563
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332343"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

Bir [RELOG_DESCRIPTOR](relog-descriptor-struct.md) nesnesi başlatılırken `RELOG_CALLBACKS` yapısı kullanılır. Windows için olay Izleme (ETW) izlemenin yeniden günlüğe kaydedilmesi sırasında hangi işlevlerin çağrılacağını belirtir.

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
| `OnStartActivity` | Etkinlik başlangıç olayını işlemek için çağırılır. |
| `OnStopActivity` | Etkinlik durdurma olayını işlemek için çağırılır. |
| `OnSimpleEvent` | Basit bir olayı işlemek için çağırılır. |
| `OnTraceInfo` | `OnBeginReloggingPass` çağrıldıktan sonra, yeniden oturum açma geçişinin başlangıcında bir kez çağırılır. |
| `OnBeginRelogging` | Yeniden günlüğe kaydetme geçişi başlamadan önce, yeniden günlüğe kaydetme oturumu başladığında çağırılır. |
| `OnEndRelogging` | Yeniden günlüğe kaydetme geçişi sona erdikten sonra bir yeniden günlüğe kaydetme oturumu sonlandırırken çağırılır. |
| `OnBeginReloggingPass` | Yeniden oturum açma geçişi Başlarken, herhangi bir olay işlenmeden önce çağırılır. |
| `OnEndReloggingPass` | Yeniden günlüğe kaydetme geçişi sonlandırırken, tüm olaylar işlendikten sonra çağırılır. |

## <a name="remarks"></a>Açıklamalar

`RELOG_CALLBACKS` yapısının tüm üyeleri geçerli bir işleve işaret etmelidir. Kabul edilen işlev imzaları hakkında daha fazla bilgi için bkz. [OnRelogEventFunc](on-relog-event-func-typedef.md), [ontraceinfofunc](on-trace-info-func-typedef.md)ve [onbeginendpassfunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
