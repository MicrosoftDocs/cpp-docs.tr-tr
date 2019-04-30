---
title: '&lt;dize&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: a3ca469058ba65f83b0df60a93c63895e34f916e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412364"
---
# <a name="ltstringgt-operators"></a>&lt;dize&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;&gt;](#op_gt_gt)|
|[İşleci&gt;=](#op_gt_eq)|[İşleci&lt;](#op_lt)|[İşleci&lt;&lt;](#op_lt_lt)|
|[İşleci&lt;=](#op_lt_eq)|[operator +](#op_add)|[operator==](#op_eq_eq)|

## <a name="op_add"></a>  operator +

İki dize nesnelerinin art arda ekler.

```cpp
template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` birleştirilecek.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` birleştirilecek.

### <a name="return-value"></a>Dönüş Değeri

Giriş dizesi birleşimi olan dize.

### <a name="remarks"></a>Açıklamalar

Her işlev aşırı yükleme `operator+` şablon sınıfının iki nesneleri birleştirmek için [basic_string sınıfı](../standard-library/basic-string-class.md). Tüm etkin bir şekilde dönüş `basic_string< CharType, Traits, Allocator>(Left).append(right)`. Daha fazla bilgi için [ekleme](../standard-library/basic-string-class.md#append).

### <a name="example"></a>Örnek

```cpp
// string_op_con.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "anti" );
   string s2 ( "gravity" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "heroine";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // Declaring a character constant
   char c1 = '!';
   cout << "The character constant c1 = " << c1 << "." << endl;

   // First member function: concatenates an  object
   // of type basic_string with an object of type basic_string
   string s12 = s1 + s2;
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;

   // Second & fourth member functions: concatenate an object
   // of type basic_string with an object of C-syle string type
   string s1s3 = s1 + s3;
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;

   // Third & fifth member functions: concatenate an object
   // of type basic_string with a character constant
   string s1s3c1 = s1s3 + c1;
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;
}
```

```Output
The basic_string s1 = anti.
The basic_string s2 = gravity.
The C-style string s3 = heroine.
The character constant c1 = !.
The string concatenating s1 & s2 is: antigravity
The string concatenating s1 & s3 is: antiheroine
The string concatenating s1 & s3 is: antiheroine!
```

## <a name="op_neq"></a>  işleç! =

İşlecin sol tarafındaki dize nesnesine sağ tarafındaki dize nesnesine eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki dize nesnesi değilse, lexicographically işlecin sağ tarafındaki dize nesnesine eşit; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma dizesi nesneler arasındaki ikili üzerinde alan kendi karakterlerin lexicographical karşılaştırma. İki dizenin eşit olup bunların aynı sayıda karakter varsa ve ilgili karakter değerlerini aynıdır. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// string_op_ne.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 != s2 )
      cout << "The strings s1 & s2 are not equal." << endl;
   else
      cout << "The strings s1 & s2 are equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 != s3 )
      cout << "The strings s1 & s3 are not equal." << endl;
   else
      cout << "The strings s1 & s3 are equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 != s2 )
      cout << "The strings s3 & s2 are not equal." << endl;
   else
      cout << "The strings s3 & s2 are equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="op_eq_eq"></a>  işleç ==

İşlecin sol tarafındaki dize nesnesinin işlecin sağ tarafındaki dize nesnesine eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki dize nesnesi lexicographically işlecin sağ tarafındaki dize nesnesine eşit; Aksi halde ise **false**.

### <a name="remarks"></a>Açıklamalar

Karşılaştırma dizesi nesneler arasındaki ikili üzerinde alan kendi karakterlerin lexicographical karşılaştırma. İki dizenin eşit olup bunların aynı sayıda karakter varsa ve ilgili karakter değerlerini aynıdır. Aksi takdirde, eşit oldukları.

### <a name="example"></a>Örnek

```cpp
// string_op_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 == s2 )
      cout << "The strings s1 & s2 are equal." << endl;
   else
      cout << "The strings s1 & s2 are not equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 == s3 )
      cout << "The strings s1 & s3 are equal." << endl;
   else
      cout << "The strings s1 & s3 are not equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 == s2 )
      cout << "The strings s3 & s2 are equal." << endl;
   else
      cout << "The strings s3 & s2 are not equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="op_lt"></a>  İşleci&lt;

Dize nesnesinin işlecin sol tarafındaki küçüktür için olup olmadığını sınar işlecin sağ tarafındaki dize nesnesi.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki dize nesnesine sağ taraftaki; dize nesnesi lexicographically küçüktür ise aksi **false**.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri arasındaki karakter kadar bunları karşılaştırılır:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bu, hiçbir inequalities ve aynı sayıda karakter dizelerine sahipsiniz ve bu nedenle dizelerin eşit olup bulur bulur.

### <a name="example"></a>Örnek

```cpp
// string_op_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 < s2 )
      cout << "The string s1 is less than the string s2." << endl;
   else
      cout << "The string s1 is not less than the string s2." << endl;

   // Second member function: comparison between left-hand object
   // of type basic_string & right-hand object of C-syle string type
   if ( s1 < s3 )
      cout << "The string s1 is less than the string s3." << endl;
   else
      cout << "The string s1 is not less than the string s3." << endl;

   // Third member function: comparison between left-hand object
   // of C-syle string type & right-hand object of type basic_string
   if ( s3 < s2 )
      cout << "The string s3 is less than the string s2." << endl;
   else
      cout << "The string s3 is not less than the string s2." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than the string s2.
The string s1 is not less than the string s3.
The string s3 is less than the string s2.
```

## <a name="op_lt_eq"></a>  İşleci&lt;=

Dize nesnesi işlecinin sol tarafında küçük olup olmadığını sınar veya dize nesnesine eşit işlecin sağ tarafındaki.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki dize nesnesi lexicographically daha küçük değerinden veya dize nesnesine sağ tarafındaki eşittir; tersi durumda olup olmadığını **false**.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri arasındaki karakter kadar bunları karşılaştırılır:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bulduğu hiçbir inequalities ve dizeler eşit olacak şekilde aynı sayıda karakter dizeleri olduğunu bulur.

### <a name="example"></a>Örnek

```cpp
// string_op_le.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 <= s2 )
      cout << "The string s1 is less than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 <= s3 )
      cout << "The string s1 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s3." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type  & right-side object of type basic_string
   if ( s2 <= s3 )
      cout << "The string s2 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than or equal to the string s2.
The string s1 is less than or equal to the string s3.
The string s2 is greater than the string s3.
```

## <a name="op_lt_lt"></a>  İşleci&lt;&lt;

Bir dize çıkış akışına yazan bir şablon işlevi.

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*_Ostr*<br/>
Yazılmakta olan çıkış akışı.

*str*<br/>
Çıkış akımına girilmesi dize.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dize değeri, çıkış akışına Yazar *_Ostr*.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev aşırı yüklemelerinin **işleci <<** bir nesneyi eklemek için *str* şablon sınıfının [basic_string](../standard-library/basic-string-class.md) akışının içine  *\_ Ostr*. İşlev etkili bir şekilde döndürür `_Ostr.write( str.c_str, str.size )`.

## <a name="op_gt"></a>  İşleci&gt;

İşlecin sol tarafındaki dize nesnesi dize nesnesine sağ tarafındaki büyük olup olmadığını sınar.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki dize nesnesi lexicographically string nesnesinin işlecin sağ tarafındaki büyük; Aksi halde ise **false**.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri arasındaki karakter kadar bunları karşılaştırılır:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bu, hiçbir inequalities ve aynı sayıda karakter dizelerine sahipsiniz ve bu nedenle dizelerin eşit olup bulur bulur.

### <a name="example"></a>Örnek

```cpp
// string_op_gt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 > s2 )
      cout << "The string s1 is greater than "
           << "the string s2." << endl;
   else
      cout << "The string s1 is not greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 > s1 )
      cout << "The string s3 is greater than "
           << "the string s1." << endl;
   else
      cout << "The string s3 is not greater than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 > s3 )
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
   else
      cout << "The string s2 is not greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is not greater than the string s2.
The string s3 is greater than the string s1.
The string s2 is greater than the string s3.
```

## <a name="op_gt_eq"></a>  İşleci&gt;=

İşlecin sol tarafındaki dize nesnesinin değerinden büyük veya işlecin sağ tarafındaki dize nesnesine eşit olup olmadığını sınar.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

*sağ*<br/>
C stili dize veya bir nesne türü `basic_string` karşılaştırılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki dize nesnesi lexicographically değerinden veya dize nesnesine sağ tarafındaki eşit; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizeleri arasındaki karakter kadar bunları karşılaştırılır:

- İki karşılık gelen karakterler eşit bulur ve bunların karşılaştırma sonucu dizeleri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulur, ancak bir dizeye uzun dize değerinden karakterlerden diğer ve kısa dize olarak kabul edilir daha fazlasına sahip.

- Bu, hiçbir inequalities ve aynı sayıda karakter dizelerine sahipsiniz ve bu nedenle dizelerin eşit olup bulur bulur.

### <a name="example"></a>Örnek

```cpp
// string_op_ge.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 >= s2 )
      cout << "The string s1 is greater than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is less than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 >= s1 )
      cout << "The string s3 is greater than or equal to "
           << "the string s1." << endl;
   else
      cout << "The string s3 is less than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 >= s3 )
      cout << "The string s2 is greater than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is less than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is less than the string s2.
The string s3 is greater than or equal to the string s1.
The string s2 is greater than or equal to the string s3.
```

## <a name="op_gt_gt"></a>  İşleci&gt;&gt;

Dize, giriş akışından okur şablon işlevi.

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*_Istr*<br/>
Sıra çıkarmak için kullanılan giriş akışı

*sağ*<br/>
Girdi akışından ayıklanan dize.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizesi değerini okur *_Istr* ve içine döndürür *doğru*.

### <a name="remarks"></a>Açıklamalar

İşleç baştaki beyaz boşlukları sürece atlayan `skipws` bayrağı ayarlanır. Sonraki karakteri bir boşluk veya dosyanın sonuna ulaşılana kadar tüm karakterleri okur.

Şablonu işlev aşırı yüklemelerinin **işleci >>** tarafından denetlenen dizinin değiştirilecek *doğru* akıştan ayıklanan öğe dizisi ile *_Istr*. Ayıklama durdurur:

- Dosya sonunda.

- İşlev ayıklar sonra `_Istr`. **Genişlik** öğeleri, bu değeri sıfır değilse.

İşlev ayıklar sonra `_Istr`. [max_size](../standard-library/basic-string-class.md#max_size) öğeleri.

- Sonra işlev bir öğe ayıklar *ch* hangi [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **CharType**> > ( `getloc`). **olan**( **ctype** \< **CharType**>:: **alanı**, *ch*) karakteri geri yerleştirin ve bu durumda true olur .

Hiçbir öğe işlevi ayıklar, çağrı [setstate](../standard-library/basic-ios-class.md#setstate)(`ios_base::failbit`). Her durumda çağıran **istr**. **Genişlik**(0) ve döndürür \* **bu**.

### <a name="example"></a>Örnek

```cpp
// string_op_read_.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string c0;
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";
   cin >> c0;
   cout << "The string entered is c0 = " << c0 << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)<br/>
