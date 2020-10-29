---
title: OptLBR sınıfı
description: C++ Build Insights SDK 'Sı OptLBR sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptLBR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5505e50b0acd961a1ff745eee36419bbaa4bd601
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923052"
---
# <a name="optlbr-class"></a>OptLBR sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`OptLBR`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [OPT_LBR](../event-table.md#opt-lbr) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class OptLBR : public Activity
{
public:
    OptLBR(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `OptLBR` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[OptLBR](#opt-lbr)

## <a name="optlbr"></a><a name="opt-lbr"></a> OptLBR

```cpp
OptLBR(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[OPT_LBR](../event-table.md#opt-lbr) bir olay.

::: moniker-end
