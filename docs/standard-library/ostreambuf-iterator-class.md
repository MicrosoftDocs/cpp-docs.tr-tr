---
title: ostreambuf_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
ms.openlocfilehash: 8e9fa10888b511ad2a500f64faf610dc7dd5ba03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373569"
---
# <a name="ostreambuf_iterator-class"></a>ostreambuf_iterator Sınıfı

Sınıf şablonu ostreambuf_iterator, çıkarma **işleci>>** ile çıktı akışına ardışık karakter öğeleri yazan bir çıktı yineleyici nesnesini açıklar. S, `ostreambuf_iterator`çıktı akışına eklenen nesne türünde genel bir tür yerine karakterlere sahip ostream_iterator Sınıfı'nınkinden farklıdır. [ostream_iterator Class](../standard-library/ostream-iterator-class.md)

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType = char class Traits = char_traits <CharType>>
```

### <a name="parameters"></a>Parametreler

*Chartype*\
ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char'** dır.

*Özellik*\
ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe `char_traits` \< bağlıdır ve varsayılan değer *CharType>' dir.*

## <a name="remarks"></a>Açıklamalar

Ostreambuf_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmalar doğrudan çıkış akışlarına bir `ostreambuf_iterator`. Sınıf, karakterlerin biçimindeki ham (biçimlendirilmemiş) G/Ç akışına erişim sağlayarak düşük düzey bir akış ve üst düzey akış yineleyicilerle ilişkili arabelleğe alma işlemini ve karakter çevirilerini atlama özelliği sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Çıkış akışına karakter yazmak için başharflere aktarılan bir `ostreambuf_iterator` yapı yı kınır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|`ostreambuf_iterator`Karakter türünü sağlayan bir tür.|
|[ostream_type](#ostreambuf_iterator_ostream_type)|Akış türünü sağlayan bir `ostream_iterator`tür.|
|[streambuf_type](#streambuf_type)|Akış türünü sağlayan bir `ostreambuf_iterator`tür.|
|[traits_type](#traits_type)|`ostream_iterator`Karakter özellikleri türünü sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[başarısız](#failed)|Çıkış akışı arabelleğine ekleme hatasını sınar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç*](#op_star)|Çıkış yineleyici ifadesini \* `i`  =  `x`uygulamak için kullanılan dereferencing işleci.|
|[işleç++](#op_add_add)|İşlemden önce ele aldığı nesneye bir döndüren işlevsel olmayan bir `ostreambuf_iterator` artış işleci.|
|[işleç=](#op_eq)|İşleç, ilişkili akış ara belleğine bir karakter ekler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yineleyici>

**Ad alanı:** std

## <a name="ostreambuf_iteratorchar_type"></a><a name="char_type"></a>ostreambuf_iterator::char_type

`ostreambuf_iterator`Karakter türünü sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostreambuf_iterator<char>::char_type CHT1;
   typedef ostreambuf_iterator<char>::traits_type CHTR1;

   // ostreambuf_iterator for stream cout
   // with new line delimiter:
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output streambuf:
   cout << "The characters written to the output stream\n"
        << " by charOutBuf are: ";
*charOutBuf = 'O';
   charOutBuf++;
*charOutBuf = 'U';
   charOutBuf++;
*charOutBuf = 'T';
   charOutBuf++;
   cout << "." << endl;
}
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="ostreambuf_iteratorfailed"></a><a name="failed"></a>ostreambuf_iterator::başarısız oldu

Çıkış akışı arabelleğine ekleme hatasını sınar.

```cpp
bool failed() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

çıkış akışı arabellesine hiçbir ekleme daha önce başarısız olduysa **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Üye **işlevi,** üyenin `operator=`herhangi bir önceki kullanımında, **subf**_-> `sputc` döndürülen **eof**için çağrı ise doğru döndürür.

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iterator_failed.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   ostreambuf_iterator<char> charOut ( cout );

*charOut = 'a';
   charOut ++;
*charOut  = 'b';
   charOut ++;
