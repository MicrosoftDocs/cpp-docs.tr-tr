---
title: is_bind_expression Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_bind_expression
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
ms.openlocfilehash: f547b6f74a86612174cb0f510870171158678f7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519424"
---
# <a name="isbindexpression-class"></a>is_bind_expression Sınıfı

Tür çağrılarak oluşturulan olmadığını test eder `bind`.

## <a name="syntax"></a>Sözdizimi

Şablon<class Ty> yapı is_bind_expression {statik const bool değeri;};

## <a name="remarks"></a>Açıklamalar

Sabit üye `value` true ise tür `Ty` bir çağrı tarafından döndürülen bir türü `bind`, aksi durumda false.

## <a name="example"></a>Örnek

```cpp
// std__functional__is_bind_expression.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}
```

```Output
0
1
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[bağlama](../standard-library/functional-functions.md#bind)<br/>
