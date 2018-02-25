---
title: "&lt;Tuple&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
dev_langs:
- C++
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
ms.openlocfilehash: ecc544c1f18e31a71d11a212fc9618a6b085f461
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="lttuplegt-functions"></a>&lt;Tuple&gt; işlevleri
||||  
|-|-|-|  
|[get](#get)|[make_tuple](#make_tuple)|[tie](#tie)|  
  
##  <a name="get"></a>  get
 Bir öğeyi alır bir `tuple` nesnesi, dizine göre veya (C ++ 14) türüne göre.  
  
```  
// by index:
// get reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr tuple_element_t<Index, tuple<Types...>>& get(tuple<Types...>& Tuple) noexcept;

// get const reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr const tuple_element_t<Index, tuple<Types...>>& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr tuple_element_t<Index, tuple<Types...>>&& get(tuple<Types...>&& Tuple) noexcept;

// (C++14) by type:
// get reference to T element of tuple
template <class T, class... Types>  
   constexpr T& get(tuple<Types...>& Tuple) noexcept;

// get const reference to T element of tuple
template <class T, class... Types>  
   constexpr const T& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to T element of tuple
template <class T, class... Types>  
   constexpr T&& get(tuple<Types...>&& Tuple) noexcept;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Index`  
 Alınacak öğenin dizini.  
  
 `Types`  
 Dizideki bildirimi sırayla türleri dizisi bildirildi.  
  
 `T`  
 Alınacak öğenin türü.  
  
 `Tuple`  
 Herhangi bir sayıda öğe içeren std::tuple.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevleri dizin değerinde bir başvuru döndürmek `Index`, veya türünde `T` içinde `tuple` nesnesi.  
  
 Çağırma `get<T>(Tuple)` tanımlama grubu t türünde bir öğe sayısından fazla veya az içeriyorsa derleyici hatası oluşturur  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include <tuple>   
#include <iostream>   
#include <string>  
  
using namespace std;  
  
int main() {  
    tuple<int, double, string> tup(0, 1.42, "Call me Tuple");  
  
    // get elements by index  
    cout << " " << get<0>(tup);  
    cout << " " << get<1>(tup);  
    cout << " " << get<2>(tup) << endl;  
  
    // get elements by type  
    cout << " " << get<int>(tup);  
    cout << " " << get<double>(tup);  
    cout << " " << get<string>(tup) << endl;    
}  
```  
  
```Output  
0 1.42 Call me Tuple  
0 1.42 Call me Tuple  
```  
  
##  <a name="make_tuple"></a>  make_tuple
 Yapar bir `tuple` öğesi değerlerinden.  
  
```  
template <class T1, class T2, ..., class TN>  
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```  
  
### <a name="parameters"></a>Parametreler  
 `TN`  
 Nth işlevi parametresi türü.  
  
 `tN`  
 Nth işlevi parametre değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevi döndürür `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)`, burada her tür `Vi` olan `X&` karşılık gelen yazdığınızda `Ti` olan `cv` `reference_wrapper<X>`; Aksi takdirde, bu `Ti`.  
  
 Bir avantajı `make_tuple` depolanmakta nesne türlerini derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenler gibi kullanmayan `make_tuple<int, int>(1, 2)` kullandığınızda `make_tuple` gereksiz yere ayrıntılı olduğundan ve derleme hatasına neden olabilen karmaşık rvalue başvuru sorunlarını ekler.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__tuple__make_tuple.cpp   
// compile by using: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    c0 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```  
 0 1 2 3
 4 5 6 7  
```  
  
##  <a name="tie"></a>  tie
 Yapar bir `tuple` öğesi başvuruları gelen.  
  
```  
template <class T1, class T2, ..., class TN>  
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```  
  
### <a name="parameters"></a>Parametreler  
 `TN`  
 Nth tanımlama grubu öğenin temel türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevi döndürür `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__tuple__tie.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    int v4 = 4;   
    double v5 = 5;   
    int v6 = 6;   
    double v7 = 7;   
    std::tie(v4, v5, v6, v7) = c0;   
  
// display contents " 0 1 2 3"   
    std::cout << " " << v4;   
    std::cout << " " << v5;   
    std::cout << " " << v6;   
    std::cout << " " << v7;   
    std::cout << std::endl;   
  
    return (0);   
}    
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Tuple >](../standard-library/tuple.md)

