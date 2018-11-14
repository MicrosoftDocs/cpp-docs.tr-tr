---
title: unary_negate Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::unary_negate
helpviewer_keywords:
- unary_negate class
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
ms.openlocfilehash: b43db182d9274281020d7ce92cfa1b3efe724197
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326023"
---
# <a name="unarynegate-class"></a>unary_negate Sınıfı

Belirtilen birli işlevi dönüş değeri verilerek bir üye işlevi sağlayan bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Predicate>
class unary_negate
    : public unaryFunction<typename Predicate::argument_type, bool>
{
public:
    explicit unary_negate(const Predicate& Func);
    bool operator()(const typename Predicate::argument_type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Negatif birli işlevi.

*Sol*<br/>
Birli işlevi negatif işleneni.

## <a name="return-value"></a>Dönüş Değeri

Birli işlevi negation.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir birli işlevi nesnesinin bir kopyasını depolar  *\_Func*. Onun üye işlevini tanımlar `operator()` döndüren olarak `!_Func(left)`.

Oluşturucusuna `unary_negate` doğrudan nadiren kullanılır. Yardımcı işlevini [not1](../standard-library/functional-functions.md#not1) bildirme ve kullanma için daha kolay bir yol sağlayan **unary_negator** bağdaştırıcısı koşul.

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
/* Output:
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