*charOut = 'c';
   cout << " are characters output individually." << endl;

   bool b1 = charOut.failed ( );
   if (b1)
       cout << "At least one insertion failed." << endl;
   else
       cout << "No insertions failed." << endl;
}
/* Output:
abc are characters output individually.
No insertions failed.
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_star"></a>ostreambuf_iterator::operatör\*

Çıktı \* yineleyici ifadesini uygulamak için kullanılan işlevsel olmayan bir dereferencing işleci *i* = *x*.

```cpp
ostreambuf_iterator<CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Ostreambuf yineleyici nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işleç yalnızca çıkış yinelemesi \* ifade *i* = *x'te,* arabelleği akış adabına giden çıktılar karakterlerine işlev eder. Ostreambuf yineleyicisine uygulandığında, yineleyiciyi döndürür; iter **iter**döndürür , ** \***

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;   // no effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_add_add"></a>ostreambuf_iterator::operator++

İşlemden önce ele aldığı karaktere bir ostream yinelemesi döndüren işlevsel olmayan bir artış işleci.

```cpp
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Başlangıçta ele verilen karaktere veya `ostreambuf_iterator` \< **CharType'a**dönüştürülebilir uygulama tanımlı bir nesneye yapılan başvuru, **Özellikler**>.

### <a name="remarks"></a>Açıklamalar

İşleç çıkış \* yineleyici ifade *i* = *x*uygulamak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;      // No effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_eq"></a>ostreambuf_iterator::operator=

İşleç, ilişkili akış ara belleğine bir karakter ekler.

```cpp
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```

### <a name="parameters"></a>Parametreler

*_Char*\
Akış arabelleğine eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Akış arabelleği ne eklenir karakter için bir başvuru.

### <a name="remarks"></a>Açıklamalar

Atama işleci bir çıkış akışına \* yazmak için çıkış yineleyici ifade *i* = *x* uygulamak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;      // No effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratorostreambuf_iterator"></a><a name="ostreambuf_iterator_ostreambuf_iterator"></a>ostreambuf_iterator:ostreambuf_iterator

Çıkış akışına karakter yazmak için başharflere aktarılan bir `ostreambuf_iterator` yapı yı kınır.

```cpp
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```

### <a name="parameters"></a>Parametreler

*strbuf*\
Çıkış akışı arabelleği işaretçisini başlatmada kullanılan output streambuf nesnesi.

*Ostr*\
Çıktı akışı arabelleği işaretçisini başlatmada kullanılan çıktı akışı nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, çıkış akışı arabellek işaretçisini *strbuf*ile başharfe çevirer.

İkinci oluşturucu çıkış akışı arabellek işaretçisini `Ostr`. `rdbuf`. Depolanan işaretçi null işaretçi olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iteratorOstreambuf_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   ostreambuf_iterator<char> charOut ( cout );

*charOut = 'O';
   charOut ++;
*charOut  = 'U';
   charOut ++;
*charOut = 'T';
   cout << " are characters output individually." << endl;

   ostreambuf_iterator<char> strOut ( cout );
   string str = "These characters are being written to the output stream.\n ";
   copy ( str.begin ( ), str. end ( ), strOut );
}
/* Output:
OUT are characters output individually.
These characters are being written to the output stream.
*/
```

## <a name="ostreambuf_iteratorostream_type"></a><a name="ostreambuf_iterator_ostream_type"></a>ostreambuf_iterator::ostream_type

Akış türünü sağlayan bir `ostream_iterator`tür.

```cpp
typedef basicOstream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `basicOstream` \< **CharType**için eşanlamlıdır , **Özellikler**>

### <a name="example"></a>Örnek

[Nasıl](#ostreambuf_iterator_ostreambuf_iterator) beyan edilip kullanılacağına `ostream_type`bir örnek için ostreambuf_iterator bakın.

## <a name="ostreambuf_iteratorstreambuf_type"></a><a name="streambuf_type"></a>ostreambuf_iterator::streambuf_type

Akış türünü sağlayan bir `ostreambuf_iterator`tür.

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `basic_streambuf` \< **CharType**için eşanlamlıdır , **Özellikler**>, karakter türü **char**için `streambuf` özel hale gelir G /O arabellekleri için bir akış sınıfı .

### <a name="example"></a>Örnek

[Nasıl](#ostreambuf_iterator_ostreambuf_iterator) beyan edilip kullanılacağına `streambuf_type`bir örnek için ostreambuf_iterator bakın.

## <a name="ostreambuf_iteratortraits_type"></a><a name="traits_type"></a>ostreambuf_iterator::traits_type

`ostream_iterator`Karakter özellikleri türünü sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Traits`ile eş anlamlıdır.

### <a name="example"></a>Örnek

```cpp
// ostreambuf_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostreambuf_iterator<char>::char_type CHT1;
   typedef ostreambuf_iterator<char>::traits_type CHTR1;

   // ostreambuf_iterator for stream cout
   // with new line delimiter:
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output streambuf:
   cout << "The characters written to the output stream\n"
        << " by charOutBuf are: ";
*charOutBuf = 'O';
   charOutBuf++;
*charOutBuf = 'U';
   charOutBuf++;
*charOutBuf = 'T';
   charOutBuf++;
   cout << "." << endl;
}
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
