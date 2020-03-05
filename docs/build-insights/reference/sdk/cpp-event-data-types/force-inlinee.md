---
title: Forceınlinee sınıfı
description: C++ Build Insights SDK 'Sı Forceınlinee sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7d3cce13601a0b3edbcd2b57664b2d0d94a7d3df
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333337"
---
# <a name="forceinlinee-class"></a>Forceınlinee sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`ForceInlinee` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FORCE_INLINEE](../event-table.md#force-inlinee) olayına uyacak şekilde kullanın.

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

[SimpleEvent](simple-event.md) temel sınıfından devralınan üyelerle birlikte `ForceInlinee` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Forceınlinee](#force-inlinee)

### <a name="functions"></a>İşlevler

[Ad](#name)
[boyutu](#size)

## <a name="force-inlinee"></a>Forceınlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FORCE_INLINEE](../event-table.md#force-inlinee) bir olay.

## <a name="name"></a>Ada

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zorla satır içine alınmış işlevin adı, UTF-8 olarak kodlanır.

## <a name="size"></a>Boyutla

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zorla satır içine alınmış işlevin, ara yönerge sayısı olarak boyutu.

::: moniker-end
