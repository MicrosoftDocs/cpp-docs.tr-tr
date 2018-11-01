---
title: is_union Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_union
helpviewer_keywords:
- is_union class
- is_union
ms.assetid: 80eda256-40b8-4db5-9ac1-d58bb8032a3e
ms.openlocfilehash: b29705f0e84e9aff9dbefe4297a67ac2a75da8b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636637"
---
# <a name="isunion-class"></a>is_union Sınıfı

Bir birleşim türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_union;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* bir birleşim türü veya `cv-qualified` tuttuğu yanlış bir birleşim türü, aksi takdirde biçiminin.

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

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_class Sınıfı](../standard-library/is-class-class.md)<br/>
