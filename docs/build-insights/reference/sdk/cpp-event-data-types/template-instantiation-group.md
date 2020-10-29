---
title: TemplateInstantiationGroup sınıfı
description: C++ derleme öngörüleri SDK TemplateInstantiationGroup sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bacd48fbf15bfbbd768b527f42587425fb0932e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922977"
---
# <a name="templateinstantiationgroup-class"></a>TemplateInstantiationGroup sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TemplateInstantiationGroup`Sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olay gruplarıyla eşleşecek şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Üyeler

Kendi [EventGroup \<TemplateInstantiation\> ](event-group.md) temel sınıfından devralınan üyelerle birlikte, `TemplateInstantiationGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a> TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Parametreler

*grubu*\
Bir [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olayları grubu.

::: moniker-end
