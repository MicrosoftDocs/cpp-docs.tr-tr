---
title: back_insert_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iterator/std::back_insert_iterator
- iterator/std::back_insert_iterator::container_type
- iterator/std::back_insert_iterator::reference
dev_langs:
- C++
helpviewer_keywords:
- std::back_insert_iterator [C++]
- std::back_insert_iterator [C++], container_type
- std::back_insert_iterator [C++], reference
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7646b26c1651ccf93fcc3bcb6828ae402ea5ca07
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="backinsertiterator-class"></a>back_insert_iterator Sınıfı
Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin arka ucunun üzerine yazar ve bu nedenle C++ dizi kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `back_insert_iterator` Sınıfı şablonlaştırılmış kapsayıcı türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Container`  
 Kapsayıcı hangi öğelerin geri türlerinin tarafından eklenecek bir `back_insert_iterator`.  
  
## <a name="remarks"></a>Açıklamalar  
 Kapsayıcının itfa edilecek sabit sürede dizininin sonuna öğe eklemenin mümkün olduğu geri ekleme dizisinin gereksinimlerini karşılaması gerekir. C++ Standart Kitaplığı dizisi kapsayıcıları tarafından tanımlanan [deque sınıfı](../standard-library/deque-class.md), [sınıf listesi](../standard-library/list-class.md) ve [vector sınıfı](../standard-library/vector-class.md) gerekli sağlamak `push_back` üye işlevini ve Bu gereksinimleri karşılamak. Bu üç kapsayıcı yanı sıra dizeleri her ile kullanmak için uyarlanmış olabilir `back_insert_iterator`s. A `back_insert_iterator` her zaman kapsayıcısı ile başlatılması gerekir.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator)|Oluşturan bir `back_insert_iterator` bir kapsayıcıda son öğesinden sonra öğeleri ekler.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[container_type](#container_type)|İçin bir kapsayıcı sağlayan bir türü `back_insert_iterator`.|  
|[Başvuru](#reference)|İçin bir başvuru sağlayan bir türü `back_insert_iterator`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç *](#op_star)|Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci * `i`  =  `x` geri eklemek için.|  
|[operator++](#op_add_add)|Artışlarla `back_insert_iterator` içine bir değer depolanmış sonraki konuma.|  
|[operator=](#op_eq)|Çıktı yineleyici ifade uygulamak için kullanılan atama işleci * `i`  =  `x` geri eklemek için.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<yineleyici >  
  
 **Namespace:** std  
  
##  <a name="back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator  
 Oluşturan bir `back_insert_iterator` bir kapsayıcıda son öğesinden sonra öğeleri ekler.  
  
```   
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Cont`  
 Kapsayıcı, `back_insert_iterator` bir öğeye eklemektir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `back_insert_iterator` parametresi kapsayıcısı için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// back_insert_iterator_back_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The initial vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   // Insertions with member function  
   back_inserter ( vec ) = 40;  
   back_inserter ( vec ) = 50;  
  
   // Alternatively, insertions can be done with template function  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 600;  
   backiter++;  
 *backiter = 700;  
  
   cout << "After the insertions, the vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The initial vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).  
```  
  
##  <a name="container_type"></a>  back_insert_iterator::container_type  
 İçin bir kapsayıcı sağlayan bir türü `back_insert_iterator`.  
  
```   
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **kapsayıcı**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// back_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The original vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::container_type vec1 = vec;  
   back_inserter ( vec1 ) = 40;  
  
   cout << "After the insertion, the vector is: ( ";  
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector vec is: ( 1 2 3 ).  
After the insertion, the vector is: ( 1 2 3 40 ).  
```  
  
##  <a name="op_star"></a>  back_insert_iterator::operator*  
 Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci \* *ı* = *x*.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı arkasındaki eklenen öğesine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Çıktı yineleyici ifade uygulamak için kullanılan  **\*Iter** = **değeri**. Varsa **Iter** öğenin bir sırada sonra adresleri yineleyici olan  **\*Iter** = **değeri** , öğenin değeri ile değiştirir ve desteklemez Dizideki öğelerin toplam sayısını değiştirin.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// back_insert_iterator_back_insert.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).  
```  
  
##  <a name="op_add_add"></a>  back_insert_iterator::operator++  
 Artışlarla `back_insert_iterator` içine bir değer depolanmış sonraki konuma.  
  
```  
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `back_insert_iterator` içine bir değer depolanmış sonraki konumu adresleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Preincrementation ve postincrementation işleçleri aynı sonucu döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// back_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 3 ; ++i )    
   {  
      vec.push_back ( 10 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 30;  
   backiter++;      // Increment to the next element  
 *backiter = 40;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 10 20 ).  
After the insertions, the vector vec becomes: ( 10 20 30 40 ).  
```  
  
##  <a name="op_eq"></a>  back_insert_iterator::operator=  
 Ekler veya arka uç kapsayıcı üzerine bir değer iter.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Kapsayıcıya eklenecek değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı arkasındaki eklenen son öğe başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işleci değerlendirir `Container.push_back( val)`,  
  
 ardından döndürür `*this`. İkinci üye işleci değerlendirir  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 ardından döndürür `*this`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// back_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="reference"></a>  back_insert_iterator::reference  
 İçin bir başvuru sağlayan bir türü `back_insert_iterator`.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili kapsayıcı tarafından denetlenen dizi bir öğe için bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// back_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::reference   
        RefLast = *(vec.end ( ) - 1 );  
   cout << "The last element in the vector vec is: "   
        << RefLast << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
The last element in the vector vec is: 3.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Yineleyici >](../standard-library/iterator.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

