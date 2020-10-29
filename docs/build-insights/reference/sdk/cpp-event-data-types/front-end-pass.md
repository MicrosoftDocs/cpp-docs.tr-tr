---
title: FrontEndPass sınıfı
description: C++ derleme öngörüleri SDK FrontEndPass sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2959b1b80163819287b1907c9d25ca75aa5bbc2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923203"
---
# <a name="frontendpass-class"></a>FrontEndPass sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndPass`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FRONT_END_PASS](../event-table.md#front-end-pass) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

' In [Compilerpass](compiler-pass.md) temel sınıfından devralınan üyelerle birlikte, `FrontEndPass` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FrontEndPass](#front-end-pass)

## <a name="frontendpass"></a><a name="front-end-pass"></a> FrontEndPass

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FRONT_END_PASS](../event-table.md#front-end-pass) bir olay.

::: moniker-end
