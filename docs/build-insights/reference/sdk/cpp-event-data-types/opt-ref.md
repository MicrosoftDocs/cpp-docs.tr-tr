---
title: Seçenekbaşvurusu sınıfı
description: C++ Build Insights SDK 'sı başvuru sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2abad6489012250862bc0721663572d03261bd4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333106"
---
# <a name="optref-class"></a>Seçenekbaşvurusu sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`OptRef` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [OPT_REF](../event-table.md#opt-ref) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `OptRef` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Seçenekbaşvurusu](#opt-ref)

## <a name="opt-ref"></a>Seçenekbaşvurusu

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[OPT_REF](../event-table.md#opt-ref) bir olay.

::: moniker-end
