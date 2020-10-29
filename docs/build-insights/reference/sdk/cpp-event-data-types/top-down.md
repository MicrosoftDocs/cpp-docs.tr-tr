---
title: Topın sınıfı
description: C++ derleme öngörüleri SDK 'Sı alt sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88622461b27a6037d8d7fbb73cd324978302c941
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920430"
---
# <a name="topdown-class"></a>Topın sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TopDown`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [TOP_DOWN](../event-table.md#top-down) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `TopDown` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[TopDown](#top-down)

## <a name="topdown"></a><a name="top-down"></a> Aşağı aşağı

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[TOP_DOWN](../event-table.md#top-down) bir olay.

::: moniker-end
