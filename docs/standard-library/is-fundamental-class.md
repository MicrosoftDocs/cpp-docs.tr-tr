---
title: is_fundamental Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_fundamental
helpviewer_keywords:
- is_fundamental class
- is_fundamental
ms.assetid: b84eee84-2fb2-4611-beaf-b384074d8b6a
ms.openlocfilehash: d16dfeebabd5909212425fcc27b355110e891d89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348451"
---
# <a name="isfundamental-class"></a>is_fundamental Sınıfı

Void veya aritmetik türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_fundamental;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* diğer bir deyişle, bir temel türü olan **void**, kayan bir integral türü işaret türü veya bir `cv-qualified` bunlardan biri, aksi takdirde false tuttuğu biçimi.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_fundamental.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_fundamental<trivial> == " << std::boolalpha
        << std::is_fundamental<trivial>::value << std::endl;
    std::cout << "is_fundamental<int> == " << std::boolalpha
        << std::is_fundamental<int>::value << std::endl;
    std::cout << "is_fundamental<const float> == " << std::boolalpha
        << std::is_fundamental<const float>::value << std::endl;
    std::cout << "is_fundamental<void> == " << std::boolalpha
        << std::is_fundamental<void>::value << std::endl;

    return (0);
    }
```

```Output
is_fundamental<trivial> == false
is_fundamental<int> == true
is_fundamental<const float> == true
is_fundamental<void> == true
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_compound Sınıfı](../standard-library/is-compound-class.md)<br/>
