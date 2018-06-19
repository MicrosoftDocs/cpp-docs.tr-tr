---
title: ostream_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iterator/std::ostream_iterator
- iterator/std::ostream_iterator::char_type
- iterator/std::ostream_iterator::ostream_type
- iterator/std::ostream_iterator::traits_type
dev_langs:
- C++
helpviewer_keywords:
- std::ostream_iterator [C++]
- std::ostream_iterator [C++], char_type
- std::ostream_iterator [C++], ostream_type
- std::ostream_iterator [C++], traits_type
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49626cbb33ed1220ad82cbec10ad675769b054d6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863614"
---
# <a name="ostreamiterator-class"></a>ostream_iterator Sınıfı

Şablon sınıfı ostream_iterator ardışık öğelere ayıklama ile çıkış akışı üzerine yazar bir çıktı yineleyici nesneyi tanımlayan **işleci <<**.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parametreler

*Tür* çıkış akışı eklenecek nesne türü.

`CharType` Karakter türünü temsil eden tür `ostream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char`.

`Traits` Karakter türünü temsil eden tür `ostream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >.*

Ostream_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Çıkış akışları kullanarak doğrudan algoritmaları yazılabilir bir `ostream_iterator`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostream_iterator](#ostream_iterator)|Oluşturan bir `ostream_iterator` yani başlatılmış ve ayrılmış için çıkış akışı yazılamıyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Karakter türü için sağlayan bir türü `ostream_iterator`.|
|[ostream_type](#ostream_type)|Akış türü için sağlayan bir türü `ostream_iterator`.|
|[traits_type](#traits_type)|Karakter nitelikler tür sağlayan bir tür `ostream_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç *](#op_star)|Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci * `i`  =  `x`.|
|[operator ++](#op_add_add)|Döndüren bir işlevsel artış işleci bir `ostream_iterator` işlemi çağrılmadan önce de aynı nesneye onu ele.|
|[operator=](#op_eq)|Çıktı yineleyici ifade uygulamak için kullanılan atama işleci * `i`  =  `x` çıkış akışına yazmak için.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="char_type"></a>  ostream_iterator::char_type

Yineleyici karakter türü için sağlayan türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

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
\* Output:
The integers written to the output stream
by intOut are:
10
20
30
*\
```

## <a name="op_star"></a>  ostream_iterator::operator*

Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci \* *II* = *x*.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Çıktı yineleyici gereksinimlerini, `ostream_iterator` karşılamalıdır yalnızca ifade gerektiren \* *II* = *t* geçerli ve hiçbir şey hakkında diyor**işleci** veya `operator=` kendi başlarına. Bu uygulamada üye işleci döndürür  **\*bu**.

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
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="op_add_add"></a>  ostream_iterator::operator++

Döndüren bir işlevsel artış işleci bir `ostream_iterator` işlemi çağrılmadan önce de aynı nesneye onu ele.

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Her iki bu üye işleçleri dönmek  **\*bu**.

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
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="op_eq"></a>  ostream_iterator::operator=

Atama işleci output_iterator ifade uygulamak için kullanılan * `i`  =  `x` çıkış akışına yazmak için.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parametreler

`val` Nesne türü değeri `Type` çıkış akışı eklenecek.

### <a name="return-value"></a>Dönüş Değeri

İşleç ekler `val` belirtilen sınırlayıcıyı nesneyle ilişkili çıktı akışa arkasından [ostream_iterator Oluşturucusu](#ostream_iterator) (varsa) ve ardından bir başvuru döndürür `ostream_iterator`.

### <a name="remarks"></a>Açıklamalar

Çıktı yineleyici gereksinimleri, `ostream_iterator` getirmelidir yalnızca ifadesi gerektirir * `ii`  =  `t` geçerli ve hiçbir şey işletmeni veya işletmeni hakkında diyor, kendi =. Bu üye işleci döndürür `*this`.

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
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="ostream_iterator"></a>  ostream_iterator::ostream_iterator

Oluşturan bir `ostream_iterator` yani başlatılmış ve ayrılmış için çıkış akışı yazılamıyor.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parametreler

`_Ostr` Çıkış akışı türü [ostream_iterator::ostream_type](#ostream_type) üzerinden yinelendiğinde için.

`_Delimiter` Değerler arasında çıktı akışına eklenir ve sınırlayıcı.

### <a name="remarks"></a>Açıklamalar

Çıkış akışı işaretçiyle ilk Oluşturucu başlatır `&_Ostr`. Sınırlayıcı dize işaretçisi boş bir dize belirler.

İkinci Oluşturucu, çıkış akışı işaretçi başlatır `&_Ostr` ve sınırlayıcı dize işaretçisi ile `_Delimiter`.

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
\* Output:
10
20
Elements output without delimiter: 123456
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :
*\
```

## <a name="ostream_type"></a>  ostream_iterator::ostream_type

Yineleyici akışı türü için sağlayan türü.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`>, iostream hiyerarşisinin stream sınıfı tanımlayan yazmak için kullanılan nesne.

### <a name="example"></a>Örnek

Bkz: [ostream_iterator](#ostream_iterator) bildirme ve kullanma konusunda bir örnek için `ostream_type`.

## <a name="traits_type"></a>  ostream_iterator::traits_type

Yineleyici karakter nitelikler türünün sağlayan türü.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **nitelikler**.

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
\* Output:
The integers written to output stream
by intOut are:
1
10
100
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
