---
title: front_insert_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iterator/std::front_insert_iterator
- iterator/std::front_insert_iterator::container_type
- iterator/std::front_insert_iterator::reference
dev_langs:
- C++
helpviewer_keywords:
- std::front_insert_iterator [C++]
- std::front_insert_iterator [C++], container_type
- std::front_insert_iterator [C++], reference
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aacb6fda870f698bef23184912fc3becfd6c7e2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="frontinsertiterator-class"></a>front_insert_iterator Sınıfı

Çıkış yineleyici gereksinimlerini karşılayan bir yineleyici bağdaştırıcısını açıklar. Bu öğeleri eklemek yerine bir dizinin önüne yazar ve bu nedenle C++ dizi kapsayıcılarının yineleyiciler tarafından sağlanan üzerine yazma semantiklerinden farklı semantikler sağlar. `front_insert_iterator` Sınıfı şablonlaştırılmış kapsayıcı türü.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Container>
class front_insert_iterator;
```

### <a name="parameters"></a>Parametreler

`Container` Kapsayıcı türü hangisinin öğeleridir tarafından eklenecek ön içine bir `front_insert_iterator`.

## <a name="remarks"></a>Açıklamalar

Kapsayıcının itfa edilecek sabit sürede dizininin başına öğe eklemenin mümkün olduğu ön ekleme dizisinin gereksinimlerini karşılaması gerekir. Tarafından tanımlanan C++ Standart Kitaplığı dizisi kapsayıcıları [deque sınıfı](../standard-library/deque-class.md) ve [sınıf listesi](../standard-library/list-class.md) gerekli sağlamak `push_front` üye işlev ve bu gereksinimleri karşılamak. Bunun aksine, kapsayıcıları tarafından tanımlanan sıra [vector sınıfı](../standard-library/vector-class.md) bu gereksinimleri karşılamadığı ve kullanmak için uyarlanmış olamaz `front_insert_iterator`s. A `front_insert_iterator` her zaman kapsayıcısı ile başlatılması gerekir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[front_insert_iterator](#front_insert_iterator)|Belirtilen kapsayıcı nesnesinin önünde öğeler ekleyebilen bir yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Ön ekleme yapılacak kapsayıcıyı temsil eden bir tür.|
|[Başvuru](#reference)|İlişkili kapsayıcı tarafından denetlenen bir dizi içindeki bir öğeye başvuru sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç *](#op_star)|Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci * `i`  =  `x` ön eklemek için.|
|[operator ++](#op_add_add)|Artışlarla `front_insert_iterator` içine bir değer depolanmış sonraki konuma.|
|[operator=](#op_eq)|Çıktı yineleyici ifade uygulamak için kullanılan atama işleci * `i`  =  `x` ön eklemek için.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<yineleyici >

**Namespace:** std

## <a name="container_type"></a>  front_insert_iterator::container_type

Ön ekleme yapılacak kapsayıcıyı temsil eden bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **kapsayıcı**.

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
\* Output:
The list L2 is: ( 40 10 20 ).
*\
```

## <a name="front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator

Belirtilen kapsayıcı nesnesinin önünde öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
explicit front_insert_iterator(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

`_Cont` Kapsayıcı nesnesine `front_insert_iterator` öğeleri eklemektir.

### <a name="return-value"></a>Dönüş Değeri

A `front_insert_iterator` parametresi kapsayıcı nesnesinin.

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
\* Output:
The list L is:
 ( -2 0 2 4 6 8 10 12 14 16 ).
After the front insertions, the list L is:
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).
*\
```

## <a name="op_star"></a>  front_insert_iterator::operator*

Bu adresleri öğesi döndürme Ekle yineleyici dereferences.

```cpp
front_insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlevini ele öğenin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çıktı yineleyici ifade uygulamak için kullanılan  **\*Iter** = **değeri**. Varsa **Iter** öğenin bir sırada sonra adresleri yineleyici olan  **\*Iter** = **değeri** , öğenin değeri ile değiştirir ve desteklemez Dizideki öğelerin toplam sayısını değiştirin.

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
\* Output:
The list L is:
 ( -2 0 2 4 6 8 10 12 14 16 ).
After the front insertions, the list L is:
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).
*\
```

## <a name="op_add_add"></a>  front_insert_iterator::operator++

Artışlarla `back_insert_iterator` içine bir değer depolanmış sonraki konuma.

```cpp
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

A `front_insert_iterator` içine bir değer depolanmış sonraki konumu adresleme.

### <a name="remarks"></a>Açıklamalar

Preincrementation ve postincrementation işleçleri aynı sonucu döndürür.

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
\* Output:
The list L1 is: ( 30 20 10 ).
*\
```

## <a name="op_eq"></a>  front_insert_iterator::operator=

(İter) ekler kapsayıcı önüne üzerine bir değer.

```cpp
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```

### <a name="parameters"></a>Parametreler

`val` Kapsayıcıya atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcının öne eklenen son öğe başvuru.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci değerlendirir `container.push_front( val)`, ardından döndürür `*this`.

İkinci üye işleci değerlendirir

`container->push_front((typename Container::value_type&&) val)`,

ardından döndürür `*this`.

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
\* Output:
The list L1 is: ( 30 20 10 ).
*\
```

## <a name="reference"></a>  front_insert_iterator::reference

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
\* Output:
The list L is: ( 30 20 10 ).
The first element in the list L is: 30.
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
