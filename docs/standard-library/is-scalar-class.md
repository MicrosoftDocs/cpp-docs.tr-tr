---
title: is_scalar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_scalar
helpviewer_keywords:
- is_scalar class
- is_scalar
ms.assetid: a0cdfc9a-f27e-4808-890f-6ed7942db60c
ms.openlocfilehash: 2b981e009b895d55c251bc55a654739fe1eb5b95
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520315"
---
# <a name="isscalar-class"></a>is_scalar Sınıfı

Skalar türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_scalar;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutar türü *Ty* bir Entegral türü olduğunda, bir değişken türü, bir numaralandırma türü, bir işaretçi türü veya bir işaretçi üye türüne işaret veya `cv-qualified` bunlardan biri, aksi takdirde false tuttuğu biçimi.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_scalar.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_scalar<trivial> == " << std::boolalpha
        << std::is_scalar<trivial>::value << std::endl;
    std::cout << "is_scalar<trivial *> == " << std::boolalpha
        << std::is_scalar<trivial *>::value << std::endl;
    std::cout << "is_scalar<int> == " << std::boolalpha
        << std::is_scalar<int>::value << std::endl;
    std::cout << "is_scalar<float> == " << std::boolalpha
        << std::is_scalar<float>::value << std::endl;

    return (0);
    }
```

```Output
is_scalar<trivial> == false
is_scalar<trivial *> == true
is_scalar<int> == true
is_scalar<float> == true
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_compound Sınıfı](../standard-library/is-compound-class.md)<br/>
