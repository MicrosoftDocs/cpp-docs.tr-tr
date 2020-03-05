---
title: Frontendfılegroup sınıfı
description: C++ BUILD Insights SDK ön ek sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 343a5a0d798d6c719088bd49668e70b10fba6d1a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333330"
---
# <a name="frontendfilegroup-class"></a>Frontendfılegroup sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FrontEndFileGroup` sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [FRONT_END_FILE](../event-table.md#front-end-file) olay gruplarıyla eşleşecek şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>Üyeler

[\<FrontEndFile\>temel sınıfındaki EventGroup](event-group.md) 'un devralınan üyeleri ile birlikte `FrontEndFileGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Frontendfılegroup](#front-end-file-group)

## <a name="front-end-file-group"></a>Frontendfılegroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>Parametreler

*grup*\
Bir [FRONT_END_FILE](../event-table.md#front-end-file) olayları grubu.

::: moniker-end
