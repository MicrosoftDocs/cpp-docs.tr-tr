---
title: SymbolName sınıfı
description: C++ Build Insights SDK SymbolName sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1306fb43d6c2140a75b36c5f142532916cf26ae4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324348"
---
# <a name="symbolname-class"></a>SymbolName sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `SymbolName` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [SYMBOL_NAME](../event-table.md#symbol-name) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

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

[SimpleEvent](simple-event.md) taban sınıfından devralınan üyelerle `SymbolName` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Sembol Adı](#symbol-name)

### <a name="functions"></a>İşlevler

[Anahtar](#key)
[Adı](#name)

## <a name="key"></a><a name="key"></a>Anahtar

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu sembolle temsil edilen tür için sayısal bir tanımlayıcı. Bu tanımlayıcı, derleyici ön uç geçişi nde benzersizdir.

## <a name="name"></a><a name="name"></a>Adı

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

UTF-8'de kodlanan sembolle temsil edilen türün adı.

## <a name="symbolname"></a><a name="symbol-name"></a>Sembol Adı

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[SYMBOL_NAME](../event-table.md#symbol-name) bir olay.

::: moniker-end
