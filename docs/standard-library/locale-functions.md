---
title: '&lt;Yerel&gt; ayar işlevleri'
ms.date: 11/04/2016
f1_keywords:
- locale/std::has_facet
- locale/std::isalnum
- locale/std::isalpha
- locale/std::iscntrl
- locale/std::isdigit
- locale/std::isgraph
- locale/std::islower
- locale/std::isprint
- locale/std::ispunct
- locale/std::isspace
- locale/std::isupper
- locale/std::isxdigit
- locale/std::tolower
- locale/std::toupper
- locale/std::use_facet
ms.assetid: b06c1ceb-33a7-48d3-8d4b-2714bbb27f14
helpviewer_keywords:
- std::has_facet [C++]
- std::isalnum [C++]
- std::isalpha [C++]
- std::iscntrl [C++]
- std::isdigit [C++]
- std::isgraph [C++]
- std::islower [C++]
- std::isprint [C++]
- std::ispunct [C++]
- std::isspace [C++]
- std::isupper [C++]
- std::isxdigit [C++]
- std::tolower [C++]
- std::toupper [C++]
- std::use_facet [C++]
ms.openlocfilehash: 3c5d81aecb5e78a8fd3c3f32da82f6048ae4fac8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453561"
---
# <a name="ltlocalegt-functions"></a>&lt;Yerel&gt; ayar işlevleri

