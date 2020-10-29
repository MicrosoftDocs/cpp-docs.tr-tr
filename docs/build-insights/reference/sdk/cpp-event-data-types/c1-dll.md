---
title: C1DLL sınıfı
description: C++ derleme öngörüleri SDK C1DLL sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C1DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a8f1f6fdaf9a2c16e07fa5096cfcb585f8c3d9f2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920847"
---
# <a name="c1dll-class"></a>C1DLL sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`C1DLL`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [C1_DLL](../event-table.md#c1-dll) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class C1DLL : public Activity
{
public:
    C1DLL(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `C1DLL` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[C1DLL](#c1-dll)

## <a name="c1dll"></a><a name="c1-dll"></a> C1DLL

```cpp
C1DLL(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[C1_DLL](../event-table.md#c1-dll) bir olay.

::: moniker-end
