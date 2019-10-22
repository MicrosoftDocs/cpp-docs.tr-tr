---
title: unary_negate Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::unary_negate
helpviewer_keywords:
- unary_negate class
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
ms.openlocfilehash: 2d9f0bedd9e541e65f04ac20375f16f41413cf03
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72684429"
---
# <a name="unary_negate-class"></a>unary_negate Sınıfı

Belirtilen birli işlevin dönüş değerini geçersiz hale getirmeden bir üye işlevi sağlayan bir sınıf şablonu. [Not_fn](functional-functions.md#not_fn)için c++ 17 ' de kullanım dışı bırakılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Predicate>
class unary_negate
    : public unaryFunction<typename Predicate::argument_type, bool>
{
    explicit unary_negate(const Predicate& Func);
    bool operator()(const typename Predicate::argument_type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*Func* \
Değillenmiş birli işlev.

*sol* \
Birli işlevin, iç içe yapılacak işleneni.

## <a name="return-value"></a>Dönüş Değeri

Birli işlevin değilleme.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu *\_Func*birli işlev nesnesinin bir kopyasını depolar. @No__t_1 döndüren `operator()` üye işlevini tanımlar.

@No__t_0 Oluşturucusu nadiren doğrudan kullanılır. [Not1](../standard-library/functional-functions.md#not1) yardımcı işlevi, **unary_negator** bağdaştırıcı koşulunu bildirmek ve kullanmak için daha kolay bir yol sağlar.

## <a name="example"></a>Örnek

```cpp
// functional_unary_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));

    // The following helper function not1 also works for the above line
    // not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```
