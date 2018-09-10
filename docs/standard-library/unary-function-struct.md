---
title: unary_function yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::unary
dev_langs:
- C++
helpviewer_keywords:
- unary_function class
ms.assetid: 04c2fbdc-c1f6-48ed-b6cc-292a6d484627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff8e486be6e28de313a8e1a20634af4c50c350e8
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313864"
---
# <a name="unaryfunction-struct"></a>unary_function Yapısı

Birli işlev nesnesi sağlayan türetilen sınıfları tarafından devralındığından türlerini tanımlayan boş bir temel yapı.

## <a name="syntax"></a>Sözdizimi

```cpp
struct unary_function
{
   typedef Arg argument_type;
   typedef Result result_type;
};
```
## <a name="remarks"></a>Açıklamalar

Şablon yapı biçiminde bir üye işlevi tanımlayan sınıflar için temel olarak hizmet veren **result_type**`operator()`( **constargument_type &**) **const**.

Tüm bu türetilmiş birli işlevleri kendi tek bağımsız değişken türü olarak başvurabilir **argument_type** ve kendi dönüş türü olarak **result_type**.

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
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
