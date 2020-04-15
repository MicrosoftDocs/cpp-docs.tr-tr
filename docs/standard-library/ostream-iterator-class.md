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
ms.openlocfilehash: a0c794fe2ff7897bcb6d6412613689100a977589
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373591"
---
# <a name="ostream_iterator-class"></a>ostream_iterator Sınıfı

Sınıf şablonu ostream_iterator, çıkarma `operator <<`ile çıktı akışına ardışık öğeler yazan bir çıktı yineleyici nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parametreler

*Türü*\
Çıkış akımına eklenecek nesnenin türü.

*Chartype*\
`ostream_iterator`Için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char'** dır.

*Özellik*\
`ostream_iterator`Için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe `char_traits` \< bağlıdır ve varsayılan değer *CharType>' dir.*

Ostream_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmalar doğrudan çıkış akışlarına bir `ostream_iterator`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Ostream_iterator](#ostream_iterator)|Çıkış akışına yazmak için başharflerle ve sınırlandırılan bir şey `ostream_iterator` inşa eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|`ostream_iterator`Karakter türünü sağlayan bir tür.|
|[ostream_type](#ostream_type)|Akış türünü sağlayan bir `ostream_iterator`tür.|
|[traits_type](#traits_type)|`ostream_iterator`Karakter özellikleri türünü sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç*](#op_star)|Çıkış yineleyici ifadesini \* `i`  =  `x`uygulamak için kullanılan dereferencing işleci.|
|[işleç++](#op_add_add)|İşlemden önce ele aldığı nesneye bir döndüren işlevsel olmayan bir `ostream_iterator` artış işleci.|
|[işleç=](#op_eq)|Atama işleci, çıktı akışına yazmak \* `i`  =  `x` için çıktı yineleyici ifadesini uygulamak için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yineleyici>

**Ad alanı:** std

## <a name="ostream_iteratorchar_type"></a><a name="char_type"></a>ostream_iterator::char_type

Yineleyicinin karakter türünü sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

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

## <a name="ostream_iteratoroperator"></a><a name="op_star"></a>ostream_iterator::operatör*

Çıkış yineleyici \* ifadesini uygulamak için kullanılan dereferencing işleci *ii* = *x*.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir referans `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Bir çıktı yineleyici için gereksinimleri `ostream_iterator` tatmin etmek gerekir \* sadece ifade *ii* = *t* geçerli olması gerektirir ve **operatör** veya kendi `operator=` hakkında hiçbir şey söylüyor. Bu uygulamada üye operatör ** \*bu**döndürür.

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

## <a name="ostream_iteratoroperator"></a><a name="op_add_add"></a>ostream_iterator::operator++

İşlemden önce ele aldığı nesneye bir döndüren işlevsel olmayan bir `ostream_iterator` artış işleci.

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir referans `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Bu üye işleçler hem ** \*bu**döndürün.

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

## <a name="ostream_iteratoroperator"></a><a name="op_eq"></a>ostream_iterator::operator=

Atama işleci, bir \* `i`  =  `x` çıktı akışına yazmak için output_iterator ifadesini uygulamak için kullanılır.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Çıkış akışına eklenecek `Type` tür nesnesinin değeri.

### <a name="return-value"></a>Dönüş Değeri

İşleç, nesneyle ilişkili çıkış akışına *val* ekler, ardından ostream_iterator [oluşturucuda](#ostream_iterator) (varsa) belirtilen sınırlayıcıyı `ostream_iterator`takip eder ve sonra .

### <a name="remarks"></a>Açıklamalar

Bir çıktı yineleyici için gereksinimleri `ostream_iterator` yerine getirmek gerekir \* `ii`  =  `t` sadece ifade geçerli olması gerekir ve operatör veya operatör = kendi hakkında hiçbir şey söylüyor. Bu üye `*this`operatör döndürür.

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

## <a name="ostream_iteratorostream_iterator"></a><a name="ostream_iterator"></a>ostream_iterator:ostream_iterator

Çıkış akışına yazmak için başharflerle ve sınırlandırılan bir şey `ostream_iterator` inşa eder.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parametreler

*_Ostr*\
Ostream_iterator türü çıkış [akışı::ostream_type](#ostream_type) üzerinde yinelenecek.

*_Delimiter*\
Değerler arasında çıkış akışına eklenen sınır sayılıcı.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu çıkış akışı işaretçisini `&_Ostr`. Delimiter dize işaretçiboş bir dize belirtir.

İkinci oluşturucu ile `&_Ostr` çıkış akışı işaretçisi ve *_Delimiter*ile delimiter dize işaretçisi başharflerini.

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

## <a name="ostream_iteratorostream_type"></a><a name="ostream_type"></a>ostream_iterator:ostream_type

Yineleyicinin akış türünü sağlayan bir tür.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yazmak için kullanılabilecek nesneleri `Traits` tanımlayan iostream hiyerarşisinin akış sınıfı olan [basic_ostream,](../standard-library/basic-ostream-class.md)< `CharType`> eşanlamlıdır.

### <a name="example"></a>Örnek

Nasıl [ostream_iterator](#ostream_iterator) bildirilir ve kullanılacağına `ostream_type`bir örnek için ostream_iterator bakın.

## <a name="ostream_iteratortraits_type"></a><a name="traits_type"></a>ostream_iterator::traits_type

Yineleyicinin karakter özellikleri türünü sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Traits`ile eş anlamlıdır.

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
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
