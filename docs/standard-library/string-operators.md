---
title: '&lt;dize &gt; işleçleri'
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
ms.openlocfilehash: 0e63054365f4b29cf474a46dbf7c730f54759792
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217395"
---
# <a name="ltstringgt-operators"></a>&lt;dize &gt; işleçleri

||||
|-|-|-|
|[işleç! =](#op_neq)|[işleç&gt;](#op_gt)|[işleç&gt;&gt;](#op_gt_gt)|
|[işleç&gt;=](#op_gt_eq)|[işleç&lt;](#op_lt)|[işleç&lt;&lt;](#op_lt_lt)|
|[işleç&lt;=](#op_lt_eq)|[işleç +](#op_add)|[işleç = =](#op_eq_eq)|

## <a name="operator"></a><a name="op_add"></a>işleç +

İki dize nesnesini birleştirir.

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

*tarafta*\
Bir C stili dize veya birleştirilecek türü nesne `basic_string` .

*Right*\
Bir C stili dize veya birleştirilecek türü nesne `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

Giriş dizelerinin bitiştirilmesi olan dize.

### <a name="remarks"></a>Açıklamalar

Her bir yeniden yüklemeyi, `operator+` sınıf şablonu [basic_string sınıfının](../standard-library/basic-string-class.md)iki nesnesini birleştirmek için çalışır. Tüm etkin şekilde geri döner `basic_string< CharType, Traits, Allocator>(Left).append(right)` . Daha fazla bilgi için bkz. [append](../standard-library/basic-string-class.md#append).

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

## <a name="operator"></a><a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesine eşit olup olmadığını sınar.

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

*tarafta*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

*Right*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki dize nesnesi, sağ taraftaki dize nesnesine sözcüıgrafik olarak eşit değilse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Dize nesneleri arasındaki karşılaştırma, karakterlerinin ikili bir lexıgraf karşılaştırmasını temel alır. İki dize aynı sayıda karakter içeriyorsa ve ilgili karakter değerleri aynıysa eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesine eşit olup olmadığını sınar.

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

*tarafta*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

*Right*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki dize nesnesi, sağ taraftaki dize nesnesine lexıgrafik eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Dize nesneleri arasındaki karşılaştırma, karakterlerinin ikili bir lexıgraf karşılaştırmasını temel alır. İki dize aynı sayıda karakter içeriyorsa ve ilgili karakter değerleri aynıysa eşittir. Aksi takdirde, bunlar eşit değildir.

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

## <a name="operatorlt"></a><a name="op_lt"></a>işlecinde&lt;

İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük olup olmadığını sınar.

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

*tarafta*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

*Right*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki dize nesnesi, sağ taraftaki dize nesnesinden sözcüıgrafik değerinden küçükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgraf karşılaştırması, bu karakterleri şu kadar karakterle karşılaştırır:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karaktere sahip olduğunu ve bu nedenle dizelerin eşit olduğunu bulduğunu bulur.

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

## <a name="operatorlt"></a><a name="op_lt_eq"></a>işlecinde&lt;=

İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük veya ona eşit olup olmadığını sınar.

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

*tarafta*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

*Right*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki dize nesnesi, sağ taraftaki dize nesnesinden sözcüıgrafiksel olarak küçüktür veya eşitse. Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgraf karşılaştırması, bu karakterleri şu kadar karakterle karşılaştırır:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakter içerdiğinden, dizelerin eşit olduğundan emin olur.

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

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>işlecinde&lt;&lt;

Çıkış akışına bir dize yazan bir şablon işlevi.

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*_Ostr*\
Yazılan çıkış akışı.

*üstbilgisine*\
Çıkış akışına girilecek dize.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizenin değerini, çıkış akışına *_Ostr*yazar.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, sınıf şablonu [basic_string](../standard-library/basic-string-class.md) bir nesne *Str* eklemek için **işleç<<** aşırı * \_ yükler.* İşlevi etkin bir şekilde döndürür `_Ostr.write( str.c_str, str.size )` .

## <a name="operatorgt"></a><a name="op_gt"></a>işlecinde&gt;

İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük olup olmadığını sınar.

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

*tarafta*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

*Right*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki dize nesnesi sağ taraftaki dize nesnesinden sözcüıgrafik büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgraf karşılaştırması, bu karakterleri şu kadar karakterle karşılaştırır:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karaktere sahip olduğunu ve bu nedenle dizelerin eşit olduğunu bulduğunu bulur.

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

## <a name="operatorgt"></a><a name="op_gt_eq"></a>işlecinde&gt;=

İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük veya ona eşit olup olmadığını sınar.

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

*tarafta*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

*Right*\
Karşılaştırılacak bir C stili dize veya tür nesnesi `basic_string` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki dize nesnesi, sağ taraftaki dize nesnesinden sözcüıgrafik veya daha büyük olmalıdır; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Dizeler arasında bir lexıgraf karşılaştırması, bu karakterleri şu kadar karakterle karşılaştırır:

- Karşılık gelen iki karakteri eşit olarak bulur ve karşılaştırma sonuçları, dizeler arasındaki Karşılaştırmanın sonucu olarak alınır.

- Herhangi bir değer yok buluyor, ancak bir dize diğerinin daha fazla karaktere sahip ve daha kısa dize, daha uzun bir dizeden daha az kabul edilir.

- Herhangi bir inede bulmadan, dizelerin aynı sayıda karakteri olduğunu ve bu nedenle dizelerin eşit olduğunu bulur.

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

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>işlecinde&gt;&gt;

Giriş akışından bir dizeyi okuyan bir şablon işlevi.

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*_Istr*\
Diziyi ayıklamak için kullanılan giriş akışı

*Right*\
Giriş akışından ayıklanan dize.

### <a name="return-value"></a>Dönüş Değeri

*_Istr* belirtilen dizenin değerini okur ve *sağa*döndürür.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlanmadığı takdirde işleç baştaki boşlukları atlar `skipws` . Sonraki karakter bir boşluk olana veya dosyanın sonuna ulaşılana kadar aşağıdaki tüm karakterleri okur.

Şablon işlevi, bir dizi *_Istr*ayıklanan bir dizi öğe ile *doğrudan* denetlenen sırayı değiştirmek için **işleç>>** aşırı yükler. Ayıklama durduruluyor:

- Dosya sonunda.

- İşlev ayıkladıktan sonra `_Istr` . Bu değer sıfır değilse **Width** öğeleri.

İşlev ayıkladıktan sonra `_Istr` . [max_size](../standard-library/basic-string-class.md#max_size) öğeleri.

- İşlev, *ch* [use_facet](../standard-library/basic-filebuf-class.md#open) <  **CType** \< **CharType**> > () için bir öğe ch öğesini ayıkladıktan sonra `getloc` . **is**( **CType** \< **CharType**> :: **Space**, *ch*) değeri true 'dur, bu durumda karakter geri konur.

İşlev hiçbir öğe ayıklaıyorsa, [SetState](../standard-library/basic-ios-class.md#setstate)() öğesini çağırır `ios_base::failbit` . Herhangi bir durumda, **ISTR**çağırır. **Width**(0) ve döndürür \* **`this`** .

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

[\<string>](../standard-library/string.md)
