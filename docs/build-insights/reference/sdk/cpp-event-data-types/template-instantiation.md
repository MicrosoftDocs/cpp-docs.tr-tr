---
title: Templateörneklemesi sınıfı
description: C++ Build Insights SDK 'Sı Templateörneklemesi sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7ff03aaa431f5c5e217f605698a255686411b479
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920443"
---
# <a name="templateinstantiation-class"></a>Templateörneklemesi sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TemplateInstantiation`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

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

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `TemplateInstantiation` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[TemplateInstantiation](#template-instantiation)

### <a name="functions"></a>İşlevler

[Tür](#kind) 
 [Primarytemplatesymbolkey](#primary-template-symbol-key) 
 [Specializationsymbolkey](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a> Denetlenmesi

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gerçekleştirilen şablon örneği oluşturma türünü tanımlayan bir kod.

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a> PrimaryTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelleştirilmiş şablon türü için sayısal bir tanımlayıcı. Bu tanımlayıcı, bir derleyici ön ucu geçişi içinde benzersizdir.

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a> SpecializationSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelleşmenin türü için sayısal tanımlayıcı. Bu tanımlayıcı, bir derleyici ön ucu geçişi içinde benzersizdir.

## <a name="templateinstantiation"></a><a name="template-instantiation"></a> Templateörneklemesi

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) bir olay.

::: moniker-end
