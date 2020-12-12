---
description: 'Hakkında daha fazla bilgi edinin: is_abstract sınıfı'
title: is_abstract Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_abstract
helpviewer_keywords:
- is_abstract class
- is_abstract
ms.assetid: 8867f660-3434-404c-ba90-c26607a5e0d2
ms.openlocfilehash: 9b2fe31d2f4e742381c4e2e76a668d4e68e76b75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323893"
---
# <a name="is_abstract-class"></a>is_abstract Sınıfı

Türün soyut sınıf olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_abstract;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

*Tür değeri* en az bir saf sanal işlevi olan bir sınıfdaysa, tür koşulu true, aksi takdirde false değerini alır.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_abstract.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct abstract
    {
    virtual int val() = 0;
    };

int main()
    {
    std::cout << "is_abstract<trivial> == " << std::boolalpha
        << std::is_abstract<trivial>::value << std::endl;
    std::cout << "is_abstract<abstract> == " << std::boolalpha
        << std::is_abstract<abstract>::value << std::endl;

    return (0);
    }
```

```Output
is_abstract<trivial> == false
is_abstract<abstract> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_polymorphic sınıfı](../standard-library/is-polymorphic-class.md)
