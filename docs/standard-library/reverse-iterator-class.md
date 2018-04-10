---
title: reverse_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::reverse_iterator
- iterator/std::reverse_iterator::difference_type
- iterator/std::reverse_iterator::iterator_type
- iterator/std::reverse_iterator::pointer
- iterator/std::reverse_iterator::reference
- iterator/std::reverse_iterator::base
- iterator/std::reverse_iterator::operator_star
dev_langs:
- C++
helpviewer_keywords:
- std::reverse_iterator [C++]
- std::reverse_iterator [C++], difference_type
- std::reverse_iterator [C++], iterator_type
- std::reverse_iterator [C++], pointer
- std::reverse_iterator [C++], reference
- std::reverse_iterator [C++], base
- std::reverse_iterator [C++], operator_star
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b72f9bc378c37eed6660091f04dfabc01bc5d4c3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="reverseiterator-class"></a>reverse_iterator Sınıfı
Şablon sınıfı, yalnızca tersten rastgele erişim veya çift yönlü bir yineleyici gibi davranan bir ters yineleyici nesnesini tanımlayan bir yineleyici bağdaştırıcısıdır. Bir aralığın geriye doğru geçişini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### <a name="parameters"></a>Parametreler  
 RandomIterator  
 Yineleyiciyi tersten çalışmaya uygun olacak şekilde temsil eden tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıca mevcut C++ Standart Kitaplığı kapsayıcılarını tanımlayan `reverse_iterator` ve `const_reverse_iterator` türleri ve üye işlevleri sahip `rbegin` ve `rend` ters yineleyiciler döndürür. Bu yineleyicilerde üzerine yazma semantikleri vardır. `reverse_iterator` Bağdaştırıcısı semantiği eklemek ve akışları ile de kullanılabilir sunar gibi bu işlevselliği ek niteliğindedir.  
  
 `reverse_iterator` Gerektiren bir çift yönlü yineleyici değil çağırmalıdır herhangi bir üyenin işlevleri `operator+=`, `operator+`, `operator-=`, `operator-`, veya `operator[]`, hangi yalnızca kullanılabilir rasgele erişim yineleyiciler ile.  
  
 Yineleyici aralığı [*ilk*, *son*), sol taraftaki köşeli ayraç eklenmesi, gösterir burada *ilk* ve sağ parantez gösterir öğeleri kadar ancak hariç dahil edilmesi *son* kendisi. Aynı öğeleri ters sırada içerdiği [ **rev** - *ilk*, **rev** - *son*) için olması durumunda *son* bir geçmiş--uç öğe bir sırada sonra ilk öğedir **rev** - *ilk* ters sırası işaret \*(*son* - 1). Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:  
  
 &\*( **reverse_iterator** ( *ı* )) == &\*( *ı* - 1).  
  
 Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Yineleyici (2, 4, 6, 8) dizisi 6 öğesinde ele varsa bunu sonra `reverse_iterator` adresi ters sırada (8, 6, 4, 2) 4 öğe olur.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[reverse_iterator](#reverse_iterator)|Varsayılan yapıları `reverse_iterator` veya `reverse_iterator` temel yineleyici gelen.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[difference_type](#difference_type)|İkisi arasındaki farkı sağlayan bir türü `reverse_iterator`aynı kapsayıcı içindeki öğelerine başvuran s.|  
|[iterator_type](#iterator_type)|İçin temel alınan yineleyici sağlayan bir türü bir `reverse_iterator`.|  
|[pointer](#pointer)|Tarafından gönderilen bir öğe için bir işaretçi sağlayan bir türü bir `reverse_iterator`.|  
|[reference](#reference)|Bir öğe tarafından ele başvuru sağlayan bir türü bir `reverse_iterator`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[base](#base)|Temel alınan yineleyici gelen kurtarır kendi `reverse_iterator`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator_star](#op_star)|Öğesini döndüren bir `reverse_iterator` adresleri.|  
|[operator+](#op_add)|Yineleyici için uzaklık ekler ve yeni döndürür `reverse_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.|  
|[operator++](#op_add_add)|Artışlarla `reverse_iterator` sonraki öğeye.|  
|[operator+=](#op_add_eq)|Belirtilen uzaklığı ekler bir `reverse_iterator`.|  
|[operator-](#operator-)|Uzaklık çıkarır bir `reverse_iterator` ve döndüren bir `reverse_iterator` uzaklık konumunda öğe adresleme.|  
|[operator--](#operator--)|Azaltır `reverse_iterator` önceki öğesi.|  
|[operator-=](#operator-_eq)|Belirtilen uzaklığı çıkarır bir `reverse_iterator`.|  
|[operator->](#operator-_gt)|Tarafından ele öğesine bir işaretçi döndüren `reverse_iterator`.|  
|[Operator &#91; &#93;](#op_at)|Bir öğe uzaklık başvuru tarafından ele öğeden döndürür bir `reverse_iterator` konumlar belirtilen sayısı.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
##  <a name="base"></a>  reverse_iterator::base  
 Temel alınan yineleyici gelen kurtarır kendi `reverse_iterator`.  
  
```   
RandomIterator base() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arka plandaki yineleyici `reverse_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan kendi yineleyiciler tüm geriye doğru yineleyiciler ilişkili kimlik şöyledir:  
  
 &\*( `reverse_iterator` ( *i* ) ) == &\*( *i* - 1 ).  
  
 Uygulamada, ters sırada buna `reverse_iterator` öğesi bir konuma (sağında) başvurur yineleyici özgün dizisinde başvurulan öğe. Yineleyici (2, 4, 6, 8) dizisi 6 öğesinde ele varsa bunu sonra `reverse_iterator` adresi ters sırada (8, 6, 4, 2) 4 öğe olur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_base.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos, bpos;  
   pos = find ( vec.begin ( ), vec.end ( ), 6 );  
   cout << "The iterator pos points to: " << *pos << "." << endl;  
  
   typedef reverse_iterator<vector<int>::iterator>::iterator_type it_vec_int_type;  
  
   reverse_iterator<it_vec_int_type> rpos ( pos );  
   cout << "The reverse_iterator rpos points to: " << *rpos   
        << "." << endl;  
  
   bpos = rpos.base ( );  
   cout << "The iterator underlying rpos is bpos & it points to: "   
        << *bpos << "." << endl;  
}  
```  
  
##  <a name="difference_type"></a>  reverse_iterator::difference_type  
 İkisi arasındaki farkı sağlayan bir türü `reverse_iterator`aynı kapsayıcı içindeki öğelerine başvuran s.  
  
```   
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type; 
```  
  
### <a name="remarks"></a>Açıklamalar  
 `reverse_iterator` Fark türüdür yineleyici fark türü ile aynı.  
  
 Yineleyici ayırdedici nitelik typename eşanlamlısı türüdür `iterator_traits` \< **RandomIterator**> **:: işaretçi**.  
  
### <a name="example"></a>Örnek  
  Bkz: [reverse_iterator::operator &#91; &#93;](#op_at) bildirme ve kullanma konusunda bir örnek için `difference_type`.  
  
##  <a name="iterator_type"></a>  reverse_iterator::iterator_type  
 İçin temel alınan yineleyici sağlayan bir türü bir `reverse_iterator`.  
  
```  
typedef RandomIterator iterator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Iterator`.  
  
### <a name="example"></a>Örnek  
  Bkz: [reverse_iterator::base](#base) bildirme ve kullanma konusunda bir örnek için `iterator_type`.  
  
##  <a name="op_star"></a>  reverse_iterator::operator*  
 Bir reverse_iterator adresleri öğesi döndürür.  
  
```   
reference operator*() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Reverse_iterator tarafından ele öğeleri değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç döndürür \*( **geçerli** - 1).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_ref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos, bpos;  
   pos = find ( vec.begin ( ), vec.end ( ), 6 );  
  
   // Declare a difference type for a parameter  
   // declare a reference return type  
   reverse_iterator<vector<int>::iterator>::reference refpos = *pos;  
   cout << "The iterator pos points to: " << refpos << "." << endl;  
}  
```  
  
##  <a name="op_add"></a>  reverse_iterator::operator+  
 Yineleyici için uzaklık ekler ve yeni döndürür `reverse_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.  
  
```  
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Off`  
 Ters yineleyici eklenecek uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `reverse_iterator` uzaklık öğesi adresleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca, kullanılabilir `reverse_iterator` rasgele erişim yineleyici gereksinimlerini karşılar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_add.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   vector <int>::reverse_iterator rVPOS2 =rVPOS1 + 2; // offset added  
   cout << "After the +2 offset, the iterator rVPOS2 points\n"  
        << " to the 3rd element in the reversed sequence: "  
        << *rVPOS2 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 10.  
After the +2 offset, the iterator rVPOS2 points  
 to the 3rd element in the reversed sequence: 6.  
```  
  
##  <a name="op_add_add"></a>  reverse_iterator::operator++  
 Reverse_iterator önceki öğeye artırır.  
  
```  
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk işleci preincremented döndürür `reverse_iterator` ve postincrement işleci ikinci bir kopyası artırılır döndürür `reverse_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca, kullanılabilir `reverse_iterator` çift yönlü yineleyici gereksinimlerini karşılar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i - 1 );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the last element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1++;  // postincrement, preincrement: ++rVPSO1  
  
   cout << "After incrementing, the iterator rVPOS1 points\n"  
        << " to the second element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 3 5 7 9 ).  
The vector vec reversed is: ( 9 7 5 3 1 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 9.  
After incrementing, the iterator rVPOS1 points  
 to the second element in the reversed sequence: 7.  
```  
  
##  <a name="op_add_eq"></a>  reverse_iterator::operator+=  
 Belirtilen kayma reverse_iterator ekler.  
  
```  
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `Off`  
 Yineleyici artırmak üzere uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru tarafından ele öğesine `reverse_iterator`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_addoff.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )   
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the last element  
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );  
  
   cout << "The iterator rVPOS1 initially points to the first "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1+=2;   // addition of an offset  
   cout << "After the +2 offset, the iterator rVPOS1 now points\n"  
        << " to the third element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator rVPOS1 initially points to the first element  
 in the reversed sequence: 10.  
After the +2 offset, the iterator rVPOS1 now points  
 to the third element in the reversed sequence: 6.  
```  
  
##  <a name="reverse_iterator__operator-"></a>  reverse_iterator::operator-  
 Uzaklık çıkarır bir `reverse_iterator` ve döndüren bir `reverse_iterator` uzaklık konumunda öğe adresleme.  
  
```  
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Off`  
 Reverse_iterator çıkarılır uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `reverse_iterator` uzaklık öğesi adresleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca, kullanılabilir `reverse_iterator` rasgele erişim yineleyici gereksinimlerini karşılar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_sub.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 3 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   vector <int>::reverse_iterator rVPOS2 =rVPOS1 - 2; // offset subtracted  
   cout << "After the -2 offset, the iterator rVPOS2 points\n"  
        << " to the 2nd element from the last in the reversed sequence: "  
        << *rVPOS2 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 3 6 9 12 15 ).  
The vector vec reversed is: ( 15 12 9 6 3 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 3.  
After the -2 offset, the iterator rVPOS2 points  
 to the 2nd element from the last in the reversed sequence: 9.  
```  
  
##  <a name="reverse_iterator__operator--"></a>  reverse_iterator::operator--  
 Azaltır önceki öğesine reverse_iterator.  
  
```  
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk işleci predecremented döndürür `reverse_iterator` ve postdecrement işleci ikinci bir kopyası indirildiği döndürür `reverse_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca, kullanılabilir `reverse_iterator` çift yönlü yineleyici gereksinimlerini karşılar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_decr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )    
   {  
      vec.push_back ( 2 * i - 1 );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
   rVPOS1--;  // postdecrement, predecrement: --rVPSO1  
  
   cout << "After the decrement, the iterator rVPOS1 points\n"  
        << " to the next-to-last element in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 3 5 7 9 ).  
The vector vec reversed is: ( 9 7 5 3 1 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 1.  
After the decrement, the iterator rVPOS1 points  
 to the next-to-last element in the reversed sequence: 3.  
```  
  
##  <a name="reverse_iterator__operator-_eq"></a>  reverse_iterator::operator-=  
 Belirtilen uzaklığı çıkarır bir `reverse_iterator`.  
  
```  
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `Off`  
 Uzaklık çıkartma yapılacak `reverse_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca, kullanılabilir `reverse_iterator` rasgele erişim yineleyici gereksinimlerini karşılar.  
  
 İşleç değerlendirir **geçerli** + _ *devre dışı*. ardından döndürür  **\*bu**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_op_suboff.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 3 * i );  
   }  
  
   vector <int>::iterator vIter;  
  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   // Initializing reverse_iterators to the first element  
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;  
  
   cout << "The iterator rVPOS1 initially points to the last "  
        << "element\n in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
  
   rVPOS1-=2;      // Subtraction of an offset  
   cout << "After the -2 offset, the iterator rVPOS1 now points\n"  
        << " to the 2nd element from the last in the reversed sequence: "  
        << *rVPOS1 << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 3 6 9 12 15 ).  
The vector vec reversed is: ( 15 12 9 6 3 ).  
The iterator rVPOS1 initially points to the last element  
 in the reversed sequence: 3.  
After the -2 offset, the iterator rVPOS1 now points  
 to the 2nd element from the last in the reversed sequence: 9.  
```  
  
##  <a name="reverse_iterator__operator-_gt"></a>  reverse_iterator::operator-&gt;  
 Tarafından ele öğesine bir işaretçi döndüren `reverse_iterator`.  
  
```   
pointer operator->() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından ele öğesi için bir işaretçi `reverse_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç döndürür  **& \* \*bu**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_ptrto.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef vector<pair<int,int> > pVector;  
   pVector vec;  
   vec.push_back(pVector::value_type(1,2));  
   vec.push_back(pVector::value_type(3,4));  
   vec.push_back(pVector::value_type(5,6));  
  
   pVector::iterator pvIter;  
   cout << "The vector vec of integer pairs is:\n( ";  
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)  
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";  
   cout << ")" << endl << endl;  
  
   pVector::reverse_iterator rpvIter;  
   cout << "The vector vec reversed is:\n( ";  
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++ )  
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";  
   cout << ")" << endl << endl;  
  
   pVector::iterator pos = vec.begin ( );  
   pos++;  
   cout << "The iterator pos points to:\n( " << pos -> first << ", "   
   << pos -> second << " )" << endl << endl;  
  
   pVector::reverse_iterator rpos (pos);   
  
   // Use operator -> with return type: why type int and not int*  
   int fint = rpos -> first;  
   int sint = rpos -> second;  
  
   cout << "The reverse_iterator rpos points to:\n( " << fint << ", "   
   << sint << " )" << endl;  
}  
```  
  
```Output  
The vector vec of integer pairs is:  
( ( 1, 2) ( 3, 4) ( 5, 6) )  
  
The vector vec reversed is:  
( ( 5, 6) ( 3, 4) ( 1, 2) )  
  
The iterator pos points to:  
( 3, 4 )  
  
The reverse_iterator rpos points to:  
( 1, 2 )  
```  
  
##  <a name="op_at"></a>  reverse_iterator::operator[]  
 Bir öğe uzaklık başvuru tarafından ele öğeden döndürür bir `reverse_iterator` konumlar belirtilen sayısı.  
  
```   
reference operator[](difference_type Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Off`  
 Uzaklık `reverse_iterator` adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe uzaklık referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç döndürür  **\*** (  **\*bu** + `Off`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_ret_ref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( 2 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos;  
   pos = find ( vec.begin ( ), vec.end ( ), 8 );  
   reverse_iterator<vector<int>::iterator> rpos ( pos );  
  
   // Declare a difference type for a parameter  
   reverse_iterator<vector<int>::iterator>::difference_type diff = 2;  
  
   cout << "The iterator pos points to: " << *pos << "." << endl;  
   cout << "The iterator rpos points to: " << *rpos << "." << endl;  
  
   // Declare a reference return type & use operator[]  
   reverse_iterator<vector<int>::iterator>::reference refrpos = rpos [diff];  
   cout << "The iterator rpos now points to: " << refrpos << "." << endl;     
}  
```  
  
```Output  
The vector vec is: ( 2 4 6 8 10 ).  
The vector vec reversed is: ( 10 8 6 4 2 ).  
The iterator pos points to: 8.  
The iterator rpos points to: 6.  
The iterator rpos now points to: 2.  
```  
  
##  <a name="pointer"></a>  reverse_iterator::pointer  
 Tarafından gönderilen bir öğe için bir işaretçi sağlayan bir türü bir `reverse_iterator`.  
  
```  
typedef typename iterator_traits<RandomIterator>::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyici ayırdedici nitelik typename eşanlamlısı türüdür `iterator_traits` \< *RandomIterator*> **:: işaretçi**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_pointer.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef vector<pair<int,int> > pVector;  
   pVector vec;  
   vec.push_back( pVector::value_type( 1,2 ) );  
   vec.push_back( pVector::value_type( 3,4 ) );  
   vec.push_back( pVector::value_type( 5,6 ) );  
  
   pVector::iterator pvIter;  
   cout << "The vector vec of integer pairs is:\n" << "( ";  
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)  
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";  
   cout << ")" << endl;  
  
   pVector::reverse_iterator rpvIter;  
   cout << "\nThe vector vec reversed is:\n" << "( ";  
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++)  
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";  
   cout << ")" << endl;  
  
   pVector::iterator pos = vec.begin ( );  
   pos++;  
   cout << "\nThe iterator pos points to:\n"  
        << "( " << pos -> first << ", "  
        << pos -> second << " )" << endl;  
  
   pVector::reverse_iterator rpos (pos);  
   cout << "\nThe iterator rpos points to:\n"  
        << "( " << rpos -> first << ", "  
        << rpos -> second << " )" << endl;  
}  
```  
  
```Output  
The vector vec of integer pairs is:  
( ( 1, 2) ( 3, 4) ( 5, 6) )  
  
The vector vec reversed is:  
( ( 5, 6) ( 3, 4) ( 1, 2) )  
  
The iterator pos points to:  
( 3, 4 )  
  
The iterator rpos points to:  
( 1, 2 )  
```  
  
##  <a name="reference"></a>  reverse_iterator::reference  
 Reverse_iterator tarafından gönderilen bir öğe için bir başvuru sağlar türü.  
  
```  
typedef typename iterator_traits<RandomIterator>::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyici ayırdedici nitelik typename eşanlamlısı türüdür `iterator_traits` \< *RandomIterator*> **:: başvuru**.  
  
### <a name="example"></a>Örnek  
  Bkz: [reverse_iterator::operator &#91; &#93;](#op_at) veya [reverse_iterator::operator *](#op_star) bildirme ve kullanma örnekleri için **başvuru**.  
  
##  <a name="reverse_iterator"></a>  reverse_iterator::reverse_iterator  
 Varsayılan yapıları `reverse_iterator` veya `reverse_iterator` temel yineleyici gelen.  
  
```   
reverse_iterator();  
explicit reverse_iterator(RandomIterator right);

template <class Type>  
reverse_iterator(const reverse_iterator<Type>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İçin uyarlanmış yapılacağı yineleyici bir `reverse_iterator`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan `reverse_iterator` veya `reverse_iterator` temel yineleyici uyarlama.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:  
  
 &\*( `reverse_iterator` ( *i* ) ) == &\*( *i* - 1 ).  
  
 Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Yineleyici (2, 4, 6, 8) dizisi 6 öğesinde ele varsa bunu sonra `reverse_iterator` adresi ters sırada (8, 6, 4, 2) 4 öğe olur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// reverse_iterator_reverse_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 6 ; ++i )  
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::reverse_iterator rvIter;  
   cout << "The vector vec reversed is: ( ";  
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)  
      cout << *rvIter << " ";  
   cout << ")." << endl;  
  
   vector <int>::iterator pos;  
   pos = find ( vec.begin ( ), vec.end ( ), 4 );  
   cout << "The iterator pos = " << *pos << "." << endl;  
  
   vector <int>::reverse_iterator rpos ( pos );  
   cout << "The reverse_iterator rpos = " << *rpos   
        << "." << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

