---
title: add_volatile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf15ef0b5134af7831cf2e71b4235df9534f3425
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841303"
---
# <a name="addvolatile-class"></a>add_volatile Sınıfı

Bir değişken türü belirtilen türden yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parametreler

*T* değiştirmek için türü.

## <a name="remarks"></a>Açıklamalar

Örneği `add_volatile<T>` üye typedef sahip `type` diğer bir deyişle *T* varsa *T* başvuru, bir işlev veya bir geçici nitelenmiş tür Aksi takdirde değer `volatile` *T*. Diğer ad `add_volatile_t` üye typedef erişmek için bir kısayol `type`.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_volatile Sınıfı](../standard-library/remove-volatile-class.md)<br/>
