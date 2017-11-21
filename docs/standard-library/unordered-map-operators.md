---
title: "&lt;unordered_map&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
dev_langs: C++
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 9825a0073355700edbe1906e8b2cad4535085bf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltunorderedmapgt-operators"></a>&lt;unordered_map&gt; işleçleri
|||||  
|-|-|-|-|  
|[operator! =](#op_neq)|[operator ==](#op_eq_eq)|[operator! =](#op_neq_multimap)|[operator ==](#op_eq_eq_multimap)|  
  
##  <a name="op_neq"></a>operator! =  
 Testleri olup olmadığını [unordered_map](../standard-library/unordered-map-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_map nesnesine eşit değil.  
  
```
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `unordered_map`.  
  
 `right`  
 Türünde bir nesne `unordered_map`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`unordered_maps eşit değilse; `false` eşit olup olmadıkları.  
  
### <a name="remarks"></a>Açıklamalar  
 Unordered_map nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_maps aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// unordered_map_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Çıktı:**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="op_eq_eq"></a>operator ==  
 Testleri olup olmadığını [unordered_map](../standard-library/unordered-map-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_map nesnesine eşit değil.  
  
```
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `unordered_map`.  
  
 `right`  
 Türünde bir nesne `unordered_map`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`unordered_maps eşitse; `false` eşit değillerse.  
  
### <a name="remarks"></a>Açıklamalar  
 Unordered_map nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_maps aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// unordered_map_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Çıktı:**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
##  <a name="op_neq_multimap"></a>operator! =  
 Testleri olup olmadığını [unordered_multimap](../standard-library/unordered-multimap-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_multimap nesnesine eşit değil.  
  
```
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `unordered_multimap`.  
  
 `right`  
 Türünde bir nesne `unordered_multimap`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`unordered_multimaps eşit değilse; `false` eşit olup olmadıkları.  
  
### <a name="remarks"></a>Açıklamalar  
 Unordered_multimap nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_multimaps aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit değildir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// unordered_multimap_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Çıktı:**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="op_eq_eq_multimap"></a>operator ==  
 Testleri olup olmadığını [unordered_multimap](../standard-library/unordered-multimap-class.md) nesne işlecinin sol tarafındaki sağ tarafında unordered_multimap nesnesine eşit değil.  
  
```
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `unordered_multimap`.  
  
 `right`  
 Türünde bir nesne `unordered_multimap`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`unordered_multimaps eşitse; `false` eşit değillerse.  
  
### <a name="remarks"></a>Açıklamalar  
 Unordered_multimap nesneleri arasındaki karşılaştırma öğelerini depoladıkları rastgele sıralama ölçütü etkilenmez. İki unordered_multimaps aynı sayıda öğe varsa ve diğer kapsayıcı öğeleri sıralamaya öğeleridir bir kapsayıcıdaki eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// unordered_multimap_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd  
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Çıktı:**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< unordered_map >](../standard-library/unordered-map.md)



