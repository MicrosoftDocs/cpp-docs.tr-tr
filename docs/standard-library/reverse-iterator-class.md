---
title: reverse_iterator Sınıfı
ms.date: 03/27/2019
f1_keywords:
- xutility/std::reverse_iterator
- iterator/std::reverse_iterator::difference_type
- iterator/std::reverse_iterator::iterator_type
- iterator/std::reverse_iterator::pointer
- iterator/std::reverse_iterator::reference
- iterator/std::reverse_iterator::base
- iterator/std::reverse_iterator::operator_star
helpviewer_keywords:
- std::reverse_iterator [C++]
- std::reverse_iterator [C++], difference_type
- std::reverse_iterator [C++], iterator_type
- std::reverse_iterator [C++], pointer
- std::reverse_iterator [C++], reference
- std::reverse_iterator [C++], base
- std::reverse_iterator [C++], operator_star
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
ms.openlocfilehash: 882d0f7f4930e9d809098a29384a962d0aa8f4ea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373430"
---
# <a name="reverse_iterator-class"></a>reverse_iterator Sınıfı

Sınıf şablonu, rasgele erişim veya çift yönlü yineleyici gibi görünen bir ters yineleyici nesnesini açıklayan bir yineleyici bağdaştırıcıdır. Bir aralığın geriye doğru geçişini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class RandomIterator>
class reverse_iterator
```

### <a name="parameters"></a>Parametreler

RandomIterator Ters çalışacak şekilde uyarlanacak yineleyiciyi temsil eden tür.

## <a name="remarks"></a>Açıklamalar

Varolan C++ Standart `reverse_iterator` Kitaplık kapsayıcıları da tanımlar ve `const_reverse_iterator` türleri ve üye işlevleri `rbegin` vardır ve `rend` ters yineleyiciler döndürür. Bu yineleyicilerde üzerine yazma semantikleri vardır. Adaptör, `reverse_iterator` kesici uç semantik sunduğu ve akışlarla da kullanılabilen bu işlevi tamamlar.

Çift `reverse_iterator` yönlü bir yineleme gerektiren üye işlevlerin `operator+=`hiçbirini aramamalıdır `operator+`, `operator-=` `operator-`, `operator[]`, veya , sadece rasgele erişim yineleyiciler ile kullanılabilir.

Bir yineleyicinin aralığı [*ilk*, *son*), soldaki kare parantez *first* ilk ve sağdaki parantez dahil gösterir kadar ama *son* kendisi hariç öğelerin dahil gösterir. Aynı öğeler ters dizide yer alan [ **devir** - *ilk*, **devir** - *son*) böylece *son* bir dizide bir-past-the-end öğesi ise, sonra ilk öğe **devir** - *first* ilk ters sıra noktaları \**(son* - 1). Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( **reverse_iterator** ( *i* ) \*) == &( *i* - 1 ).

Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Yani bir yineleyici sırayla 6 öğesini ele aldıysa (2, 4, `reverse_iterator` 6, 8), ters sırada (8, 6, 4, 2) 4 öğesini ele alacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Reverse_iterator](#reverse_iterator)|Varsayılan `reverse_iterator` veya altta `reverse_iterator` yatan bir yineleyiciden bir oluşturma.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Aynı kapsayıcıiçindeki elemanlara `reverse_iterator`atıfta bulunan iki s arasındaki farkı sağlayan bir tür.|
|[iterator_type](#iterator_type)|Bir `reverse_iterator`.|
|[pointer](#pointer)|Bir . tarafından adreslenen bir öğeiçin `reverse_iterator`işaretçi sağlayan bir tür|
|[Başvuru](#reference)|Bir . tarafından adreslenen bir öğeye `reverse_iterator`başvuru sağlayan bir tür|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[base](#base)|Altta yatan yineleyiciyi kurtarır. `reverse_iterator`|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator_star](#op_star)|Bir `reverse_iterator` adrese ele alan öğeyi döndürür.|
|[işleç+](#op_add)|Bir yineleyiciye bir ofset ekler `reverse_iterator` ve yeni ofset konumunda eklenen öğeyi ele döndürür.|
|[işleç++](#op_add_add)|Bir sonraki `reverse_iterator` öğeye artışlar.|
|[işleç+=](#op_add_eq)|Bir 'den belirli `reverse_iterator`bir ofset ekler.|
|[işleç-](#operator-)|A'dan `reverse_iterator` bir ofset çıkarır `reverse_iterator` ve ofset konumundaki eleman adedidöndürür.|
|[işleç-](#operator--)|Önceki öğeye `reverse_iterator` doğru kararnameler.|
|[işleç-=](#operator-_eq)|Belirli bir ofset çıkarır. `reverse_iterator`|
|[operatör->](#op-arrow)|Bir işaretçiyi ' tarafından `reverse_iterator`adreslenen öğeye döndürür.|
|[operatör&#91;&#93;](#op_at)|Belirli sayıda pozisyon tarafından `reverse_iterator` ele alınan öğeden bir eleman mahsup başvurusu verir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yineleyici>

**Ad alanı:** std

## <a name="reverse_iteratorbase"></a><a name="base"></a>reverse_iterator::taban

Altta yatan yineleyiciyi kurtarır. `reverse_iterator`

```cpp
RandomIterator base() const;
```

### <a name="return-value"></a>Dönüş Değeri

Altında yatan `reverse_iterator`yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm ters yineleyicileri temel yineleyicileriyle ilişkilendiren kimlik şudur:

&\*( `reverse_iterator` ( *i* ) \*) = == &( *i* - 1 ).

Uygulamada, bu ters sırada `reverse_iterator` bir konum ötesinde öğe (sağda) iterator orijinal sırada atıfta olduğu öğeanlamına gelir. Yani bir yineleyici sırayla 6 öğesini ele aldıysa (2, 4, `reverse_iterator` 6, 8), ters sırada (8, 6, 4, 2) 4 öğesini ele alacaktır.

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

## <a name="reverse_iteratordifference_type"></a><a name="difference_type"></a>reverse_iterator::difference_type

Aynı kapsayıcıiçindeki elemanlara `reverse_iterator`atıfta bulunan iki s arasındaki farkı sağlayan bir tür.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type;
```

