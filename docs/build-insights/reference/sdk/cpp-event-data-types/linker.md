---
title: Bağlayıcı sınıfı
description: C++ Derleme ÖNGÖRÜLERI SDK Bağlayıcısı sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bb8948d7772046e18d5db5002deed48d0dd88375
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333190"
---
# <a name="linker-class"></a>Bağlayıcı sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Linker` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Bağlayıcı](../event-table.md#linker) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin, [çağırma](invocation.md) temel sınıfından birlikte `Linker` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Bağlayıcı](#linker)

## <a name="linker"></a>Bağlayıcı

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[Bağlayıcı](../event-table.md#linker) olayı.

::: moniker-end
