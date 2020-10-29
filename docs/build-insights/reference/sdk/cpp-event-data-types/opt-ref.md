---
title: Seçenekbaşvurusu sınıfı
description: C++ derleme öngörüleri SDK 'Sı başvuru sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72d3867456ecc2bb643239ddb0186668e43f69ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920521"
---
# <a name="optref-class"></a>Seçenekbaşvurusu sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`OptRef`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [OPT_REF](../event-table.md#opt-ref) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `OptRef` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[OptRef](#opt-ref)

## <a name="optref"></a><a name="opt-ref"></a> Seçenekbaşvurusu

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[OPT_REF](../event-table.md#opt-ref) bir olay.

::: moniker-end
