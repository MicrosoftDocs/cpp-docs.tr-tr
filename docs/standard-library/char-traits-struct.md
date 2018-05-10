---
title: char_traits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits
- iosfwd/std::char_traits::char_type
- iosfwd/std::char_traits::int_type
- iosfwd/std::char_traits::off_type
- iosfwd/std::char_traits::pos_type
- iosfwd/std::char_traits::state_type
- iosfwd/std::char_traits::assign
- iosfwd/std::char_traits::compare
- iosfwd/std::char_traits::copy
- iosfwd/std::char_traits::_Copy_s
- iosfwd/std::char_traits::eof
- iosfwd/std::char_traits::eq
- iosfwd/std::char_traits::eq_int_type
- iosfwd/std::char_traits::find
- iosfwd/std::char_traits::length
- iosfwd/std::char_traits::lt
- iosfwd/std::char_traits::move
- iosfwd/std::char_traits::_Move_s
- iosfwd/std::char_traits::not_eof
- iosfwd/std::char_traits::to_char_type
- iosfwd/std::char_traits::to_int_type
dev_langs:
- C++
helpviewer_keywords:
- char_traits struct
- char_traits class
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3250bd3a80c46345b7b83c524f6aa084ea0b3c11
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="chartraits-struct"></a>char_traits Yapısı

Char_traits yapısı bir karakter ile ilişkili öznitelikleri açıklanmaktadır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
struct char_traits;
```

### <a name="parameters"></a>Parametreler

`CharType` Öğe veri türü.

## <a name="remarks"></a>Açıklamalar

Şablon yapı türü için çeşitli karakter nitelikler açıklar **CharType**. Şablon sınıfı [basic_string](../standard-library/basic-string-class.md) dahil olmak üzere birkaç iostream şablon sınıfları yanı sıra [basic_ios](../standard-library/basic-ios-class.md), türdeki öğeleri işlemek için bu bilgileri kullanın **CharType** . Bu tür bir öğe türü açık yapım veya yok etme gerektirmemelidir. Varsayılan bir oluşturucu, kopya oluşturucu ve beklenen semantiği ile bir atama işleci sağlamanız gerekir. Bit düzeyinde kopyasını atama aynı etkiye olması gerekir. Char_traits yapısı üye işlevlerini hiçbiri istisnalar atabilirsiniz.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Karakter türü.|
|[int_type](#int_type)|Türünde bir karakteri temsil eden bir tamsayı türü `char_type` veya bir dosya sonu (EOF) karakter.|
|[off_type](#off_type)|Bir akış konumları arasında uzaklıkları gösterebilir tamsayı türü.|
|[pos_type](#pos_type)|Bir akış konumlarını temsil edebilen bir tamsayı türü.|
|[state_type](#state_type)|Akıştaki birden çok baytlı karakterleri dönüştürme durumda temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Bir karakter değeri diğerine atar.|
|[Karşılaştırma](#compare)|İki dizeyi karakter belirtilen sayıya kadar karşılaştırır.|
|[Kopyalama](#copy)|Belirtilen sayıda karakteri bir dizeden başka bir konuma kopyalar. Kullanım dışı. Kullanım [char_traits::_Copy_s](#copy_s) yerine.|
|[_Copy_s](#copy_s)|Belirtilen sayıda karakteri bir dizeden başka bir konuma kopyalar.|
|[eof](#eof)|Dosya sonu (EOF) karakteri döndürür.|
|[EQ](#eq)|İki olup olmadığını sınar `char_type` karakterler eşit olur.|
|[eq_int_type](#eq_int_type)|İki karakter olarak temsil olup olmadığını sınar `int_type`s eşit.|
|[Bul](#find)|Belirtilen bir karakterin karakter aralığı içinde ilk a geçişi arar.|
|[uzunluğu](#length)|Bir dizenin uzunluğunu döndürür.|
|[lt](#lt)|Başka değerinden bir karakter olup olmadığını sınar.|
|[Taşıma](#move)|Belirtilen sayıda karakteri bir sırası başka bir olası çakışan, sıralı kopyalar. Kullanım dışı. Kullanım [char_traits::_Move_s](#move_s) yerine.|
|[_Move_s](#move_s)|Belirtilen sayıda karakteri bir sırası başka bir olası çakışan, sıralı kopyalar.|
|[not_eof](#not_eof)|Bir karakter dosya sonu (EOF) karakteri olup olmadığını sınar.|
|[to_char_type](#to_char_type)|Dönüştüren bir `int_type` karşılık gelen karakter `char_type` karakter ve sonucu döndürür.|
|[to_int_type](#to_int_type)|Dönüştüren bir `char_type` karşılık gelen karakter `int_type` karakter ve sonucu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<dize >

**Namespace:** std

## <a name="assign"></a>  char_traits::Assign

Bir karakter değeri veya başka bir dize öğelerinde çeşitli atar.

```cpp
static void assign(char_type& _CharTo,
    const char_type& _CharFrom);

