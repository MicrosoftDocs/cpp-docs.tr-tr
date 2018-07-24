---
title: ostreambuf_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
dev_langs:
- C++
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6693fe0c4e34ce4749feef05bf0a1fe0213ac866
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207727"
---
# <a name="ostreambufiterator-class"></a>ostreambuf_iterator Sınıfı

Şablon sınıfı ostreambuf_iterator ardışık karakter öğeleri çıkış akışına yazan yineleyici bir çıkış nesnesi tanımlar **işleci >>**. `ostreambuf_iterator`s öğesinden farklı [ostream_iterator sınıfı](../standard-library/ostream-iterator-class.md) , çıkış akışına eklenen nesnenin türü, genel tür yerine karakterlere sahip.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType = char class Traits = char_traits <CharType>>
```

### <a name="parameters"></a>Parametreler

*CharType* ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**.

*Nitelikler* ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >.*

## <a name="remarks"></a>Açıklamalar

Ostreambuf_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Algoritmaları, çıktı kullanılarak doğrudan yazılabilir bir `ostreambuf_iterator`. Sınıf, karakterlerin biçimindeki ham (biçimlendirilmemiş) G/Ç akışına erişim sağlayarak düşük düzey bir akış ve üst düzey akış yineleyicilerle ilişkili arabelleğe alma işlemini ve karakter çevirilerini atlama özelliği sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Oluşturur bir `ostreambuf_iterator` karakterleri çıkış akımına yazmak için başlatılan.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|İçin karakter türünü sağlayan bir tür `ostreambuf_iterator`.|
|[ostream_type](#ostreambuf_iterator_ostream_type)|Akış türü için sağlayan bir tür `ostream_iterator`.|
|[streambuf_type](#streambuf_type)|Akış türü için sağlayan bir tür `ostreambuf_iterator`.|
|[traits_type](#traits_type)|Karakter nitelikleri için sağlayan bir tür türü `ostream_iterator`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Başarısız oldu](#failed)|Çıkış akışı arabelleğine ekleme hatasını sınar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator *](#op_star)|Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* `i`  =  `x`.|
|[operator ++](#op_add_add)|Döndüren işlevsiz bir artış işleci bir `ostreambuf_iterator` işlemi çağrılmadan önce aynı nesneye onu ele.|
|[operator=](#op_eq)|İşleç, ilişkili akış ara belleğine bir karakter ekler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="char_type"></a>  ostreambuf_iterator::char_type

İçin karakter türünü sağlayan bir tür `ostreambuf_iterator`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `CharType`.

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
\* Output:
The characters written to the output stream
 by charOutBuf are: OUT.
*\
```

## <a name="failed"></a>  ostreambuf_iterator::Failed

Çıkış akışı arabelleğine ekleme hatasını sınar.

```cpp
bool failed() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** çıktı akış arabelleğine hiçbir ekleme başarısız oldu, daha önce; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü **true** sahipse, üye önceki kullanımı `operator=`, çağrı **alt**_ -> `sputc` döndürülen **eof**.

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
\* Output:
abc are characters output individually.
No insertions failed.
*\
```

## <a name="op_star"></a>  ostreambuf_iterator::operator\*

Çıkış yineleyici ifadesini uygulamak için kullanılan bir işlevsiz işleci başvurusunu kaldırma \* *miyim* = *x*.

```cpp
ostreambuf_iterator<CharType, Traits>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Ostreambuf yineleyici nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işleç işlevleri yalnızca çıkış yineleyici ifadesini \* *miyim* = *x* karakterleri çıkarmak için akış arabelleği. Ostreambuf yineleyici uygulanan yineleyiciyi döndürür;  **\*iter** döndürür **iter**,

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
\* Output:
Elements written to output stream:
OUT
*\
```

## <a name="op_add_add"></a>  ostreambuf_iterator::operator++

İşlemden önce ele aynı karakterle ostream yineleyici döndüren işlevsiz bir artış işleci çağrıldı.

```cpp
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk olarak ele karaktere veya dönüştürülebilen bir uygulama tanımlı bir nesneye bir başvuru `ostreambuf_iterator` \< **CharType**, **nitelikler**>.

### <a name="remarks"></a>Açıklamalar

İşleci için çıkış yineleyici ifadesini uygulamak için kullanılan \* *miyim* = *x*.

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
\* Output:
Elements written to output stream:
OUT
*\
```

## <a name="op_eq"></a>  ostreambuf_iterator::operator=

İşleç, ilişkili akış ara belleğine bir karakter ekler.

```cpp
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```

### <a name="parameters"></a>Parametreler

*_Char* akış arabelleğine eklenecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Bir akış arabelleğine eklenmiş olan karaktere başvuru.

### <a name="remarks"></a>Açıklamalar

Çıkış yineleyici ifadesini uygulamak için kullanılan atama işleci \* *miyim* = *x* çıkış akışına yazmak için.

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
\* Output:
Elements written to output stream:
OUT
*\
```

## <a name="ostreambuf_iterator_ostreambuf_iterator"></a>  ostreambuf_iterator::ostreambuf_iterator

Oluşturur bir `ostreambuf_iterator` karakterleri çıkış akımına yazmak için başlatılan.

```cpp
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```

### <a name="parameters"></a>Parametreler

*strbuf* çıktı akış arabelleğine işaretçiyi başlatmak için kullanılan çıkış streambuf nesnesi.

*Ostr* çıktı akış arabelleğine işaretçiyi başlatmak için kullanılan çıkış akış nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu başlatır ve çıktı akış arabelleğine işaretçiyle *strbuf*.

İkinci oluşturucu başlatır ve çıktı akış arabelleğine işaretçiyle `Ostr`. `rdbuf`. Depolanmış bir işaretçiyle bir null işaretçi olmamalıdır.

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
\* Output:
OUT are characters output individually.
These characters are being written to the output stream.
*\
```

## <a name="ostreambuf_iterator_ostream_type"></a>  ostreambuf_iterator::ostream_type

Akış türü için sağlayan bir tür `ostream_iterator`.

```cpp
typedef basicOstream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `basicOstream` \< **CharType**, **nitelikler**>

### <a name="example"></a>Örnek

Bkz: [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) bildirme ve kullanma konusunda bir örnek için `ostream_type`.

## <a name="streambuf_type"></a>  ostreambuf_iterator::streambuf_type

Akış türü için sağlayan bir tür `ostreambuf_iterator`.

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `basic_streambuf` \< **CharType**, **nitelikler**>, duruma bir akış sınıf g/ç arabelleği için `streambuf` karaktertürüiçinözelleştirilmiş,**char**.

### <a name="example"></a>Örnek

Bkz: [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) bildirme ve kullanma konusunda bir örnek için `streambuf_type`.

## <a name="traits_type"></a>  ostreambuf_iterator::traits_type

Karakter nitelikleri için sağlayan bir tür türü `ostream_iterator`.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Traits`.

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
\* Output:
The characters written to the output stream
 by charOutBuf are: OUT.
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
