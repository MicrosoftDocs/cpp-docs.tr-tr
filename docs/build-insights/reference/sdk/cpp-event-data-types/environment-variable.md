---
title: EnvironmentVariable sınıfı
description: C++ derleme öngörüleri SDK EnvironmentVariable sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f707ab744aaf6097975ba9e189815df3c9f32266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920769"
---
# <a name="environmentvariable-class"></a>EnvironmentVariable sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`EnvironmentVariable`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

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

Devralınan üyelerin [SimpleEvent](simple-event.md) temel sınıfından birlikte, `EnvironmentVariable` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>İşlevler

[Ad](#name) 
 [Değer](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a> EnvironmentVariable

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) bir olay.

## <a name="name"></a><a name="name"></a> Ada

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ortam değişkeninin adı.

## <a name="value"></a><a name="value"></a> Deeri

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ortam değişkeninin değeri.

::: moniker-end
