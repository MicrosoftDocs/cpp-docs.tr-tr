---
title: reverse_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 348cff70b46af133009703c513ac9d939486cd91
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105919"
---
# <a name="reverseiterator-class"></a>reverse_iterator Sınıfı

Şablon sınıfı, yalnızca tersten rastgele erişim veya çift yönlü bir yineleyici gibi davranan bir ters yineleyici nesnesini tanımlayan bir yineleyici bağdaştırıcısıdır. Bir aralığın geriye doğru geçişini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class RandomIterator>
class reverse_iterator
```

### <a name="parameters"></a>Parametreler

Randomıterator yineleyiciyi tersten çalışmaya uygun olacak şekilde temsil eden tür.

## <a name="remarks"></a>Açıklamalar

Var olan C++ Standart Kitaplığı kapsayıcıları da tanımlamanız `reverse_iterator` ve `const_reverse_iterator` türleri ve üye işlevlerde `rbegin` ve `rend` ters yineleyici döndüren. Bu yineleyicilerde üzerine yazma semantikleri vardır. `reverse_iterator` Bağdaştırıcısı bu işlevselliği ekleme semantikleri ve akışları ile de kullanılabilir sunduğu tamamlar.

`reverse_iterator` Gerektiren çift yönlü bir yineleyici gerekir değil herhangi bir üye işlevleri çağırma `operator+=`, `operator+`, `operator-=`, `operator-`, veya `operator[]`, hangi yalnızca kullanılabilir rasgele erişim yineleyicileri ile.

Bir yineleyicinin aralığı [*ilk*, *son*), burada sol köşeli ayraç eklenmesi, gösteren *ilk* ve sağdaki parantezler gösterir en fazla ancak hariç öğelerin eklenmesi *son* kendisi. Tersine çevrilmiş sırada dahil aynı öğeleri [ **rev** - *ilk*, **rev** - *son*) için olması durumunda *son* bir-past--end öğesi bir dizideki ilk öğe ise **rev** - *ilk* ters dizide işaret \*(*son* - 1). Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( **reverse_iterator** ( *miyim* )) == &\*( *miyim* - 1).

Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Böyle bir yineleyici 6 öğesini dizideki (2, 4, 6, 8), ele sonra `reverse_iterator` ters dizide (8, 6, 4, 2) 4 öğesine adresi olur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[reverse_iterator](#reverse_iterator)|Varsayılan yapıları `reverse_iterator` veya `reverse_iterator` temel yineleyiciden.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|İkisi arasındaki farkı sağlayan bir tür `reverse_iterator`aynı kapsayıcı içindeki öğelere başvuran.|
|[iterator_type](#iterator_type)|İçin temel bir yineleyici sağlayan tür bir `reverse_iterator`.|
|[İşaretçi](#pointer)|Tarafından ele alınan öğeye işaretçi sağlayan bir tür bir `reverse_iterator`.|
|[Başvuru](#reference)|Tarafından ele alınan öğeye başvuru sağlayan bir tür bir `reverse_iterator`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Temel yineleyiciden kurtarır kendi `reverse_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator_star](#op_star)|Öğeyi döndürür bir `reverse_iterator` adresleri.|
|[operator +](#op_add)|Yineleyiciye bir uzaklık ekler ve yeni döndürür `reverse_iterator` eklenen öğeyi yeni uzaklık konumunda ele alan.|
|[operator ++](#op_add_add)|Artışlarla `reverse_iterator` sonraki öğeye.|
|[operator+=](#op_add_eq)|Öğesinden belirtilen bir uzaklık ekler bir `reverse_iterator`.|
|[operator-](#operator-)|Öğesinden bir uzaklık çıkarı bir `reverse_iterator` ve döndüren bir `reverse_iterator` uzaklık konumunda öğeyi ele alan.|
|[--işleci](#operator--)|Azaltır `reverse_iterator` öğesini önceki öğeye.|
|[-= işleci](#operator-_eq)|Öğesinden belirtilen bir uzaklık çıkarır bir `reverse_iterator`.|
|[-> işleci](#operator-_gt)|Yineleyicisinin adreslediği öğeye bir işaretçi döndürür `reverse_iterator`.|
|[işleci&#91;&#93;](#op_at)|Yineleyicisinin adreslediği öğeye bir öğe uzaklığı için bir başvuru döndürür bir `reverse_iterator` belirli sayıdaki uzaklığına göre.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="base"></a>  reverse_iterator::Base

Temel yineleyiciden kurtarır kendi `reverse_iterator`.

```cpp
RandomIterator base() const;
```

### <a name="return-value"></a>Dönüş Değeri

Alttaki yineleyiciyi `reverse_iterator`.

### <a name="remarks"></a>Açıklamalar

Tüm ters Yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( `reverse_iterator` ( *miyim* )) == &\*( *miyim* - 1).

Uygulamada, ters sırada buna `reverse_iterator` öğenin bir ötesindeki (sağındaki) başvuracaktır yineleyici özgün dizisinde başvurulan öğe. Böyle bir yineleyici 6 öğesini dizideki (2, 4, 6, 8), ele sonra `reverse_iterator` ters dizide (8, 6, 4, 2) 4 öğesine adresi olur.

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

## <a name="difference_type"></a>  reverse_iterator::difference_type

İkisi arasındaki farkı sağlayan bir tür `reverse_iterator`aynı kapsayıcı içindeki öğelere başvuran.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type;
```

### <a name="remarks"></a>Açıklamalar

`reverse_iterator` Fark türü, yineleyicinin fark türüne ile aynı.

Türü yineleyici nitelik typename eşanlamlıdır `iterator_traits` \< **Randomıterator**> **:: işaretçi**.

### <a name="example"></a>Örnek

Bkz: [reverse_iterator::operator&#91; &#93; ](#op_at) bildirme ve kullanma konusunda bir örnek için `difference_type`.

## <a name="iterator_type"></a>  reverse_iterator::iterator_type

İçin temel bir yineleyici sağlayan tür bir `reverse_iterator`.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Iterator`.

### <a name="example"></a>Örnek

Bkz: [reverse_iterator::base](#base) bildirme ve kullanma konusunda bir örnek için `iterator_type`.

## <a name="op_star"></a>  reverse_iterator::operator\*

Bir reverse_iterator adresleri öğeyi döndürür.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Reverse_iterator tarafından ele alınan öğelerin değeri.

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

## <a name="op_add"></a>  reverse_iterator::operator+

Yineleyiciye bir uzaklık ekler ve yeni döndürür `reverse_iterator` eklenen öğeyi yeni uzaklık konumunda ele alan.

```cpp
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Ters yineleyici eklenecek olan uzaklık.

### <a name="return-value"></a>Dönüş Değeri

A `reverse_iterator` uzaklık öğeyi ele alan.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca, kullanılabilir `reverse_iterator` bir rastgele erişim yineleyici için gereksinimleri karşılar.

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

## <a name="op_add_add"></a>  reverse_iterator::operator++

Reverse_iterator öğesini önceki öğeye artırır.

```cpp
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk işleç preincremented döndürür `reverse_iterator` ve ikinci postincrement işleci, artımlı bir kopyasını döndürür `reverse_iterator`.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca, kullanılabilir `reverse_iterator` çift yönlü bir yineleyici için gereksinimleri karşılar.

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

## <a name="op_add_eq"></a>  reverse_iterator::operator +=

Bir reverse_iterator belirtilen bir uzaklık ekler.

```cpp
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Yineleyici artırmak üzere uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

Tarafından ele alınan öğeye başvuru `reverse_iterator`.

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

## <a name="reverse_iterator__operator-"></a>  reverse_iterator::operator-

Öğesinden bir uzaklık çıkarı bir `reverse_iterator` ve döndüren bir `reverse_iterator` uzaklık konumunda öğeyi ele alan.

```cpp
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Reverse_iterator çıkarılsın uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

A `reverse_iterator` uzaklık öğeyi ele alan.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca, kullanılabilir `reverse_iterator` bir rastgele erişim yineleyici için gereksinimleri karşılar.

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

## <a name="reverse_iterator__operator--"></a>  reverse_iterator::operator--

Azaltır öğesini önceki öğeye reverse_iterator.

```cpp
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk işleç predecremented döndürür `reverse_iterator` ve postdecrement işleci, ikinci bir kopyasını indirildiği döndürür `reverse_iterator`.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca, kullanılabilir `reverse_iterator` çift yönlü bir yineleyici için gereksinimleri karşılar.

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

## <a name="reverse_iterator__operator-_eq"></a>  reverse_iterator::operator-=

Öğesinden belirtilen bir uzaklık çıkarır bir `reverse_iterator`.

```cpp
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Çıkarmanın yapılacağı uzaklık `reverse_iterator`.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca, kullanılabilir `reverse_iterator` bir rastgele erişim yineleyici için gereksinimleri karşılar.

İşleç değerlendirir **geçerli** + _ *kapalı*. ardından döndürür  **\*bu**.

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

## <a name="op_arrow"></a>  reverse_iterator::operator-&gt;

Yineleyicisinin adreslediği öğeye bir işaretçi döndürür `reverse_iterator`.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından ele alınan öğeye işaretçi `reverse_iterator`.

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

## <a name="op_at"></a>  reverse_iterator::operator]

Yineleyicisinin adreslediği öğeye bir öğe uzaklığı için bir başvuru döndürür bir `reverse_iterator` belirli sayıdaki uzaklığına göre.

```cpp
reference operator[](difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*<br/>
Uzaklığı `reverse_iterator` adresi.

### <a name="return-value"></a>Dönüş Değeri

Referans öğesi.

### <a name="remarks"></a>Açıklamalar

İşleç döndürür <strong>\*</strong>(  **\*bu** + `Off`).

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

## <a name="pointer"></a>  reverse_iterator::pointer

Tarafından ele alınan öğeye işaretçi sağlayan bir tür bir `reverse_iterator`.

```cpp
typedef typename iterator_traits<RandomIterator>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyici nitelik typename eşanlamlıdır `iterator_traits` \< *Randomıterator*> **:: işaretçi**.

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

## <a name="reference"></a>  reverse_iterator::Reference

Bir reverse_iterator tarafından ele alınan öğeye başvuru sağlayan bir tür.

```cpp
typedef typename iterator_traits<RandomIterator>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyici nitelik typename eşanlamlıdır `iterator_traits` \< *Randomıterator*> **:: reference**.

### <a name="example"></a>Örnek

Bkz: [reverse_iterator::operator&#91; &#93; ](#op_at) veya [reverse_iterator::operator *](#op_star) bildirme ve kullanma örnekleri için `reference`.

## <a name="reverse_iterator"></a>  reverse_iterator::reverse_iterator

Varsayılan yapıları `reverse_iterator` veya `reverse_iterator` temel yineleyiciden.

```cpp
reverse_iterator();
explicit reverse_iterator(RandomIterator right);

template <class Type>
reverse_iterator(const reverse_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Yineleyiciyi tersten çalışmaya uygun olacak bir `reverse_iterator`.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan `reverse_iterator` veya `reverse_iterator` temel bir yineleyici uyarlama.

### <a name="remarks"></a>Açıklamalar

Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( `reverse_iterator` ( *miyim* )) == &\*( *miyim* - 1).

Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Böyle bir yineleyici 6 öğesini dizideki (2, 4, 6, 8), ele sonra `reverse_iterator` ters dizide (8, 6, 4, 2) 4 öğesine adresi olur.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
