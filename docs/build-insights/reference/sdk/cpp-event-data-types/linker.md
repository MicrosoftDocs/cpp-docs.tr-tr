---
title: Bağlayıcı sınıfı
description: C++ derleme öngörüleri SDK Bağlayıcısı sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf5544d725c12db8962d888944d4a281387207fa
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923095"
---
# <a name="linker-class"></a>Bağlayıcı sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Linker`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Bağlayıcı](../event-table.md#linker) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin, [çağırma](invocation.md) temel sınıfından birlikte, `Linker` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Bağlayıcı](#linker)

## <a name="linker"></a><a name="linker"></a> Bağlayıcı

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[Bağlayıcı](../event-table.md#linker) olayı.

::: moniker-end
