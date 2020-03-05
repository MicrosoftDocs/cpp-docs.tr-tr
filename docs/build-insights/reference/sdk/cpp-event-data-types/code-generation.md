---
title: CodeGeneration sınıfı
description: C++ BUILD Insights SDK CodeGeneration sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CodeGeneration
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1bc56794a197b9ae7bf116757581fb5a49699462
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333484"
---
# <a name="codegeneration-class"></a>CodeGeneration sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`CodeGeneration` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [CODE_GENERATION](../event-table.md#code-generation) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class CodeGeneration : public Activity
{
public:
    CodeGeneration(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `CodeGeneration` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[CodeGeneration](#code-generation)

## <a name="code-generation"></a>CodeGeneration

```cpp
CodeGeneration(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[CODE_GENERATION](../event-table.md#code-generation) bir olay.

::: moniker-end
