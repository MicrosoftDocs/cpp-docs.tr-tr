---
title: Lii put sınıfı
description: C++ derleme öngörüleri SDK 'Sı oluşturma sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7cb759403a3e9b922ffa861b3938bcb874adac32
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920625"
---
# <a name="liboutput-class"></a>Lii put sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`LibOutput`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [LIB_OUTPUT](../event-table.md#lib-output) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class LibOutput : public FileOutput
{
public:
    LibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya çıkışı](file-output.md) temel sınıfından devralınan üyelerle birlikte, `LibOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[LibOutput](#lib-output)

## <a name="liboutput"></a><a name="lib-output"></a> Lii put

```cpp
LibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[LIB_OUTPUT](../event-table.md#lib-output) bir olay.

::: moniker-end
