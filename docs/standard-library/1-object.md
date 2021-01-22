---
description: 'Daha fazla bilgi edinin: _1 nesnesi'
title: _1 Nesnesi
ms.date: 01/15/2021
f1_keywords:
- _1
- std::_1
- functional/std::_1
- std::_2
- functional/std::_2
- std::_3
- functional/std::_3
- std::_4
- functional/std::_4
- std::_5
- functional/std::_5
- std::_6
- functional/std::_6
- std::_7
- functional/std::_7
- std::_8
- functional/std::_8
- std::_9
- functional/std::_9
- std::_10
- functional/std::_10
- std::_11
- functional/std::_11
- std::_12
- functional/std::_12
- std::_13
- functional/std::_13
- std::_14
- functional/std::_14
- std::_15
- functional/std::_15
- std::_16
- functional/std::_16
- std::_17
- functional/std::_17
- std::_18
- functional/std::_18
- std::_19
- functional/std::_19
- std::_20
- functional/std::_20
- functional/std::placeholders
- std::placeholders
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
ms.openlocfilehash: d6c7550580b1b73485d0d3ee1bcde7497e828650
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667529"
---
# <a name="_1-object"></a>`_1` Nesne

Değiştirilebilen bağımsız değişkenler için yer tutucular.

## <a name="syntax"></a>Syntax

```cpp
namespace placeholders {
    extern unspecified _1, _2, ... _N
} // namespace placeholders (within std)
```

## <a name="remarks"></a>Açıklamalar

Nesneler, `_1, _2, ... _N` tarafından döndürülen bir nesneye yapılan işlev çağrısında sırasıyla birinci, ikinci,...,-n bağımsız değişkenini temsil eden yer tutuculardır [`bind`](functional-functions.md#bind) . Örneğin, `_6` ifadesi değerlendirildiğinde altıncı bağımsız değişkenin nereye ekleneceğini belirtmek için kullanırsınız `bind` .

Microsoft uygulamasında, değeri `_N` 20 ' dir.

## <a name="example"></a>Örnek

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }
```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```
