---
description: 'Hakkında daha fazla bilgi edinin: reverse_iterator sınıfı'
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
ms.openlocfilehash: 0aa8b03188d8b5a6e2ce004579b7b3cc2fb9b254
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148973"
---
# <a name="reverse_iterator-class"></a>reverse_iterator Sınıfı

Sınıf şablonu, yalnızca ters erişimli bir rastgele erişim veya çift yönlü Yineleyici gibi davranan bir ters Yineleyici nesnesini açıklayan bir yineleyici bağdaştırıcısı. Bir aralığın geriye doğru geçişini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class RandomIterator>
class reverse_iterator
```

### <a name="parameters"></a>Parametreler

RandomIterator, geriye doğru çalışacak şekilde uyarlanan yineleyiciyi temsil eden tür.

## <a name="remarks"></a>Açıklamalar

Mevcut C++ standart kitaplığı kapsayıcıları Ayrıca, ve türlerini tanımlar ve `reverse_iterator` `const_reverse_iterator` Bu işlevleri `rbegin` ve `rend` ters yineleyiciler döndüren üye işlevlerini de tanımlar. Bu yineleyicilerde üzerine yazma semantikleri vardır. `reverse_iterator`Bağdaştırıcı, ekleme semantiğini sağladığından bu işlevselliği tamamlar ve akışlar ile de kullanılabilir.

`reverse_iterator`Çift yönlü bir yineleyici gerektiren,,,, `operator+=` `operator+` `operator-=` `operator-` veya `operator[]` Yalnızca rastgele erişim yineleyiciler ile kullanılabilen üye işlevlerinden herhangi birini çağırmamalıdır.

Yineleyicinin aralığı [*First*, *Last*), burada sol taraftaki köşeli ayraç *ilk* ve ayracın dahil olduğu, *en son* kendisi hariç olan öğelerin dahil edildiği anlamına gelir. Aynı öğeler ters çevrilme dizisine [ **Rev**  -  *First*, **Rev**  -  *Last*) dahil edilir, böylece, *son* bir dizideki son bir öğe ise, ardından ters sırada **ilk açılan** öğe  -   \* (*son* -1). Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( **reverse_iterator** ( *i* )) = = &\* ( *i* -1).

Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Bu nedenle, bir Yineleyici dizideki 6 öğe (2, 4, 6, 8) ile ilgilenirse, `reverse_iterator` ters dizideki öğe 4 ' ü (8, 6, 4, 2) ele alınacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[reverse_iterator](#reverse_iterator)|`reverse_iterator`Temel bir yineleyiciden varsayılan veya bir oluşturur `reverse_iterator` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|`reverse_iterator`Aynı kapsayıcı içindeki öğelere başvuran iki s arasındaki farkı sağlayan bir tür.|
|[iterator_type](#iterator_type)|İçin temel yineleyiciyi sağlayan bir tür `reverse_iterator` .|
|[pointer](#pointer)|Tarafından bahsedilen bir öğeye işaretçi sağlayan bir tür `reverse_iterator` .|
|[başvurunun](#reference)|Tarafından bahsedilen bir öğeye başvuru sağlayan bir tür `reverse_iterator` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Temel yineleyiciyi öğesinden kurtarır `reverse_iterator` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator_star](#op_star)|Adreslerin bulunduğu öğeyi döndürür `reverse_iterator` .|
|[işleç +](#op_add)|Bir yineleyici için bir konum ekler ve yeni bir konum konumundaki `reverse_iterator` Eklenen öğeyi yeni adreslemeyi döndürür.|
|[işleç + +](#op_add_add)|Öğesini bir `reverse_iterator` sonraki öğeye artırır.|
|[işleç + =](#op_add_eq)|İçinden belirtilen bir sapmayı ekler `reverse_iterator` .|
|[işlecinde](#operator-)|Bir sapmayı bir uzaklığa çıkartır `reverse_iterator` ve `reverse_iterator` öğe, konum konumunu bir ele döndürür.|
|[işleç--](#operator--)|`reverse_iterator`Önceki öğeye kadar azaltır.|
|[işleç-=](#operator-_eq)|Belirtilen bir sapmayı kaynağından çıkartır `reverse_iterator` .|
|[operator->](#op-arrow)|Tarafından belirtilen öğeye bir işaretçi döndürür `reverse_iterator` .|
|[işleç&#91;&#93;](#op_at)|Belirtilen sayıda konum tarafından bahsedilen öğeden bir öğe kaydırmasına yönelik bir başvuru döndürür `reverse_iterator` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="reverse_iteratorbase"></a><a name="base"></a> reverse_iterator:: Base

Temel yineleyiciyi öğesinden kurtarır `reverse_iterator` .

```cpp
RandomIterator base() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan Yineleyici `reverse_iterator` .

