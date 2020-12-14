---
description: 'Hakkında daha fazla bilgi edinin: is_reference sınıfı'
title: is_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_reference
helpviewer_keywords:
- is_reference class
- is_reference
ms.assetid: 3d9e631f-3092-430c-843e-e914ab58c257
ms.openlocfilehash: 85b824f6abe9800f1b85a6e8e81416551cb72155
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259467"
---
# <a name="is_reference-class"></a>is_reference Sınıfı

Tür bir başvuruysa sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_reference;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri bir nesneye veya işleve *başvuru ise,* tür koşulu true, aksi takdirde false barındırır.

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

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_pointer sınıfı](../standard-library/is-pointer-class.md)
