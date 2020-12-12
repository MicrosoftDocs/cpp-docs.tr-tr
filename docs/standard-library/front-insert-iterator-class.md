---
description: 'Hakkında daha fazla bilgi edinin: front_insert_iterator sınıfı'
title: front_insert_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- iterator/std::front_insert_iterator
- iterator/std::front_insert_iterator::container_type
- iterator/std::front_insert_iterator::reference
helpviewer_keywords:
- std::front_insert_iterator [C++]
- std::front_insert_iterator [C++], container_type
- std::front_insert_iterator [C++], reference
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
ms.openlocfilehash: 79690f51ce108357a6131c6ab811cee23c6c4529
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324284"
---
# <a name="front_insert_iterator-class"></a>front_insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin önüne yazar ve bu nedenle C++ dizi kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `front_insert_iterator`Sınıf kapsayıcının türü üzerinde şablonsaldır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class front_insert_iterator;
```

### <a name="parameters"></a>Parametreler

*Kapsayıcı*\
Kapsayıcı türü, tarafından hangi öğelerin eklenebileceği önüne `front_insert_iterator` .

## <a name="remarks"></a>Açıklamalar

Kapsayıcının itfa edilecek sabit sürede dizininin başına öğe eklemenin mümkün olduğu ön ekleme dizisinin gereksinimlerini karşılaması gerekir. [Deque Sınıfı](../standard-library/deque-class.md) ve [List sınıfı](../standard-library/list-class.md) tarafından tanımlanan C++ standart kitaplık sırası kapsayıcıları, gerekli `push_front` üye işlevini sağlar ve bu gereksinimleri karşılar. Buna karşılık, [vektör sınıfı](../standard-library/vector-class.md) tarafından tanımlanan dizi kapsayıcıları bu gereksinimleri karşılamaz ve ile kullanmak için uyarlayamaz `front_insert_iterator` . `front_insert_iterator`Her zaman kapsayıcısı ile birlikte başlatılmalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[front_insert_iterator](#front_insert_iterator)|Belirtilen kapsayıcı nesnesinin önünde öğeler ekleyebilen bir yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Ön ekleme yapılacak kapsayıcıyı temsil eden bir tür.|
|[başvurunun](#reference)|İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|\* `i`  =  `x` Ön ekleme için çıkış yineleyici ifadesini uygulamak üzere kullanılan başvuru başvurusu.|
|[işleç + +](#op_add_add)|Değerini, `front_insert_iterator` bir değerin depolanabileceği bir sonraki konuma arttırır.|
|[işleç =](#op_eq)|\* `i`  =  `x` Ön ekleme için çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<iterator>

**Ad alanı:** std

## <a name="front_insert_iteratorcontainer_type"></a><a name="container_type"></a> front_insert_iterator:: container_type

Ön ekleme yapılacak kapsayıcıyı temsil eden bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *kapsayıcısının* eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// front_insert_iterator_container_type.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L1;
   front_insert_iterator<list<int> >::container_type L2 = L1;
   front_inserter ( L2 ) = 20;
   front_inserter ( L2 ) = 10;
   front_inserter ( L2 ) = 40;

   list <int>::iterator vIter;
   cout << "The list L2 is: ( ";
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The list L2 is: ( 40 10 20 ).
*/
```

## <a name="front_insert_iteratorfront_insert_iterator"></a><a name="front_insert_iterator"></a> front_insert_iterator:: front_insert_iterator

