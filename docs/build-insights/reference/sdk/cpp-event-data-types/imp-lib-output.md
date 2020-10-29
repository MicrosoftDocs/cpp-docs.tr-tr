---
title: Implii put sınıfı
description: C++ Build Insights SDK 'Sı ımplii put sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ImpLibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 01adb0041a3d212acf1bb846ced9019600016cda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923180"
---
# <a name="impliboutput-class"></a>Implii put sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`ImpLibOutput`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class ImpLibOutput : public FileOutput
{
public:
    ImpLibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya çıkışı](file-output.md) temel sınıfından devralınan üyelerle birlikte, `ImpLibOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ImpLibOutput](#imp-lib-output)

## <a name="impliboutput"></a><a name="imp-lib-output"></a> Implii put

```cpp
ImpLibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) bir olay.

::: moniker-end
