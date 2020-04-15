---
title: Derleyici sınıfı
description: C++ Build Insights SDK Derleyici sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9b0a2622c4bc0bc19d7222977fe24c060ee8709e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325026"
---
# <a name="compiler-class"></a>Derleyici sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `Compiler` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [DerLEYICI](../event-table.md#compiler) olayıyla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Çağrı](invocation.md) taban sınıfından devralınan üyelerle birlikte, `Compiler` sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Derleyici](#compiler)

## <a name="compiler"></a><a name="compiler"></a>Derleyici

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[Derleyici](../event-table.md#compiler) olayı.

::: moniker-end
