---
title: RELOG_CALLBACKS yapısı
description: C++ derleme öngörüleri SDK RELOG_CALLBACKS yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b3beb656aa72ce4c8519c56c4c8bf6ca6577cf4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919806"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_CALLBACKS` [RELOG_DESCRIPTOR](relog-descriptor-struct.md) nesnesi başlatılırken yapı kullanılır. Windows için olay Izleme (ETW) izlemenin yeniden günlüğe kaydedilmesi sırasında hangi işlevlerin çağrılacağını belirtir.

## <a name="syntax"></a>Syntax

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

| Ad | Açıklama |
|--|--|
| `OnStartActivity` | Etkinlik başlangıç olayını işlemek için çağırılır. |
| `OnStopActivity` | Etkinlik durdurma olayını işlemek için çağırılır. |
| `OnSimpleEvent` | Basit bir olayı işlemek için çağırılır. |
| `OnTraceInfo` | Yeniden oturum açma geçişinin başlangıcında bir kez çağırılır, sonrasında `OnBeginReloggingPass` çağırılır. |
| `OnBeginRelogging` | Yeniden günlüğe kaydetme geçişi başlamadan önce, yeniden günlüğe kaydetme oturumu başladığında çağırılır. |
| `OnEndRelogging` | Yeniden günlüğe kaydetme geçişi sona erdikten sonra bir yeniden günlüğe kaydetme oturumu sonlandırırken çağırılır. |
| `OnBeginReloggingPass` | Yeniden oturum açma geçişi Başlarken, herhangi bir olay işlenmeden önce çağırılır. |
| `OnEndReloggingPass` | Yeniden günlüğe kaydetme geçişi sonlandırırken, tüm olaylar işlendikten sonra çağırılır. |

## <a name="remarks"></a>Açıklamalar

Yapının tüm üyeleri `RELOG_CALLBACKS` geçerli bir işleve işaret etmelidir. Kabul edilen işlev imzaları hakkında daha fazla bilgi için bkz. [OnRelogEventFunc](on-relog-event-func-typedef.md), [ontraceinfofunc](on-trace-info-func-typedef.md)ve [onbeginendpassfunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
