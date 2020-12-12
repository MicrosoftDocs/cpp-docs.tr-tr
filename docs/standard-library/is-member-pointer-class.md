---
description: 'Hakkında daha fazla bilgi edinin: is_member_pointer sınıfı'
title: is_member_pointer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_member_pointer
helpviewer_keywords:
- is_member_pointer class
- is_member_pointer
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
ms.openlocfilehash: e1e2e5be39859109dd707f55a368fabe19f477a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323652"
---
# <a name="is_member_pointer-class"></a>is_member_pointer Sınıfı

Türün üye işaretçisi olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_member_pointer;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür kümesi bir üye işlevi işaretçisi veya üye nesnesi işaretçisi ya da bunlardan birinin bir biçimi ise, yanlış *bir değer içeriyorsa* tür belirtiminin bir örneği true olarak saklar `cv-qualified` .

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_member_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_member_pointer<trivial *> == "
        << std::boolalpha
        << std::is_member_pointer<trivial *>::value
        << std::endl;
    std::cout << "is_member_pointer<int trivial::*> == "
        << std::boolalpha
        << std::is_member_pointer<int trivial::*>::value
        << std::endl;
    std::cout << "is_member_pointer<int (functional::*)()> == "
        << std::boolalpha
        << std::is_member_pointer<int (functional::*)()>::value
        << std::endl;

    return (0);
    }
```

```Output
is_member_pointer<trivial *> == false
is_member_pointer<int trivial::*> == true
is_member_pointer<int (functional::*)()> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_member_function_pointer sınıfı](../standard-library/is-member-function-pointer-class.md)\
[is_member_object_pointer sınıfı](../standard-library/is-member-object-pointer-class.md)\
[is_pointer sınıfı](../standard-library/is-pointer-class.md)
