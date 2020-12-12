---
description: 'Hakkında daha fazla bilgi edinin: is_integral sınıfı'
title: is_integral Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: db586054614b9a5ef49ffe9fe8b643b35c65a217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323707"
---
# <a name="is_integral-class"></a>is_integral Sınıfı

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

Tür değeri integral türlerden biri veya integral türlerinden birinin bir formu *ise tür* koşulu örneği true, `cv-qualified` Aksi takdirde false barındırır.

İntegral türü,,,, **`bool`** , **`char`** **`unsigned char`** **`signed char`** **`wchar_t`** **`short`** , **`unsigned short`** , **`int`** , **`unsigned int`** , **`long`** , ve **`unsigned long`** ' den biridir. Ayrıca, bunları sağlayan derleyiciler ile, bir integral türü,,, **`long long`** **`unsigned long long`** **`__int64`** ve **işaretsiz __int64** olabilir.

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

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[is_enum sınıfı](../standard-library/is-enum-class.md)\
[is_floating_point sınıfı](../standard-library/is-floating-point-class.md)
