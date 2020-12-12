---
description: 'Hakkında daha fazla bilgi edinin: unary_function struct'
title: unary_function Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::unary
helpviewer_keywords:
- unary_function class
ms.assetid: 04c2fbdc-c1f6-48ed-b6cc-292a6d484627
ms.openlocfilehash: 441bbecbd356dddb20d8b8249dbaa39ccfbcc3ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207403"
---
# <a name="unary_function-struct"></a>unary_function Yapısı

Birli işlev nesnesi sağlayan türetilmiş sınıflar tarafından devralınabilir olabilecek türleri tanımlayan boş bir temel yapı.

## <a name="syntax"></a>Syntax

```cpp
struct unary_function
{
   typedef Arg argument_type;
   typedef Result result_type;
};
```

## <a name="remarks"></a>Açıklamalar

Şablon yapısı, formun üye işlevini tanımlayan sınıflar için temel görevi görür `result_type operator()( constargument_type& ) const` .

Tüm türetilmiş birli işlevler, **argument_type** olarak tek bağımsız değişken türüne ve **result_type** olarak dönüş türüne başvurabilir.

## <a name="example"></a>Örnek

```cpp
// functional_unary_function.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan10: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 10);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(), greaterthan10());
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
```
