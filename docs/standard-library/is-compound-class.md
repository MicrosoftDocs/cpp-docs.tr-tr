---
title: is_compound Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: ea878af96908478b1956deee3858a9d2f48c2f0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502082"
---
# <a name="iscompound-class"></a>is_compound Sınıfı

Belirtilen tür temel olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Bir tür koşulu örneğini **false** varsa türünü *Ty* temel türü (varsa, diğer bir deyişle, [is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > tutar  **doğru**); Aksi halde tutan **true**. Bu nedenle, koşul tutan **true** varsa *Ty* olan bir dizi türü, bir işlev türü, işaretçi **void** veya bir nesneye veya bir işlev, başvuru, bir sınıf, UNION, bir numaralandırma veya bir Statik olmayan sınıf üye işaretçisi veya *cv nitelenmiş* bunlardan birinin biçimi.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }

```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_class Sınıfı](../standard-library/is-class-class.md)<br/>
