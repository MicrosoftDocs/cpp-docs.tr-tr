---
title: ayırıcı &lt; void &gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: af29c70dca56b1e68eef3614357269c587a77ec9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623675"
---
# <a name="allocatorltvoidgt-class"></a>ayırıcı &lt; void &gt; sınıfı

Bu bağlamda anlamlı olan türleri tanımlayarak **void**türüne sahip sınıf şablonu ayırıcı özelleştirmesi.

## <a name="syntax"></a>Söz dizimi

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

Sınıfı, **void**türü için sınıf şablonu [ayırıcısını](allocator-class.md) açık bir şekilde özelleştirir. Oluşturucuları ve atama operatörü sınıf şablonuyla aynı şekilde davranır, ancak yalnızca aşağıdaki türleri tanımlar:

- [const_pointer](allocator-class.md#const_pointer).

- [işaretçi](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- iç içe bir sınıf şablonunu yeniden [bağlayın](allocator-class.md#rebind).
