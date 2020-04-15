---
title: '&lt;dize&gt; operatörleri'
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
ms.openlocfilehash: fef2eb784eca9c9eabbdcd727b051d5c2a4ccfd2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376645"
---
# <a name="ltstringgt-operators"></a>&lt;dize&gt; operatörleri

||||
|-|-|-|
|[işleç!=](#op_neq)|[Işleç&gt;](#op_gt)|[Işleç&gt;&gt;](#op_gt_gt)|
|[Işleç&gt;=](#op_gt_eq)|[Işleç&lt;](#op_lt)|[Işleç&lt;&lt;](#op_lt_lt)|
|[Işleç&lt;=](#op_lt_eq)|[işleç+](#op_add)|[işleç==](#op_eq_eq)|

## <a name="operator"></a><a name="op_add"></a>işleç+

İki dize nesnesi birleştirir.

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

*Sol*\
Bir C stili dize veya `basic_string` bir tür nesnesi concatenated için.

*Doğru*\
Bir C stili dize veya `basic_string` bir tür nesnesi concatenated için.

### <a name="return-value"></a>Dönüş Değeri

Giriş dizelerinin biraraya getirin.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunun `operator+` iki nesnesini basic_string [Sınıf'ı](../standard-library/basic-string-class.md)birleştirmek için her biri aşırı yüklenir. Tüm etkili `basic_string< CharType, Traits, Allocator>(Left).append(right)`bir şekilde geri dönün. Daha fazla bilgi için [eke](../standard-library/basic-string-class.md#append)bakın.

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

## <a name="operator"></a><a name="op_neq"></a>işleç!=

Işlecinin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesine eşit olmamasını test edin.

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

*Sol*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

*Doğru*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki dize nesnesi sağ taraftaki dize nesnesine lexicographically eşit değilse **doğru;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Dize nesneleri arasındaki karşılaştırma, karakterlerinin çift yönlü lexicographical karşılaştırmasını temel alıncaya dayanır. Aynı sayıda karaktere sahiplerse ve ilgili karakter değerleri aynıysa, iki dize eşittir. Aksi takdirde, eşit değildir.

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

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

Işlecinin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesine eşit olup olmadığını test edin.

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

*Sol*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

*Doğru*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki dize nesnesi lexicographically sağ taraftaki dize nesnesine eşit ise **doğru;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Dize nesneleri arasındaki karşılaştırma, karakterlerinin çift yönlü lexicographical karşılaştırmasını temel alıncaya dayanır. Aynı sayıda karaktere sahiplerse ve ilgili karakter değerleri aynıysa, iki dize eşittir. Aksi takdirde, eşit değildir.

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

## <a name="operatorlt"></a><a name="op_lt"></a>Işleç&lt;

İşleçin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesinden daha az olup olmadığını test edin.

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

*Sol*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

*Doğru*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki dize nesnesi lexicographically sağ taraftaki dize nesnesinden daha az ise **doğru;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma kadar karakter karakter karşılaştırır:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu ve böylece dizelerin eşit olduğunu bulur.

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

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Işleç&lt;=

Işlecinin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesinden daha az veya eşit olup olmadığını test edin.

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

*Sol*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

*Doğru*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki dize nesnesi lexicographically daha az veya sağ taraftaki dize nesnesine eşit ise **doğru;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma kadar karakter karakter karşılaştırır:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu bulur, böylece dizeleri eşittir.

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

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Işleç&lt;&lt;

Çıktı akışına bir dize yazan şablon işlevi.

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*_Ostr*\
Çıkış akışı na yazılır.

*Str*\
Çıkış akışına girilecek dize.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dize değerini çıkış akışına *_Ostr.*

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, sınıf şablonuna [basic_string](../standard-library/basic-string-class.md) bir nesne *str* eklemek için **<<işleci** aşırı * \_yükler.* İşlev etkin `_Ostr.write( str.c_str, str.size )`bir şekilde döndürür.

## <a name="operatorgt"></a><a name="op_gt"></a>Işleç&gt;

İşleçin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesinden daha büyük olup olmadığını test edin.

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

*Sol*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

*Doğru*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki dize nesnesi lexicographically sağ taraftaki dize nesnesinden büyükse **doğru;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma kadar karakter karakter karşılaştırır:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulmaz ve dizelerin aynı sayıda karaktere sahip olduğunu ve böylece dizelerin eşit olduğunu bulur.

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

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Işleç&gt;=

İşleyicinin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesinden büyük veya eşit olup olmadığını test edin.

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

*Sol*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

*Doğru*\
C stili dize veya karşılaştırılması gereken bir tür `basic_string` nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki dize nesnesi lexicographically daha büyük veya sağ taraftaki dize nesnesine eşit ise **doğru;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasında bir lexicographical karşılaştırma kadar karakter karakter karşılaştırır:

- Bu iki karşılık gelen karakter eşit siz bulur ve bunların karşılaştırma sonucu dizeleri arasında karşılaştırma sonucu olarak alınır.

- Hiçbir eşitsizlik bulur, ancak bir dize diğerinden daha fazla karaktere sahiptir ve kısa dize daha uzun dize daha az olarak kabul edilir.

- Hiçbir eşitsizlik bulur ve dizeleri karakter aynı sayıda bulur ve böylece dizeleri eşittir.

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

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>Işleç&gt;&gt;

Giriş akışından bir dize okuyan bir şablon işlevi.

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*_Istr*\
Sırayı ayıklamak için kullanılan giriş akışı

*Doğru*\
Giriş akışından çıkarılan dize.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dize değerini *_Istr* okur ve *sağa*döndürür.

### <a name="remarks"></a>Açıklamalar

Operatör, `skipws` bayrak ayarlı şatmadığı sürece önde gelen beyaz boşlukları atlar. Bir sonraki karakter beyaz bir boşluk olana veya dosyanın sonuna ulaşılana kadar aşağıdaki tüm karakterleri okur.

Şablon işlevi, *sağ* tarafından kontrol edilen diziyi *_Istr*akıştan çıkarılan bir dizi öğeyle değiştirmeye>>**işleç** aşırı yükler. Çıkarma durur:

- Dosyanın sonunda.

- Fonksiyon özleri `_Istr`sonra . bu değer sıfır değilse, **genişlik** elemanları.

Fonksiyon özleri `_Istr`sonra . [max_size](../standard-library/basic-string-class.md#max_size) elementler.

- Fonksiyon bir öğe *ch* ayıklar sonra [hangi use_facet](../standard-library/basic-filebuf-class.md#open)<  `getloc`**ctype** \< **CharType**> >( ). **(** **ctype** \< **CharType**>:: **space**, *ch*) doğrudur, bu durumda karakter geri konur.

İşlev hiçbir öğeyi ayıklarsa, [setstate](../standard-library/basic-ios-class.md#setstate)()`ios_base::failbit`olarak adlandırılır. Her durumda, **bu istr**çağırır. **genişliği**(0) \* ve **bu**döndürür.

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

[\<dize>](../standard-library/string.md)
