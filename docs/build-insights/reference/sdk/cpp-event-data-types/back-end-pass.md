---
title: BackEndPass sınıfı
description: C++ BUILD Insights SDK BackEndPass sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c159fa09b5d8a4156fc6bd886fc36da09a66db73
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333547"
---
# <a name="backendpass-class"></a>BackEndPass sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`BackEndPass` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [BACK_END_PASS](../event-table.md#back-end-pass) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

`BackEndPass` sınıfı, [Compilerpass](compiler-pass.md) temel sınıfından devralınan üyelerle birlikte aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[BackEndPass](#back-end-pass)

## <a name="back-end-pass"></a>BackEndPass

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[BACK_END_PASS](../event-table.md#back-end-pass) bir olay.

::: moniker-end
