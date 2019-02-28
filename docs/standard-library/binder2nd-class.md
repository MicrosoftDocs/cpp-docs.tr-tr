---
title: binder2nd Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: 8c1ed74da939c5f5cc83a2a109d32b43b5ac7f41
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006493"
---
# <a name="binder2nd-class"></a>binder2nd Sınıfı

Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ikinci bağımsız değişkeni bağlayarak birli nesnesine dönüştürür. bir oluşturucu sağlayan bir şablon sınıfı. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;

protected:
    Operation op;
    typename Operation::second_argument_type value;
};
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Birli işlevi nesnesine dönüştürülecek ikili fonksiyon nesnesi.

*sağ*<br/>
İkinci bağımsız değişken ikili işlev nesnesine bağlı olduğu değeri.

*Sol*<br/>
Uyarlanmış ikili nesne sabit değeri ikinci bağımsız değişkeni olarak karşılaştıran bir bağımsız değişken değeri.

## <a name="return-value"></a>Dönüş Değeri

İkili fonksiyon nesnesi ikinci bağımsız değişkeni değere bağlama gelen sonuçları birli işlev nesnesi *doğru*.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir ikili fonksiyon nesnesi _ kopyasını depoladığından *Func* içinde `op`ve bir kopyasını *doğru* içinde `value`. Onun üye işlevini tanımlar `operator()` döndüren olarak **op**( `left`, **değer**).

Varsa `Func` türünde bir nesnedir `Operation` ve c, bir sabit ardından [bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`, `c` ) değerine eşdeğer olan `binder2nd` sınıf oluşturucusu `binder2nd` \<  **İşlem**> ( `Func`, `c` ) ve daha kolay.

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
