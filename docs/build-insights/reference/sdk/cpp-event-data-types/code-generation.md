---
title: CodeGeneration sınıfı
description: C++ Build Insights SDK CodeGeneration sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CodeGeneration
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9d9ba3667a96c0a4fa4fe6dc76087536ef2202e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920833"
---
# <a name="codegeneration-class"></a>CodeGeneration sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`CodeGeneration`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [CODE_GENERATION](../event-table.md#code-generation) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class CodeGeneration : public Activity
{
public:
    CodeGeneration(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `CodeGeneration` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[CodeGeneration](#code-generation)

## <a name="codegeneration"></a><a name="code-generation"></a> CodeGeneration

```cpp
CodeGeneration(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[CODE_GENERATION](../event-table.md#code-generation) bir olay.

::: moniker-end
