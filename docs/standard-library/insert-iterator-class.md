---
description: 'Hakkında daha fazla bilgi edinin: insert_iterator sınıfı'
title: insert_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- iterator/std::insert_iterator
- iterator/std::insert_iterator::container_type
- iterator/std::insert_iterator::reference
helpviewer_keywords:
- std::insert_iterator [C++]
- std::insert_iterator [C++], container_type
- std::insert_iterator [C++], reference
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
ms.openlocfilehash: d9089e0ab592ed6c8289570cc422aa6183444d55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231582"
---
# <a name="insert_iterator-class"></a>insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin üzerine yazar ve bu nedenle C++ dizisi ve ilişkili kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `insert_iterator`Sınıfı, uyarlanmakta olan kapsayıcının türü üzerinde şablonlanmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class insert_iterator;
```

### <a name="parameters"></a>Parametreler

*Kapsayıcı*\
Öğelerinin içine ekleneceği kapsayıcının türü `insert_iterator` .

## <a name="remarks"></a>Açıklamalar

Türünün kapsayıcısı, `Container` değişken boyutlu bir kapsayıcı için gereksinimleri karşılamalıdır ve parametrelerin tür olduğu `Container::iterator` `Container::value_type` ve bir tür döndüren iki bağımsız değişkenli bir INSERT üye işlevine sahip olmalıdır `Container::iterator` . C++ standart kitaplık sırası ve sıralanmış ilişkilendirilebilir kapsayıcılar bu gereksinimleri karşılar ve ' de kullanılmak üzere uyarlanmıştır `insert_iterator` . İlişkilendirilebilir kapsayıcılar için, konum bağımsız değişkeni, ne kadar iyi olduğuna bağlı olarak performans düşmesi ve artması olasılığı bulunan bir gösterge olarak ele alınır. `insert_iterator`Her zaman kapsayıcında başlatılmış olmalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[insert_iterator](#insert_iterator)|Bir `insert_iterator` kapsayıcıda belirtilen konuma bir öğe ekleyen bir oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Genel ekleme yapılacak kapsayıcıyı temsil eden bir tür.|
|[başvurunun](#reference)|İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|`i`  =  Genel bir ekleme için çıkış yineleyici ifadesini uygulamak için kullanılan işleç başvurusu `x` .|
|[işleç + +](#op_add_add)|Değerini, `insert_iterator` bir değerin depolanabileceği bir sonraki konuma arttırır.|
|[işleç =](#op_eq)|`i`  =  Genel ekleme için çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci `x` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<iterator>

**Ad alanı:** std

## <a name="insert_iteratorcontainer_type"></a><a name="container_type"></a> insert_iterator:: container_type

Genel ekleme yapılacak kapsayıcıyı temsil eden bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *kapsayıcısının* eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// insert_iterator_container_type.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L1;
   insert_iterator<list<int> >::container_type L2 = L1;
   inserter ( L2, L2.end ( ) ) = 20;
   inserter ( L2, L2.end ( ) ) = 10;
   inserter ( L2, L2.begin ( ) ) = 40;

   list <int>::iterator vIter;
   cout << "The list L2 is: ( ";
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The list L2 is: ( 40 20 10 ).
*/
```

## <a name="insert_iteratorinsert_iterator"></a><a name="insert_iterator"></a> insert_iterator:: insert_iterator

Bir `insert_iterator` kapsayıcıda belirtilen konuma bir öğe ekleyen bir oluşturur.

