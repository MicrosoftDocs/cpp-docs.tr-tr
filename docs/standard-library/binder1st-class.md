---
title: binder1st Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder1st
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
ms.openlocfilehash: 15b704134d47b7bf7d8857bf380c756b0b03a1b0
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688382"
---
# <a name="binder1st-class"></a>binder1st Sınıfı

İkili işlevin ilk bağımsız değişkenini belirtilen bir değere bağlayarak bir ikili işlev nesnesini birli işlev nesnesine dönüştüren bir Oluşturucu sağlayan bir sınıf şablonu. [Bağlama](functional-functions.md#bind)için c++ 11 ' de kullanımdan kaldırılmıştır ve c++ 17 ' de kaldırılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Operation>
class binder1st
    : public unaryFunction <typename Operation::second_argument_type,
                             typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder1st(
        const Operation& binary_fn,
        const typename Operation::first_argument_type& left);

    result_type operator()(const argument_type& right) const;
    result_type operator()(const argument_type& right) const;

protected:
    Operation op;
    typename Operation::first_argument_type value;
};
```

### <a name="parameters"></a>Parametreler

*binary_fn* \
Birli işlev nesnesine dönüştürülecek ikili işlev nesnesi.

*sol* \
İkili işlev nesnesinin ilk bağımsız değişkeninin bağlanacağı değer.

*sağ* \
Uyarbınary nesnesinin, ikinci bağımsız değişkenin sabit değeriyle karşılaştırıldığı bağımsız değişkenin değeri.

## <a name="return-value"></a>Dönüş Değeri

İkili işlev nesnesinin ilk bağımsız değişkenini *sol*değere bağlamayı sağlayan birli işlev nesnesi.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, `op` bir ikili *işlev nesnesinin bir* kopyasını ve `value` *sol* bir kopyasını depolar. @No__t_1 döndüren `operator()` üye işlevini tanımlar.

*Binary_fn* , `Operation` türünde bir nesnedir ve `c` bir sabittir, `bind1st(binary_fn, c)` `binder1st<Operation>(binary_fn, c)` daha kolay bir eşdeğerdir. Daha fazla bilgi için bkz. [bind1st](../standard-library/functional-functions.md#bind1st).

## <a name="example"></a>Örnek

```cpp
// functional_binder1st.cpp
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
        binder1st<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare use of binder2nd fixing 2nd argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder2nd<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
```
