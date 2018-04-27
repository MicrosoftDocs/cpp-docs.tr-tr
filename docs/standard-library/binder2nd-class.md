---
title: binder2nd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::binder2nd
dev_langs:
- C++
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1784f396fd657a04395020353a5ad00fd99dd440
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="binder2nd-class"></a>binder2nd Sınıfı

İkili işlevinin ikinci bağımsız değişkeni belirtilen değere bağlama tarafından ikili işlev nesnesi bir birli işlevi nesnesine dönüştürür bir oluşturucu sağlayan bir şablon sınıfı.

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

`Func` Birli işlevi nesnesine dönüştürülecek ikili işlev nesnesi.

`right` İkinci bağımsız değişken ikili işlev nesnesinin bağlanacak olduğu değeri.

`left` İkinci bağımsız değişkeni sabit değer için uyarlanmış ikili nesne karşılaştırır bağımsız değişkeninin değeri.

## <a name="return-value"></a>Dönüş Değeri

Değerine ikinci bağımsız değişken ikili işlev nesnesinin bağlama sonuçları birli işlev nesnesi `right.`

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir ikili işlevi nesne _ bir kopyasını depolar *Func* içinde **op**ve bir kopyasını `right` içinde **değeri**. Üye işlevini tanımlar `operator()` döndürme olarak **op**( `left`, **değeri**).

Varsa `Func` türünde bir nesne **işlemi** ve c bir sabit sonra [bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`, `c` ) eşdeğerdir `binder2nd` sınıfı oluşturucusu `binder2nd` \< **İşlemi**> ( `Func`, `c` ) ve daha kullanışlıdır.

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

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
