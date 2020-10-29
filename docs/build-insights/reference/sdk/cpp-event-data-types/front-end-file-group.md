---
title: Frontendfılegroup sınıfı
description: C++ derleme öngörüleri SDK Frontendfılegroup sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 902b394f645030fed4eeb79bae79535e6d246a1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923237"
---
# <a name="frontendfilegroup-class"></a>Frontendfılegroup sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFileGroup`Sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [FRONT_END_FILE](../event-table.md#front-end-file) olay gruplarıyla eşleşecek şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>Üyeler

Kendi [EventGroup \<FrontEndFile\> ](event-group.md) temel sınıfından devralınan üyelerle birlikte, `FrontEndFileGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FrontEndFileGroup](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a> Frontendfılegroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>Parametreler

*grubu*\
Bir [FRONT_END_FILE](../event-table.md#front-end-file) olayları grubu.

::: moniker-end
