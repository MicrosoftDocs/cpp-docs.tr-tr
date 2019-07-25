---
title: is_integral Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: a367bb06f49dd2c9c64f0c257a3573add5645efe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456248"
---
# <a name="isintegral-class"></a>is_integral Sınıfı

Tür integral ise sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür değeri integral türlerden biri veya `cv-qualified` integral türlerinden birinin bir formu *ise tür* koşulu örneği true, aksi takdirde false barındırır.

İntegral türü **bool**, **char**, **işaretsiz karakter**, **imzalanmış char**, **wchar_t**, **Short**, **işaretsiz Short**, **int**, **işaretsiz int**, **Long**ve **işaretsiz Long**'dan biridir. Ayrıca, bunları sağlayan derleyiciler ile, bir integral türü **uzun uzun**, **imzasız uzun uzun**, **__int64**ve **işaretsiz __int64**olabilir.

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[is_enum sınıfı](../standard-library/is-enum-class.md)\
[is_floating_point Sınıfı](../standard-library/is-floating-point-class.md)
