---
title: is_union Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_union
helpviewer_keywords:
- is_union class
- is_union
ms.assetid: 80eda256-40b8-4db5-9ac1-d58bb8032a3e
ms.openlocfilehash: 3b4383fd96c359661d225433dbe9e7dd8b7f939f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458895"
---
# <a name="isunion-class"></a>is_union Sınıfı

Tür bir Union ise sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_union;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir birleşim türü veya `cv-qualified` birleşim türünde bir form ise *,* türü koşulun bir örneği true, aksi takdirde false değerini taşır.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_union.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

union ints
    {
    int in;
    long lo;
    };

int main()
    {
    std::cout << "is_union<trivial> == " << std::boolalpha
        << std::is_union<trivial>::value << std::endl;
    std::cout << "is_union<int> == " << std::boolalpha
        << std::is_union<int>::value << std::endl;
    std::cout << "is_union<ints> == " << std::boolalpha
        << std::is_union<ints>::value << std::endl;

    return (0);
    }
```

```Output
is_union<trivial> == false
is_union<int> == false
is_union<ints> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[is_class Sınıfı](../standard-library/is-class-class.md)
