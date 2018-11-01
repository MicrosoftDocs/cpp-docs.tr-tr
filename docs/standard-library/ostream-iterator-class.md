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
ms.openlocfilehash: 6a065a100faf5ea40be161e980de2913add917fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449237"
---
# <a name="ostreamiterator-class"></a>ostream_iterator Sınıfı

Şablon sınıfı ostream_iterator ardışık öğeleri çıkış akışına yazan yineleyici bir çıkış nesnesi tanımlar `operator <<`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
Çıkış akımına eklenecek nesnenin türü.

*CharType*<br/>
İçin karakter türünü temsil eden tür `ostream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**.

*Nitelikler*<br/>
İçin karakter türünü temsil eden tür `ostream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >.*

Ostream_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmaları, çıktı kullanılarak doğrudan yazılabilir bir `ostream_iterator`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostream_iterator](#ostream_iterator)|Oluşturur bir `ostream_iterator` çıkış akışına diğer bir deyişle başlatılan ve sınırlanan yazma.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|İçin karakter türünü sağlayan bir tür `ostream_iterator`.|
|[ostream_type](#ostream_type)|Akış türü için sağlayan bir tür `ostream_iterator`.|
|[traits_type](#traits_type)|Karakter nitelikleri için sağlayan bir tür türü `ostream_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator *](#op_star)|Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* `i`  =  `x`.|
|[operator ++](#op_add_add)|Döndüren işlevsiz bir artış işleci bir `ostream_iterator` işlemi çağrılmadan önce aynı nesneye onu ele.|
|[operator=](#op_eq)|Çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci \* `i`  =  `x` çıkış akışına yazmak için.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="char_type"></a>  ostream_iterator::char_type

İçin karakter türünü bir yineleyici sağlayan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `CharType`.

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

Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* *II* = *x*.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Bir çıkış yineleyici için gereksinimleri, `ostream_iterator` karşılamalıdır yalnızca ifade gerektiren \* *II* = *t* geçerli olması ve hiçbir şey hakkında diyor**işleci** veya `operator=` kendi. Bu uygulamada üye işleci döndürür  **\*bu**.

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

Döndüren işlevsiz bir artış işleci bir `ostream_iterator` işlemi çağrılmadan önce aynı nesneye onu ele.

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Hem bu üye işleçleri dönüş  **\*bu**.

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

Output_iterator ifadesini uygulamak için kullanılan atama işleci \* `i`  =  `x` çıkış akışına yazmak için.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Nesne türü değeri `Type` çıkış akımına eklenecek.

### <a name="return-value"></a>Dönüş Değeri

İşleç ekler *val* nesnesiyle ilişkili çıkış akımına ardından belirtilen sınırlayıcıya göre [ostream_iterator Oluşturucusu](#ostream_iterator) (varsa) ve ardından birbaşvurudöndürür`ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Bir çıkış yineleyici için gereksinimleri, `ostream_iterator` karşılamalıdır yalnızca ifade gerektiren \* `ii`  =  `t` geçerli olması ve hiçbir şey işleci veya işleç hakkında diyor, kendi =. Bu üye işleci döndürür `*this`.

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

Oluşturur bir `ostream_iterator` çıkış akışına diğer bir deyişle başlatılan ve sınırlanan yazma.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parametreler

*_Ostr*<br/>
Çıkış akışına türü [ostream_iterator::ostream_type](#ostream_type) üzerinden yinelenir için.

*_Delimiter*<br/>
Çıkış akışına değerleri arasındaki eklenen sınırlayıcısı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu başlatır ve çıkış akışı işaretçiyle `&_Ostr`. Ayırıcı dize işaretçisi, boş bir dize belirtir.

İkinci oluşturucu başlatır ve çıkış akışı işaretçiyle `&_Ostr` ayırıcı dize işaretçisi ile *_Delimiter*.

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

Yineleyici türü akış için sağlayan bir tür.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`>, bir akış sınıf iostream hiyerarşinin yazmak için kullanılan nesneleri tanımlayan.

### <a name="example"></a>Örnek

Bkz: [ostream_iterator](#ostream_iterator) bildirme ve kullanma konusunda bir örnek için `ostream_type`.

## <a name="traits_type"></a>  ostream_iterator::traits_type

İçin karakter nitelikleri türünü yineleyici sağlayan tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Traits`.

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

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
