---
title: EnvironmentVariable sınıfı
description: C++ BUILD Insights SDK EnvironmentVariable sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 19e9278e76fb2116dac30a0e790fba86c6c56484
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333442"
---
# <a name="environmentvariable-class"></a>EnvironmentVariable sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`EnvironmentVariable` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) bir olayla eşleştirmek için kullanın.

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

[SimpleEvent](simple-event.md) temel sınıfından devralınan üyelerle birlikte `EnvironmentVariable` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>İşlevler

[Ad](#name)
[değeri](#value)

## <a name="environment-variable"></a>EnvironmentVariable

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) bir olay.

## <a name="name"></a>Ada

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ortam değişkeninin adı.

## <a name="value"></a>Deeri

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ortam değişkeninin değeri.

::: moniker-end
