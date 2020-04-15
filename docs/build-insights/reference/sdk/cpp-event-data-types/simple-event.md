---
title: SimpleEvent sınıfı
description: C++ Build Insights SDK SimpleEvent sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 414ff5c1af99acc612384c1ae39f6e12ab051275
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324364"
---
# <a name="simpleevent-class"></a>SimpleEvent sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `SimpleEvent` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. Herhangi bir basit olay maç için kullanın. Sınıftarafından eşleşebilecek tüm olayları görmek için etkinlik `SimpleEvent` [tablosuna](../event-table.md) bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Olay](event.md) taban sınıfından devralınan üyelerle `SimpleEvent` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[SimpleEvent](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a>SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Herhangi bir basit olay.

::: moniker-end
