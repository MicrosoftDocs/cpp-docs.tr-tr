---
title: C2DLL sınıfı
description: C++ Build Insights SDK C2DLL sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C2DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7711acf800999d4e97c3ae56fa2100a632a245b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325087"
---
# <a name="c2dll-class"></a>C2DLL sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `C2DLL` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [C2_DLL](../event-table.md#c2-dll) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class C2DLL : public Activity
{
public:
    C2DLL(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `C2DLL` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[C2DLL](#c2-dll)

## <a name="c2dll"></a><a name="c2-dll"></a>C2DLL

```cpp
C2DLL(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[C2_DLL](../event-table.md#c2-dll) bir olay.

::: moniker-end