### <a name="remarks"></a>Açıklamalar

Tüm ters yineleyicileri temel yineleyiciler ile ilişkilendiren kimlik:

&\*( `reverse_iterator` ( *ı* )) = = &\* ( *i* -1).

Uygulamada, bu, tersine çevrilmiş dizide, `reverse_iterator` yineleyicinin orijinal sırada başvurduğu öğenin bir konumdan bir konuma (öğesinin sağına) başvuracağı anlamına gelir. Bu nedenle, bir Yineleyici dizideki 6 öğe (2, 4, 6, 8) ile ilgilenirse, `reverse_iterator` ters dizideki öğe 4 ' ü (8, 6, 4, 2) ele alınacaktır.

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

## <a name="reverse_iteratordifference_type"></a><a name="difference_type"></a> reverse_iterator::d ifference_type

`reverse_iterator`Aynı kapsayıcı içindeki öğelere başvuran iki s arasındaki farkı sağlayan bir tür.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type;
```

### <a name="remarks"></a>Açıklamalar

`reverse_iterator`Fark türü yineleyici fark türüyle aynıdır.

Tür, yineleyici nitelik TypeName `iterator_traits` \< **RandomIterator**> **::p oınter** için bir eş anlamlı.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [reverse_iterator:: operator&#91;&#93;](#op_at) `difference_type` .

## <a name="reverse_iteratoriterator_type"></a><a name="iterator_type"></a> reverse_iterator:: iterator_type

İçin temel yineleyiciyi sağlayan bir tür `reverse_iterator` .

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Iterator` .

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [reverse_iterator:: Base](#base) `iterator_type` .

## <a name="reverse_iteratoroperator"></a><a name="op_star"></a> reverse_iterator:: işleci\*

Bir reverse_iterator adresinin bulunduğu öğeyi döndürür.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Reverse_iterator tarafından belirtilen öğelerin değeri.

### <a name="remarks"></a>Açıklamalar

İşleç döndürür \* ( **geçerli** -1).

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

## <a name="reverse_iteratoroperator"></a><a name="op_add"></a> reverse_iterator:: operator +

Bir yineleyici için bir konum ekler ve yeni bir konum konumundaki `reverse_iterator` Eklenen öğeyi yeni adreslemeyi döndürür.

```cpp
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Dışına*\
Tersine yineleyiciye eklenecek olan Aralık.

### <a name="return-value"></a>Dönüş Değeri

Bir `reverse_iterator` adres boşluğu öğesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca, `reverse_iterator` bir rastgele erişim Yineleyici için gereksinimleri karşılıyorsa kullanılabilir.

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

## <a name="reverse_iteratoroperator"></a><a name="op_add_add"></a> reverse_iterator:: operator + +

Önceki öğeye reverse_iterator artırır.

```cpp
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, ön arttırılan `reverse_iterator` ve ikincisi, postıncrement işleci, artın bir kopyasını döndürür `reverse_iterator` .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca `reverse_iterator` çift yönlü bir yineleyici için gereksinimleri karşılıyorsa kullanılabilir.

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

## <a name="reverse_iteratoroperator"></a><a name="op_add_eq"></a> reverse_iterator:: operator + =

Reverse_iterator belirtilen bir sapmayı ekler.

```cpp
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```

### <a name="parameters"></a>Parametreler

*Dışına*\
Yineleyicinin artılacağı fark.

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğesine bir başvuru `reverse_iterator` .

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

## <a name="reverse_iteratoroperator-"></a><a name="operator-"></a> reverse_iterator:: operator-

Bir sapmayı bir uzaklığa çıkartır `reverse_iterator` ve `reverse_iterator` öğe, konum konumunu bir ele döndürür.

```cpp
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Dışına*\
Reverse_iterator çıkarılacak olan Aralık.

### <a name="return-value"></a>Dönüş Değeri

Bir `reverse_iterator` adres boşluğu öğesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca, `reverse_iterator` bir rastgele erişim Yineleyici için gereksinimleri karşılıyorsa kullanılabilir.

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

## <a name="reverse_iteratoroperator--"></a><a name="operator--"></a> reverse_iterator:: operator--

Reverse_iterator önceki öğeye göre azaltır.

```cpp
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, predecremented döndürür `reverse_iterator` ve ikinci olarak, postazaltma işleci, azaltma işlevinin bir kopyasını döndürür `reverse_iterator` .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca `reverse_iterator` çift yönlü bir yineleyici için gereksinimleri karşılıyorsa kullanılabilir.

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

## <a name="reverse_iteratoroperator-"></a><a name="operator-_eq"></a> reverse_iterator:: operator-=

Belirtilen bir sapmayı kaynağından çıkartır `reverse_iterator` .

```cpp
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```

### <a name="parameters"></a>Parametreler

*Dışına*\
Öğesinden çıkarılacak olan Aralık `reverse_iterator` .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca, `reverse_iterator` bir rastgele erişim Yineleyici için gereksinimleri karşılıyorsa kullanılabilir.

İşleç **geçerli**  +  *kapatmayı* değerlendirir ve **\* bunu** döndürür.

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

## <a name="reverse_iteratoroperator-gt"></a><a name="op-arrow"></a> reverse_iterator:: operator-&gt;

Tarafından belirtilen öğeye bir işaretçi döndürür `reverse_iterator` .

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından bahsedilen öğe için bir işaretçi `reverse_iterator` .

### <a name="remarks"></a>Açıklamalar

İşleci **& \* \* bunu** döndürür.

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

## <a name="reverse_iteratoroperator"></a><a name="op_at"></a> reverse_iterator:: operator []

Belirtilen sayıda konum tarafından bahsedilen öğeden bir öğe kaydırmasına yönelik bir başvuru döndürür `reverse_iterator` .

```cpp
reference operator[](difference_type Off) const;
```

### <a name="parameters"></a>Parametreler

*Dışına*\
Adresten gelen fark `reverse_iterator` .

### <a name="return-value"></a>Dönüş Değeri

Öğe kaydırmasına başvuru.

### <a name="remarks"></a>Açıklamalar

İşleci <strong>\*</strong> ( **\* this**  +  `Off` ) döndürür.

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

## <a name="reverse_iteratorpointer"></a><a name="pointer"></a> reverse_iterator::p oınter

Tarafından bahsedilen bir öğeye işaretçi sağlayan bir tür `reverse_iterator` .

```cpp
typedef typename iterator_traits<RandomIterator>::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik TypeName `iterator_traits` \< *RandomIterator*> **::p oınter** için bir eş anlamlı.

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

## <a name="reverse_iteratorreference"></a><a name="reference"></a> reverse_iterator:: Reference

Bir reverse_iterator tarafından belirtilen öğeye başvuru sağlayan bir tür.

```cpp
typedef typename iterator_traits<RandomIterator>::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik TypeName `iterator_traits` \< *RandomIterator*> **:: Reference** için bir eş anlamlı.

### <a name="example"></a>Örnek

Bildirme ve kullanma örnekleri için bkz. [reverse_iterator:: operator&#91;&#93;](#op_at) veya [reverse_iterator:: operator *](#op_star) `reference` .

## <a name="reverse_iteratorreverse_iterator"></a><a name="reverse_iterator"></a> reverse_iterator:: reverse_iterator

`reverse_iterator`Temel bir yineleyiciden varsayılan veya bir oluşturur `reverse_iterator` .

```cpp
reverse_iterator();
explicit reverse_iterator(RandomIterator right);

template <class Type>
reverse_iterator(const reverse_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
' A uyarlanabilen Yineleyici `reverse_iterator` .

### <a name="return-value"></a>Dönüş Değeri

Temel bir `reverse_iterator` yineleyiciden bir varsayılan veya bir `reverse_iterator` uyum.

### <a name="remarks"></a>Açıklamalar

Tüm ters yineleyicilerin kendi temel yineleyicileriyle ilişkili kimliği aşağıdaki gibidir:

&\*( `reverse_iterator` ( *ı* )) = = &\* ( *i* -1).

Uygulamada, bunun anlamı ters dizideki reverse_iterator öğesinin, yineleyicinin özgün dizinde başvurduğu öğenin bir ötesindeki (sağındaki) konuma başvuracağıdır. Bu nedenle, bir Yineleyici dizideki 6 öğe (2, 4, 6, 8) ile ilgilenirse, `reverse_iterator` ters dizideki öğe 4 ' ü (8, 6, 4, 2) ele alınacaktır.

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
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
