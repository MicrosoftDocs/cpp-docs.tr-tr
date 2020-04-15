---
title: LinkerGroup sınıfı
description: C++ Build Insights SDK LinkerGroup sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c59d62938e5bd7b839ad12a321a03510e708e0fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324654"
---
# <a name="linkergroup-class"></a>LinkerGroup sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `LinkerGroup` MatchEventStack ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [MatchEventStack](../functions/match-event-stack.md) [LINKER](../event-table.md#linker) etkinlik gruplarını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>Üyeler

[OlayGrubu\<Bağlayıcı\> ](event-group.md) taban sınıfından devralınan üyelerle birlikte, `LinkerGroup` sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[LinkerGroup](#linker-group)

## <a name="linkergroup"></a><a name="linker-group"></a>LinkerGroup

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>Parametreler

*Grup*\
BIR grup [LINKER](../event-table.md#linker) olayı.

::: moniker-end
