---
title: "binder1st sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::binder1st
dev_langs:
- C++
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3764a4ef76425ef1b92b7eef2f46803d291a91a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="binder1st-class"></a>binder1st Sınıfı
İkili işlevinin ilk bağımsız değişken belirtilen değere bağlama tarafından ikili işlev nesnesi bir birli işlevi nesnesine dönüştürür bir oluşturucu sağlayan bir şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
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
  
#### <a name="parameters"></a>Parametreler  
 `Func`  
 Birli işlevi nesnesine dönüştürülecek ikili işlev nesnesi.  
  
 `left`  
 İlk bağımsız değişken ikili işlev nesnesinin bağlanacak olduğu değeri.  
  
 `right`  
 İkinci bağımsız değişkeni sabit değer için uyarlanmış ikili nesne karşılaştırır bağımsız değişkeninin değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değerine ilk bağımsız değişken ikili işlev nesnesinin bağlama sonuçları birli işlev nesnesi `left.`  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı bir ikili işlevi nesnesinin bir kopyasını depolar `Func` içinde **op**ve bir kopyasını `left` içinde **değeri**. Üye işlevini tanımlar `operator()` döndürme olarak **op**( **değeri**, `right`).  
  
 Varsa `Func` türünde bir nesne **işlemi** ve `c` bir sabit ise [bind1st](../standard-library/functional-functions.md#bind1st) ( `Func`, `c` ) eşdeğerdir `binder1st` sınıfı Oluşturucu `binder1st` \< **işlemi**> ( `Func`, `c` ) ve daha kullanışlıdır.  
  
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
\* Output:   
The vector v1 = ( 0 5 10 15 20 25 )  
The number of elements in v1 greater than 10 is: 3.  
The number of elements in v1 less than 10 is: 2.  
*\  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



