---
title: WholeProgramAnalysis sınıfı
description: C++ BUILD Insights SDK WholeProgramAnalysis sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b8e41242acb9e902b250bab960b1c2042dd981a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332938"
---
# <a name="wholeprogramanalysis-class"></a>WholeProgramAnalysis sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`WholeProgramAnalysis` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `WholeProgramAnalysis` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[WholeProgramAnalysis](#whole-program-analysis)

## <a name="whole-program-analysis"></a>WholeProgramAnalysis

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) bir olay.

::: moniker-end
