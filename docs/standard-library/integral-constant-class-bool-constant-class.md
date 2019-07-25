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
ms.openlocfilehash: c85da1f3be7821f8d82cd2b19dab2a5864426a5a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452041"
---
# <a name="integralconstant-class-boolconstant-class"></a>integral_constant sınıfı, bool_constant sınıfı

Bir tür ve değerden tamsayı sabiti oluşturur.

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

*ŞI*\
Sabitin türü.

*Yönetim*\
Sabitin değeri.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir integral türü T ve bu türün *v* değeri ile özelleştirilse, belirtilen değere sahip bu integral türünün bir sabitini tutan bir nesneyi temsil eder.  `integral_constant` Adlı `type` üye, oluşturulan şablon özelleştirmesi türü için bir diğer addır `value` ve üye, uzmanlığı oluşturmak için kullanılan *v* değerini tutar.

Şablon sınıfı,, *T* bağımsız değişkeni olarak **bool** kullanan, öğesinin `integral_constant` açık kısmi bir özelleştirmesi. `bool_constant`

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

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[false_type](../standard-library/type-traits-typedefs.md#false_type)\
[true_type](../standard-library/type-traits-typedefs.md#true_type)
