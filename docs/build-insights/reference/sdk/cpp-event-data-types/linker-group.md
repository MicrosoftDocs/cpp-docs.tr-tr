---
title: LinkerGroup sınıfı
description: C++ derleme öngörüleri SDK LinkerGroup sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8a818cf7524405d4e2f29a1987e93b77371607cc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923114"
---
# <a name="linkergroup-class"></a>LinkerGroup sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`LinkerGroup`Sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Bağlayıcı](../event-table.md#linker) olaylarının gruplarıyla eşleştirmek için bunu kullanın.

## <a name="syntax"></a>Syntax

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>Üyeler

Kendi [EventGroup \<Linker\> ](event-group.md) temel sınıfından devralınan üyelerle birlikte, `LinkerGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[LinkerGroup](#linker-group)

## <a name="linkergroup"></a><a name="linker-group"></a> LinkerGroup

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>Parametreler

*grubu*\
[Bağlayıcı](../event-table.md#linker) olayları grubu.

::: moniker-end
