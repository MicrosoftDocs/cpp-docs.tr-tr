---
description: 'Hakkında daha fazla bilgi edinin: is_pointer sınıfı'
title: is_pointer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_pointer
helpviewer_keywords:
- is_pointer class
- is_pointer
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
ms.openlocfilehash: 003f25a40edd3f4c0b80a8402d38027cd81949cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230646"
---
# <a name="is_pointer-class"></a>is_pointer Sınıfı

Tür bir işaretçisiyse sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_pointer;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir işaretçi, bir nesne işaretçisi veya bir işlev işaretçisi ya da bunlardan birinin bir biçimi ise, yanlış *bir değer içeriyorsa* tür belirtiminin bir örneği true olarak tutulur **`void`** `cv-qualified` . `is_pointer` *Ty* bir üye işaretçisi veya üye işlevine yönelik bir işaretçi ise, yanlış bir değer içerir.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_pointer<trivial> == " << std::boolalpha
        << std::is_pointer<trivial>::value << std::endl;
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha
        << std::is_pointer<int trivial::*>::value << std::endl;
    std::cout << "is_pointer<trivial *> == " << std::boolalpha
        << std::is_pointer<trivial *>::value << std::endl;
    std::cout << "is_pointer<int> == " << std::boolalpha
        << std::is_pointer<int>::value << std::endl;
    std::cout << "is_pointer<int *> == " << std::boolalpha
        << std::is_pointer<int *>::value << std::endl;

    return (0);
    }
```

```Output
is_pointer<trivial> == false
is_pointer<int trivial::*> == false
is_pointer<trivial *> == true
is_pointer<int> == false
is_pointer<int *> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_member_pointer sınıfı](../standard-library/is-member-pointer-class.md)\
[is_reference sınıfı](../standard-library/is-reference-class.md)
