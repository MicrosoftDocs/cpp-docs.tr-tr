---
title: Pass1 sınıfı
description: C++ BUILD Insights SDK Pass1 sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d81a933e21f6976624808be358230305459e4992
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333092"
---
# <a name="pass1-class"></a>Pass1 sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Pass1` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bir [PASS1](../event-table.md#pass1) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Inkerpass](linker-pass.md) temel sınıfından devralınan üyelerle birlikte `Pass1` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Pass1](#pass1)

## <a name="pass1"></a>Pass1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [PASS1](../event-table.md#pass1) olayı.

::: moniker-end