```cpp
insert_iterator(Container& _Cont, typename Container::iterator _It);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
İçine `insert_iterator` öğe eklemek için olduğu kapsayıcı.

*_It*\
Ekleme konumu.

### <a name="remarks"></a>Açıklamalar

Tüm kapsayıcılar, tarafından çağrılan INSERT member işlevine sahiptir `insert_iterator` . İlişkilendirilebilir kapsayıcılar için position parametresi yalnızca bir öneridir. Inserter işlevi, değerlere eklemek için uygun bir yol sağlar.

### <a name="example"></a>Örnek

```cpp
// insert_iterator_insert_iterator.cpp
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
   for (i = 1 ; i < 4 ; ++i )
   {
      L.push_back ( 10 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the member function to insert an element
   inserter ( L, L.begin ( ) ) = 2;

   // Alternatively, you may use the template version
   insert_iterator< list < int> > Iter(L, L.end ( ) );
*Iter = 300;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The list L is:
( 10 20 30 ).
After the insertions, the list L is:
( 2 10 20 30 300 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_star"></a> insert_iterator:: operator *

Ekleme yineleyicisinin, öğeyi döndüren adresler olduğunu ortadan kaldırır.

```cpp
insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi, belirtilen öğenin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çıkış Yineleyici ifadesi **\* Iter** değerini uygulamak için kullanılır  =  . `Iter`Bir dizideki bir öğeyi ele alan bir yineleyici ise, **\* Iter**  =  **değeri** bu öğenin değerini değeri ile değiştirir ve dizideki toplam öğe sayısını değiştirmez.

### <a name="example"></a>Örnek

```cpp
// insert_iterator_op_deref.cpp
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
   for (i = 0 ; i < 4 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The original list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   insert_iterator< list < int> > Iter(L, L.begin ( ) );
*Iter = 10;
*Iter = 20;
*Iter = 30;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The original list L is:
( 0 2 4 6 ).
After the insertions, the list L is:
( 10 20 30 0 2 4 6 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_add_add"></a> insert_iterator:: operator + +

Değerini, `insert_iterator` bir değerin depolanabileceği bir sonraki konuma arttırır.

```cpp
insert_iterator<Container>& operator++();

insert_iterator<Container> operator++(int);
```

### <a name="parameters"></a>Parametreler

Bir `insert_iterator` değerin depolanabileceği bir sonraki konumu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Hem Preincrementation hem de postincrementation işleçleri aynı sonucu döndürür.

### <a name="example"></a>Örnek

```cpp
// insert_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 5 ; ++i )
   {
      vec.push_back (  i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is:\n ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   insert_iterator<vector<int> > ii ( vec, vec.begin ( ) );
*ii = 30;
   ii++;
*ii = 40;
   ii++;
*ii = 50;

   cout << "After the insertions, the vector vec becomes:\n ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The vector vec is:
( 1 2 3 4 ).
After the insertions, the vector vec becomes:
( 30 40 50 1 2 3 4 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_eq"></a> insert_iterator:: operator =

Kapsayıcıya bir değer ekler ve yeni öğeye işaret etmek için güncelleştirilmiş yineleyici döndürür.

```cpp
insert_iterator<Container>& operator=(
    typename Container::const_reference val,);

insert_iterator<Container>& operator=(
    typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Kapsayıcıya atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcıya yerleştirilen öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci değerlendirilir

`Iter = container->insert(Iter, val)`;

`++Iter;`

ardından döndürür **`*this`** .

İkinci üye işleci değerlendirilir

`Iter = container->insert(Iter, std::move(val));`

`++Iter;`

ardından döndürür **`*this`** .

### <a name="example"></a>Örnek

```cpp
// insert_iterator_op_assign.cpp
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
   for (i = 0 ; i < 4 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The original list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   insert_iterator< list < int> > Iter(L, L.begin ( ) );
*Iter = 10;
*Iter = 20;
*Iter = 30;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The original list L is:
( 0 2 4 6 ).
After the insertions, the list L is:
( 10 20 30 0 2 4 6 ).
*/
```

## <a name="insert_iteratorreference"></a><a name="reference"></a> insert_iterator:: Reference

İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, ilişkili kapsayıcı tarafından denetlenen sıranın bir öğesine başvuruyu açıklar.

### <a name="example"></a>Örnek

```cpp
// insert_iterator_container_reference.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L;
   insert_iterator<list<int> > iivIter( L , L.begin ( ) );
*iivIter = 10;
*iivIter = 20;
*iivIter = 30;

   list<int>::iterator LIter;
   cout << "The list L is: ( ";
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++ )
      cout << *LIter << " ";
   cout << ")." << endl;

   insert_iterator<list<int> >::reference
        RefFirst = *(L.begin ( ));
   cout << "The first element in the list L is: "
        << RefFirst << "." << endl;
}
/* Output:
The list L is: ( 10 20 30 ).
The first element in the list L is: 10.
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
