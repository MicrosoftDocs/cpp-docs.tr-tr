---
description: 'Daha fazla bilgi edinin: binder2nd Class'
title: binder2nd Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: a3c76fcea22045ee7e723ad3ad51390c39f602ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325498"
---
# <a name="binder2nd-class"></a>binder2nd Sınıfı

İkili işlevin ikinci bağımsız değişkenini belirtilen bir değere bağlayarak bir ikili işlev nesnesini birli işlev nesnesine dönüştüren bir Oluşturucu sağlayan bir sınıf şablonu. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*melerinin*\
Birli işlev nesnesine dönüştürülecek ikili işlev nesnesi.

*Right*\
İkili işlev nesnesinin ikinci bağımsız değişkeninin bağlanacağı değer.

*tarafta*\
Uyarbınary nesnesinin, ikinci bağımsız değişkenin sabit değeriyle karşılaştırıldığı bağımsız değişkenin değeri.

## <a name="return-value"></a>Döndürülen değer

İkili işlev nesnesinin ikinci bağımsız değişkenini *sağ* değere bağlamakla sonuçlanan birli işlev nesnesi.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, içinde bir ikili *işlev nesnesinin bir* kopyasını ve içindeki `op` bir kopyasını depolar  `value` . Üye işlevini `operator()` iade olarak tanımlar `op(left, value)` .

*Func* , türünde bir nesnedir `Operation` ve c bir sabittir, [bind2nd](../standard-library/functional-functions.md#bind2nd) `(func, c)` `binder2nd` sınıf oluşturucusuna eşdeğerdir `binder2nd<Operation>(func, c)` ve daha uygundur.

## <a name="example"></a>Örnek

```cpp
// functional_binder2nd.cpp
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
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder2nd<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare using binder1st fixing 1st argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder1st<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
```
