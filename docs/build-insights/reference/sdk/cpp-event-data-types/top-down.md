---
title: Topın sınıfı
description: C++ Build Insights SDK 'sı alt sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2d4ef1f2f824bca9ab8e45f8fb030727e6e4007b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332952"
---
# <a name="topdown-class"></a>Topın sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TopDown` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [TOP_DOWN](../event-table.md#top-down) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `TopDown` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Aşağı aşağı](#top-down)

## <a name="top-down"></a>Aşağı aşağı

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[TOP_DOWN](../event-table.md#top-down) bir olay.

::: moniker-end