### <a name="remarks"></a>Açıklamalar

`reverse_iterator` Fark türü, yineleyici farkı türüyle aynıdır.

Tür, iterator özelliği typename `iterator_traits` \< **RandomIterator**> **::pointer**ile eş anlamlıdır.

### <a name="example"></a>Örnek

Bkz. [reverse_iterator::operatör nasıl](#op_at) beyan edilip `difference_type`kullanılacağına bir örnek için&#91;&#93;.

## <a name="reverse_iteratoriterator_type"></a><a name="iterator_type"></a>reverse_iterator:iterator_type

Bir `reverse_iterator`.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Iterator`ile eş anlamlıdır.

### <a name="example"></a>Örnek

Bkz. [reverse_iterator::nasıl](#base) bildirilir ve kullanılacağına `iterator_type`bir örnek için temel.

## <a name="reverse_iteratoroperator"></a><a name="op_star"></a>reverse_iterator::operatör\*

reverse_iterator adresledeğinin verdiği öğeyi döndürür.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

reverse_iterator tarafından ele verilen öğelerin değeri.

### <a name="remarks"></a>Açıklamalar

Operatör döner \* **(akım** - 1).

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

## <a name="reverse_iteratoroperator"></a><a name="op_add"></a>reverse_iterator::operatör+

Bir yineleyiciye bir ofset ekler `reverse_iterator` ve yeni ofset konumunda eklenen öğeyi ele döndürür.

```cpp
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*\
Ters yineleyiciye eklenecek ofset.

### <a name="return-value"></a>Dönüş Değeri

Ofset öğesi `reverse_iterator` ele alma.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca rasgele `reverse_iterator` erişim yinelemesi gereksinimlerini karşılarsa kullanılabilir.

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

## <a name="reverse_iteratoroperator"></a><a name="op_add_add"></a>reverse_iterator::operator++

reverse_iterator önceki öğeye göre artışlar.

```cpp
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk işleç preincremented `reverse_iterator` döndürür ve ikinci, postincrement işleci, artışlı `reverse_iterator`bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, yalnızca `reverse_iterator` çift yönlü bir yineleme nin gereksinimlerini karşılarsa kullanılabilir.

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

## <a name="reverse_iteratoroperator"></a><a name="op_add_eq"></a>reverse_iterator::operator+=

reverse_iterator belirli bir ofset ekler.

```cpp
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```

### <a name="parameters"></a>Parametreler

*Kapalı*\
Yinelemeyi artımlı ofset.

### <a name="return-value"></a>Dönüş Değeri

`reverse_iterator`Tarafından ele verilen elemana bir başvuru.

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

## <a name="reverse_iteratoroperator-"></a><a name="operator-"></a>reverse_iterator::operatör-

A'dan `reverse_iterator` bir ofset çıkarır `reverse_iterator` ve ofset konumundaki eleman adedidöndürür.

```cpp
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*\
Reverse_iterator çıkarılacak mahsup.

### <a name="return-value"></a>Dönüş Değeri

Ofset öğesi `reverse_iterator` ele alma.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca rasgele `reverse_iterator` erişim yinelemesi gereksinimlerini karşılarsa kullanılabilir.

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

## <a name="reverse_iteratoroperator--"></a><a name="operator--"></a>reverse_iterator::operatör--

reverse_iterator önceki öğeye göre erteler.

```cpp
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk işleç predecremented `reverse_iterator` döndürür ve ikinci, postdecrement işleci, kararnamenin `reverse_iterator`bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, yalnızca `reverse_iterator` çift yönlü bir yineleme nin gereksinimlerini karşılarsa kullanılabilir.

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

## <a name="reverse_iteratoroperator-"></a><a name="operator-_eq"></a>reverse_iterator::operator-=

Belirli bir ofset çıkarır. `reverse_iterator`

```cpp
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```

### <a name="parameters"></a>Parametreler

*Kapalı*\
Ofset `reverse_iterator`çıkarılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca rasgele `reverse_iterator` erişim yinelemesi gereksinimlerini karşılarsa kullanılabilir.

İşleç **geçerli** + *Kapalı'yı* değerlendirir ve ** \*bunu**döndürür.

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

## <a name="reverse_iteratoroperator-gt"></a><a name="op-arrow"></a>reverse_iterator::operatör-&gt;

Bir işaretçiyi ' tarafından `reverse_iterator`adreslenen öğeye döndürür.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

'nin adreslediği `reverse_iterator`öğenin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Operatör ** & \* \*bunu**döndürür.

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

## <a name="reverse_iteratoroperator"></a><a name="op_at"></a>reverse_iterator::operatör[]

Belirli sayıda pozisyon tarafından `reverse_iterator` ele alınan öğeden bir eleman mahsup başvurusu verir.

```cpp
reference operator[](difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Kapalı*\
`reverse_iterator` Adresten mahsup.

### <a name="return-value"></a>Dönüş Değeri

Öğe ofset için başvuru.

### <a name="remarks"></a>Açıklamalar

Operatör döndürür <strong>\*</strong>( + `Off` ** \*bu).**

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

## <a name="reverse_iteratorpointer"></a><a name="pointer"></a>reverse_iterator::pointer

Bir . tarafından adreslenen bir öğeiçin `reverse_iterator`işaretçi sağlayan bir tür

```cpp
typedef typename iterator_traits<RandomIterator>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, iterator özelliği typename `iterator_traits` \< *RandomIterator*> **::pointer**ile eş anlamlıdır.

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

## <a name="reverse_iteratorreference"></a><a name="reference"></a>reverse_iterator::başvuru

bir reverse_iterator tarafından adreslenen bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename iterator_traits<RandomIterator>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici özellik `iterator_traits` \< türü *randomiterator*> için eşanlamlıdır **::reference**.

### <a name="example"></a>Örnek

Bkz. [reverse_iterator::operatör&#91;&#93;](#op_at) veya [reverse_iterator::operator*](#op_star) nasıl `reference`bildirilir ve kullanılır.

## <a name="reverse_iteratorreverse_iterator"></a><a name="reverse_iterator"></a>reverse_iterator:reverse_iterator

Varsayılan `reverse_iterator` veya altta `reverse_iterator` yatan bir yineleyiciden bir oluşturma.

```cpp
reverse_iterator();
explicit reverse_iterator(RandomIterator right);

template <class Type>
reverse_iterator(const reverse_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
`reverse_iterator`Bir .

### <a name="return-value"></a>Dönüş Değeri

Varsayılan `reverse_iterator` veya `reverse_iterator` temel bir yineleyicinin uyarlanması.

### <a name="remarks"></a>Açıklamalar

Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( `reverse_iterator` ( *i* ) \*) = == &( *i* - 1 ).

Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Yani bir yineleyici sırayla 6 öğesini ele aldıysa (2, 4, `reverse_iterator` 6, 8), ters sırada (8, 6, 4, 2) 4 öğesini ele alacaktır.

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

[\<iterator>](../standard-library/iterator.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