static char_type *assign(char_type* strTo,
    size_t _Num,
    char_type _CharFrom);
```

### <a name="parameters"></a>Parametreler

**_** *CharFrom* değeri olan atanacak karakter.

*_CharTo* karakter değeri atanacak öğe.

* strTo * ilk öğeleri karakter değerleri atanmış olan dize veya karakter dizisi.

`_Num` Değerler atanması giderek öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İkinci üye işlevi işaretçi dizeye olan ilk döndüren `_Num` öğeleri değerlerini atanmış *_CharFrom*.

### <a name="example"></a>Örnek

```cpp
// char_traits_assign.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function assigning
   // one character value to another character
   char ChTo = 't';
   const char ChFrom = 'f';
   cout << "The initial characters ( ChTo , ChFrom ) are: ( "
        << ChTo << " , " << ChFrom << " )." << endl;
   char_traits<char>::assign ( ChTo , ChFrom );
   cout << "After assigning, the characters ( ChTo , ChFrom ) are: ( "
        << ChTo << " , " << ChFrom << " )." << endl << endl;

   // The second member function assigning
   // character values to initial part of a string
   char_traits<char>::char_type s1[] = "abcd-1234-abcd";
   char_traits<char>::char_type* result1;
   cout << "The target string s1 is: " << s1 << endl;
   result1 = char_traits<char>::assign ( s1 , 4 , 'f' );
   cout << "The result1 = assign ( s1 , 4 , 'f' ) is: "
        << result1 << endl;
}
```

```Output
The initial characters ( ChTo , ChFrom ) are: ( t , f ).
After assigning, the characters ( ChTo , ChFrom ) are: ( f , f ).

