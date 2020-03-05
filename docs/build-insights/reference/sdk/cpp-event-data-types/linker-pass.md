---
title: LinkerPass sınıfı
description: C++ BUILD Insights SDK LinkerPass sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49a46b57d82391f4c253128c14b1b81d52945eae
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333204"
---
# <a name="linkerpass-class"></a>LinkerPass sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`LinkerPass` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bir [PASS1](../event-table.md#pass1) veya [PASS2](../event-table.md#pass2) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `LinkerPass` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[LinkerPass](#linker-pass)

## <a name="linker-pass"></a>LinkerPass

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [PASS1](../event-table.md#pass1) veya [PASS2](../event-table.md#pass2) olayı.

::: moniker-end
