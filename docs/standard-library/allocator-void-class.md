---
title: Allocator&lt;void&gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: 5591570527946895d1e0456b23327d7fabc4bef5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646122"
---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt; sınıfı

Bir türüne şablon sınıf ayırıcı uzmanlığı **void**, bu bağlamda mantıklı türleri tanımlama.

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

Sınıfı bir şablon sınıfı açıkça uzmanlaşmış [ayırıcı](../standard-library/allocator-class.md) türünün **void**. Oluşturucu ve atama işleci Şablon sınıfı olduğu gibi aynı şekilde davranır, ancak yalnızca şu türleri tanımlar:

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [İşaretçi](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [rebind](../standard-library/allocator-class.md#rebind), iç içe geçmiş Şablon sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
