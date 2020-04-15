---
title: Pass1 sınıfı
description: C++ Build Insights SDK Pass1 sınıfı referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 039c2cc92b8461009c235baa7e49484eb2a4f49f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324415"
---
# <a name="pass1-class"></a>Pass1 sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `Pass1` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. Bir [PASS1](../event-table.md#pass1) olayıyla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Kendi LinkerPass](linker-pass.md) taban sınıfından devralınan üyeleri `Pass1` ile birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Geçiş1](#pass1)

## <a name="pass1"></a><a name="pass1"></a>Geçiş1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Bir [PASS1](../event-table.md#pass1) olayı.

::: moniker-end
