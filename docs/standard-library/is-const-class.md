---
title: is_const sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_const
dev_langs:
- C++
helpviewer_keywords:
- is_const class
- is_const
ms.assetid: 55b8e887-9c3f-4a1d-823a-4a257337b205
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e7cb63583f8c3dda0515e198d31086432785df3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isconst-class"></a>is_const Sınıfı

Const türündeyse testleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_const;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Varsa true türü koşulu örneğini tutan `Ty` olan `const-qualified`.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
{
    int val;
};

int main()
{
    std::cout << "is_const<trivial> == " << std::boolalpha
        << std::is_const<trivial>::value << std::endl;
    std::cout << "is_const<const trivial> == " << std::boolalpha
        << std::is_const<const trivial>::value << std::endl;
    std::cout << "is_const<int> == " << std::boolalpha
        << std::is_const<int>::value << std::endl;
    std::cout << "is_const<const int> == " << std::boolalpha
        << std::is_const<const int>::value << std::endl;

    return (0);
}

```

```Output
is_const<trivial> == false
is_const<const trivial> == true
is_const<int> == false
is_const<const int> == true
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_volatile Sınıfı](../standard-library/is-volatile-class.md)<br/>
