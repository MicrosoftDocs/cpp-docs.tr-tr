---
title: Derleyici sınıfı
description: C++ derleme öngörüleri SDK derleyicisi sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 52f8bb2ffc474cbf8e58552c77a4bb9fabc13c7e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923318"
---
# <a name="compiler-class"></a>Derleyici sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Compiler`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bir [derleyici](../event-table.md#compiler) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin, [çağırma](invocation.md) temel sınıfından birlikte, `Compiler` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Derleyici](#compiler)

## <a name="compiler"></a><a name="compiler"></a> Derleyici

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [derleyici](../event-table.md#compiler) olayı.

::: moniker-end
