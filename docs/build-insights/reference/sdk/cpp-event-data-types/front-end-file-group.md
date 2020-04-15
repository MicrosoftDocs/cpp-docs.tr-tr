---
title: FrontEndFileGroup sınıfı
description: C++ Build Insights SDK FrontEndFileGroup sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d2eebb650e59e750e5ebde74914dca5f0ef4779d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324767"
---
# <a name="frontendfilegroup-class"></a>FrontEndFileGroup sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `FrontEndFileGroup` MatchEventStack ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [MatchEventStack](../functions/match-event-stack.md) [FRONT_END_FILE](../event-table.md#front-end-file) etkinlik gruplarını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>Üyeler

[EventGroup\<\> FrontEndFile](event-group.md) taban sınıfından devralınan üyelerle `FrontEndFileGroup` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FrontEndFileGroup](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a>FrontEndFileGroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>Parametreler

*Grup*\
Bir grup [FRONT_END_FILE](../event-table.md#front-end-file) olayı.

::: moniker-end
