---
title: '&lt;Yineleyici&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- xutility/std::operator!=
- xutility/std::operator&gt;
- xutility/std::operator&gt;=
- xutility/std::operator&lt;
- xutility/std::operator&lt;=
- xutility/std::operator+
- xutility/std::operator-
- xutility/std::operator==
dev_langs:
- C++
ms.assetid: b7c664f0-49d4-4993-b5d1-9ac4859fdddc
helpviewer_keywords:
- std::operator!= (iterator)
- std::operator&gt; (iterator)
- std::operator&gt;= (iterator)
- std::operator&lt; (iterator)
- std::operator&lt;= (iterator), std::operator== (iterator)
ms.openlocfilehash: 411fcf8969ba13c4f50360c3db151f0801fd5a28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltiteratorgt-operators"></a>&lt;Yineleyici&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator +](#op_add)|
|[operator-](#operator-)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden farklı olup olmadığını sınar.

```cpp
template <class RandomIterator>
bool operator!=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator!=(const istream_iterator<Type, CharType, Traits, Distance>& left, const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator!=(const istreambuf_iterator<CharType, Traits>& left, const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yineleyici**.

`right` Türünde bir nesne **yineleyici**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yineleyici nesneleri eşit; değilse **false** yineleyici nesneleri eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Bir kapsayıcıda aynı öğeleri adresi bir yineleyici nesne diğerine eşittir. Bir kapsayıcıda farklı öğeler için iki yineleyiciler noktası ise, ardından bunlar eşit değildir.

### <a name="example"></a>Örnek

```cpp
// iterator_op_ne.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 9 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;
}
```

```Output
The vector vec is: ( 1 2 3 4 5 6 7 8 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 8.
The iterators are equal.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 7.
The iterators are not equal.
```

## <a name="op_eq_eq"></a>  operator ==

İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit olup olmadığını sınar.

```cpp
template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator==(
    const istream_iterator<Type, CharType, Traits, Distance>& left,
    const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator==(
    const istreambuf_iterator<CharType, Traits>& left,
    const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türü yineleyici bir nesne.

`right` Türü yineleyici bir nesne.

### <a name="return-value"></a>Dönüş Değeri

`true` Yineleyici nesneleri eşitse; `false` yineleyici nesneleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

Bir kapsayıcıda aynı öğeleri adresi bir yineleyici nesne diğerine eşittir. Bir kapsayıcıda farklı öğeler için iki yineleyiciler noktası ise, ardından bunlar eşit değildir.

İlk iki şablon işleçleri yalnızca her iki true döndürecek `left` ve `right` aynı yineleyici depolar. Üçüncü şablon işleci yalnızca her iki, true döndürür `left` ve `right` aynı akış işaretçisini depolayın. Dördüncü şablon işleci döndürür ` left.equal ( right)`.

### <a name="example"></a>Örnek

```cpp
// iterator_op_eq.cpp
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
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterators are equal.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterators are not equal.
```

## <a name="op_lt"></a>  işleci&lt;

İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden küçük olup olmadığını sınar.

```cpp
template <class RandomIterator>
bool operator<(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türünde bir nesne **yineleyici**.

`right` Türünde bir nesne **yineleyici**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yineleyici ifadesinin sol tarafındaki ifade; sağ tarafındaki yineleyici küçükse **false** sağdaki yineleyici eşit veya daha büyük olduğunda.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı bir yineleyici nesnesi tarafından ele öğeden önceki oluşuyor öğenin adresleri değişirse bir yineleyici nesne başka bir küçüktür. Diğer yineleyici nesne olarak aynı öğesi veya diğer yineleyici nesne tarafından ele öğeden kapsayıcısında daha sonra oluşan bir öğe adresleri değişirse bir yineleyici nesnesi diğerinden daha az değil.

### <a name="example"></a>Örnek

```cpp
// iterator_op_lt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1& rVPOS2 initially point to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1& rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is not less than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
```

## <a name="op_lt_eq"></a>  işleci&lt;=

İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan küçük olup olmadığını sınar.

```cpp
template <class RandomIterator>
bool operator<=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türü yineleyici bir nesne.

`right` Türü yineleyici bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yineleyici ifadesinin sol tarafındaki ifade; sağ tarafındaki yineleyici eşit veya daha az ise **false** sağdaki yineleyici büyükse.

### <a name="remarks"></a>Açıklamalar

Bir yineleyici diğerine eşit veya aynı öğeye adresleri ya da daha önce kapsayıcı öğeden oluşan bir öğe bir yineleyici nesnesi tarafından ele nesnesidir. Daha sonra diğer yineleyici nesne tarafından ele öğeden kapsayıcı ortaya çıkan öğenin adresleri değişirse bir yineleyici nesne diğerinden daha büyüktür.

### <a name="example"></a>Örnek

```cpp
// iterator_op_le.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ) + 1,
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the second element
 in the reversed sequence: 8.
The iterator rVPOS2 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is greater than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
```

## <a name="op_gt"></a>  işleci&gt;

İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden büyük olup olmadığını sınar.

```cpp
template <class RandomIterator>
bool operator>(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türü yineleyici bir nesne.

`right` Türü yineleyici bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yineleyici ifadesinin sol tarafındaki ifade; sağ tarafındaki yineleyici değerden fazlaysa: **false** sağdaki yineleyici küçük veya buna eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Daha sonra diğer yineleyici nesne tarafından ele öğeden kapsayıcı ortaya çıkan öğenin adresleri değişirse bir yineleyici nesne diğerinden daha büyüktür. Bir yineleyici nesnesi aynı öğesi diğer yineleyici nesne olarak veya diğer yineleyici nesne tarafından ele öğeden önceki kapsayıcısında oluşan bir öğe adresleri değişirse diğerinden daha büyük değil.

### <a name="example"></a>Örnek

```cpp
// iterator_op_gt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is greater than the iterator rVPOS2.
```

## <a name="op_gt_eq"></a>  işleci&gt;=

İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan büyük olup olmadığını sınar.

```cpp
template <class RandomIterator>
bool operator>=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parametreler

`left` Türü yineleyici bir nesne.

`right` Türü yineleyici bir nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** yineleyici ifadesinin sol tarafındaki ifade; sağ tarafındaki yineleyici eşit veya daha büyük ise **false** sağdaki yineleyici daha az ise.

### <a name="remarks"></a>Açıklamalar

Aynı kapsayıcı diğer yineleyici nesne tarafından ele öğeden daha sonra oluşan bir öğesi veya adresleri değişirse bir yineleyici büyük veya ona eşit başka bir nesnedir. Kapsayıcı bir yineleyici nesnesi tarafından ele öğeden önceki oluşuyor öğenin adresleri değişirse bir yineleyici nesne başka bir küçüktür.

### <a name="example"></a>Örnek

```cpp
// iterator_op_ge.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( ) + 1;

   cout << "The iterator rVPOS1 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS2 initially points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is greater than or equal to the iterator rVPOS2.
```

## <a name="op_add"></a>  operator +

Yineleyici için uzaklık ekler ve döndürür bir `move_iterator` veya `reverse_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.

```cpp
template <class RandomIterator, class Diff>
move_iterator<RandomIterator>
operator+(
    Diff _Off,
    const move_iterator<RandomIterator>& right);

template <class RandomIterator>
reverse_iterator<RandomIterator>
operator+(
    Diff _Off,
    const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parametreler

`_Off` Const move_iterator const reverse_iterator kaydırılacağı için mi konum sayısı.

`right` Kaydırılacağı yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Toplamını döndürür `right`  +  `_Off`.

### <a name="example"></a>Örnek

```cpp
// iterator_op_insert.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   vector<int>::difference_type diff = 4;
   rVPOS1 = diff +rVPOS1;

   cout << "The iterator rVPOS1 now points to the fifth "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 now points to the fifth element
 in the reversed sequence: 2.
```

## <a name="operator-"></a>  operator-

Bir yineleyiciyi bir başkasından çıkarır ve farkı döndürür.

```cpp
template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Yineleyici.

`right` Yineleyici.

### <a name="return-value"></a>Dönüş Değeri

İki yineleyiciler arasındaki fark `.`

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci döndürür `left.base() - right.base()`.

İkinci şablon işleci döndürür `right.current - left.current`.

`Tdiff` döndürülen ifade türü tarafından belirlenir. Aksi takdirde, değer `RandomIterator1::difference_type`.

### <a name="example"></a>Örnek

```cpp
// iterator_op_sub.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
          rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
        << "the first element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   for (i = 1; i < 5; ++i)
   {
      rVPOS2++;
   }
   cout << "The iterator rVPOS2 now points to the fifth "
        << "element\n in the reversed sequence: "
        << *rVPOS2 << "." << endl;

   vector<int>::difference_type diff = rVPOS2 - rVPOS1;
   cout << "The difference: rVPOS2 - rVPOS1= "
        << diff << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS2 now points to the fifth element
 in the reversed sequence: 2.
The difference: rVPOS2 - rVPOS1= 4.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
