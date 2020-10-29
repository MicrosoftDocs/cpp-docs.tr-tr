---
title: OnRelogEventFunc typedef
description: C++ derleme öngörüleri SDK OnRelogEventFunc typedef başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ed639ab59b900f97d29dc69240e45b2f52f2f3b3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919754"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`OnRelogEventFunc`Typedef, [RELOG_CALLBACKS](relog-callbacks-struct.md) yapısında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Geçerli olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

*relogSession*\
[Injectevent](../functions/inject-event.md)çağrılırken kullanılacak yeniden günlüğe kaydetme oturum işaretçisi.

*callbackContext*\
[RELOG_DESCRIPTOR](analysis-descriptor-struct.md)içinde bu geri çağırma için ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını denetleyen [CALLBACK_CODE](callback-code-enum.md) değeri.

::: moniker-end
