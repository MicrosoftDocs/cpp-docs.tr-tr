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
ms.openlocfilehash: be4421a7646756da5687ebc9b98f18daf4845809
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687213"
---
# <a name="ostreambuf_iterator-class"></a>ostreambuf_iterator Sınıfı

Sınıf şablonu ostreambuf_iterator, ardışık karakter öğelerini ayıklama **işleci > >** çıkış akışına yazan bir çıkış yineleyici nesnesini açıklar. @No__t_0s, çıkış akışına eklenmekte olan nesne türünde genel bir tür yerine karakterleri olan [ostream_iterator sınıfından](../standard-library/ostream-iterator-class.md) farklılık gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType = char class Traits = char_traits <CharType>>
```

### <a name="parameters"></a>Parametreler

*CharType* \
ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**' dır.

*Nitelikler* \
ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >* ' dir.

## <a name="remarks"></a>Açıklamalar

Ostreambuf_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmalar, bir `ostreambuf_iterator` kullanarak Çıkış akışlarına doğrudan yazılabilir. Sınıf, karakterlerin biçimindeki ham (biçimlendirilmemiş) G/Ç akışına erişim sağlayarak düşük düzey bir akış ve üst düzey akış yineleyicilerle ilişkili arabelleğe alma işlemini ve karakter çevirilerini atlama özelliği sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Çıkış akışına karakter yazmak için başlatılan bir `ostreambuf_iterator` oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|@No__t_0 karakter türü için sağlayan bir tür.|
|[ostream_type](#ostreambuf_iterator_ostream_type)|@No__t_0 akış türü için sağlayan bir tür.|
|[streambuf_type](#streambuf_type)|@No__t_0 akış türü için sağlayan bir tür.|
|[traits_type](#traits_type)|@No__t_0 karakter nitelikleri türü için sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başaramadı](#failed)|Çıkış akışı arabelleğine ekleme hatasını sınar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|@No__t_0 `i`  =  `x` çıkış yineleyici ifadesini uygulamak için kullanılan, başvuru kaldırma işleci.|
|[işleç + +](#op_add_add)|İşlem çağrılmadan önce, kendisine ait olan nesneye `ostreambuf_iterator` döndüren işlevsel bir artış işleci.|
|[işleç =](#op_eq)|İşleç, ilişkili akış ara belleğine bir karakter ekler.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iterator >

**Ad alanı:** std

## <a name="char_type"></a>ostreambuf_iterator::char_type

@No__t_0 karakter türü için sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `CharType` şablon parametresi için bir eş anlamlı.

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

## <a name="failed"></a>ostreambuf_iterator:: Failed

Çıkış akışı arabelleğine ekleme hatasını sınar.

```cpp
bool failed() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

çıkış akışı arabelleğine ekleme işlemi daha önce başarısız olduysa, **doğru** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, üyenin `operator=` önceki bir sürümünde, **subf**_-> `sputc` çağrısı **EOF**olarak döndürülürse **true** döndürür.

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

## <a name="op_star"></a>ostreambuf_iterator:: operator \*

@No__t_0 *ı*  = *x*çıkış yineleyici ifadesini uygulamak için kullanılan işlevsel olmayan bir başvuru işleci.

```cpp
ostreambuf_iterator<CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Ostreamarabelleğe yineleyici nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işleç yalnızca çıkış Yineleyici ifadesinde çalışır \*  = *x* ' *i* , akış arabelleği için çıkış karakteri. Bir ostreamarabelleğe Yineleyici, yineleyiciyi döndürür; **\*iter** , **iter**döndürür

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

## <a name="op_add_add"></a>ostreambuf_iterator:: operator + +

İşlem çağrılmadan önce, bir ostream yineleyicisini aynı karaktere getiren bir işlevsel artış işleci.

```cpp
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Başlangıçta başvurulan karaktere veya `ostreambuf_iterator` \< **CharType**, **nitelikler**> dönüştürülebilir bir uygulama tanımlı nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

İşleci, çıkış yineleyici ifadesi \* i  = *x*' *i* uygulamak için kullanılır.

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

## <a name="op_eq"></a>ostreambuf_iterator:: operator =

İşleç, ilişkili akış ara belleğine bir karakter ekler.

```cpp
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```

### <a name="parameters"></a>Parametreler

*_Char* \
Akış arabelleğine eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Akış arabelleğine yerleştirilen karaktere başvuru.

### <a name="remarks"></a>Açıklamalar

Çıkış Yineleyici ifadesini uygulamak için kullanılan atama işleci, çıkış akışına yazmak için *ı*  = *x* \*.

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

## <a name="ostreambuf_iterator_ostreambuf_iterator"></a>ostreambuf_iterator::ostreambuf_iterator

Çıkış akışına karakter yazmak için başlatılan bir `ostreambuf_iterator` oluşturur.

```cpp
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```

### <a name="parameters"></a>Parametreler

*strarabelleğe* \
Çıkış akışı arabellek işaretçisini başlatmak için kullanılan çıkış streambuffer nesnesi.

*OSTR* \
Çıkış akışı arabellek işaretçisini başlatmak için kullanılan çıkış akışı nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, çıkış akışı arabellek işaretçisini *strBuffer*ile başlatır.

İkinci Oluşturucu çıkış akışı arabellek işaretçisini `Ostr` başlatır. `rdbuf`. Saklı işaretçinin bir null işaretçi olmaması gerekir.

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

## <a name="ostreambuf_iterator_ostream_type"></a>ostreambuf_iterator::ostream_type

@No__t_0 akış türü için sağlayan bir tür.

```cpp
typedef basicOstream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `basicOstream` \< **CharType**, **nitelikler** > için bir eş anlamlı

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) .

## <a name="streambuf_type"></a>ostreambuf_iterator::streambuf_type

@No__t_0 akış türü için sağlayan bir tür.

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>Açıklamalar

Tür \< **CharType**, **nitelikler**> `basic_streambuf`, **char**karakter türü Için özelleştirilse, g/ç arabellekleri için bir akış sınıfı `streambuf` olan bir eş anlamlı.

### <a name="example"></a>Örnek

@No__t_1 bildirme ve kullanma hakkında bir örnek için bkz. [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) .

## <a name="traits_type"></a>ostreambuf_iterator::traits_type

@No__t_0 karakter nitelikleri türü için sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `Traits` şablon parametresi için bir eş anlamlı.

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

[\<iterator >](../standard-library/iterator.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
