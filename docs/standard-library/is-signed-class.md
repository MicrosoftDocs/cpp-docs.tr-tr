---
description: 'Hakkında daha fazla bilgi edinin: is_signed sınıfı'
title: is_signed Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_signed
helpviewer_keywords:
- is_signed class
- is_signed
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
ms.openlocfilehash: fefdf5e178bfbb5d2d77220ba51e36b2574606ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247689"
---
# <a name="is_signed-class"></a>is_signed Sınıfı

Tür işaretli bir tamsayı ise test edin.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_signed;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri, işaretli bir integral türü veya imzalı bir integral türü *ise true* , `cv-qualified` Aksi takdirde false değerini tutar.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_signed.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_signed<trivial> == " << std::boolalpha
        << std::is_signed<trivial>::value << std::endl;
    std::cout << "is_signed<int> == " << std::boolalpha
        << std::is_signed<int>::value << std::endl;
    std::cout << "is_signed<unsigned int> == " << std::boolalpha
        << std::is_signed<unsigned int>::value << std::endl;
    std::cout << "is_signed<float> == " << std::boolalpha
        << std::is_signed<float>::value << std::endl;

    return (0);
    }
```

```Output
is_signed<trivial> == false
is_signed<int> == true
is_signed<unsigned int> == false
is_signed<float> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_unsigned sınıfı](../standard-library/is-unsigned-class.md)
