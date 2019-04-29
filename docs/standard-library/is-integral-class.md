---
title: is_integral Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: c7d0d8b8572c26bfa75b9fab81900c0ae21fb932
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336501"
---
# <a name="isintegral-class"></a>is_integral Sınıfı

İntegral türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* integral türlerinden biri veya `cv-qualified` false tuttuğu integral türlerinden birini, aksi takdirde biçiminin.

Bir tamsayı türü biridir **bool**, **char**, **imzasız char**, **signed char**, **wchar_t**, **kısa**, **işaretsiz**, **int**, **işaretsiz int**, **uzun**ve **işaretsiz uzun**. Ayrıca, sağlayacağını derleyicilerle bir tamsayı türü olabilir **uzun uzun**, **işaretsiz long long**, **__int64**, ve **unsigned __int64**.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }
```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_enum Sınıfı](../standard-library/is-enum-class.md)<br/>
[is_floating_point Sınıfı](../standard-library/is-floating-point-class.md)<br/>
