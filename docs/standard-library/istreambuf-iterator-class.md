---
description: 'Hakkında daha fazla bilgi edinin: istreambuf_iterator sınıfı'
title: istreambuf_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- streambuf/std::istreambuf_iterator
- iterator/std::istreambuf_iterator::char_type
- iterator/std::istreambuf_iterator::int_type
- iterator/std::istreambuf_iterator::istream_type
- iterator/std::istreambuf_iterator::streambuf_type
- iterator/std::istreambuf_iterator::traits_type
- iterator/std::istreambuf_iterator::equal
helpviewer_keywords:
- std::istreambuf_iterator [C++]
- std::istreambuf_iterator [C++], char_type
- std::istreambuf_iterator [C++], int_type
- std::istreambuf_iterator [C++], istream_type
- std::istreambuf_iterator [C++], streambuf_type
- std::istreambuf_iterator [C++], traits_type
- std::istreambuf_iterator [C++], equal
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
ms.openlocfilehash: 221141f5dd97be80b6f13b677f4ed253d75e1054
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306735"
---
# <a name="istreambuf_iterator-class"></a>istreambuf_iterator Sınıfı

Sınıf şablonu istreambuf_iterator, bir giriş akışı arabelleğinden karakter öğelerini çıkaran ve işaretçi türündeki bir nesne üzerinden eriştiği bir giriş Yineleyici nesnesini açıklar `basic_streambuf` \< **CharType**, **Traits**> .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType class Traits = char_traits <CharType>>
class istreambuf_iterator
: public iterator<input_iterator_tag, CharType, typename Traits ::off_type, CharType*, CharType&>
```

### <a name="parameters"></a>Parametreler

*CharType*\
istreambuf_iterator için karakter türünü temsil eden tür.

*Lerdir*\
istreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType> . *

## <a name="remarks"></a>Açıklamalar

istreambuf_iterator sınıfının, bir giriş yineleyici için gereksinimleri karşılaması gerekir.

Null olmayan bir saklı işaretçiyle istreambuf_iterator sınıfının bir nesnesini oluşturduktan veya artırdıktan sonra, nesne, ilişkili giriş akışından *CharType* türünde bir nesneyi ayıklamaya ve depolamaya etkin bir şekilde çalışır. Ayıklama, ancak nesne başvurusu kaldırılana veya kopyalanana kadar gecikebilir. Ayıklama işlemi başarısız olursa, nesne etkili bir şekilde depolanan işaretçinin yerini alır, böylece bir dizi sonu gösterge oluşturur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istreambuf_iterator](#istreambuf_iterator)|`istreambuf_iterator`Giriş akışından karakter okumak için başlatılan bir oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Öğesinin karakter türü için sağlayan bir tür `ostreambuf_iterator` .|
|[int_type](#int_type)|İçin tamsayı türü sağlayan bir tür `istreambuf_iterator` .|
|[istream_type](#istream_type)|Akış türü için sağlayan bir tür `istream_iterator` .|
|[streambuf_type](#streambuf_type)|Akış türü için sağlayan bir tür `istreambuf_iterator` .|
|[traits_type](../standard-library/istream-iterator-class.md#traits_type)|Öğesinin karakter nitelikleri türü için sağlayan bir tür `istream_iterator` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[sıfıra](#equal)|İki giriş akışı önbelleği yineleyicisi arasındaki eşitliği sınar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|Başvuru kaldırma işleci akıştaki sonraki karakteri döndürür.|
|[işleç + +](#op_add_add)|Giriş akışındaki sonraki öğeyi döndürür ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.|
|[operator->](#op_arrow)|Varsa, bir üyenin değerini döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="istreambuf_iteratorchar_type"></a><a name="char_type"></a> istreambuf_iterator:: char_type

Öğesinin karakter türü için sağlayan bir tür `ostreambuf_iterator` .

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *CharType* şablon parametresi için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <algorithm>

int main( )
{
   using namespace std;

   typedef istreambuf_iterator<char>::char_type CHT1;
   typedef istreambuf_iterator<char>::traits_type CHTR1;

   cout << "(Try the example: 'So many dots to be done'\n"
        << " then an Enter key to insert into the output,\n"
        << " & use a ctrl-Z Enter key combination to exit): ";

   // istreambuf_iterator for input stream
   istreambuf_iterator< CHT1, CHTR1> charInBuf ( cin );
   ostreambuf_iterator<char> charOut ( cout );

   // Used in conjunction with replace_copy algorithm
   // to insert into output stream and replace spaces
   // with dot-separators
   replace_copy ( charInBuf , istreambuf_iterator<char>( ),
        charOut , ' ' , '.' );
}
```

