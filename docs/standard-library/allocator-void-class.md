---
title: ayırıcı &lt; void &gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: b6ca3f8b994756a21d85860fd8aff429ee38e58b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87204943"
---
# <a name="allocatorltvoidgt-class"></a>ayırıcı &lt; void &gt; sınıfı

**`void`** Bu bağlamda anlamlı olan türleri tanımlayarak yazmak için sınıf şablonu ayırıcı özelleştirmesi.

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

Sınıfı, türü için sınıf şablonu [ayırıcısını](allocator-class.md) açık bir şekilde özelleştirir **`void`** . Oluşturucuları ve atama operatörü sınıf şablonuyla aynı şekilde davranır, ancak yalnızca aşağıdaki türleri tanımlar:

- [const_pointer](allocator-class.md#const_pointer).

- [işaretçi](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- iç içe bir sınıf şablonunu yeniden [bağlayın](allocator-class.md#rebind).
