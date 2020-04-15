---
title: ForceInlinee sınıfı
description: C++ Build Insights SDK ForceInlinee sınıfı referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c6a1af0384197a0a3b6062ad9ef30537c348190d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324778"
---
# <a name="forceinlinee-class"></a>ForceInlinee sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `ForceInlinee` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [FORCE_INLINEE](../event-table.md#force-inlinee) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>Üyeler

[SimpleEvent](simple-event.md) taban sınıfından devralınan üyelerle `ForceInlinee` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>İşlevler

[Ad](#name)
[Boyutu](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a>ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[FORCE_INLINEE](../event-table.md#force-inlinee) bir olay.

## <a name="name"></a><a name="name"></a>Adı

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

UTF-8'de kodlanmış kuvvet inlined fonksiyonunun adı.

## <a name="size"></a><a name="size"></a>Boyutu

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir ara öğretim sayısı olarak kuvvet inlined fonksiyonun boyutu.

::: moniker-end
