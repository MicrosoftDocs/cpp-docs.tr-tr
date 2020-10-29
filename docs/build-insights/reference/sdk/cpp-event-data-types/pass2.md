---
title: Pass2 sınıfı
description: C++ derleme öngörüleri SDK Pass2 sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 17f915371f70a6f4398d91251680c460aa231feb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920508"
---
# <a name="pass2-class"></a>Pass2 sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Pass2`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bir [PASS2](../event-table.md#pass2) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Inkerpass](linker-pass.md) temel sınıfından devralınan üyelerle birlikte, `Pass2` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Pass2](#pass2)

## <a name="pass2"></a><a name="pass2"></a> Pass2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [PASS2](../event-table.md#pass2) olayı.

::: moniker-end
