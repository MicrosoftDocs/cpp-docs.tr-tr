---
title: Function Sınıfı
description: C++ derleme öngörüleri SDK Işlev sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 874477b9ca31095bfcf4ba3c7a6fd220dc073415
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920651"
---
# <a name="function-class"></a>Function Sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Function`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [İşlev](../event-table.md#function) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `Function` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[İşlev](#function)

### <a name="functions"></a>İşlevler

[Ad](#name)

## <a name="function"></a><a name="function"></a> Çalışmayacaktır

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [işlev](../event-table.md#function) olayı.

## <a name="name"></a><a name="name"></a> Ada

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Dönüş Değeri

UTF-8 olarak kodlanmış işlevin adı.

::: moniker-end
