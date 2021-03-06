---
description: 'Hakkında daha fazla bilgi edinin: back_insert_iterator sınıfı'
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
ms.openlocfilehash: e8c188da7201ccb78866981ffb64e168d1a8fc32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132776"
---
# <a name="back_insert_iterator-class"></a>back_insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin arka ucunun üzerine yazar ve bu nedenle C++ dizi kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `back_insert_iterator`Sınıf kapsayıcının türü üzerinde şablonsaldır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class back_insert_iterator;
```

### <a name="parameters"></a>Parametreler

*Kapsayıcı*\
Kapsayıcı türü, öğesinin geri ekleneceği öğelerin bir `back_insert_iterator` .

## <a name="remarks"></a>Açıklamalar

Kapsayıcının itfa edilecek sabit sürede dizininin sonuna öğe eklemenin mümkün olduğu geri ekleme dizisinin gereksinimlerini karşılaması gerekir. [Deque Sınıfı](../standard-library/deque-class.md), [List sınıfı](../standard-library/list-class.md) ve [Vector sınıfı](../standard-library/vector-class.md) tarafından tanımlanan C++ standart kitaplık sırası kapsayıcıları, gerekli `push_back` üye işlevini sağlar ve bu gereksinimleri karşılar. Bu üç kapsayıcı ve dizelerin her biri, s ile kullanılmak üzere uyarlanmıştır `back_insert_iterator` . `back_insert_iterator`Her zaman kapsayıcısı ile birlikte başlatılmalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[back_insert_iterator](#back_insert_iterator)|Bir `back_insert_iterator` kapsayıcıdaki son öğeden sonra öğeleri ekleyen bir oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|İçin kapsayıcı sağlayan bir tür `back_insert_iterator` .|
|[başvurunun](#reference)|İçin başvuru sağlayan bir tür `back_insert_iterator` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|\* `i`  =  `x` Bir geri ekleme için çıkış yineleyici ifadesini uygulamak için kullanılan işleç başvurusu.|
|[işleç + +](#op_add_add)|Değerini, `back_insert_iterator` bir değerin depolanabileceği bir sonraki konuma arttırır.|
|[işleç =](#op_eq)|\* `i`  =  `x` Bir geri ekleme için çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<iterator>

**Ad alanı:** std

## <a name="back_insert_iteratorback_insert_iterator"></a><a name="back_insert_iterator"></a> back_insert_iterator:: back_insert_iterator

Bir `back_insert_iterator` kapsayıcıdaki son öğeden sonra öğeleri ekleyen bir oluşturur.

```cpp
explicit back_insert_iterator(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
`back_insert_iterator`Öğesinin içine bir öğe ekleneceği kapsayıcı.

### <a name="return-value"></a>Dönüş Değeri

`back_insert_iterator`Parametre kapsayıcısı için bir.

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

## <a name="back_insert_iteratorcontainer_type"></a><a name="container_type"></a> back_insert_iterator:: container_type

İçin kapsayıcı sağlayan bir tür `back_insert_iterator` .

```cpp
typedef Container
container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **kapsayıcısının** eşanlamlısıdır.

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

## <a name="back_insert_iteratoroperator"></a><a name="op_star"></a> back_insert_iterator:: işleci\*

Çıkış Yineleyici ifadesi \* *ı*  =  *x*'i uygulamak için kullanılan işleç başvurusu.

```cpp
back_insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının arkasına yerleştirilen öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

Çıkış Yineleyici ifadesi **\* Iter** değerini uygulamak için kullanılır  =  . **İter** , bir dizideki bir öğeyi ele alan bir yineleyici ise, **\* iter**  =  **değeri** bu öğenin değerini değeri ile değiştirir ve dizideki toplam öğe sayısını değiştirmez.

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

## <a name="back_insert_iteratoroperator"></a><a name="op_add_add"></a> back_insert_iterator:: operator + +

Değerini, `back_insert_iterator` bir değerin depolanabileceği bir sonraki konuma arttırır.

```cpp
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `back_insert_iterator` değerin depolanabileceği bir sonraki konumu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Hem Preincrementation hem de postincrementation işleçleri aynı sonucu döndürür.

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

## <a name="back_insert_iteratoroperator"></a><a name="op_eq"></a> back_insert_iterator:: operator =

Bir kapsayıcının arka ucuna bir değer ekler veya gönderir.

```cpp
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Kapsayıcıya eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının arkasına yerleştirilen son öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci değerlendirilir `Container.push_back( val)` ,

ardından döndürür **`*this`** . İkinci üye işleci değerlendirilir

`container->push_back((typename Container::value_type&&)val)`,

ardından döndürür **`*this`** .

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

## <a name="back_insert_iteratorreference"></a><a name="reference"></a> back_insert_iterator:: Reference

İçin başvuru sağlayan bir tür `back_insert_iterator` .

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, ilişkili kapsayıcı tarafından denetlenen sıranın bir öğesine başvuruyu açıklar.

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
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
