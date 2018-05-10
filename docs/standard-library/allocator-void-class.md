---
title: Allocator&lt;void&gt; sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4179ddae0506d21ca3969559b05c618ab4d73e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt; sınıfı

Türü için Şablon sınıfı ayırıcısı uzmanlaşması `void`, bu bağlamda anlamlı türleri tanımlama.

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

Sınıf şablonu sınıfı açıkça uzmanlaşmış [ayırıcısı](../standard-library/allocator-class.md) türü için *void.* Oluşturucular ve atama işleci Şablon sınıfı için olduğu gibi aynı şekilde davranır, ancak yalnızca şu türleri tanımlar:

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [İşaretçi](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [rebind](../standard-library/allocator-class.md#rebind), bir şablon sınıfı iç içe geçmiş.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
