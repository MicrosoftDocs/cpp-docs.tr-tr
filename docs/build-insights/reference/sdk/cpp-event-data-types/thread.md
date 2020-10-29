---
title: Thread sınıfı
description: C++ derleme öngörüleri SDK Iş parçacığı sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Thread
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a483536281aaa87a169a40473fe3f0c4ad10bc96
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922953"
---
# <a name="thread-class"></a>Thread sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Thread`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Iş parçacığı](../event-table.md#thread) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class Thread : public Activity
{
public:
    Thread(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `Thread` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Zincirinin](#thread)

## <a name="thread"></a><a name="thread"></a> Zincirinin

```cpp
Thread(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[Iş parçacığı](../event-table.md#thread) olayı.

::: moniker-end