The target string s1 is: abcd-1234-abcd
The result1 = assign ( s1 , 4 , 'f' ) is: ffff-1234-abcd
```

## <a name="char_type"></a>  char_traits::char_type

Karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

### <a name="example"></a>Örnek

Örneğin bkz [kopya](#copy) bildirme ve kullanma konusunda bir örnek için `char_type`.

## <a name="compare"></a>  char_traits::COMPARE

İki dizeyi karakter belirtilen sayıya kadar karşılaştırır.

```cpp
static int compare(const char_type* str1,
    const char_type* str2,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

* str1 * birbirlerine Karşılaştırılacak ilk iki dizeleri.

* str2 * birbirlerine Karşılaştırılacak ikinci iki dizeleri.

`_Num` Karşılaştırılacak dizelerde öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk dizesi saniye sayısından az dize, iki dizeyi eşit ya da pozitif bir değer varsa ilk dizesi ikinci dize büyükse 0 negatif bir değer.

### <a name="remarks"></a>Açıklamalar

Dize karşılaştırması öğe ilk eşitlik için test öğe yapıldığında ve sırada çiftlerini eşit değil testleri, daha sonra bunlar için test edildiğini küçüktür.

İki dizeleri karşılaştırmak eşit bir aralığında ancak diğerinden daha uzun biridir durumunda küçük kısa iki daha uzun.

### <a name="example"></a>Örnek

```cpp
// char_traits_compare.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main() {
   using namespace std;

   char_traits<char>::char_type* s1 = "CAB";
   char_traits<char>::char_type* s2 = "ABC";
   char_traits<char>::char_type* s3 = "ABC";
   char_traits<char>::char_type* s4 = "ABCD";

   cout << "The string s1 is: " << s1 << endl;
   cout << "The string s2 is: " << s2 << endl;
   cout << "The string s3 is: " << s3 << endl;
   cout << "The string s4 is: " << s4 << endl;

   int comp1, comp2, comp3, comp4;
   comp1 = char_traits<char>::compare ( s1 , s2 , 2 );
   comp2 = char_traits<char>::compare ( s2 , s3 , 3 );
   comp3 = char_traits<char>::compare ( s3 , s4 , 4 );
   comp4 = char_traits<char>::compare ( s4 , s3 , 4 );
   cout << "compare ( s1 , s2 , 2 ) = " << comp1 << endl;
   cout << "compare ( s2 , s3 , 3 ) = " << comp2 << endl;
   cout << "compare ( s3 , s4 , 4 ) = " << comp3 << endl;
   cout << "compare ( s4 , s3 , 4 ) = " << comp4 << endl;
}
```

## <a name="copy"></a>  char_traits::Copy

Belirtilen sayıda karakteri bir dizeden başka bir konuma kopyalar.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir. Kullanmayı [char_traits::_Copy_s](#copy_s) yerine.

```cpp
static char_type *copy(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

`_To` Karakter kopyalanan dizisini almak için hedeflenen dize veya karakter dizisi başındaki öğesi.

`_From` Kopyalanacak kaynak dize veya karakter dizisi başındaki öğesi.

`_Num` Kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk öğe karakter kopyalanan dizisini almak için hedeflenen dize veya karakter diziye kopyalar.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef karakter sıraları çakışmaması gerekir.

### <a name="example"></a>Örnek

```cpp
// char_traits_copy.cpp
// compile with: /EHsc /W3
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type s1[] = "abcd-1234-abcd";
   char_traits<char>::char_type s2[] = "ABCD-1234";
   char_traits<char>::char_type* result1;
   cout << "The source string is: " << s1 << endl;
   cout << "The destination string is: " << s2 << endl;
   // Note: char_traits::copy is potentially unsafe, consider
   // using char_traits::_Copy_s instead.
   result1 = char_traits<char>::copy ( s1 , s2 , 4 );  // C4996
   cout << "The result1 = copy ( s1 , s2 , 4 ) is: "
        << result1 << endl;
}
```

```Output
The source string is: abcd-1234-abcd
The destination string is: ABCD-1234
The result1 = copy ( s1 , s2 , 4 ) is: ABCD-1234-abcd
```

## <a name="copy_s"></a>  char_traits::_Copy_s

Belirtilen sayıda karakteri bir dizeden başka bir konuma kopyalar.

```cpp
static char_type *_Copy_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Parametreler

`dest` Karakter kopyalanan dizisini almak için hedeflenen dize veya karakter dizisi.

`dest_size` Boyutunu `dest`. Varsa `char_type` olan `char`, sonra da bu boyut bayttır. Varsa `char_type` olan `wchar_t`, bu boyut sözcükleri sonra.

`_From` Kopyalanacak kaynak dize veya karakter dizisi.

`count` Kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Karakter kopyalanan dizisini almak için hedeflenen dize veya karakter dizisi.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef karakter sıraları çakışmaması gerekir.

### <a name="example"></a>Örnek

```cpp
// char_traits__Copy_s.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
    using namespace std;

    char_traits<char>::char_type s1[] = "abcd-1234-abcd";
    char_traits<char>::char_type s2[] = "ABCD-1234";
    char_traits<char>::char_type* result1;
    cout << "The source string is: " << s1 << endl;
    cout << "The destination string is: " << s2 << endl;
    result1 = char_traits<char>::_Copy_s(s1,
        char_traits<char>::length(s1), s2, 4);
    cout << "The result1 = _Copy_s(s1, "
         << "char_traits<char>::length(s1), s2, 4) is: "
         << result1 << endl;
}
```

```Output
The source string is: abcd-1234-abcd
The destination string is: ABCD-1234
The result1 = _Copy_s(s1, char_traits<char>::length(s1), s2, 4) is: ABCD-1234-abcd
```

## <a name="eof"></a>  char_traits::EOF

Dosya sonu (EOF) karakteri döndürür.

```cpp
static int_type eof();
```

### <a name="return-value"></a>Dönüş Değeri

EOF karakter.

### <a name="remarks"></a>Açıklamalar

Dosya sonu temsil eden bir değer (gibi `EOF` veya `WEOF`).

Bu değer geçerli bir eşleşmelidir değil C++ Standart durumları `char_type` değeri. Visual C++ derleyicisi türü için bu kısıtlamayı zorlar `char`, ancak türü için `wchar_t`. Aşağıdaki örnek bunu gösterir.

### <a name="example"></a>Örnek

```cpp
// char_traits_eof.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main()
{
    using namespace std;

    char_traits<char>::char_type ch1 = 'x';
    char_traits<char>::int_type int1;
    int1 = char_traits<char>::to_int_type(ch1);
    cout << "char_type ch1 is '" << ch1 << "' and corresponds to int_type "
         << int1 << "." << endl << endl;

    char_traits<char>::int_type int2 = char_traits<char>::eof();
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;

    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;
}
```

```Output
char_type ch1 is 'x' and corresponds to int_type 120.

The eof marker for char_traits<char> is: -1
The eof marker for char_traits<wchar_t> is: 65535
```

## <a name="eq"></a>  char_traits::eq

İki olup olmadığını sınar `char_type` karakterler eşit olur.

```cpp
static bool eq(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

`_Ch1` Eşitlik için test edilecek ilk iki karakter.

`_Ch2` Eşitlik için test ikinci iki karakter.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilk karakter, ikinci karakter eşit aksi **false**.

### <a name="example"></a>Örnek

```cpp
// char_traits_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::char_type ch2 =  'y';
   char_traits<char>::char_type ch3 =  'x';

   // Testing for equality
   bool b1 = char_traits<char>::eq ( ch1 , ch2 );
   if ( b1 )
      cout << "The character ch1 is equal "
           << "to the character ch2." << endl;
   else
      cout << "The character ch1 is not equal "
           << "to the character ch2." << endl;

   // An equivalent and alternatively test procedure
   if ( ch1 == ch3 )
      cout << "The character ch1 is equal "
           << "to the character ch3." << endl;
   else
      cout << "The character ch1 is not equal "
           << "to the character ch3." << endl;
}
```

```Output
The character ch1 is not equal to the character ch2.
The character ch1 is equal to the character ch3.
```

## <a name="eq_int_type"></a>  char_traits::eq_int_type

İki karakter olarak temsil olup olmadığını sınar `int_type`veya s eşit.

```cpp
static bool eq_int_type(const int_type& _Ch1, const int_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

`_Ch1` İlk iki karakter eşitlik için test **int_type**s.

`_Ch2` Eşitlik sınanacak ikinci iki karakter `int_type`s.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilk karakter, ikinci karakter eşit aksi **false**.

### <a name="example"></a>Örnek

```cpp
// char_traits_eq_int_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::char_type ch2 =  'y';
   char_traits<char>::char_type ch3 =  'x';

   // Converting from char_type to int_type
   char_traits<char>::int_type int1, int2 , int3;
   int1 =char_traits<char>:: to_int_type ( ch1 );
   int2 =char_traits<char>:: to_int_type ( ch2 );
   int3 =char_traits<char>:: to_int_type ( ch3 );

   cout << "The char_types and corresponding int_types are:"
        << "\n    ch1 = " << ch1 << " corresponding to int1 = "
        << int1 << "."
        << "\n    ch2 = " << ch2 << " corresponding to int1 = "
        << int2 << "."
        << "\n    ch3 = " << ch3 << " corresponding to int1 = "
        << int3 << "." << endl << endl;

   // Testing for equality of int_type representations
   bool b1 = char_traits<char>::eq_int_type ( int1 , int2 );
   if ( b1 )
      cout << "The int_type representation of character ch1\n "
           << "is equal to the int_type representation of ch2."
           << endl;
   else
      cout << "The int_type representation of character ch1\n is "
           << "not equal to the int_type representation of ch2."
           << endl;

   // An equivalent and alternatively test procedure
   if ( int1 == int3 )
      cout << "The int_type representation of character ch1\n "
           << "is equal to the int_type representation of ch3."
           << endl;
   else
      cout << "The int_type representation of character ch1\n is "
           << "not equal to the int_type representation of ch3."
           << endl;
}
```

```Output
The char_types and corresponding int_types are:
    ch1 = x corresponding to int1 = 120.
    ch2 = y corresponding to int1 = 121.
    ch3 = x corresponding to int1 = 120.

The int_type representation of character ch1
 is not equal to the int_type representation of ch2.
The int_type representation of character ch1
 is equal to the int_type representation of ch3.
```

## <a name="find"></a>  char_traits::Find

Belirtilen bir karakterin karakter aralığı içinde ilk a geçişi arar.

```cpp
static const char_type* find(const char_type* str,
    size_t _Num,
    const char_type& _Ch);
```

### <a name="parameters"></a>Parametreler

`str` Aranacak dizedeki ilk karakter.

`_Num` Konum, birinciden sayım sayısı aranacak aralığında.

`_Ch` Aralığı içinde arama yapılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen karakterin herhangi bir eşleşme varsa bu aralıktaki ilk örneğini gösteren bir işaretçi; Aksi takdirde null işaretçi.

### <a name="example"></a>Örnek

```cpp
// char_traits_find.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   const char* s1 = "f2d-1234-abcd";
   const char* result1;
   cout << "The string to be searched is: " << s1 << endl;

   // Searching for a 'd' in the first 6 positions of string s1
   result1 = char_traits<char>::find ( s1 , 6 , 'd');
   cout << "The character searched for in s1 is: "
        << *result1 << endl;
   cout << "The string beginning with the first occurrence\n "
        << "of the character 'd' is: " << result1 << endl;

   // When no match is found the NULL value is returned
   const char* result2;
   result2 = char_traits<char>::find ( s1 , 3 , 'a');
   if ( result2 == NULL )
      cout << "The result2 of the search is NULL." << endl;
   else
      cout << "The result2 of the search  is: " << result1
           << endl;
}
```

```Output
The string to be searched is: f2d-1234-abcd
The character searched for in s1 is: d
The string beginning with the first occurrence
 of the character 'd' is: d-1234-abcd
The result2 of the search is NULL.
```

## <a name="int_type"></a>  char_traits::int_type

Türünde bir karakteri temsil eden bir tamsayı türü `char_type` veya bir dosya sonu (EOF) karakter.

```cpp
typedef long int_type;
```

### <a name="remarks"></a>Açıklamalar

Cast türünün değerini yazmak olası olmalıdır **CharType** için `int_type` sonra geri **CharType** özgün değeri değiştirmeden.

### <a name="example"></a>Örnek

Örneğin bkz [eq_int_type](#eq_int_type) bildirme ve kullanma konusunda bir örnek için `int_type`.

## <a name="length"></a>  char_traits::length

Bir dizenin uzunluğunu döndürür.

```cpp
static size_t length(const char_type* str);
```

### <a name="parameters"></a>Parametreler

`str` C-ölçülecek uzunluğunu olan dize.

### <a name="return-value"></a>Dönüş Değeri

Değil null Sonlandırıcı ölçülen dizideki öğelerin sayısı.

### <a name="example"></a>Örnek

```cpp
// char_traits_length.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   const char* str1= "Hello";
   cout << "The C-string str1 is: " << str1 << endl;

   size_t lenStr1;
   lenStr1 = char_traits<char>::length ( str1 );
   cout << "The length of C-string str1 is: "
        << lenStr1 << "." << endl;
}
```

```Output
The C-string str1 is: Hello
The length of C-string str1 is: 5.
```

## <a name="lt"></a>  char_traits::lt

Başka değerinden bir karakter olup olmadığını sınar.

```cpp
static bool lt(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

`_Ch1` İçin sınanacak ilk iki karakter küçüktür.

`_Ch2` İçin sınanacak ikinci iki karakter küçüktür.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilk karakter düşükse ikinciden karakter; Aksi takdirde **false**.

### <a name="example"></a>Örnek

```cpp
// char_traits_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::char_type ch2 =  'y';
   char_traits<char>::char_type ch3 =  'z';

   // Testing for less than
   bool b1 = char_traits<char>::lt ( ch1 , ch2 );
   if ( b1 )
      cout << "The character ch1 is less than "
           << "the character ch2." << endl;
   else
      cout << "The character ch1 is not less "
           << "than the character ch2." << endl;

   // An equivalent and alternatively test procedure
   if ( ch3 <  ch2 )
      cout << "The character ch3 is less than "
           << "the character ch2." << endl;
   else
      cout << "The character ch3 is not less "
           << "than the character ch2." << endl;
}
```

```Output
The character ch1 is less than the character ch2.
The character ch3 is not less than the character ch2.
```

## <a name="move"></a>  char_traits::Move

Belirtilen sayıda karakteri bir sırada başka büyük olasılıkla dizisi çakışan kopyalar.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir. Kullanmayı [char_traits::_Move_s](#move_s) yerine.

```cpp
static char_type *move(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

`_To` Karakter kopyalanan dizisini almak için hedeflenen dize veya karakter dizisi başındaki öğesi.

`_From` Kopyalanacak kaynak dize veya karakter dizisi başındaki öğesi.

`_Num` Kaynak dizesi kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk öğe `_To` karakter kopyalanan dizisini almak için hedeflenen dize veya karakter diziye kopyalar.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef çakışabilir.

### <a name="example"></a>Örnek

```cpp
// char_traits_move.cpp
// compile with: /EHsc /W3
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type sFrom1[] =  "abcd-1234-abcd";
   char_traits<char>::char_type sTo1[] =  "ABCD-1234";
   char_traits<char>::char_type* result1;
   cout << "The source string sFrom1 is: " << sFrom1 << endl;
   cout << "The destination stringsTo1 is: " << sTo1 << endl;
   // Note: char_traits::move is potentially unsafe, consider
   // using char_traits::_Move_s instead.
   result1 = char_traits<char>::move ( sTo1 ,  sFrom1 , 4 );  // C4996
   cout << "The result1 = move ( sTo1 , sFrom1 , 4 ) is: "
        << result1 << endl << endl;

   // When source and destination overlap
   char_traits<char>::char_type sToFrom2[] = "abcd-1234-ABCD";
   char_traits<char>::char_type* result2;
   cout << "The source/destination string sToFrom2 is: "
        << sToFrom2 << endl;
   const char* findc = char_traits<char>::find ( sToFrom2 , 4 , 'c' );
   // Note: char_traits::move is potentially unsafe, consider
   // using char_traits::_Move_s instead.
   result2 = char_traits<char>::move ( sToFrom2 , findc , 8 );  // C4996
   cout << "The result2 = move ( sToFrom2 , findc , 8 ) is: "
        << result2 << endl;
}
```

```Output
The source string sFrom1 is: abcd-1234-abcd
The destination stringsTo1 is: ABCD-1234
The result1 = move ( sTo1 , sFrom1 , 4 ) is: abcd-1234

The source/destination string sToFrom2 is: abcd-1234-ABCD
The result2 = move ( sToFrom2 , findc , 8 ) is: cd-1234-4-ABCD
```

## <a name="move_s"></a>  char_traits::_Move_s

Belirtilen sayıda karakteri bir sırada başka büyük olasılıkla dizisi çakışan kopyalar.

```cpp
static char_type *_Move_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Parametreler

`dest` Karakter kopyalanan dizisini almak için hedeflenen dize veya karakter dizisi başındaki öğesi.

`dest_size` Boyutunu `dest`. Varsa `char_type` olan `char`, sonra da bu bayttır. Varsa `char_type` olan `wchar_t`, bu sözcükleri olur.

`_From` Kopyalanacak kaynak dize veya karakter dizisi başındaki öğesi.

`count` Kaynak dizesi kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk öğe `dest` karakter kopyalanan dizisini almak için hedeflenen dize veya karakter diziye kopyalar.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef çakışabilir.

### <a name="example"></a>Örnek

```cpp
// char_traits__Move_s.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
    using namespace std;

    char_traits<char>::char_type sFrom1[] =  "abcd-1234-abcd";
    char_traits<char>::char_type sTo1[] =  "ABCD-1234";
    char_traits<char>::char_type* result1;
    cout << "The source string sFrom1 is: " << sFrom1 << endl;
    cout << "The destination stringsTo1 is: " << sTo1 << endl;
    result1 = char_traits<char>::_Move_s(sTo1,
        char_traits<char>::length(sTo1), sFrom1, 4);
    cout << "The result1 = _Move_s(sTo1, "
         << "char_traits<char>::length(sTo1), sFrom1, 4) is: "
         << result1 << endl << endl;

    // When source and destination overlap
    char_traits<char>::char_type sToFrom2[] = "abcd-1234-ABCD";
    char_traits<char>::char_type* result2;
    cout << "The source/destination string sToFrom2 is: "
         << sToFrom2 << endl;
    const char* findc = char_traits<char>::find(sToFrom2, 4, 'c');
    result2 = char_traits<char>::_Move_s(sToFrom2,
        char_traits<char>::length(sToFrom2), findc, 8);
    cout << "The result2 = _Move_s(sToFrom2, "
        << "char_traits<char>::length(sToFrom2), findc, 8) is: "
         << result2 << endl;
}
```

```Output
The source string sFrom1 is: abcd-1234-abcd
The destination stringsTo1 is: ABCD-1234
The result1 = _Move_s(sTo1, char_traits<char>::length(sTo1), sFrom1, 4) is: abcd-1234

The source/destination string sToFrom2 is: abcd-1234-ABCD
The result2 = _Move_s(sToFrom2, char_traits<char>::length(sToFrom2), findc, 8) is: cd-1234-4-ABCD
```

## <a name="not_eof"></a>  char_traits::not_eof

Bir karakter dosya sonu (EOF) karakteri değil veya EOF olup olmadığını sınar.

```cpp
static int_type not_eof(const int_type& _Ch);
```

### <a name="parameters"></a>Parametreler

`_Ch` Karakter olarak temsil edilen bir `int_type` veya EOF karakter olup test edilmelidir.

### <a name="return-value"></a>Dönüş Değeri

`int_type` Karakter gösterimi test durumunda **int_type** karakteri, EOF karakter eşit değil.

Varsa karakter `int_type` değerdir EOF eşit `int_type` sonra değer **false**.

### <a name="example"></a>Örnek

```cpp
// char_traits_not_eof.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( ) {
   using namespace std;

   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::int_type int1;
   int1 = char_traits<char>:: to_int_type ( ch1 );
   cout << "The char_type ch1 is " << ch1
        << " corresponding to int_type: "
        << int1 << "." << endl;

   // EOF member function
   char_traits <char>::int_type int2 = char_traits<char>::eof ( );
   cout << "The eofReturn is: " << int2 << endl;

   // Testing for EOF or another character
   char_traits <char>::int_type eofTest1, eofTest2;
   eofTest1 = char_traits<char>::not_eof ( int1 );
   if ( !eofTest1 )
      cout << "The eofTest1 indicates ch1 is an EOF character."
              << endl;
   else
      cout << "The eofTest1 returns: " << eofTest1
           << ", which is the character: "
           <<  char_traits<char>::to_char_type ( eofTest1 )
           << "." << endl;

   eofTest2 = char_traits<char>::not_eof ( int2 );
   if ( !eofTest2 )
      cout << "The eofTest2 indicates int2 is an EOF character."
           << endl;
   else
      cout << "The eofTest1 returns: " << eofTest2
           << ", which is the character: "
           <<  char_traits<char>::to_char_type ( eofTest2 )
           << "." << endl;
}
```

```Output
The char_type ch1 is x corresponding to int_type: 120.
The eofReturn is: -1
The eofTest1 returns: 120, which is the character: x.
The eofTest2 indicates int2 is an EOF character.
```

## <a name="off_type"></a>  char_traits::off_type

Bir akış konumları arasında uzaklıkları gösterebilir tamsayı türü.

```cpp
typedef streamoff off_type;
```

### <a name="remarks"></a>Açıklamalar

Türü işlemleri konumlandırma çeşitli akışında katılan bir bayt uzaklığı depolayan bir nesneyi tanımlayan imzalı bir tamsayıdır. Genellikle eşanlamlısı [streamoff](../standard-library/ios-typedefs.md#streamoff), ancak bu tür temelde aynı özellikleri bulunur.

## <a name="pos_type"></a>  char_traits::pos_type

Bir akış konumlarını temsil edebilen bir tamsayı türü.

```cpp
typedef streampos pos_type;
```

### <a name="remarks"></a>Açıklamalar

Bir akış içinde rastgele dosya konumu göstergesi geri yüklemek için gerekli tüm bilgileri depolayan bir nesne türünü tanımlar. Genellikle eşanlamlısı [streampos](../standard-library/ios-typedefs.md#streampos), ancak her durumda türü olarak temelde aynı özelliklere sahip.

## <a name="state_type"></a>  char_traits::state_type

Bir akış birden çok baytlı karakterleri dönüştürme durumu temsil eden tür.

```cpp
typedef implementation-defined state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür dönüştürme durumu temsil eden bir nesne açıklar. Genellikle eşanlamlısı `mbstate_t`, ancak her durumda türü olarak temelde aynı özelliklere sahip.

