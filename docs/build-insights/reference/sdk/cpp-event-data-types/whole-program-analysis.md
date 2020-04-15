---
title: WholeProgramAnalysis sınıfı
description: C++ Build Insights SDK WholeProgramAnalysis sınıf referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c68441b7da09f9880bbb2f97544b1ad8da2f631f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324125"
---
# <a name="wholeprogramanalysis-class"></a>WholeProgramAnalysis sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `WholeProgramAnalysis` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `WholeProgramAnalysis` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[BütünProgramAnalizi](#whole-program-analysis)

## <a name="wholeprogramanalysis"></a><a name="whole-program-analysis"></a>BütünProgramAnalizi

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) bir olay.

::: moniker-end
