---
title: Pass1 sınıfı
description: C++ derleme öngörüleri SDK Pass1 sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 99ada8a2db5ac464113d9805797d4b4555367e77
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923038"
---
# <a name="pass1-class"></a>Pass1 sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Pass1`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bir [PASS1](../event-table.md#pass1) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Inkerpass](linker-pass.md) temel sınıfından devralınan üyelerle birlikte, `Pass1` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Pass1](#pass1)

## <a name="pass1"></a><a name="pass1"></a> Pass1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [PASS1](../event-table.md#pass1) olayı.

::: moniker-end
