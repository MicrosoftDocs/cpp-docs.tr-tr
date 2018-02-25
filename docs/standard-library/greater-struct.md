---
title: "greater yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::greater
dev_langs:
- C++
helpviewer_keywords:
- greater struct
- greater function
ms.assetid: ebc348e1-edcd-466b-b21a-db95bd8f9079
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e414d0ba4d53c1fc8e4a6500e79533ea38d9e42
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="greater-struct"></a>greater Yapısı
Büyük gerçekleştirir ikili bir koşulu-işlemine kıyasla ( `operator>`) bağımsız değişkenlerini üzerinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Type = void>
struct greater : public binary_function <Type, Type, bool>  
{
    bool operator()(
    const Type& Left,
    const Type& Right) const;

 };

// specialized transparent functor for operator>
template <>
struct greater<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    ->  decltype(std::forward<T>(Left)> std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Parametreler  
 `Type`, `T`, `U`  
 Destekleyen herhangi bir türü bir `operator>` türündeki işlenenler belirtilen veya çıkarsanan alır.  
  
 `Left`  
 Sol işleneni büyük-işlemi daha. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `T`.  
  
 `Right`  
 Büyük sağ işleneni-işlemi daha. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `U`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucu `Left > Right`. Özel şablonu tarafından döndürülen türüne sahip sonuç iletilmesini mükemmel `operator>`.  
  
## <a name="remarks"></a>Açıklamalar  
 İkili karşılaştırma `greater` <  `Type`> katı bir zayıf türü öğesi değerleri kümesi sıralama sağlar `Type` eşdeğer sınıfları içinde bu tür için standart matematiksel gereksinimleri karşılıyor ve yalnızca, Bu nedenle sipariş. Tüm öğeleri farklı değerleri birbirine göre sıralanmış, herhangi bir işaretçi türü için özelleştirmeleri toplam, öğelerin sıralaması verim.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// functional_greater.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
  
   int i;  
   for ( i = 0 ; i < 8 ; i++ )  
   {  
      v1.push_back( rand( ) );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,   
   // specify binary predicate greater<int>( )  
   sort( v1.begin( ), v1.end( ), greater<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```
Original vector v1 = (41 18467 6334 26500 19169 15724 11478 29358)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500 29358)
Resorted vector v1 = (29358 26500 19169 18467 15724 11478 6334 41)
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



