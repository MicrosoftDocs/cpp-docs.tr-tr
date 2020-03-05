---
title: TemplateInstantiationGroup sınıfı
description: C++ BUILD Insights SDK TemplateInstantiationGroup sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 281088b4c6cbd39b2fb7677180a7966b490ec3ac
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332994"
---
# <a name="templateinstantiationgroup-class"></a>TemplateInstantiationGroup sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TemplateInstantiationGroup` sınıfı, [Matcheventstack](../functions/match-event-stack.md) ve [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olay gruplarıyla eşleşecek şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Üyeler

[\<Templateörneklemesi\>](event-group.md) temel sınıf olan olay grubundan devralınan üyelere birlikte `TemplateInstantiationGroup` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="template-instantiation-group"></a>TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Parametreler

*grup*\
Bir [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olayları grubu.

::: moniker-end
