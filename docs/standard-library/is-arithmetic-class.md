---
title: is_arithmetic Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_arithmetic
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
ms.openlocfilehash: 7aff4b051786c3d77dacb65ddbdbd29fa695ca48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520659"
---
# <a name="isarithmetic-class"></a>is_arithmetic Sınıfı

Aritmetik türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* olduğu bir aritmetik tür, diğer bir deyişle, bir tamsayı türü veya bir kayan nokta türüne, veya bir `cv-qualified` bunlardan biri, aksi takdirde false tuttuğu biçimi.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_arithmetic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha
        << std::is_arithmetic<trivial>::value << std::endl;
    std::cout << "is_arithmetic<int> == " << std::boolalpha
        << std::is_arithmetic<int>::value << std::endl;
    std::cout << "is_arithmetic<float> == " << std::boolalpha
        << std::is_arithmetic<float>::value << std::endl;

    return (0);
    }
```

```Output
is_arithmetic<trivial> == false
is_arithmetic<int> == true
is_arithmetic<float> == true
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_floating_point Sınıfı](../standard-library/is-floating-point-class.md)<br/>
[is_integral Sınıfı](../standard-library/is-integral-class.md)<br/>
