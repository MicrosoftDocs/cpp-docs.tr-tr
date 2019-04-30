---
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
ms.openlocfilehash: fb18c67b6e7949486c33e95c7daf6bc6868d0baa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404896"
---
# <a name="insertiterator-class"></a>insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin üzerine yazar ve bu nedenle C++ dizisi ve ilişkili kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `insert_iterator` Sınıfı uyarlanan kapsayıcının türü üzerinde şablonlaştırılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class insert_iterator;
```

### <a name="parameters"></a>Parametreler

*Kapsayıcı*<br/>
İçine öğeler tarafından ekleneceği bir kapsayıcı türü bir `insert_iterator`.

## <a name="remarks"></a>Açıklamalar

Kapsayıcı türünün `Container` değişken boyutlu kapsayıcı için gereksinimleri karşılaması gerekir ve üye işlevi ekleme iki bağımsız değişken parametre türü olduğu sahip `Container::iterator` ve `Container::value_type` ve bir tür döndüren `Container::iterator`. C++ Standart Kitaplığı dizisi ve sıralanmış ilişkilendirilebilir kapsayıcılar bu gereksinimleri karşılar ve ile kullanmak üzere uyarlanabilir `insert_iterator`s. İlişkilendirilebilir kapsayıcılar için, konum bağımsız değişkeni, ne kadar iyi olduğuna bağlı olarak performans düşmesi ve artması olasılığı bulunan bir gösterge olarak ele alınır. Bir `insert_iterator` her zaman kapsayıcısıyla birlikte başlatılmalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[insert_iterator](#insert_iterator)|Oluşturur bir `insert_iterator` , bir kapsayıcı içinde belirtilen konuma bir öğe ekler.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Genel ekleme yapılacak kapsayıcıyı temsil eden bir tür.|
|[Başvuru](#reference)|İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator *](#op_star)|Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma * `i`  =  `x` genel ekleme için.|
|[operator ++](#op_add_add)|Artışlarla `insert_iterator` sonraki konuma içine bir değer depolanabilir.|
|[operator=](#op_eq)|Çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci * `i`  =  `x` genel ekleme için.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<yineleyici >

**Namespace:** std

## <a name="container_type"></a>  insert_iterator::container_type

Genel ekleme yapılacak kapsayıcıyı temsil eden bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *kapsayıcı*.

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

## <a name="insert_iterator"></a>  insert_iterator::insert_iterator

Oluşturur bir `insert_iterator` , bir kapsayıcı içinde belirtilen konuma bir öğe ekler.

```cpp
insert_iterator(Container& _Cont, typename Container::iterator _It);
```

### <a name="parameters"></a>Parametreler

*_Cont*<br/>
Kapsayıcıya `insert_iterator` öğeleri eklemektir.

*_Bt*<br/>
Ekleme için konumu.

### <a name="remarks"></a>Açıklamalar

Tüm kapsayıcıları çağıran INSERT üye işlevi olan `insert_iterator`. İlişkili kapsayıcılar için yalnızca bir öneri pozisyon parametredir. İnserter işlevi değerleri eklemek için kullanışlı bir yol sağlar.

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

## <a name="op_star"></a>  insert_iterator::operator *

Adresleri öğedir döndüren ekleme yineleyici başvurusunu kaldırır.

```cpp
insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi, ele alınan öğenin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çıkış yineleyici ifadesini uygulamak için kullanılan  **\*Iter** = **değer**. Varsa `Iter` sonra bir dizisi içindeki bir öğeyi adresleyen bir yineleyici olduğunu  **\*Iter** = **değeri** toplam sayısı değişmez ve bu öğenin değeri ile değiştirir. Dizideki öğeleri.

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

## <a name="op_add_add"></a>  insert_iterator::operator++

Artışlarla `insert_iterator` sonraki konuma içine bir değer depolanabilir.

```cpp
insert_iterator<Container>& operator++();

insert_iterator<Container> operator++(int);
```

### <a name="parameters"></a>Parametreler

A `insert_iterator` içine bir değer depolanabilir sonraki konumu ele alan.

### <a name="remarks"></a>Açıklamalar

Preincrementation hem postincrementation işleçler aynı sonucu döndürür.

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

## <a name="op_eq"></a>  insert_iterator::operator=

Kapsayıcıya bir değer ekler ve yeni bir öğe için işaret edecek şekilde güncelleştirilmiş bir yineleyici döndürür.

```cpp
insert_iterator<Container>& operator=(
    typename Container::const_reference val,);

insert_iterator<Container>& operator=(
    typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Kapsayıcıya atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcıya eklenen öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci değerlendirir

`Iter = container->insert(Iter, val)`;

`++Iter;`

Ardından döndürür `*this`.

İkinci üye işleci değerlendirir

`Iter = container->insert(Iter, std::move(val));`

`++Iter;`

Ardından döndürür `*this`.

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

## <a name="reference"></a>  insert_iterator::reference

İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Açıklamalar

İlişkili kapsayıcı tarafından denetlenen dizinin bir öğesine bir başvuru türü açıklar.

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

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
