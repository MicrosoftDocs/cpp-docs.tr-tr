---
description: 'Daha fazla bilgi edinin: ayırıcı &lt; void &gt; sınıfı'
title: ayırıcı &lt; void &gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: a6468c35f4660736cd297ffd7ae3d0738bbf0756
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163515"
---
# <a name="allocatorltvoidgt-class"></a>ayırıcı &lt; void &gt; sınıfı

**`void`** Bu bağlamda anlamlı olan türleri tanımlayarak yazmak için sınıf şablonu ayırıcı özelleştirmesi.

## <a name="syntax"></a>Syntax

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

Sınıfı, türü için sınıf şablonu [ayırıcısını](allocator-class.md) açık bir şekilde özelleştirir **`void`** . Oluşturucuları ve atama operatörü sınıf şablonuyla aynı şekilde davranır, ancak yalnızca aşağıdaki türleri tanımlar:

- [const_pointer](allocator-class.md#const_pointer).

- [işaretçi](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- iç içe bir sınıf şablonunu yeniden [bağlayın](allocator-class.md#rebind).
