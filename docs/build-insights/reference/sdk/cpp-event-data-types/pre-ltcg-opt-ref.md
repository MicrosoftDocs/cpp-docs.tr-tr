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
ms.openlocfilehash: 6786e317f0221126ec6e15c50f3fad58c5982266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923008"
---
# <a name="preltcgoptref-class"></a>Preltcgseçenekbaşvurusu sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`PreLTCGOptRef`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `PreLTCGOptRef` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[PreLTCGOptRef](#pre-ltcg-opt-ref)

## <a name="preltcgoptref"></a><a name="pre-ltcg-opt-ref"></a> Preltcgseçenekbaşvurusu

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) bir olay.

::: moniker-end
