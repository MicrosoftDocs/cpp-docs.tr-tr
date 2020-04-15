---
title: back_insert_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- iterator/std::back_insert_iterator
- iterator/std::back_insert_iterator::container_type
- iterator/std::back_insert_iterator::reference
helpviewer_keywords:
- std::back_insert_iterator [C++]
- std::back_insert_iterator [C++], container_type
- std::back_insert_iterator [C++], reference
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
ms.openlocfilehash: c3bbb2ec8ce9a09dd17c4744a80913f95d85bd00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376903"
---
# <a name="back_insert_iterator-class"></a>back_insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin arka ucunun üzerine yazar ve bu nedenle C++ dizi kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. Sınıf, `back_insert_iterator` kapsayıcının türüne göre baştan çıkarıcıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class back_insert_iterator;
```

### <a name="parameters"></a>Parametreler

*Kapsayıcı*\
Bir `back_insert_iterator`.

## <a name="remarks"></a>Açıklamalar

Kapsayıcının itfa edilecek sabit sürede dizininin sonuna öğe eklemenin mümkün olduğu geri ekleme dizisinin gereksinimlerini karşılaması gerekir. C++ Standart Kitaplık sıra lı kapsayıcılar [deque Sınıfı](../standard-library/deque-class.md)tarafından `push_back` tanımlanan, liste [Sınıfı](../standard-library/list-class.md) ve vektör [Sınıfı](../standard-library/vector-class.md) gerekli üye işlevi sağlar ve bu gereksinimleri karşılar. Bu üç kap ve dizeleri her s ile `back_insert_iterator`kullanmak için adapte edilebilir. A `back_insert_iterator` her zaman konteyner ile baş harfe getirilmelidir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[back_insert_iterator](#back_insert_iterator)|Bir `back_insert_iterator` kapsayıcıdaki son öğeden sonra öğeleri ekleyen bir yapı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Için bir kapsayıcı sağlayan `back_insert_iterator`bir tür.|
|[Başvuru](#reference)|`back_insert_iterator`Için bir başvuru sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç*](#op_star)|Dereferencing işleci bir geri ekleme için \* `i`  =  `x` çıkış yineleyici ifadesini uygulamak için kullanılır.|
|[işleç++](#op_add_add)|Bir değerin `back_insert_iterator` depolanabileceği bir sonraki konuma artışlar.|
|[işleç=](#op_eq)|Atama işleci, bir geri ekleme \* `i`  =  `x` için çıktı yineleyici ifadesini uygulamak için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi** \<: iterator>

**Ad alanı:** std

## <a name="back_insert_iteratorback_insert_iterator"></a><a name="back_insert_iterator"></a>back_insert_iterator:back_insert_iterator

Bir `back_insert_iterator` kapsayıcıdaki son öğeden sonra öğeleri ekleyen bir yapı.

```cpp
explicit back_insert_iterator(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
`back_insert_iterator` Bir öğeyi ekecek kapsayıcı.

### <a name="return-value"></a>Dönüş Değeri

Parametre kapsayıcısı için A. `back_insert_iterator`

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

## <a name="back_insert_iteratorcontainer_type"></a><a name="container_type"></a>back_insert_iterator:container_type

Için bir kapsayıcı sağlayan `back_insert_iterator`bir tür.

```cpp
typedef Container
container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **Kapsayıcısı**ile eş anlamlıdır.

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

## <a name="back_insert_iteratoroperator"></a><a name="op_star"></a>back_insert_iterator::operatör\*

Çıkış yineleyici \* ifadesini uygulamak için kullanılan dereferencing işleci *i* = *x*.

```cpp
back_insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının arkasına yerleştirilen öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Çıktı yineleyici ifadesini =  ** \*** uygulamak için kullanılan Iter**değeri.** **Iter** bir dizideki öğeyi ele alan bir yineleyici ise, ** \*Iter** = **değeri** bu öğeyi değerle değiştirir ve dizideki toplam öğe sayısını değiştirmez.

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

## <a name="back_insert_iteratoroperator"></a><a name="op_add_add"></a>back_insert_iterator::operator++

Bir değerin `back_insert_iterator` depolanabileceği bir sonraki konuma artışlar.

```cpp
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `back_insert_iterator` değerin depolanabileceği bir sonraki konumu ele alan bir adres.

### <a name="remarks"></a>Açıklamalar

Hem preincrementation hem de postincrementation operatörleri aynı sonucu döndürer.

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

## <a name="back_insert_iteratoroperator"></a><a name="op_eq"></a>back_insert_iterator::operator=

Bir değeri bir kapsayıcının arka ucuna ekler veya iter.

```cpp
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Kapsayıcıya eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının arkasına eklenen son öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye `Container.push_back( val)`operatör,

sonra `*this`döner. İkinci üye operatör değerlendirir

`container->push_back((typename Container::value_type&&)val)`,

sonra `*this`döner.

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

## <a name="back_insert_iteratorreference"></a><a name="reference"></a>back_insert_iterator::referans

`back_insert_iterator`Için bir başvuru sağlayan bir tür.

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, ilişkili kapsayıcı tarafından denetlendirilen dizinin bir öğesine yapılan bir başvuruyu açıklar.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
