---
title: is_compound Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: 003ddcf77c30bc2dc5491218dfbf00731517bdeb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452898"
---
# <a name="iscompound-class"></a>is_compound Sınıfı

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

Tür belirtiminin bir örneği, *Ty* türü temel bir tür ise (yani, [is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > **true**olursa) **false** barındırır. Aksi takdirde, **true**olarak tutulur. Bu nedenle, *Ty* bir dizi türü, bir işlev türü, **void** veya bir nesne ya da bir işlev, bir başvuru, sınıf, birleşim, numaralandırma veya statik olmayan sınıf üyesine yönelik bir işaretçi ya da bir *CV nitelenmiş* formu ise **true** olarak tutulur. Bunlardan biri.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[is_class Sınıfı](../standard-library/is-class-class.md)
