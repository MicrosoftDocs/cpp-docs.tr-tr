---
title: SymbolName sınıfı
description: C++ Build Insights SDK 'Sı SymbolName sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a749d95b3812df8b1cc0cd7d2da037e98467cefc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920482"
---
# <a name="symbolname-class"></a>SymbolName sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`SymbolName`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [SYMBOL_NAME](../event-table.md#symbol-name) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [SimpleEvent](simple-event.md) temel sınıfından birlikte, `SymbolName` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[SymbolName](#symbol-name)

### <a name="functions"></a>İşlevler

[Anahtar](#key) 
 [Ad](#name)

## <a name="key"></a><a name="key"></a> Anahtar

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu simge tarafından temsil edilen tür için sayısal tanımlayıcı. Bu tanımlayıcı, bir derleyici ön ucu geçişi içinde benzersizdir.

## <a name="name"></a><a name="name"></a> Ada

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

UTF-8 ile kodlanmış, simgesiyle temsil edilen türün adı.

## <a name="symbolname"></a><a name="symbol-name"></a> SymbolName

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[SYMBOL_NAME](../event-table.md#symbol-name) bir olay.

::: moniker-end
