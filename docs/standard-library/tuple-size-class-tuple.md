---
title: "tuple_size sınıfı; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs: C++
helpviewer_keywords: std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef3d1fae353de8962684b080c223bd4a6a235acf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tuplesize-class"></a>tuple_size sınıfı;
Öğe sayısını raporları, bir `tuple` içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
   struct tuple_size;  
  
// number of elements in array  
template <class Elem, size_t Size>  
   struct tuple_size<array<Elem, Size>>  
      : integral_constant<size_t, Size>; 
  
// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>> 
      : integral_constant<size_t, 2>

// size of tuple  
template <class... Types>  
   struct tuple_size<tuple<Types...>>  
      : integral_constant<size_t, sizeof...(Types)>;  
  
// size of const tuple  
template <class Tuple>  
   struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template <class Tuple>  
   struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template <class Tuple>  
   struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>Parametreler  
*Tanımlama grubu*  
Kayıt türü. 
  
*Elem*  
Dizi öğelerin türü. 
  
*Boyutu*  
Dizinin boyutu. 
  
*T1*  
Çiftinin ilk üye türü. 
  
*T2*  
İkinci üye çiftinin türü. 
  
*Türler*  
Başlığın öğeleri türleri. 
  
  
## <a name="remarks"></a>Açıklamalar  
Şablon sınıfı bir üyenin `value` değeri olan tanımlama grubu türü kapsamını diğer bir deyişle bir tam sayı sabit ifade `Tuple`.  
  
Diziler için şablon özelleştirmesi bir üyenin `value` değeri olan bir tam sayı sabit ifade `Size`, dizinin boyutunu olduğu.  
  
Şablon uzmanlık çifti için bir üyenin `value` değeri 2 olan başka bir deyişle bir tam sayı sabit ifade.  
  
## <a name="example"></a>Örnek  
  
```cpp  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
```  
  
```Output  
 0 1.5 2 3.7  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<kayıt >  
 **Başlık:** \<dizi > (için dizi uzmanlık)  
 **Başlık:** \<yardımcı programı > (için çifti uzmanlık)  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Tuple >](../standard-library/tuple.md)   
 [Tanımlama grubu](../standard-library/tuple-class.md)  
 [tuple_element sınıfı](../standard-library/tuple-element-class-tuple.md)
