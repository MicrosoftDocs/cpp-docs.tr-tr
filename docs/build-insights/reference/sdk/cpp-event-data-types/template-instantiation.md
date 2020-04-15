---
title: TemplateInstantiation sınıfı
description: C++ Build Insights SDK TemplateInstantiation sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ba8fd10efc6a536c9160f10b19e19e17bfaaad98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324226"
---
# <a name="templateinstantiation-class"></a>TemplateInstantiation sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `TemplateInstantiation` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class TemplateInstantiation : public Activity
{
public:
    enum class Kind
    {
        CLASS       = TEMPLATE_INSTANTIATION_KIND_CODE_CLASS,
        FUNCTION    = TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION,
        VARIABLE    = TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE,
        CONCEPT     = TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT
    };

    TemplateInstantiation(const RawEvent& event);

    const unsigned long long& SpecializationSymbolKey() const;
    const unsigned long long& PrimaryTemplateSymbolKey() const;

    Kind Kind() const;
};
```

## <a name="members"></a>Üyeler

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `TemplateInstantiation` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ŞablonAnında](#template-instantiation)

### <a name="functions"></a>İşlevler

[Tür](#kind)
[PrimaryTemplateSymbolKey](#primary-template-symbol-key)
[UzmanlıkSymbolKey](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a>Tür

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan şablon anlık oluşturma türünü açıklayan bir kod.

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a>BirincilTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelleştirilmiş şablon türü için sayısal bir tanımlayıcı. Bu tanımlayıcı, derleyici ön uç geçişi nde benzersizdir.

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a>UzmanlıkSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uzmanlık türü için sayısal tanımlayıcı. Bu tanımlayıcı, derleyici ön uç geçişi nde benzersizdir.

## <a name="templateinstantiation"></a><a name="template-instantiation"></a>ŞablonAnında

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) bir olay.

::: moniker-end
