---
title: '&lt;type_traits&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::false_type
- xtr1common/std::false_type
- type_traits/std::true_type
- xtr1common/std::true_type
ms.assetid: 8ac040ca-ed2d-4570-adc9-cb5626530053
ms.openlocfilehash: eff1a99fb95f15c6377e8a74cca36e718cbd6fd9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422586"
---
# <a name="lttype_traitsgt-typedefs"></a>&lt;type_traits&gt; tür tanımları

|||
|-|-|
|[false_type](#false_type)|[true_type](#true_type)|

## <a name="false_type"></a>false_type typedef

Tamsayı sabiti yanlış değerle tutar.

```cpp
typedef integral_constant<bool, false> false_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon özelleştirmesi için bir eş anlamlı `integral_constant`.

### <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main() {
    std::cout << "false_type == " << std::boolalpha
        << std::false_type::value << std::endl;
    std::cout << "true_type == " << std::boolalpha
        << std::true_type::value << std::endl;

    return (0);
}
```

```Output
false_type == false
true_type == true
```

## <a name="true_type"></a>true_type typedef

Gerçek değer ile integral sabiti barındırır.

```cpp
typedef integral_constant<bool, true> true_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon özelleştirmesi için bir eş anlamlı `integral_constant`.

### <a name="example"></a>Örnek

```cpp
// std__type_traits__true_type.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main() {
    std::cout << "false_type == " << std::boolalpha
        << std::false_type::value << std::endl;
    std::cout << "true_type == " << std::boolalpha
        << std::true_type::value << std::endl;

    return (0);
}
```

```Output
false_type == false
true_type == true
```

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
