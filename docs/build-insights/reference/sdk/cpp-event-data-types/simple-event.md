---
title: SimpleEvent sınıfı
description: C++ Derleme ÖNGÖRÜLERI SDK basit olay sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4c30f81236138328322d8c870d4ad69d9988b49a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333050"
---
# <a name="simpleevent-class"></a>SimpleEvent sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`SimpleEvent` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Herhangi bir basit olayla eşleştirmek için kullanın. `SimpleEvent` sınıfıyla eşleştirileceği tüm olayları görmek için [olay tablosuna](../event-table.md) bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [olay](event.md) temel sınıfından birlikte `SimpleEvent` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[SimpleEvent](#simple-event)

## <a name="simple-event"></a>SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Herhangi bir basit olay.

::: moniker-end
