---
title: add_pointer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7a80ffbfbcfb8c350eecc54e87c4cadaaab0295
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841424"
---
# <a name="addpointer-class"></a>add_pointer Sınıfı

Belirtilen türden bir işaretçi türü sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Parametreler

*T* değiştirmek için türü.

## <a name="remarks"></a>Açıklamalar

Üye typedef `type` aynı türde adları `remove_reference<T>::type*`. Diğer ad `add_pointer_t` üye typedef erişmek için bir kısayol `type`.

Bir işaretçi bir başvuru yapmak için geçersiz olduğundan `add_pointer` başvuru varsa kaldırır, kendisinden önce belirtilen türden işaretçi-için-type hale getirir. Sonuç olarak, bir türü ile kullanabileceğiniz `add_pointer` türü bir başvuru olup hakkında kaygı olmadan.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterilmiştir `add_pointer` türü türü için bir işaretçi ile aynıdır.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_pointer Sınıfı](../standard-library/remove-pointer-class.md)<br/>
