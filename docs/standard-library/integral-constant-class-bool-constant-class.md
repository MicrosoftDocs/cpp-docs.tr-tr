---
title: integral_constant sınıfı, bool_constant sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
helpviewer_keywords:
- std::integral_constant [C++]
- std::bool_constant [C++]
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
ms.openlocfilehash: ef65a669b322c386a3ccc886b484c67fe2a0ea06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623138"
---
# <a name="integralconstant-class-boolconstant-class"></a>integral_constant sınıfı, bool_constant sınıfı

Bir türü ve değeri bir tamsayı sabit yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T, T v>
struct integral_constant {
   static constexpr T value = v;
   typedef T value_type;
   typedef integral_constant<T, v> type;
   constexpr operator value_type() const noexcept;
   constexpr value_type operator()() const noexcept;
   };
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sabit türü.

*v*<br/>
Sabit değer.

## <a name="remarks"></a>Açıklamalar

`integral_constant` Şablon sınıfı, özelleştirilmiş bir integral türünde olduğunda *T* ve bir değer *v* bu tür bir sabit tamsayı türü belirtilen değerle tutan bir nesneyi temsil eder. Adlı üye `type` oluşturulan şablon uzmanlığı türü için bir diğer addır ve `value` üye değeri tutan *v* özelleştirmesi oluşturmak için kullanılır.

`bool_constant` Şablon sınıfı, bir açık kısmi alt uzmanlaşması `integral_constant` kullanan **bool** olarak *T* bağımsız değişken.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__integral_constant.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "integral_constant<int, 5> == "
        << std::integral_constant<int, 5>::value << std::endl;
    std::cout << "integral_constant<bool, false> == " << std::boolalpha
        << std::integral_constant<bool, false>::value << std::endl;

    return (0);
    }

```

```Output
integral_constant<int, 5> == 5
integral_constant<bool, false> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[false_type](../standard-library/type-traits-typedefs.md#false_type)<br/>
[true_type](../standard-library/type-traits-typedefs.md#true_type)<br/>
