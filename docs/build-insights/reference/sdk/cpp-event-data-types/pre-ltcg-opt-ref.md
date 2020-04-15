---
title: PreLTCGOptRef sınıfı
description: C++ Build Insights SDK PreLTCGOptRef sınıfı referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a48dc2db0345333da3ec66ccb3a345323b4f10c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324396"
---
# <a name="preltcgoptref-class"></a>PreLTCGOptRef sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `PreLTCGOptRef` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `PreLTCGOptRef` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[PreLTCGOptRef](#pre-ltcg-opt-ref)

## <a name="preltcgoptref"></a><a name="pre-ltcg-opt-ref"></a>PreLTCGOptRef

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) bir olay.

::: moniker-end
