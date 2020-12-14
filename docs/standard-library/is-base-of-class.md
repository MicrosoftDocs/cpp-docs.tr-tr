---
description: 'Hakkında daha fazla bilgi edinin: is_base_of sınıfı'
title: is_base_of Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_base_of
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
ms.openlocfilehash: 6cb2b55a6df687fbb7da74ca3c696a8a9b0ffbad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231270"
---
# <a name="is_base_of-class"></a>is_base_of Sınıfı

Bir türün başka bir temel olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>Parametreler

*Temel*\
Sınanacak temel sınıf.

*Miþ*\
Test edilecek türetilmiş tür.

## <a name="remarks"></a>Açıklamalar

Tür *tabanı* , *türetilmiş* türün temel sınıfı ise true, aksi takdirde false barındırır.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_convertible sınıfı](../standard-library/is-convertible-class.md)
