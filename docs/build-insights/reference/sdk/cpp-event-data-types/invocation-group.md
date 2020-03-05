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
ms.openlocfilehash: b9a2bbcd2b7649b9b5703adc08ed41b272e10276
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333239"
---
# <a name="invocationgroup-class"></a>Invocationgroup sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`InvocationGroup` sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Derleyici](../event-table.md#compiler) ve [bağlayıcı](../event-table.md#linker) olaylarının bir karışımını içeren grupları eşleştirmek için bunu kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Üyeler

\<\>temel sınıf olan [EventGroup](event-group.md) 'tan devralınan üyelere birlikte `InvocationGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Incationgroup](#invocation-group)

## <a name="invocation-group"></a>Incationgroup

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Parametreler

*grup*\
[Derleyici](../event-table.md#compiler) ve [bağlayıcı](../event-table.md#linker) olaylarının karışımını içeren bir grup.

::: moniker-end
