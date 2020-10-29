---
title: Invocationgroup sınıfı
description: C++ Build Insights SDK 'Sı ınvocationgroup sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a8d4786a228ab25551ee36ce22637d44dc07307
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920638"
---
# <a name="invocationgroup-class"></a>Invocationgroup sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`InvocationGroup`Sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Derleyici](../event-table.md#compiler) ve [bağlayıcı](../event-table.md#linker) olaylarının bir karışımını içeren grupları eşleştirmek için bunu kullanın.

## <a name="syntax"></a>Syntax

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Üyeler

Kendi [EventGroup \<Invocation\> ](event-group.md) temel sınıfından devralınan üyelerle birlikte, `InvocationGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[InvocationGroup](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a> Incationgroup

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Parametreler

*grubu*\
[Derleyici](../event-table.md#compiler) ve [bağlayıcı](../event-table.md#linker) olaylarının karışımını içeren bir grup.

::: moniker-end
