---
title: is_reference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_reference
dev_langs:
- C++
helpviewer_keywords:
- is_reference class
- is_reference
ms.assetid: 3d9e631f-3092-430c-843e-e914ab58c257
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 306981349f6be43db685eff8c90c81d4cb521569
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isreference-class"></a>is_reference Sınıfı

Tür bir başvuruysa sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_reference;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Ty` başvurudur bir nesne ya da false tuttuğu işlevi, aksi takdirde.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_reference.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_reference<trivial> == " << std::boolalpha
        << std::is_reference<trivial>::value << std::endl;
    std::cout << "is_reference<trivial&> == " << std::boolalpha
        << std::is_reference<trivial&>::value << std::endl;
    std::cout << "is_reference<int()> == " << std::boolalpha
        << std::is_reference<int()>::value << std::endl;
    std::cout << "is_reference<int(&)()> == " << std::boolalpha
        << std::is_reference<int(&)()>::value << std::endl;

    return (0);
    }

```

```Output
is_reference<trivial> == false
is_reference<trivial&> == true
is_reference<int()> == false
is_reference<int(&)()> == true
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_pointer Sınıfı](../standard-library/is-pointer-class.md)<br/>
