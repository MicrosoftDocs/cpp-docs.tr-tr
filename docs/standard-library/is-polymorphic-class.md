---
title: is_polymorphic Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_polymorphic
helpviewer_keywords:
- is_polymorphic class
- is_polymorphic
ms.assetid: 4e1704db-d6f9-4154-a100-0ba02a373f20
ms.openlocfilehash: 662d68d13e076733e9923d0fad7e9272cd01b559
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455718"
---
# <a name="ispolymorphic-class"></a>is_polymorphic Sınıfı

Türün bir sanal işlevi varsa sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_polymorphic;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri, bir sanal işlevi bildiren veya devralan bir sınıf *ise,* yanlış bir değer içeriyorsa tür belirtiminin bir örneği true olarak tutulur.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_polymorphic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct throws
    {
    throws() throw(int)
        {
        }

    throws(const throws&) throw(int)
        {
        }

    throws& operator=(const throws&) throw(int)
        {
        }

    virtual ~throws()
        {
        }

    int val;
    };

int main()
    {
    std::cout << "is_polymorphic<trivial> == " << std::boolalpha
        << std::is_polymorphic<trivial>::value << std::endl;
    std::cout << "is_polymorphic<throws> == " << std::boolalpha
        << std::is_polymorphic<throws>::value << std::endl;

    return (0);
    }
```

```Output
is_polymorphic<trivial> == false
is_polymorphic<throws> == true
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[is_abstract Sınıfı](../standard-library/is-abstract-class.md)
