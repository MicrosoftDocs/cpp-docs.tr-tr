---
title: ImpLibOutput sınıfı
description: C++ Build Insights SDK ImpLibOutput sınıf referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ImpLibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 98905dfe75484e98e14a0fa575e75fe3ab284559
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324710"
---
# <a name="impliboutput-class"></a>ImpLibOutput sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `ImpLibOutput` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class ImpLibOutput : public FileOutput
{
public:
    ImpLibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya Çıktısı](file-output.md) taban sınıfından devralınan üyelerle `ImpLibOutput` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ImplibOutput](#imp-lib-output)

## <a name="impliboutput"></a><a name="imp-lib-output"></a>ImplibOutput

```cpp
ImpLibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) bir olay.

::: moniker-end
