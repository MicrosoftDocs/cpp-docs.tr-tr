---
title: TopDown sınıfı
description: C++ Build Insights SDK TopDown sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7c0c957fa17daaec34710debeda634192c63d1da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324208"
---
# <a name="topdown-class"></a>TopDown sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `TopDown` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [TOP_DOWN](../event-table.md#top-down) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `TopDown` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Topdown](#top-down)

## <a name="topdown"></a><a name="top-down"></a>Topdown

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[TOP_DOWN](../event-table.md#top-down) bir olay.

::: moniker-end
