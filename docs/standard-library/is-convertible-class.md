---
description: 'Hakkında daha fazla bilgi edinin: is_convertible sınıfı'
title: is_convertible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_convertible
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
ms.openlocfilehash: 4f5c9413eb33dd38d68929fe6b92f4581eced521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231205"
---
# <a name="is_convertible-class"></a>is_convertible Sınıfı

Bir tür diğerine dönüştürülebilir olduğunda sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class From, class To>
struct is_convertible;
```

### <a name="parameters"></a>Parametreler

*Kaynak*\
Dönüştürülecek tür.

*Kalite*\
Dönüştürülecek tür.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, ifadesi `To to = from;` `from` türü bir nesne ise doğru bir biçimde olduğunda true olarak tutulur `From` .

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_convertible.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha
        << std::is_convertible<trivial, int>::value << std::endl;
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha
        << std::is_convertible<trivial, trivial>::value << std::endl;
    std::cout << "is_convertible<char, int> == " << std::boolalpha
        << std::is_convertible<char, int>::value << std::endl;

    return (0);
    }
```

```Output
is_convertible<trivial, int> == false
is_convertible<trivial, trivial> == true
is_convertible<char, int> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_base_of sınıfı](../standard-library/is-base-of-class.md)