## <a name="istreambuf_iteratorequal"></a><a name="equal"></a> istreambuf_iterator:: eşittir

İki giriş akışı arabellek yineleyiciler arasındaki denklik için testler.

```cpp
bool equal(const istreambuf_iterator<CharType, Traits>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Eşitlik için denetlenecek Yineleyici.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Her iki `istreambuf_iterator` s de akış yineleyiciler ise veya ikisi de bir akış sonu yineleyicisi değilse, aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bir Aralık, ile `istreambuf_iterator` geçerli konum ve akış sonu yineleyicisi tarafından tanımlanır, ancak tüm uç olmayan akış yineleyiciler üye işlevi altında eşdeğer olduğundan `equal` , herhangi bir alt Aralık tanımlamak mümkün değildir `istreambuf_iterator` . `==`Ve `!=` işleçleri aynı semantiğe sahiptir.

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_equal.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "(Try the example: 'Hello world!'\n"
        << " then an Enter key to insert into the output,\n"
        << " & use a ctrl-Z Enter key combination to exit): ";

   istreambuf_iterator<char> charReadIn1 ( cin );
   istreambuf_iterator<char> charReadIn2 ( cin );

   bool b1 = charReadIn1.equal ( charReadIn2 );

   if (b1)
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;
}
```

## <a name="istreambuf_iteratorint_type"></a><a name="int_type"></a> istreambuf_iterator:: int_type

İçin tamsayı türü sağlayan bir tür `istreambuf_iterator` .

```cpp
typedef typename traits_type::int_type int_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `Traits::int_type` .

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_int_type.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;
   istreambuf_iterator<char>::int_type inttype1 = 100;
   cout << "The inttype1 = " << inttype1 << "." << endl;
}
/* Output:
The inttype1 = 100.
*/
```

## <a name="istreambuf_iteratoristream_type"></a><a name="istream_type"></a> istreambuf_iterator:: istream_type

Akış türü için sağlayan bir tür `istreambuf_iterator` .

```cpp
typedef basic_istream<CharType, Traits> istream_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `basic_istream` \< **CharType**, **Traits**> .

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [istreambuf_iterator](#istreambuf_iterator) `istream_type` .

## <a name="istreambuf_iteratoristreambuf_iterator"></a><a name="istreambuf_iterator"></a> istreambuf_iterator:: istreambuf_iterator

Giriş akışından karakter okumak için başlatılan bir istreambuf_iterator oluşturur.

```cpp
istreambuf_iterator(streambuf_type* strbuf = 0) throw();
istreambuf_iterator(istream_type& _Istr) throw();
```

### <a name="parameters"></a>Parametreler

*strarabelleğe*\
Eklendiği giriş akış arabelleği `istreambuf_iterator` .

*_Istr*\
Eklendiği giriş akışı `istreambuf_iterator` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş akışı arabellek işaretçisini *strBuffer* ile başlatır. İkinci Oluşturucu, giriş akışı arabellek işaretçisini *_Istr* ile başlatır. `rdbuf`ve sonuç olarak, sonunda türünde bir nesne ayıklamaya ve depolamaya çalışır `CharType` .

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_istreambuf_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;

   // Following declarations will not compile:
   istreambuf_iterator<char>::istream_type &istrm = cin;
   istreambuf_iterator<char>::streambuf_type *strmbf = cin.rdbuf( );

   cout << "(Try the example: 'Oh what a world!'\n"
      << " then an Enter key to insert into the output,\n"
      << " & use a ctrl-Z Enter key combination to exit): ";
   istreambuf_iterator<char> charReadIn ( cin );
   ostreambuf_iterator<char> charOut ( cout );

   // Used in conjunction with replace_copy algorithm
   // to insert into output stream and replace spaces
   // with hyphen-separators
   replace_copy ( charReadIn , istreambuf_iterator<char>( ),
      charOut , ' ' , '-' );
}
```

