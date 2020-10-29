---
title: ObjOutput sınıfı
description: C++ Build Insights SDK 'Sı ObjOutput sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5c88ed6f1faa307d90a73104d3183adc8e50c542
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923068"
---
# <a name="objoutput-class"></a>ObjOutput sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`ObjOutput`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [OBJ_OUTPUT](../event-table.md#obj-output) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya çıkışı](file-output.md) temel sınıfından devralınan üyelerle birlikte, `ObjOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ObjOutput](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a> ObjOutput

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[OBJ_OUTPUT](../event-table.md#obj-output) bir olay.

::: moniker-end
