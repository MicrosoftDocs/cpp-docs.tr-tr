---
title: OptICF sınıfı
description: C++ Build Insights SDK 'Sı OptICF sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptICF
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b7594d573a0e4eaf2e19f306b8a109923ba235dc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333113"
---
# <a name="opticf-class"></a>OptICF sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`OptICF` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [OPT_ICF](../event-table.md#opt-icf) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class OptICF : public Activity
{
public:
    OptICF(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `OptICF` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[OptICF](#opt-icf)

## <a name="opt-icf"></a>OptICF

```cpp
OptICF(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[OPT_ICF](../event-table.md#opt-icf) bir olay.

::: moniker-end
