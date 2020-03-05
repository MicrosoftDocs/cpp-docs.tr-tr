---
title: Preltcgseçenekbaşvurusu sınıfı
description: C++ Build Insights SDK 'Sı Preltcgseçenekbaşvurusu sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4690feddcf615a82226ce5ad2f3ee242749db04a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333071"
---
# <a name="preltcgoptref-class"></a>Preltcgseçenekbaşvurusu sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`PreLTCGOptRef` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `PreLTCGOptRef` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Preltcgseçenekbaşvurusu](#pre-ltcg-opt-ref)

## <a name="pre-ltcg-opt-ref"></a>Preltcgseçenekbaşvurusu

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) bir olay.

::: moniker-end
