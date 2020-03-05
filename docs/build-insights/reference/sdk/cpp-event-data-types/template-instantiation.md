---
title: Templateörneklemesi sınıfı
description: C++ Build Insights SDK 'Sı templateörneklemesi sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2c94f8d3a4613e072c03f6dd4c846798d3d2122b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332973"
---
# <a name="templateinstantiation-class"></a>Templateörneklemesi sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TemplateInstantiation` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olayına uyacak şekilde kullanın.

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

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `TemplateInstantiation` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Templateörneklemesi](#template-instantiation)

### <a name="functions"></a>İşlevler

[Tür](#kind)
[primarytemplatesymbolkey](#primary-template-symbol-key)
[specializationsymbolkey](#specialization-symbol-key)

## <a name="kind"></a>Denetlenmesi

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gerçekleştirilen şablon örneği oluşturma türünü tanımlayan bir kod.

## <a name="primary-template-symbol-key"></a>PrimaryTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelleştirilmiş şablon türü için sayısal bir tanımlayıcı. Bu tanımlayıcı, bir derleyici ön ucu geçişi içinde benzersizdir.

## <a name="specialization-symbol-key"></a>SpecializationSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelleşmenin türü için sayısal tanımlayıcı. Bu tanımlayıcı, bir derleyici ön ucu geçişi içinde benzersizdir.

## <a name="template-instantiation"></a>Templateörneklemesi

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) bir olay.

::: moniker-end