## <a name="to_char_type"></a>  char_traits::to_char_type

Dönüştüren bir `int_type` karşılık gelen karakter `char_type` karakter ve sonucu döndürür.

```cpp
static char_type to_char_type(const int_type& _Ch);
```

### <a name="parameters"></a>Parametreler

`_Ch` `int_type` Karakter olarak gösterilemeyecek kadar bir `char_type`.

### <a name="return-value"></a>Dönüş Değeri

`char_type` Karakter karşılık gelen `int_type` karakter.

Değerini `_Ch` , temsil edilemez bu nedenle, belirtilmeyen bir sonuç verir.

### <a name="remarks"></a>Açıklamalar

Dönüştürme işlemlerinin [to_int_type](#to_int_type) ve `to_char_type` birbirlerine, ters olan böylece:

`to_int_type` ( `to_char_type` ( *x* ) ) == *x*

herhangi bir için `int_type` *x* ve

`to_char_type` ( `to_int_type` ( *x* ) ) == *x*

herhangi bir için `char_type` *x*.

### <a name="example"></a>Örnek

```cpp
// char_traits_to_char_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type ch1 =  'a';
   char_traits<char>::char_type ch2 =  'b';
   char_traits<char>::char_type ch3 =  'a';

   // Converting from char_type to int_type
   char_traits<char>::int_type int1, int2 , int3;
   int1 =char_traits<char>:: to_int_type ( ch1 );
   int2 =char_traits<char>:: to_int_type ( ch2 );
   int3 =char_traits<char>:: to_int_type ( ch3 );

   cout << "The char_types and corresponding int_types are:"
        << "\n    ch1 = " << ch1 << " corresponding to int1 = "
        << int1 << "."
        << "\n    ch2 = " << ch2 << " corresponding to int1 = "
        << int2 << "."
        << "\n    ch3 = " << ch3 << " corresponding to int1 = "
        << int3 << "." << endl << endl;

   // Converting from int_type back to char_type
   char_traits<char>::char_type rec_ch1;
   rec_ch1 = char_traits<char>:: to_char_type ( int1);
   char_traits<char>::char_type rec_ch2;
   rec_ch2 = char_traits<char>:: to_char_type ( int2);

   cout << "The recovered char_types and corresponding int_types are:"
        << "\n    recovered ch1 = " << rec_ch1 << " from int1 = "
        << int1 << "."
        << "\n    recovered ch2 = " << rec_ch2 << " from int2 = "
        << int2 << "." << endl << endl;

   // Testing that the conversions are inverse operations
   bool b1 = char_traits<char>::eq ( rec_ch1 , ch1 );
   if ( b1 )
      cout << "The recovered char_type of ch1"
           << " is equal to the original ch1." << endl;
   else
      cout << "The recovered char_type of ch1"
           << " is not equal to the original ch1." << endl;

   // An equivalent and alternatively test procedure
   if ( rec_ch2 == ch2 )
      cout << "The recovered char_type of ch2"
           << " is equal to the original ch2." << endl;
   else
      cout << "The recovered char_type of ch2"
           << " is not equal to the original ch2." << endl;
}
```

```Output
The char_types and corresponding int_types are:
    ch1 = a corresponding to int1 = 97.
    ch2 = b corresponding to int1 = 98.
    ch3 = a corresponding to int1 = 97.

The recovered char_types and corresponding int_types are:
    recovered ch1 = a from int1 = 97.
    recovered ch2 = b from int2 = 98.

The recovered char_type of ch1 is equal to the original ch1.
The recovered char_type of ch2 is equal to the original ch2.
```

## <a name="to_int_type"></a>  char_traits::to_int_type

Dönüştüren bir `char_type` karşılık gelen karakter `int_type` karakter ve sonucu döndürür.

```cpp
static int_type to_int_type(const char_type& _Ch);
```

### <a name="parameters"></a>Parametreler

`_Ch` `char_type` Karakter olarak gösterilemeyecek kadar bir `int_type`.

### <a name="return-value"></a>Dönüş Değeri

`int_type` Karakter karşılık gelen `char_type` karakter.

### <a name="remarks"></a>Açıklamalar

Dönüştürme işlemlerinin `to_int_type` ve [to_char_type](#to_char_type) birbirlerine, ters olan böylece:

`to_int_type` ( `to_char_type` ( *x* ) ) == *x*

herhangi bir için `int_type` *x*, ve

`to_char_type` ( `to_int_type` ( *x* ) ) == *x*

herhangi bir için `char_type` *x*.

### <a name="example"></a>Örnek

```cpp
// char_traits_to_int_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   char_traits<char>::char_type ch1 = 'a';
   char_traits<char>::char_type ch2 = 'b';
   char_traits<char>::char_type ch3 = 'a';

   // Converting from char_type to int_type
   char_traits<char>::int_type int1, int2 , int3;
   int1 =char_traits<char>:: to_int_type ( ch1 );
   int2 =char_traits<char>:: to_int_type ( ch2 );
   int3 =char_traits<char>:: to_int_type ( ch3 );

   cout << "The char_types and corresponding int_types are:"
        << "\n    ch1 = " << ch1 << " corresponding to int1 = "
        << int1 << "."
        << "\n    ch2 = " << ch2 << " corresponding to int1 = "
        << int2 << "."
        << "\n    ch3 = " << ch3 << " corresponding to int1 = "
        << int3 << "." << endl << endl;

   // Converting from int_type back to char_type
   char_traits<char>::char_type rec_ch1;
   rec_ch1 = char_traits<char>:: to_char_type ( int1);
   char_traits<char>::char_type rec_ch2;
   rec_ch2 = char_traits<char>:: to_char_type ( int2);

   cout << "The recovered char_types and corresponding int_types are:"
        << "\n    recovered ch1 = " << rec_ch1 << " from int1 = "
        << int1 << "."
        << "\n    recovered ch2 = " << rec_ch2 << " from int2 = "
        << int2 << "." << endl << endl;

   // Testing that the conversions are inverse operations
   bool b1 = char_traits<char>::eq ( rec_ch1 , ch1 );
   if ( b1 )
      cout << "The recovered char_type of ch1"
           << " is equal to the original ch1." << endl;
   else
      cout << "The recovered char_type of ch1"
           << " is not equal to the original ch1." << endl;

   // An equivalent and alternatively test procedure
   if ( rec_ch2 == ch2 )
      cout << "The recovered char_type of ch2"
           << " is equal to the original ch2." << endl;
   else
      cout << "The recovered char_type of ch2"
           << " is not equal to the original ch2." << endl;
}
```

```Output
The char_types and corresponding int_types are:
    ch1 = a corresponding to int1 = 97.
    ch2 = b corresponding to int1 = 98.
    ch3 = a corresponding to int1 = 97.

The recovered char_types and corresponding int_types are:
    recovered ch1 = a from int1 = 97.
    recovered ch2 = b from int2 = 98.

The recovered char_type of ch1 is equal to the original ch1.
The recovered char_type of ch2 is equal to the original ch2.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
