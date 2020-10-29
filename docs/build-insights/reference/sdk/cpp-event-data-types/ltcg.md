---
title: LTCG sınıfı
description: C++ derleme öngörüleri SDK LTCG sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LTCG
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3b6bab629307c9fc4fb021df2e75772d5247566d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920560"
---
# <a name="ltcg-class"></a>LTCG sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`LTCG`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [LTCG](../event-table.md#ltcg) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class LTCG : public Activity
{
public:
    LTCG(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `LTCG` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[LTCG](#ltcg)

## <a name="ltcg"></a><a name="ltcg"></a> LTCG

```cpp
LTCG(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [LTCG](../event-table.md#ltcg) olayı.

::: moniker-end
