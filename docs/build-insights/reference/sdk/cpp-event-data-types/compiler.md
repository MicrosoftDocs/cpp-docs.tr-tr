---
title: Derleyici sınıfı
description: C++ BUILD Insights SDK derleyicisi sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a63a0bad1ab6063d5986fec77b5135f500ded1ce
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333463"
---
# <a name="compiler-class"></a>Derleyici sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Compiler` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bir [derleyici](../event-table.md#compiler) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin, [çağırma](invocation.md) temel sınıfından birlikte `Compiler` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Derleyici](#compiler)

## <a name="compiler"></a>Derleyici

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [derleyici](../event-table.md#compiler) olayı.

::: moniker-end
