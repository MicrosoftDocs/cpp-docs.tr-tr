---
title: binder1st Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder1st
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
ms.openlocfilehash: 384a870a10c9f806684443d8c67647e924b6b2aa
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243380"
---
# <a name="binder1st-class"></a>binder1st Sınıfı

Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ilk bağımsız değişkeni bağlayarak birli nesnesine dönüştürür. bir oluşturucu sağlayan bir şablon sınıfı. Şunun için C ++ 11'de kullanım dışı [bağlama](functional-functions.md#bind)ve C ++ 17 sürümünde kaldırılmıştır.

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

*binary_fn*\
Birli işlevi nesnesine dönüştürülecek ikili fonksiyon nesnesi.

*Sol*\
İlk bağımsız değişken ikili işlev nesnesine bağlı olduğu değeri.

*sağ*\
Uyarlanmış ikili nesne sabit değeri ikinci bağımsız değişkeni olarak karşılaştıran bir bağımsız değişken değeri.

## <a name="return-value"></a>Dönüş Değeri

İkili fonksiyon nesnesi öğesinin ilk bağımsız değişkeninin değeri bağlama gelen sonuçları birli işlev nesnesi *sol*.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir ikili fonksiyon nesnesinin bir kopyasını depolar *binary_fn* içinde `op`ve bir kopyasını *sol* içinde `value`. Onun üye işlevini tanımlar `operator()` döndüren olarak `op(value, right)`.

Varsa *binary_fn* türünde bir nesnedir `Operation` ve `c` bir sabit ise `bind1st(binary_fn, c)` daha kullanışlı bir eşdeğeridir `binder1st<Operation>(binary_fn, c)`. Daha fazla bilgi için [bind1st](../standard-library/functional-functions.md#bind1st).

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
