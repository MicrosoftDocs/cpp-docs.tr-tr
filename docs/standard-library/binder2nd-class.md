---
title: binder2nd Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: 297f91dd9283b9f004247d2d1814b30a17e7ffa2
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72890101"
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

*func*\
Birli işlev nesnesine dönüştürülecek ikili işlev nesnesi.

*sağ* \
İkili işlev nesnesinin ikinci bağımsız değişkeninin bağlanacağı değer.

*sol* \
Uyarbınary nesnesinin, ikinci bağımsız değişkenin sabit değeriyle karşılaştırıldığı bağımsız değişkenin değeri.

## <a name="return-value"></a>Dönüş değeri

İkili işlev nesnesinin ikinci bağımsız değişkenini *sağ*değere bağlamakla sonuçlanan birli işlev nesnesi.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, `op`bir ikili *işlev nesnesinin bir* kopyasını ve `value`*sağ* bir kopyasını depolar. `op(left, value)`döndüren `operator()` üye işlevini tanımlar.

*Func* , `Operation` türünde bir nesnedir ve c bir sabittir, [bind2nd](../standard-library/functional-functions.md#bind2nd)`(func, c)` `binder2nd` sınıf oluşturucusuna `binder2nd<Operation>(func, c)`ve daha uygun şekilde eşdeğerdir.

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
