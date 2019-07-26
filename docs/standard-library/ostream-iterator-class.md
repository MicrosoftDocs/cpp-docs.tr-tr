---
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
ms.openlocfilehash: cebe127eb985e564289db100fa56b0b979104819
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447085"
---
# <a name="ostreamiterator-class"></a>ostream_iterator Sınıfı

Şablon sınıfı ostream_iterator, ardışık öğeleri ayıklama `operator <<`ile çıkış akışına yazan bir çıkış yineleyici nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Çıkış akımına eklenecek nesnenin türü.

*CharType*\
İçin karakter türünü temsil eden tür `ostream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**' dır.

*Lerdir*\
İçin karakter türünü temsil eden tür `ostream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >.*

Ostream_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmalar, kullanarak `ostream_iterator`Çıkış akışlarına doğrudan yazılabilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostream_iterator](#ostream_iterator)|Başlatılmış ve `ostream_iterator` çıkış akışına yazılacak şekilde ayrılmış bir yapı oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Öğesinin karakter türü için sağlayan bir tür `ostream_iterator`.|
|[ostream_type](#ostream_type)|Akış türü `ostream_iterator`için sağlayan bir tür.|
|[traits_type](#traits_type)|Öğesinin karakter nitelikleri türü için sağlayan bir tür `ostream_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|Çıkış \* Yineleyici ifadesini `i`  = uygulamak için kullanılan işleçbaşvurusu.`x`|
|[işleç + +](#op_add_add)|İşlem çağrılmadan önce, kendisine ait olan `ostream_iterator` nesneye döndüren işlevsel bir artış işleci.|
|[operator=](#op_eq)|Çıkış bir akışa yazmak \* için çıkış yineleyici ifadesini `i`  =  `x` uygulamak için kullanılan atama işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="char_type"></a>  ostream_iterator::char_type

Yineleyicinin karakter türü için sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`için bir eş anlamlı.

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

## <a name="op_star"></a>  ostream_iterator::operator*

Çıkış \* Yineleyici ifadesi *II* = *x*'i uygulamak için kullanılan, başvuru kaldırma işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Öğesine bir başvuru `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Karşılaması `ostream_iterator` \* gereken bir çıkış yineleyicisi için gereksinimler yalnızca ifade *II* = 'nin geçerli olmasını gerektirir ve **işleç** veya `operator=` kendi üzerinde hiçbir şey*söylemez.* Bu uygulamadaki üye işleci  **\*bunu**döndürür.

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

## <a name="op_add_add"></a>  ostream_iterator::operator++

İşlem çağrılmadan önce, kendisine ait olan `ostream_iterator` nesneye döndüren işlevsel bir artış işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Öğesine bir başvuru `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Bu üye işleçleri her ikisi  **\*de döndürür.**

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

## <a name="op_eq"></a>  ostream_iterator::operator=

Bir çıkış akışına \* yazmak için output_iterator ifadesini `i`  =  `x` uygulamak için kullanılan atama işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Çıkış akışına eklenecek türü `Type` nesnenin değeri.

### <a name="return-value"></a>Dönüş Değeri

İşleci, nesnesiyle ilişkili çıkış akışına *değer* ekler, ardından [ostream_iterator oluşturucusunda](#ostream_iterator) (varsa) belirtilen sınırlayıcıdan gelir ve sonra öğesine bir `ostream_iterator`başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Karşılaması `ostream_iterator` gereken bir çıkış yineleyicisi için gereksinimler yalnızca ifadenin  =  \* `ii` `t` geçerli olmasını gerektirir ve işleç veya işleç ile ilgili herhangi bir şey ya da kendi başına bir şey söyler. Bu üye işleci döndürür `*this`.

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

## <a name="ostream_iterator"></a>  ostream_iterator::ostream_iterator

Başlatılmış ve `ostream_iterator` çıkış akışına yazılacak şekilde ayrılmış bir yapı oluşturur.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parametreler

*_Ostr*\
[Ostream_iterator:: ostream_type](#ostream_type) türündeki çıkış akışı, tekrarlandırılır.

*_Sınırlayıcı*\
Değerler arasında çıkış akışına eklenen sınırlayıcı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çıkış akışı işaretçisini ile `&_Ostr`başlatır. Sınırlayıcı dize işaretçisi boş bir dize atar.

İkinci Oluşturucu çıkış akışı işaretçisini `&_Ostr` ve sınırlayıcı dize işaretçisiyle *_sınırlayıcıyla*başlatır.

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

## <a name="ostream_type"></a>  ostream_iterator::ostream_type

Yineleyicinin akış türü için sağlayan bir tür.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, yazmak için kullanılabilecek nesneleri tanımlayan iostream hiyerarşisinin akış sınıfı olan [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`> için bir eş anladır.

### <a name="example"></a>Örnek

Bildirme [](#ostream_iterator) ve kullanma `ostream_type`hakkında bir örnek için bkz. ostream_iterator.

## <a name="traits_type"></a>ostream_iterator::traits_type

Yineleyicinin karakter nitelikleri türü için sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Traits`için bir eş anlamlı.

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

[\<Yineleyici >](../standard-library/iterator.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
