---
title: InvocationGroup sınıfı
description: C++ Build Insights SDK InvocationGroup sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ff5a73d5304a21c314c0fc5ce442e0ffc23b28fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324685"
---
# <a name="invocationgroup-class"></a>InvocationGroup sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `InvocationGroup` MatchEventStack ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [MatchEventStack](../functions/match-event-stack.md) [DERLEYICI](../event-table.md#compiler) ve [LINKER](../event-table.md#linker) olaylarının bir karışımını içeren grupları eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Üyeler

[OlayGrubu\<Çağırma\> ](event-group.md) taban sınıfından devralınan üyelerle `InvocationGroup` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Çağrı Grubu](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a>Çağrı Grubu

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Parametreler

*Grup*\
[DERLEYICI](../event-table.md#compiler) ve [LINKER](../event-table.md#linker) olaylarının bir karışımını içeren bir grup.

::: moniker-end
