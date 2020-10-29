---
title: SimpleEvent sınıfı
description: C++ Build Insights SDK SimpleEvent sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dc09a279157482089adedc660395feaa98376dae
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922997"
---
# <a name="simpleevent-class"></a>SimpleEvent sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`SimpleEvent`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Herhangi bir basit olayla eşleştirmek için kullanın. Sınıfıyla eşleştirileceği tüm olayları görmek için [olay tablosuna](../event-table.md) bakın `SimpleEvent` .

## <a name="syntax"></a>Syntax

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Kendi [olay](event.md) temel sınıfından devralınan üyelerle birlikte, `SimpleEvent` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[SimpleEvent](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a> SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Herhangi bir basit olay.

::: moniker-end
