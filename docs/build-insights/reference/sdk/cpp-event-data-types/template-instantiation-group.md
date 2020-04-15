---
title: TemplateInstantiationGroup sınıfı
description: C++ Build Insights SDK TemplateInstantiationGroup sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 18dd48219c7c68ce152c381eb505fe37b19ec8dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324267"
---
# <a name="templateinstantiationgroup-class"></a>TemplateInstantiationGroup sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `TemplateInstantiationGroup` MatchEventStack ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [MatchEventStack](../functions/match-event-stack.md) [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) etkinlik gruplarını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Üyeler

[OlayGrubu\<\> TemplateInstantiation](event-group.md) taban sınıfından devralınan üyelerle birlikte, `TemplateInstantiationGroup` sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a>TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Parametreler

*Grup*\
Bir grup [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olayı.

::: moniker-end