## <a name="istreambuf_iteratoroperator"></a><a name="op_star"></a> istreambuf_iterator:: operator *

Başvuru kaldırma işleci akıştaki sonraki karakteri döndürür.

```cpp
CharType operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki sonraki karakter.

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_operator_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "Type string of characters & enter to output it,\n"
      << " with stream buffer iterators,(try: 'I'll be back.')\n"
      << " repeat as many times as desired,\n"
      << " then keystroke ctrl-Z Enter to exit program: ";
   istreambuf_iterator<char> inpos ( cin );
   istreambuf_iterator<char> endpos;
   ostreambuf_iterator<char> outpos ( cout );
   while ( inpos != endpos )
   {
*outpos = *inpos;   //Put value of outpos equal to inpos
      ++inpos;
      ++outpos;
   }
}
```

## <a name="istreambuf_iteratoroperator"></a><a name="op_add_add"></a> istreambuf_iterator:: operator + +

Giriş akışındaki sonraki öğeyi döndürür ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.

```cpp
istreambuf_iterator<CharType, Traits>& operator++();
istreambuf_iterator<CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `istreambuf_iterator` veya başvurusu `istreambuf_iterator` .

### <a name="remarks"></a>Açıklamalar

İlk operatör sonunda, ilişkili giriş akışından bir nesne türünü ayıklamaya ve depolamaya çalışır `CharType` . İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_operator_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "Type string of characters & enter to output it,\n"
      << " with stream buffer iterators,(try: 'I'll be back.')\n"
      << " repeat as many times as desired,\n"
      << " then keystroke ctrl-Z Enter to exit program: ";
   istreambuf_iterator<char> inpos ( cin );
   istreambuf_iterator<char> endpos;
   ostreambuf_iterator<char> outpos ( cout );
   while ( inpos != endpos )
   {
*outpos = *inpos;
      ++inpos;   //Increment istreambuf_iterator
      ++outpos;
   }
}
```

## <a name="istreambuf_iteratoroperator-gt"></a><a name="op_arrow"></a> istreambuf_iterator:: operator-&gt;

Varsa, bir üyenin değerini döndürür.

```cpp
const Elem* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşleci **& \* \* bunu** döndürür.

## <a name="istreambuf_iteratorstreambuf_type"></a><a name="streambuf_type"></a> istreambuf_iterator:: streambuf_type

İstreambuf_iterator akış türü için sağlayan bir tür.

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `basic_streambuf` \< **CharType**, **Traits**> .

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [istreambuf_iterator](#istreambuf_iterator) `istreambuf_type` .

## <a name="istreambuf_iteratortraits_type"></a><a name="traits_type"></a> istreambuf_iterator:: traits_type

Öğesinin karakter nitelikleri türü için sağlayan bir tür `istream_iterator` .

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *nitelikleri* için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// istreambuf_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <algorithm>

int main( )
{
   using namespace std;

   typedef istreambuf_iterator<char>::char_type CHT1;
   typedef istreambuf_iterator<char>::traits_type CHTR1;

   cout << "(Try the example: 'So many dots to be done'\n"
        << " then an Enter key to insert into the output,\n"
        << " & use a ctrl-Z Enter key combination to exit): ";

   // istreambuf_iterator for input stream
   istreambuf_iterator< CHT1, CHTR1> charInBuf ( cin );
   ostreambuf_iterator<char> charOut ( cout );

   // Used in conjunction with replace_copy algorithm
   // to insert into output stream and replace spaces
   // with dot-separators
   replace_copy ( charInBuf , istreambuf_iterator<char>( ),
        charOut , ' ' , '.' );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Yineleyici yapısı](../standard-library/iterator-struct.md)\
[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
