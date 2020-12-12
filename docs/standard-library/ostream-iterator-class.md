---
description: 'Hakkında daha fazla bilgi edinin: ostream_iterator sınıfı'
title: ostream_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- iterator/std::ostream_iterator
- iterator/std::ostream_iterator::char_type
- iterator/std::ostream_iterator::ostream_type
- iterator/std::ostream_iterator::traits_type
helpviewer_keywords:
- std::ostream_iterator [C++]
- std::ostream_iterator [C++], char_type
- std::ostream_iterator [C++], ostream_type
- std::ostream_iterator [C++], traits_type
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
ms.openlocfilehash: 2123c2a9addb5024877364a1906800b244b91edb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118374"
---
# <a name="ostream_iterator-class"></a>ostream_iterator Sınıfı

Sınıf şablonu ostream_iterator, ardışık öğeleri ayıklama ile çıkış akışına yazan bir çıkış yineleyici nesnesini açıklar `operator <<` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Çıkış akımına eklenecek nesnenin türü.

*CharType*\
İçin karakter türünü temsil eden tür `ostream_iterator` . Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir **`char`** .

*Lerdir*\
İçin karakter türünü temsil eden tür `ostream_iterator` . Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType> . *

Ostream_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmalar, kullanarak Çıkış akışlarına doğrudan yazılabilir `ostream_iterator` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostream_iterator](#ostream_iterator)|`ostream_iterator`Başlatılmış ve çıkış akışına yazılacak şekilde ayrılmış bir yapı oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Öğesinin karakter türü için sağlayan bir tür `ostream_iterator` .|
|[ostream_type](#ostream_type)|Akış türü için sağlayan bir tür `ostream_iterator` .|
|[traits_type](#traits_type)|Öğesinin karakter nitelikleri türü için sağlayan bir tür `ostream_iterator` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|Çıkış Yineleyici ifadesini uygulamak için kullanılan işleç başvurusu \* `i`  =  `x` .|
|[işleç + +](#op_add_add)|İşlem çağrılmadan önce, kendisine ait olan nesneye döndüren işlevsel bir artış işleci `ostream_iterator` .|
|[işleç =](#op_eq)|Çıkış \* `i`  =  `x` bir akışa yazmak için çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="ostream_iteratorchar_type"></a><a name="char_type"></a> ostream_iterator:: char_type

Yineleyicinin karakter türü için sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `CharType` .

### <a name="example"></a>Örnek

```cpp
// ostream_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostream_iterator<int>::char_type CHT1;
   typedef ostream_iterator<int>::traits_type CHTR1;

   // ostream_iterator for stream cout
   // with new line delimiter:
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream:
   cout << "The integers written to the output stream\n"
        << "by intOut are:" << endl;
*intOut = 10;
*intOut = 20;
*intOut = 30;
}
/* Output:
The integers written to the output stream
by intOut are:
10
20
30
*/
```

## <a name="ostream_iteratoroperator"></a><a name="op_star"></a> ostream_iterator:: operator *

Çıkış Yineleyici ifadesi \* *II*  =  *x*'i uygulamak için kullanılan, başvuru kaldırma işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Öğesine bir başvuru `ostream_iterator` .

### <a name="remarks"></a>Açıklamalar

Yerine getirmeli bir çıkış yineleyicisi için gereksinimler `ostream_iterator` yalnızca ifade \* *II*'nin  =   geçerli olması gerekir ve **`operator`** ya da `operator=` kendi üzerinde veya kendi üzerinde hiçbir şey söyler. Bu uygulamadaki üye işleci **\* bunu** döndürür.

### <a name="example"></a>Örnek

```cpp
// ostream_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*intOut = 10;
   intOut++;      // No effect on iterator position
*intOut = 20;
*intOut = 30;
}
/* Output:
Elements written to output stream:
10
20
30
*/
```

## <a name="ostream_iteratoroperator"></a><a name="op_add_add"></a> ostream_iterator:: operator + +

İşlem çağrılmadan önce, kendisine ait olan nesneye döndüren işlevsel bir artış işleci `ostream_iterator` .

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Öğesine bir başvuru `ostream_iterator` .

### <a name="remarks"></a>Açıklamalar

Bu üye işleçleri her ikisi **\* de döndürür.**

### <a name="example"></a>Örnek

```cpp
// ostream_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*intOut = 10;
   intOut++;      // No effect on iterator position
*intOut = 20;
*intOut = 30;
}
/* Output:
Elements written to output stream:
10
20
30
*/
```

## <a name="ostream_iteratoroperator"></a><a name="op_eq"></a> ostream_iterator:: operator =

\* `i`  =  `x` Bir çıkış akışına yazmak için output_iterator ifadesini uygulamak için kullanılan atama işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
`Type`Çıkış akışına eklenecek türü nesnenin değeri.

### <a name="return-value"></a>Dönüş Değeri

İşleci, nesnesiyle ilişkili çıkış akışına *değer* ekler ve ardından [ostream_iterator oluşturucusunda](#ostream_iterator) (varsa) belirtilen sınırlayıcıdan sonra öğesine bir başvuru döndürür `ostream_iterator` .

### <a name="remarks"></a>Açıklamalar

Karşılaması gereken bir çıkış yineleyicisi için gereksinimler `ostream_iterator` Yalnızca ifadenin \* `ii`  =  `t` geçerli olmasını gerektirir ve işleç veya işleç ile ilgili herhangi bir şey ya da kendi başına bir şey söyler. Bu üye işleci döndürür **`*this`** .

### <a name="example"></a>Örnek

```cpp
// ostream_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*intOut = 10;
   intOut++;      // No effect on iterator position
*intOut = 20;
*intOut = 30;
}
/* Output:
Elements written to output stream:
10
20
30
*/
```

## <a name="ostream_iteratorostream_iterator"></a><a name="ostream_iterator"></a> ostream_iterator:: ostream_iterator

`ostream_iterator`Başlatılmış ve çıkış akışına yazılacak şekilde ayrılmış bir yapı oluşturur.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parametreler

*_Ostr*\
[Ostream_iterator:: ostream_type](#ostream_type) türündeki çıkış akışı tekrarlandırılır.

*_Delimiter*\
Değerler arasında çıkış akışına eklenen sınırlayıcı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çıkış akışı işaretçisini ile başlatır `&_Ostr` . Sınırlayıcı dize işaretçisi boş bir dize atar.

İkinci Oluşturucu, çıkış akışı işaretçisini `&_Ostr` ve sınırlayıcı dize işaretçisiyle *_Delimiter* ile başlatır.

### <a name="example"></a>Örnek

```cpp
// ostream_iterator_ostream_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   ostream_iterator<int> intOut ( cout , "\n" );
*intOut = 10;
   intOut++;
*intOut = 20;
   intOut++;

   int i;
   vector<int> vec;
   for ( i = 1 ; i < 7 ; ++i )
   {
      vec.push_back (  i );
   }

   // Write elements to standard output stream
   cout << "Elements output without delimiter: ";
   copy ( vec.begin ( ), vec.end ( ),
          ostream_iterator<int> ( cout ) );
   cout << endl;

   // Write elements with delimiter " : " to output stream
   cout << "Elements output with delimiter: ";
   copy ( vec.begin ( ), vec.end ( ),
          ostream_iterator<int> ( cout, " : " ) );
   cout << endl;
}
/* Output:
10
20
Elements output without delimiter: 123456
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :
*/
```

## <a name="ostream_iteratorostream_type"></a><a name="ostream_type"></a> ostream_iterator:: ostream_type

Yineleyicinin akış türü için sağlayan bir tür.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü [](../standard-library/basic-ostream-class.md) <  `CharType` , `Traits` yazmak için kullanılabilecek nesneleri tanımlayan iostream hiyerarşisinin akış sınıfı olan basic_ostream,> için bir eş anladır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [ostream_iterator](#ostream_iterator) `ostream_type` .

## <a name="ostream_iteratortraits_type"></a><a name="traits_type"></a> ostream_iterator:: traits_type

Yineleyicinin karakter nitelikleri türü için sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Traits` .

### <a name="example"></a>Örnek

```cpp
// ostream_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // The following not OK, but are just the default values:
   typedef ostream_iterator<int>::char_type CHT1;
   typedef ostream_iterator<int>::traits_type CHTR1;

   // ostream_iterator for stream cout
   // with new line delimiter:
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream:
   cout << "The integers written to output stream\n"
        << "by intOut are:" << endl;
*intOut = 1;
*intOut = 10;
*intOut = 100;
}
/* Output:
The integers written to output stream
by intOut are:
1
10
100
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
