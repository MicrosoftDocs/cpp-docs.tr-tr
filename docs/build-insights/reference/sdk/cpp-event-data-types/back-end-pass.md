---
title: BackEndPass sınıfı
description: C++ Build Insights SDK BackEndPass sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b4b1a219abdbe418efaab4537f1c6dc9a22afb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325233"
---
# <a name="backendpass-class"></a>BackEndPass sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `BackEndPass` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [BACK_END_PASS](../event-table.md#back-end-pass) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[DerleyiciPass](compiler-pass.md) taban sınıfından devralınan üyelerle `BackEndPass` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Arka Geçit](#back-end-pass)

## <a name="backendpass"></a><a name="back-end-pass"></a>Arka Geçit

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[BACK_END_PASS](../event-table.md#back-end-pass) bir olay.

::: moniker-end
