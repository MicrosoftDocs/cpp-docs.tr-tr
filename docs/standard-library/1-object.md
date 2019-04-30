---
title: _1 Nesnesi
ms.date: 11/04/2016
f1_keywords:
- _1
- std::_1
- functional/std::_1
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
ms.openlocfilehash: 183df5c2ff039ff9438b1a00c63318e16dc84c37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411285"
---
# <a name="1-object"></a>_1 Nesnesi

Değiştirilebilir bağımsız değişkenleri için yer tutucu.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace placeholders {
    extern unspecified _1,
    _2, ... _M
} // namespace placeholders (within std)
```

## <a name="remarks"></a>Açıklamalar

Nesneleri `_1, _2, ... _M` olan yer tutucuları belirleme birinci, ikinci,..., ay bağımsız değişkeni tarafından döndürülen bir nesneye yönelik işlev çağrısında sırasıyla [bağlama](../standard-library/functional-functions.md#bind). Kullandığınız `_N` bağlama ifadesi değerlendirilirken n sayılı bağımsız değişkenin ekleneceği yeri belirtmek için.

Bu uygulamada değeri, `M` 20'dir.

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

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[bağlama](../standard-library/functional-functions.md#bind)<br/>
[is_placeholder Sınıfı](../standard-library/is-placeholder-class.md)<br/>
