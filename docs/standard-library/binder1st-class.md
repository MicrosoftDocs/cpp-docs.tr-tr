---
title: binder1st Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::binder1st
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
ms.openlocfilehash: a8e962e118d162e46e2edfca3ce11e7cbf322e10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439643"
---
# <a name="binder1st-class"></a>binder1st Sınıfı

Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ilk bağımsız değişkeni bağlayarak birli nesnesine dönüştürür. bir oluşturucu sağlayan bir şablon sınıfı.

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
        const Operation& Func,
        const typename Operation::first_argument_type& left);

    result_type operator()(const argument_type& right) const;
    result_type operator()(const argument_type& right) const;

protected:
    Operation op;
    typename Operation::first_argument_type value;
};
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Birli işlevi nesnesine dönüştürülecek ikili fonksiyon nesnesi.

*Sol*<br/>
İlk bağımsız değişken ikili işlev nesnesine bağlı olduğu değeri.

*sağ*<br/>
Uyarlanmış ikili nesne sabit değeri ikinci bağımsız değişkeni olarak karşılaştıran bir bağımsız değişken değeri.

## <a name="return-value"></a>Dönüş Değeri

İkili fonksiyon nesnesi öğesinin ilk bağımsız değişkeninin değeri bağlama gelen sonuçları birli işlev nesnesi *sol*.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir ikili fonksiyon nesnesinin bir kopyasını depolar *Func* içinde `op`ve bir kopyasını *sol* içinde `value`. Onun üye işlevini tanımlar `operator()` döndüren olarak **op**( **değer**, `right`).

Varsa *Func* türünde bir nesnedir `Operation` ve `c` bir sabit ise [bind1st](../standard-library/functional-functions.md#bind1st) ( `Func`, `c` ) değerine eşdeğer olan `binder1st` sınıf oluşturucusu `binder1st` \< **İşlemi**> ( `Func`, `c` ) ve daha kolay.

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
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
