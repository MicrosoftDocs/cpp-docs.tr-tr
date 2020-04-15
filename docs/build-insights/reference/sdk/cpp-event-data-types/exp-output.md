---
title: ExpOutput sınıfı
description: C++ Build Insights SDK ExpOutput sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4c8c5f2f260596c444df7841c2a3e0c65f5163f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324825"
---
# <a name="expoutput-class"></a>ExpOutput sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `ExpOutput` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [bir EXP_OUTPUT](../event-table.md#exp-output) olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya Çıktısı](file-output.md) taban sınıfından devralınan üyelerle `ExpOutput` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ExpOutput](#exp-output)

## <a name="expoutput"></a><a name="exp-output"></a>ExpOutput

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[EXP_OUTPUT](../event-table.md#exp-output) bir olay.

::: moniker-end