||||
|-|-|-|
|[has_facet](#has_facet)|[isalnum](#isalnum)|[isalpha](#isalpha)|
|[iscntrl](#iscntrl)|[isdigit](#isdigit)|[isgraph](#isgraph)|
|[islower](#islower)|[isprint](#isprint)|[ispunct](#ispunct)|
|[isspace](#isspace)|[isupper](#isupper)|[isxdigit](#isxdigit)|
|[ToLower](#tolower)|[ToUpper](#toupper)|[use_facet](#use_facet)|

## <a name="has_facet"></a>has_facet

Belirli bir modelin belirtilen yerel ayarda depolanıp depolanmadığını sınar.

```cpp
template <class Facet>
bool has_facet(const locale& Loc);
```

### <a name="parameters"></a>Parametreler

*Çerçeve*\
Bir modelin varlığı için sınanacak yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

yerel ayarın için test edilen modeli varsa **doğru** ; değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, mevcut değilse oluşturulacak özel durumdan kaçınmak için çağrılmadan önce `use_facet` zorunlu olmayan modellerin bir yerel ayarda listelenmiş olup olmadığını denetlemek için yararlıdır.

### <a name="example"></a>Örnek

```cpp
// locale_has_facet.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result = has_facet <ctype<char> > ( loc );
   cout << result << endl;
}
```

```Output
1
```

## <a name="isalnum"></a>isalnum

Bir yerel ayardaki öğenin alfabetik bir karakter mi yoksa sayısal bir karakter mi olduğunu sınar.

```cpp
template <class CharType>
bool isalnum(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak alfasayısal öğe.

*Çerçeve*\
Sınanacak alfasayısal öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe alfasayısal ise **true** ; değilse **yanlış** .

### <a name="example"></a>Örnek

```cpp
// locale_isalnum.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isalnum ( 'L', loc);
   bool result2 = isalnum ( '@', loc);
   bool result3 = isalnum ( '3', loc);

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "alphanumeric." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not alphanumeric." << endl;

   if ( result2 )
      cout << "The character '@' in the locale is "
           << "alphanumeric." << endl;
   else
      cout << "The character '@' in the locale is "
           << " not alphanumeric." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "alphanumeric." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not alphanumeric." << endl;
}
```

```Output
The character 'L' in the locale is alphanumeric.
The character '@' in the locale is  not alphanumeric.
The character '3' in the locale is alphanumeric.
```

## <a name="isalpha"></a>isalpha

Bir yerel ayarda bulunan öğenin alfabetik bir karakter olup olmadığını sınar.

```cpp
template <class CharType>
bool isalpha(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak alfabetik öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe alfabetik ise **doğru** ; değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **Alpha**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_isalpha.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isalpha ( 'L', loc);
   bool result2 = isalpha ( '@', loc);
   bool result3 = isalpha ( '3', loc);

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "alphabetic." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not alphabetic." << endl;

   if ( result2 )
      cout << "The character '@' in the locale is "
           << "alphabetic." << endl;
   else
      cout << "The character '@' in the locale is "
           << " not alphabetic." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "alphabetic." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not alphabetic." << endl;
}
```

## <a name="iscntrl"></a>iscntrl

Bir yerel ayardaki bir öğenin bir denetim karakteri olup olmadığını sınar.

```cpp
template <class CharType>
bool iscntrl(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe bir denetim karakteri ise **true** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **cnyyyy**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_iscntrl.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = iscntrl ( 'L', loc );
   bool result2 = iscntrl ( '\n', loc );
   bool result3 = iscntrl ( '\t', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a control character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a control character." << endl;

   if ( result2 )
      cout << "The character-set 'backslash-n' in the locale\n is "
           << "a control character." << endl;
   else
      cout << "The character-set 'backslash-n' in the locale\n is "
           << " not a control character." << endl;

   if ( result3 )
      cout << "The character-set 'backslash-t' in the locale\n is "
           << "a control character." << endl;
   else
      cout << "The character-set 'backslash-n' in the locale \n is "
           << " not a control character." << endl;
}
```

## <a name="isdigit"></a>isdigit

Bir yerel ayardaki bir öğenin sayısal bir karakter olup olmadığını sınar.

```cpp
template <class CharType>
bool isdigit(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe sayısal bir karakter ise **true** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **digit**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_is_digit.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isdigit ( 'L', loc );
   bool result2 = isdigit ( '@', loc );
   bool result3 = isdigit ( '3', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a numeric character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a numeric character." << endl;

   if ( result2 )
      cout << "The character '@' in the locale is "
           << "a numeric character." << endl;
   else
      cout << "The character '@' in the locale is "
           << " not a numeric character." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "a numeric character." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not a numeric character." << endl;
}
```

## <a name="isgraph"></a>isgraph

Bir yerel ayardaki öğenin alfasayısal bir karakter mi yoksa noktalama işareti mi olduğunu sınar.

```cpp
template <class CharType>
bool isgraph(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe alfasayısal bir veya noktalama karakteri ise **true** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **Graph**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_is_graph.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isgraph ( 'L', loc );
   bool result2 = isgraph ( '\t', loc );
   bool result3 = isgraph ( '.', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is\n "
           << "an alphanumeric or punctuation character." << endl;
   else
      cout << "The character 'L' in the locale is\n "
           << " not an alphanumeric or punctuation character." << endl;

   if ( result2 )
      cout << "The character 'backslash-t' in the locale is\n "
           << "an alphanumeric or punctuation character." << endl;
   else
      cout << "The character 'backslash-t' in the locale is\n "
           << "not an alphanumeric or punctuation character." << endl;

   if ( result3 )
      cout << "The character '.' in the locale is\n "
           << "an alphanumeric or punctuation character." << endl;
   else
      cout << "The character '.' in the locale is\n "
           << " not an alphanumeric or punctuation character." << endl;
}
```

## <a name="islower"></a>islower

Bir yerel ayardaki bir öğenin küçük harf olup olmadığını sınar.

```cpp
template <class CharType>
bool islower(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe küçük harfli bir karakter ise **doğru** ; değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **Lower**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_islower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = islower ( 'L', loc );
   bool result2 = islower ( 'n', loc );
   bool result3 = islower ( '3', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a lowercase character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a lowercase character." << endl;

   if ( result2 )
      cout << "The character 'n' in the locale is "
           << "a lowercase character." << endl;
   else
      cout << "The character 'n' in the locale is "
           << " not a lowercase character." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "a lowercase character." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not a lowercase character." << endl;
}
```

## <a name="isprint"></a>isprint

Bir yerel ayardaki bir öğenin yazdırılabilir bir karakter olup olmadığını sınar.

```cpp
template <class CharType>
bool isprint(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe yazdırılabilir ise **doğru** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **Print**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_isprint.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );

   bool result1 = isprint ( 'L', loc );
   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a printable character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a printable character." << endl;

   bool result2 = isprint( '\t', loc );
   if ( result2 )
      cout << "The character 'backslash-t' in the locale is "
           << "a printable character." << endl;
   else
      cout << "The character 'backslash-t' in the locale is "
           << " not a printable character." << endl;

   bool result3 = isprint( '\n', loc );
   if ( result3 )
      cout << "The character 'backslash-n' in the locale is "
           << "a printable character." << endl;
   else
      cout << "The character 'backslash-n' in the locale is "
           << " not a printable character." << endl;
}
```

## <a name="ispunct"></a>ispunct

Bir yerel ayardaki bir öğenin bir noktalama işareti olup olmadığını sınar.

```cpp
template <class CharType>
bool ispunct(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe bir noktalama karakteri ise **true** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)`<`[CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **punct**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_ispunct.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = ispunct ( 'L', loc );
   bool result2 = ispunct ( ';', loc );
   bool result3 = ispunct ( '*', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a punctuation character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a punctuation character." << endl;

   if ( result2 )
      cout << "The character ';' in the locale is "
           << "a punctuation character." << endl;
   else
      cout << "The character ';' in the locale is "
           << " not a punctuation character." << endl;

   if ( result3 )
      cout << "The character '*' in the locale is "
           << "a punctuation character." << endl;
   else
      cout << "The character '*' in the locale is "
           << " not a punctuation character." << endl;
}
```

## <a name="isspace"></a>isspace

Bir yerel ayardaki bir öğenin bir boşluk olup olmadığını sınar.

```cpp
template <class CharType>
bool isspace(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe bir boşluk karakteri ise **true** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **Space**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_isspace.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isspace ( 'L', loc );
   bool result2 = isspace ( '\n', loc );
   bool result3 = isspace ( ' ', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a whitespace character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a whitespace character." << endl;

   if ( result2 )
      cout << "The character 'backslash-n' in the locale is "
           << "a whitespace character." << endl;
   else
      cout << "The character 'backslash-n' in the locale is "
           << " not a whitespace character." << endl;

   if ( result3 )
      cout << "The character ' ' in the locale is "
           << "a whitespace character." << endl;
   else
      cout << "The character ' ' in the locale is "
           << " not a whitespace character." << endl;
}
```

## <a name="isupper"></a>isupper

Bir yerel ayarda bulunan öğenin büyük harfle olup olmadığını sınar.

```cpp
template <class CharType>
bool isupper(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe bir büyük karakter ise **doğru** ; değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **Upper**, `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_isupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isupper ( 'L', loc );
   bool result2 = isupper ( 'n', loc );
   bool result3 = isupper ( '3', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a uppercase character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a uppercase character." << endl;

   if ( result2 )
      cout << "The character 'n' in the locale is "
           << "a uppercase character." << endl;
   else
      cout << "The character 'n' in the locale is "
           << " not a uppercase character." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "a uppercase character." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not a uppercase character." << endl;
}
```

## <a name="isxdigit"></a>isxdigit

Bir yerel ayardaki bir öğenin onaltılık bir sayıyı temsil etmek için kullanılan bir karakter olup olmadığını sınar.

```cpp
template <class CharType>
bool isxdigit(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Sınanacak öğe.

*Çerçeve*\
Sınanacak öğeyi içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

test edilen öğe, onaltılı bir sayıyı temsil etmek için kullanılan bir karakter ise **true** . değilse **yanlış** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [Şu](../standard-library/ctype-class.md#is) ( **CType** \< **CharType**>:: **xdigit**, `Ch`).

Onaltılık basamaklar sayıları temsil eden 16 ' yı, 0 ile 9 arasındaki sayıların yanı sıra 0 ile 15 arasında ondalık sayıları temsil eden büyük/küçük harf duyarsız harflerin kullanıldığı sayı olarak kullanır.

### <a name="example"></a>Örnek

```cpp
// locale_isxdigit.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isxdigit ( '5', loc );
   bool result2 = isxdigit ( 'd', loc );
   bool result3 = isxdigit ( 'q', loc );

   if ( result1 )
      cout << "The character '5' in the locale is "
           << "a hexidecimal digit-character." << endl;
   else
      cout << "The character '5' in the locale is "
           << " not a hexidecimal digit-character." << endl;

   if ( result2 )
      cout << "The character 'd' in the locale is "
           << "a hexidecimal digit-character." << endl;
   else
      cout << "The character 'd' in the locale is "
           << " not a hexidecimal digit-character." << endl;

   if ( result3 )
      cout << "The character 'q' in the locale is "
           << "a hexidecimal digit-character." << endl;
   else
      cout << "The character 'q' in the locale is "
           << " not a hexidecimal digit-character." << endl;
}
```

## <a name="tolower"></a>ToLower

Bir karakteri küçük harfe dönüştürür.

```cpp
template <class CharType>
CharType tolower(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Küçük harfe Dönüştürülecek karakter.

*Çerçeve*\
Dönüştürülecek karakteri içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Karakter küçük harfe dönüştürüldü.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [ToLower](../standard-library/ctype-class.md#tolower) ( `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_tolower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   char result1 = tolower ( 'H', loc );
   cout << "The lower case of 'H' in the locale is: "
        << result1 << "." << endl;
   char result2 = tolower ( 'h', loc );
   cout << "The lower case of 'h' in the locale is: "
        << result2 << "." << endl;
   char result3 = tolower ( '$', loc );
   cout << "The lower case of '$' in the locale is: "
        << result3 << "." << endl;
}
```

## <a name="toupper"></a>ToUpper

Bir karakteri büyük harfe dönüştürür.

```cpp
template <class CharType>
CharType toupper(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Büyük harfe Dönüştürülecek karakter.

*Çerçeve*\
Dönüştürülecek karakteri içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Karakter büyük harfe dönüştürüldü.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [use_facet](../standard-library/locale-functions.md#use_facet)< [CType](../standard-library/ctype-class.md) \< **CharType**> > ( `Loc`) döndürür. [ToUpper](../standard-library/ctype-class.md#toupper) ( `Ch`).

### <a name="example"></a>Örnek

```cpp
// locale_toupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   char result1 = toupper ( 'h', loc );
   cout << "The upper case of 'h' in the locale is: "
        << result1 << "." << endl;
   char result2 = toupper ( 'H', loc );
   cout << "The upper case of 'H' in the locale is: "
        << result2 << "." << endl;
   char result3 = toupper ( '$', loc );
   cout << "The upper case of '$' in the locale is: "
        << result3 << "." << endl;
}
```

## <a name="use_facet"></a>use_facet

Bir başvuruyu yerel ayarda depolanan belirtilen türdeki bir modele döndürür.

```cpp
template <class Facet>
const Facet& use_facet(const locale& Loc);
```

### <a name="parameters"></a>Parametreler

*Çerçeve*\
Başvurulmakta olan modelin türünü içeren const yerel ayarı.

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken yerel ayarında bulunan sınıfının `Facet` modeli için başvuru.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi tarafından döndürülen model başvurusu, kapsayan yerel ayarın herhangi bir kopyası mevcut olduğu sürece geçerli kalır. Bağımsız değişken yerel ayarında sınıfının `Facet` böyle bir model nesnesi listelenmemişse, işlev bir `bad_cast` özel durum oluşturur.

### <a name="example"></a>Örnek

```cpp
// locale_use_facet.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );
   bool result1 = use_facet<ctype<char> > ( loc1 ).is(
   ctype_base::alpha, 'a'
);
   bool result2 = use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!'
   );

   if ( result1 )
      cout << "The character 'a' in locale loc1 is alphabetic."
           << endl;
   else
      cout << "The character 'a' in locale loc1 is not alphabetic."
           << endl;

   if ( result2 )
      cout << "The character '!' in locale loc2 is alphabetic."
           << endl;
   else
      cout << "The character '!' in locale loc2 is not alphabetic."
           << endl;
}
```

```Output
The character 'a' in locale loc1 is alphabetic.
The character '!' in locale loc2 is not alphabetic.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Yerel ayar >](../standard-library/locale.md)
