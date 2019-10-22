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
ms.openlocfilehash: 63bf0a9e3f458b35421ca53d32a2d6be4b701e58
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687248"
---
# <a name="ostream_iterator-class"></a>ostream_iterator Sınıfı

Sınıf şablonu ostream_iterator, ardışık öğeleri ayıklama `operator <<` çıkış akışına yazan bir çıkış yineleyici nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parametreler

*Tür* \
Çıkış akımına eklenecek nesnenin türü.

*CharType* \
@No__t_0 için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**' dır.

*Nitelikler* \
@No__t_0 için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >* ' dir.

Ostream_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmalar, bir `ostream_iterator` kullanarak Çıkış akışlarına doğrudan yazılabilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostream_iterator](#ostream_iterator)|Başlatılmış ve çıkış akışına yazılacak şekilde sınırlanmış bir `ostream_iterator` oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|@No__t_0 karakter türü için sağlayan bir tür.|
|[ostream_type](#ostream_type)|@No__t_0 akış türü için sağlayan bir tür.|
|[traits_type](#traits_type)|@No__t_0 karakter nitelikleri türü için sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|@No__t_0 `i`  =  `x` çıkış yineleyici ifadesini uygulamak için kullanılan, başvuru kaldırma işleci.|
|[işleç + +](#op_add_add)|İşlem çağrılmadan önce, kendisine ait olan nesneye `ostream_iterator` döndüren işlevsel bir artış işleci.|
|[işleç =](#op_eq)|Çıkış Yineleyici ifadesini uygulamak için kullanılan atama işleci, bir çıkış akışına yazmak için `i`  =  `x` \*.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iterator >

**Ad alanı:** std

## <a name="char_type"></a>ostream_iterator::char_type

Yineleyicinin karakter türü için sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `CharType` şablon parametresi için bir eş anlamlı.

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

## <a name="op_star"></a>ostream_iterator:: operator *

@No__t_0 *ıı*  = *x*çıkış yineleyici ifadesini uygulamak için kullanılan başvuru başvurusu.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 başvurusu.

### <a name="remarks"></a>Açıklamalar

@No__t_0 karşılaması gereken bir çıkış yineleyicisinin gereksinimleri yalnızca Expression \* *ıı*  = *t* ' in geçerli olması ve **operatör** ya da kendi üzerinde `operator=` herhangi bir şey yazmadığını belirtir. Bu uygulamadaki üye işleci **\*this**döndürür.

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

## <a name="op_add_add"></a>ostream_iterator:: operator + +

İşlem çağrılmadan önce, kendisine ait olan nesneye `ostream_iterator` döndüren işlevsel bir artış işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu üye işleçleri her ikisi de **\*this**döndürür.

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

## <a name="op_eq"></a>ostream_iterator:: operator =

Bir çıkış akışına yazmak için `i`  =  `x` \* bir output_iterator ifadesini uygulamak için kullanılan atama işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parametreler

*val* \
Çıkış akışına eklenecek `Type` türündeki nesnenin değeri.

### <a name="return-value"></a>Dönüş Değeri

İşleci, nesnesiyle ilişkili çıkış akışına *değer* ekler, ardından [ostream_iterator oluşturucusunda](#ostream_iterator) (varsa) belirtilen sınırlayıcıdan gelir ve ardından `ostream_iterator` bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

@No__t_0 karşılaması gereken bir çıkış yineleyicisi için gereksinimler yalnızca \* `ii`  =  `t` geçerli olması gerekir ve işleç ya da işleç ile ilgili herhangi bir şey veya kendi üzerinde hiçbir şey söyler. Bu üye işleci `*this` döndürür.

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

## <a name="ostream_iterator"></a>ostream_iterator::ostream_iterator

Başlatılmış ve çıkış akışına yazılacak şekilde sınırlanmış bir `ostream_iterator` oluşturur.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parametreler

*_Ostr* \
[Ostream_iterator:: ostream_type](#ostream_type) türündeki çıkış akışı, tekrarlandırılır.

*_Sınırlayıcı* \
Değerler arasında çıkış akışına eklenen sınırlayıcı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, çıkış akışı işaretçisini `&_Ostr` ile başlatır. Sınırlayıcı dize işaretçisi boş bir dize atar.

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

## <a name="ostream_type"></a>ostream_iterator::ostream_type

Yineleyicinin akış türü için sağlayan bir tür.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yazma için kullanılabilecek nesneleri tanımlayan iostream hiyerarşisinin akış sınıfı olan [basic_ostream](../standard-library/basic-ostream-class.md) <  `CharType`, `Traits` > için bir eş anladır.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [ostream_iterator](#ostream_iterator) .

## <a name="traits_type"></a>ostream_iterator::traits_type

Yineleyicinin karakter nitelikleri türü için sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `Traits` şablon parametresi için bir eş anlamlı.

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

[\<iterator >](../standard-library/iterator.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
