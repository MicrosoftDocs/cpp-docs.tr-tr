---
title: Bağlayıcı sınıfı
description: C++ Build Insights SDK Linker sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e5d4c0c3841377fc2e029c23d5cbbd076c8029cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324594"
---
# <a name="linker-class"></a>Bağlayıcı sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `Linker` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [Bir LINKER](../event-table.md#linker) olayıyla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Çağrı](invocation.md) taban sınıfından devralınan üyelerle birlikte, `Linker` sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Bağlayıcı](#linker)

## <a name="linker"></a><a name="linker"></a>Bağlayıcı

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Bir [LINKER](../event-table.md#linker) olayı.

::: moniker-end
