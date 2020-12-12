---
description: 'Hakkında daha fazla bilgi edinin: is_compound sınıfı'
title: is_compound Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: 0bdd1b2f8c7ab827d9bed1025e30140244381c3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323836"
---
# <a name="is_compound-class"></a>is_compound Sınıfı

Belirtilen tür temel değilse sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür belirtiminin bir örneği, Ty türü **`false`** temel bir tür ise  (yani [is_fundamental](../standard-library/is-fundamental-class.md) \<Ty> tutuyorsa **`true`** ), aksi takdirde, barındırır **`true`** . Bu nedenle, **`true`** *Ty* bir dizi türü, bir işlev türü, bir **`void`** nesne ya da bir işlev, bir başvuru, sınıf, birleşim, numaralandırma veya statik olmayan sınıf üyesine yönelik bir işaretçi ya da bunlardan birinin *MF nitelikli* bir biçimi ise, koşul barındırır.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }
```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_class sınıfı](../standard-library/is-class-class.md)
