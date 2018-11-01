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
ms.openlocfilehash: 2a0510b6df656b7925fd42a4c97d768336537424
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557452"
---
# <a name="backinsertiterator-class"></a>back_insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin arka ucunun üzerine yazar ve bu nedenle C++ dizi kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `back_insert_iterator` Sınıfı kapsayıcının türü üzerinde şablonlaştırılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class back_insert_iterator;
```

### <a name="parameters"></a>Parametreler

*Kapsayıcı*<br/>
Hangi öğelerin geri kapsayıcı türü olan tarafından ekleneceği bir `back_insert_iterator`.

## <a name="remarks"></a>Açıklamalar

Kapsayıcının itfa edilecek sabit sürede dizininin sonuna öğe eklemenin mümkün olduğu geri ekleme dizisinin gereksinimlerini karşılaması gerekir. C++ Standart Kitaplığı dizisi kapsayıcıları tarafından tanımlanan [deque sınıfı](../standard-library/deque-class.md), [list sınıfı](../standard-library/list-class.md) ve [vector sınıfı](../standard-library/vector-class.md) gerekli `push_back` üye işlevi ve Bu gereksinimleri karşılar. Bu üç kapsayıcının yanı sıra dizelerin her ile kullanılacak şekilde uyarlanabilir olabilir `back_insert_iterator`s. A `back_insert_iterator` her zaman kapsayıcısıyla birlikte başlatılmalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[back_insert_iterator](#back_insert_iterator)|Oluşturur bir `back_insert_iterator` bir kapsayıcıdaki son öğeden sonra öğe ekler.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|İçin bir kapsayıcı sağlayan bir tür `back_insert_iterator`.|
|[Başvuru](#reference)|İçin bir başvuru sağlayan bir tür `back_insert_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator *](#op_star)|Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* `i`  =  `x` bir geri ekleme.|
|[operator ++](#op_add_add)|Artışlarla `back_insert_iterator` sonraki konuma içine bir değer depolanabilir.|
|[operator=](#op_eq)|Çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci \* `i`  =  `x` bir geri ekleme.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<yineleyici >

**Namespace:** std

## <a name="back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator

Oluşturur bir `back_insert_iterator` bir kapsayıcıdaki son öğeden sonra öğe ekler.

```cpp
explicit back_insert_iterator(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*<br/>
Kapsayıcı, `back_insert_iterator` bir öğe eklemektir.

### <a name="return-value"></a>Dönüş Değeri

A `back_insert_iterator` parametresi kapsayıcısı için.

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

## <a name="container_type"></a>  back_insert_iterator::container_type

İçin bir kapsayıcı sağlayan bir tür `back_insert_iterator`.

```cpp
typedef Container
container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **kapsayıcı**.

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

## <a name="op_star"></a>  back_insert_iterator::operator\*

Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* *miyim* = *x*.

```cpp
back_insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı arkasına eklenen öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Çıkış yineleyici ifadesini uygulamak için kullanılan  **\*Iter** = **değer**. Varsa **Iter** sonra bir dizisi içindeki bir öğeyi adresleyen bir yineleyici olduğunu  **\*Iter** = **değer** bu öğenin değeri ile değiştirir ve mevcut Dizideki öğelerin toplam sayısını değiştirin.

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

## <a name="op_add_add"></a>  back_insert_iterator::operator++

Artışlarla `back_insert_iterator` sonraki konuma içine bir değer depolanabilir.

```cpp
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

A `back_insert_iterator` içine bir değer depolanabilir sonraki konumu ele alan.

### <a name="remarks"></a>Açıklamalar

Preincrementation hem postincrementation işleçler aynı sonucu döndürür.

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

## <a name="op_eq"></a>  back_insert_iterator::operator=

Ekler veya bir kapsayıcının arka uç üzerine bir değer gönderir.

```cpp
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Kapsayıcıya sokulmasına değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı arkasına eklenen son öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci değerlendirir `Container.push_back( val)`,

Ardından döndürür `*this`. İkinci üye işleci değerlendirir

`container->push_back((typename Container::value_type&&)val)`,

Ardından döndürür `*this`.

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

## <a name="reference"></a>  back_insert_iterator::reference

İçin bir başvuru sağlayan bir tür `back_insert_iterator`.

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Açıklamalar

İlişkili kapsayıcı tarafından denetlenen dizinin bir öğesine bir başvuru türü açıklar.

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

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
