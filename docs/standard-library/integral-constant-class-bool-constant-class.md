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
ms.openlocfilehash: 9577ce51d4b0773f7b309fe3dc6dcb5820693dcb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689531"
---
# <a name="integral_constant-class-bool_constant-class"></a>integral_constant sınıfı, bool_constant sınıfı

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

*T* \
Sabitin türü.

*v* \
Sabitin değeri.

## <a name="remarks"></a>Açıklamalar

@No__t_0 sınıf şablonu, bir integral türü *t* ve bu türün *v* değeri ile özelleştirilse, belirtilen değere sahip bu integral türünde bir sabiti tutan nesneyi temsil eder. @No__t_0 adlı üye, oluşturulan şablon özelleştirmesi türü için bir diğer addır ve `value` üyesi, özelleştirmeyi oluşturmak için kullanılan *v* değerini tutar.

@No__t_0 sınıf şablonu, *t* bağımsız değişkeni olarak **bool** kullanan `integral_constant` bir açık kısmi özelleşmesi.

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

[< type_traits >](../standard-library/type-traits.md) \
[false_type](../standard-library/type-traits-typedefs.md#false_type) \
[true_type](../standard-library/type-traits-typedefs.md#true_type)
