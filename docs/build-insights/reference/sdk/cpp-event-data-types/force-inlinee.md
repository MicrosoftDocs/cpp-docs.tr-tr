---
title: Forceınlinee sınıfı
description: C++ Build Insights SDK Forceınlinee sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53fff7b6cfd37ba3e3211dd072c1ce3386d00fda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920677"
---
# <a name="forceinlinee-class"></a>Forceınlinee sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`ForceInlinee`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FORCE_INLINEE](../event-table.md#force-inlinee) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

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

Devralınan üyelerin [SimpleEvent](simple-event.md) temel sınıfından birlikte, `ForceInlinee` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>İşlevler

[Ad](#name) 
 [Boyut](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a> Forceınlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FORCE_INLINEE](../event-table.md#force-inlinee) bir olay.

## <a name="name"></a><a name="name"></a> Ada

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zorla satır içine alınmış işlevin adı, UTF-8 olarak kodlanır.

## <a name="size"></a><a name="size"></a> Boyutla

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zorla satır içine alınmış işlevin, ara yönerge sayısı olarak boyutu.

::: moniker-end
