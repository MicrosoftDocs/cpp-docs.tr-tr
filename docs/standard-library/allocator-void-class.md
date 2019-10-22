---
title: ayırıcı &lt;void &gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: c8d787fe03dfe6f67fb8e228308ec74b6e7f620a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688523"
---
# <a name="allocatorltvoidgt-class"></a>ayırıcı &lt;void &gt; sınıfı

Bu bağlamda anlamlı olan türleri tanımlayarak **void**türüne sahip sınıf şablonu ayırıcı özelleştirmesi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, **void**türü için sınıf şablonu [ayırıcısını](../standard-library/allocator-class.md) açık bir şekilde özelleştirir. Oluşturucuları ve atama operatörü sınıf şablonuyla aynı şekilde davranır, ancak yalnızca aşağıdaki türleri tanımlar:

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [işaretçi](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- iç içe bir sınıf şablonunu yeniden [bağlayın](../standard-library/allocator-class.md#rebind).
