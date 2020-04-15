---
title: EnvironmentVariable sınıfı
description: C++ Build Insights SDK EnvironmentDeğişken sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 963c52e0ea9e048448c6f2b3ac62d9938817467e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325011"
---
# <a name="environmentvariable-class"></a>EnvironmentVariable sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `EnvironmentVariable` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>Üyeler

[SimpleEvent](simple-event.md) taban sınıfından devralınan üyelerle `EnvironmentVariable` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ÇevreDeğişken](#environment-variable)

### <a name="functions"></a>İşlevler

[Ad](#name)
[Değeri](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a>ÇevreDeğişken

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) bir olay.

## <a name="name"></a><a name="name"></a>Adı

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çevre değişkeninin adı.

## <a name="value"></a><a name="value"></a>Değer

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ortam değişkeninin değeri.

::: moniker-end
