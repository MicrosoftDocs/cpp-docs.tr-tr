---
title: is_arithmetic Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_arithmetic
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
ms.openlocfilehash: e2c148b7cb58cf38e5f73d4e3d2297eac099ef7e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456682"
---
# <a name="isarithmetic-class"></a>is_arithmetic Sınıfı

Tür aritmetik ise sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir aritmetik tür, yani bir integral türü veya kayan nokta türü ya da bunlardan birinin bir `cv-qualified` *biçimi ise,* bir tür koşulu true, aksi takdirde false barındırır.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[is_floating_point sınıfı](../standard-library/is-floating-point-class.md)\
[is_integral Sınıfı](../standard-library/is-integral-class.md)
