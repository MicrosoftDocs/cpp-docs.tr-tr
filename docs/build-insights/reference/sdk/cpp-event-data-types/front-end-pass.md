---
title: FrontEndPass sınıfı
description: C++ BUILD Insights SDK ön ek sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cc0bf38c46b51d4a49da46be88e23afa64c12cc8
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333274"
---
# <a name="frontendpass-class"></a>FrontEndPass sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FrontEndPass` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FRONT_END_PASS](../event-table.md#front-end-pass) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

`FrontEndPass` sınıfı, [Compilerpass](compiler-pass.md) temel sınıfından devralınan üyelerle birlikte aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FrontEndPass](#front-end-pass)

## <a name="front-end-pass"></a>FrontEndPass

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FRONT_END_PASS](../event-table.md#front-end-pass) bir olay.

::: moniker-end