Belirtilen kapsayıcı nesnesinin önünde öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
explicit front_insert_iterator(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
İçine `front_insert_iterator` öğe eklemek için olduğu kapsayıcı nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`front_insert_iterator`Parametresi için bir kapsayıcı nesnesi.

### <a name="example"></a>Örnek

```cpp
// front_insert_iterator_front_insert_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = -1 ; i < 9 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the member function to insert an element
   front_inserter ( L ) = 20;

   // Alternatively, one may use the template function
   front_insert_iterator< list < int> > Iter(L);
*Iter = 30;

   cout << "After the front insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The list L is:
( -2 0 2 4 6 8 10 12 14 16 ).
After the front insertions, the list L is:
( 30 20 -2 0 2 4 6 8 10 12 14 16 ).
*/
```

## <a name="front_insert_iteratoroperator"></a><a name="op_star"></a> front_insert_iterator:: işleci\*

, Kendisine ait olduğu öğeyi döndüren ekleme yineleyicisi ' ne başvurur.

```cpp
front_insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi, belirtilen öğenin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çıkış Yineleyici ifadesi **\* Iter** değerini uygulamak için kullanılır  =  . `Iter`Bir dizideki bir öğeyi ele alan bir yineleyici ise, **\* Iter**  =  **değeri** bu öğenin değerini değeri ile değiştirir ve dizideki toplam öğe sayısını değiştirmez.

### <a name="example"></a>Örnek

```cpp
// front_insert_iterator_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for ( i = -1 ; i < 9 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   front_insert_iterator< list < int> > Iter(L);
*Iter = 20;

   // Alternatively, you may use
   front_inserter ( L ) = 30;

   cout << "After the front insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The list L is:
( -2 0 2 4 6 8 10 12 14 16 ).
After the front insertions, the list L is:
( 30 20 -2 0 2 4 6 8 10 12 14 16 ).
*/
```

## <a name="front_insert_iteratoroperator"></a><a name="op_add_add"></a> front_insert_iterator:: operator + +

Değerini, `back_insert_iterator` bir değerin depolanabileceği bir sonraki konuma arttırır.

```cpp
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `front_insert_iterator` değerin depolanabileceği bir sonraki konumu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Hem Preincrementation hem de postincrementation işleçleri aynı sonucu döndürür.

### <a name="example"></a>Örnek

```cpp
// front_insert_iterator_op_incre.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L1;
   front_insert_iterator<list<int> > iter ( L1 );
*iter = 10;
   iter++;
*iter = 20;
   iter++;
*iter = 30;
   iter++;

   list <int>::iterator vIter;
   cout << "The list L1 is: ( ";
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The list L1 is: ( 30 20 10 ).
*/
```

## <a name="front_insert_iteratoroperator"></a><a name="op_eq"></a> front_insert_iterator:: operator =

Kapsayıcının önüne bir değer ekler (gönderir).

```cpp
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Kapsayıcıya atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının önüne yerleştirilen son öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci değerlendirilir `container.push_front( val)` ve ardından döndürür **`*this`** .

İkinci üye işleci değerlendirilir

`container->push_front((typename Container::value_type&&) val)`,

ardından döndürür **`*this`** .

### <a name="example"></a>Örnek

```cpp
// front_insert_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L1;
   front_insert_iterator<list<int> > iter ( L1 );
*iter = 10;
   iter++;
*iter = 20;
   iter++;
*iter = 30;
   iter++;

   list <int>::iterator vIter;
   cout << "The list L1 is: ( ";
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The list L1 is: ( 30 20 10 ).
*/
```

## <a name="front_insert_iteratorreference"></a><a name="reference"></a> front_insert_iterator:: Reference

İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Container::reference reference;
```

### <a name="example"></a>Örnek

```cpp
// front_insert_iterator_reference.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L;
   front_insert_iterator<list<int> > fiivIter( L );
*fiivIter = 10;
*fiivIter = 20;
*fiivIter = 30;

   list<int>::iterator LIter;
   cout << "The list L is: ( ";
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)
      cout << *LIter << " ";
   cout << ")." << endl;

   front_insert_iterator<list<int> >::reference
        RefFirst = *(L.begin ( ));
   cout << "The first element in the list L is: "
        << RefFirst << "." << endl;
}
/* Output:
The list L is: ( 30 20 10 ).
The first element in the list L is: 30.
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
