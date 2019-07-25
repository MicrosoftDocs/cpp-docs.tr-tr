---
title: char_traits Yapısı
ms.date: 05/07/2019
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
helpviewer_keywords:
- char_traits struct
- char_traits class
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
ms.openlocfilehash: ea5f53fd77545713dfcc6a969f1c172d89f8e460
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459031"
---
# <a name="chartraits-struct"></a>char_traits Yapısı

Char_traits yapısı bir karakterle ilişkili öznitelikleri açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
struct char_traits;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Öğe veri türü.

## <a name="remarks"></a>Açıklamalar

Şablon yapısı, türü `CharType`için çeşitli karakter nitelikleri tanımlar. Şablon sınıfı [basic_string](../standard-library/basic-string-class.md) ve [basic_ios](../standard-library/basic-ios-class.md)dahil olmak üzere çeşitli ıostream şablon sınıfları, türündeki `CharType`öğeleri işlemek için bu bilgileri kullanın. Böyle bir öğe türü açık oluşturma veya yok etme gerektirmemelidir. Beklenen semantiklere sahip bir varsayılan Oluşturucu, kopya Oluşturucusu ve atama işleci sağlamalıdır. Bit düzeyinde bir kopya, atamayla aynı etkiye sahip olmalıdır. Yapı char_traits üye işlevlerinin hiçbiri özel durum oluşturabilir.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir karakter türü.|
|[int_type](#int_type)|Bir karakter `char_type` türü veya dosya sonu (EOF) karakteri temsil eden bir tamsayı türü.|
|[off_type](#off_type)|Akıştaki konumlar arasındaki uzaklıkları temsil eden bir tamsayı türü.|
|[pos_type](#pos_type)|Akıştaki pozisyonları temsil eden bir tamsayı türü.|
|[state_type](#state_type)|Akıştaki çok baytlı karakterler için dönüştürme durumunu temsil eden bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ata](#assign)|Diğerine bir karakter değeri atar.|
|[Karşılaştır](#compare)|İki dizelerdeki belirtilen sayıda karaktere kadar karşılaştırır.|
|[kopya](#copy)|Belirtilen sayıda karakteri bir dizeden diğerine kopyalar. Kullanım dışı. Bunun yerine [char_traits:: _Copy_s](#copy_s) kullanın.|
|[_Copy_s](#copy_s)|Belirtilen sayıda karakteri bir dizeden diğerine kopyalar.|
|[eof](#eof)|Dosya sonu (EOF) karakterini döndürür.|
|[EQ](#eq)|İki `char_type` karakterin eşit olup olmadığını sınar.|
|[eq_int_type](#eq_int_type)|Olarak `int_type`temsil edilen iki karakterin eşit olup olmadığını sınar.|
|[bilgi](#find)|Belirli bir karakterin karakter aralığında ilk oluşumunu arar.|
|[length](#length)|Bir dizenin uzunluğunu döndürür.|
|[itme](#lt)|Bir karakterin diğerinden daha küçük olup olmadığını test eder.|
|[geçiş](#move)|Bir dizideki belirtilen sayıda karakteri başka, olası örtüşme, sırayla kopyalar. Kullanım dışı. Bunun yerine [char_traits:: _Move_s](#move_s) kullanın.|
|[_Move_s](#move_s)|Bir dizideki belirtilen sayıda karakteri başka, olası örtüşme, sırayla kopyalar.|
|[not_eof](#not_eof)|Bir karakterin dosya sonu (EOF) karakteri olup olmadığını sınar.|
|[to_char_type](#to_char_type)|Karakteri karşılık gelen `char_type` karaktere dönüştürür ve sonucu döndürür. `int_type`|
|[to_int_type](#to_int_type)|Karakteri karşılık gelen `int_type` karaktere dönüştürür ve sonucu döndürür. `char_type`|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<dize >

**Ad alanı:** std

## <a name="assign"></a>char_traits:: Assign

Bir dizedeki bir veya bir dizi öğe aralığına bir karakter değeri atar.

```cpp
static void assign(char_type& _CharTo,
    const char_type& _CharFrom);

static char_type *assign(char_type* strTo,
    size_t _Num,
    char_type _CharFrom);
```

### <a name="parameters"></a>Parametreler

**_** *Charfrom* Değeri atanacak olan karakter.

*_CharTo*\
Karakter değerine atanacak olan öğe.

*strTo*\
İlk öğelerine karakter değerleri atanacak olan dize veya karakter dizisi.

*_Num*\
Değerlere atanacak olan öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İkinci üye işlevi, ilk *_Num* öğelerine *_CharFrom*değeri atanmış olan dizeye bir işaretçi döndürür.

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

## <a name="char_type"></a>char_traits::char_type

Bir karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`için bir eş anlamlı.

### <a name="example"></a>Örnek

Bildirme ve kullanma `char_type`hakkında bir örnek için bkz. [kopya](#copy) örneği.

## <a name="compare"></a>char_traits:: Compare

İki dizelerdeki belirtilen sayıda karaktere kadar karşılaştırır.

```cpp
static int compare(const char_type* str1,
    const char_type* str2,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

*str1*\
Birbirleriyle Karşılaştırılacak iki dizenin ilki.

*str2*\
İki dizenin birbirleriyle karşılaştırılacağı ikinci dize.

*_Num*\
Karşılaştırılacak dizelerin içindeki öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Birinci dize ikinci dizeden küçükse negatif bir değer, iki dize eşitse 0 veya birinci dize ikinci dizeden büyükse pozitif bir değer.

### <a name="remarks"></a>Açıklamalar

Dizeler arasındaki karşılaştırma öğe öğesine göre yapılır, eşitlik için ilk test ediliyor ve sonra dizi testlerinde öğe çifti eşit değilse, daha az test edilir.

İki dize bir Aralık üzerinde eşit olarak karşılaştırırsanız, biri diğerinin daha uzunsa, ikisinin de daha kısa olması daha küçüktür.

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

## <a name="copy"></a>char_traits:: Copy

Belirtilen sayıda karakteri bir dizeden diğerine kopyalar.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir. Bunun yerine [char_traits:: _Copy_s](#copy_s) kullanmayı göz önünde bulundurun.

```cpp
static char_type *copy(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

*_To*\
' Nin kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisinin başındaki öğesi.

*_Kimden*\
Kopyalanacak kaynak dizenin veya karakter dizisinin başındaki öğesi.

*_Num*\
Kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisine kopyalanmış ilk öğe.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef karakter dizileri çakışmamalıdır.

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

## <a name="copy_s"></a>char_traits::_Copy_s

Belirtilen sayıda karakteri bir dizeden diğerine kopyalar.

```cpp
static char_type *_Copy_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Parametreler

*HD*\
Kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisi.

*dest_size*\
*Hedef*boyutu. Char ise, bu boyut bayt olarak olur.  `char_type` Wchar_t ise, bu boyut sözcüklerdir.  `char_type`

*_Kimden*\
Kopyalanacak kaynak dize veya karakter dizisi.

*biriktirme*\
Kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisi.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef karakter dizileri çakışmamalıdır.

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

## <a name="eof"></a>char_traits:: EOF

Dosya sonu (EOF) karakterini döndürür.

```cpp
static int_type eof();
```

### <a name="return-value"></a>Dönüş Değeri

EOF karakteri.

### <a name="remarks"></a>Açıklamalar

Dosya sonunu temsil eden bir değer (örneğin, EOF veya WEOF).

Standart C++ , bu değerin geçerli `char_type` bir değere karşılık gelmesi gerektiğini belirtir. Microsoft C++ derleyicisi **char**türü için bu kısıtlamayı uygular, ancak **wchar_t**türü için kullanmaz. Aşağıdaki örnek bunu gösterir.

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

## <a name="eq"></a>char_traits:: EQ

İki `char_type` karakterin eşit olup olmadığını sınar.

```cpp
static bool eq(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

*_Ch1*\
Eşitlik için sınanacak ilk iki karakter.

*_Ch2*\
Eşitlik için test edilecek iki karakterden oluşan ikincisi.

### <a name="return-value"></a>Dönüş Değeri

ilk karakter ikinci karaktere eşitse **true** ; Aksi halde **yanlış**.

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

## <a name="eq_int_type"></a>char_traits::eq_int_type

Olarak `int_type`temsil edilen iki karakterin eşit olup olmadığını sınar.

```cpp
static bool eq_int_type(const int_type& _Ch1, const int_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

*_Ch1*\
Eşitlik `int_type`için test edilecek iki karakterden ilki.

*_Ch2*\
Eşitlik `int_type`için test edilecek iki karakterin saniyesi.

### <a name="return-value"></a>Dönüş Değeri

ilk karakter ikinci karaktere eşitse **true** ; Aksi halde **yanlış**.

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

## <a name="find"></a>char_traits:: Find

Belirli bir karakterin karakter aralığında ilk oluşumunu arar.

```cpp
static const char_type* find(const char_type* str,
    size_t _Num,
    const char_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Aranacak dizedeki ilk karakter.

*_Num*\
Aranacak aralıktaki birinciden itibaren sayım yapan konum sayısı.

*_Ch*\
Aralıkta Aranacak olan karakter.

### <a name="return-value"></a>Dönüş Değeri

Bir eşleşme bulunursa aralıktaki belirtilen karakterin ilk oluşumuna yönelik bir işaretçi. Aksi takdirde, bir null işaretçi.

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

## <a name="int_type"></a>char_traits::int_type

Bir karakter `char_type` türü veya dosya sonu (EOF) karakteri temsil eden bir tamsayı türü.

```cpp
typedef long int_type;
```

### <a name="remarks"></a>Açıklamalar

Özgün değeri değiştirmeksizin, bu tür `CharType` `int_type` bir değeri daha sonra yeniden öğesine `CharType` dönüştürme yazmak mümkün olmalıdır.

### <a name="example"></a>Örnek

Bildirme ve kullanma `int_type`hakkında bir örnek için bkz. [eq_int_type](#eq_int_type) .

## <a name="length"></a>char_traits:: length

Bir dizenin uzunluğunu döndürür.

```cpp
static size_t length(const char_type* str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Uzunluğu ölçülecek olan C dizesi.

### <a name="return-value"></a>Dönüş Değeri

Dizideki, null Sonlandırıcı dahil değil ölçülen öğe sayısı.

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

## <a name="lt"></a>char_traits:: lt

Bir karakterin diğerinden daha küçük olup olmadığını test eder.

```cpp
static bool lt(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

*_Ch1*\
Daha az test edilecek iki karakterden ilki.

*_Ch2*\
Daha az test edilecek iki karakterin ikinci sayısı.

### <a name="return-value"></a>Dönüş Değeri

ilk karakter ikinci karakterden küçükse **doğru** ; Aksi halde **yanlış**.

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

## <a name="move"></a>char_traits:: Move

Bir dizideki belirtilen sayıda karakteri diğerine, muhtemelen çakışan bir diziye kopyalar.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir. Bunun yerine [char_traits:: _Move_s](#move_s) kullanmayı göz önünde bulundurun.

```cpp
static char_type *move(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

*_To*\
' Nin kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisinin başındaki öğesi.

*_Kimden*\
Kopyalanacak kaynak dizenin veya karakter dizisinin başındaki öğesi.

*_Num*\
Kaynak dizeden kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter dizisini  almak için hedeflenen dize veya karakter dizisine kopyalanan Ilk öğe _.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef çakışmayabilir.

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

## <a name="move_s"></a>char_traits::_Move_s

Bir dizideki belirtilen sayıda karakteri diğerine, muhtemelen çakışan bir diziye kopyalar.

```cpp
static char_type *_Move_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Parametreler

*HD*\
' Nin kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisinin başındaki öğesi.

*dest_size*\
*Hedef*boyutu. Char ise, bu bayt olarak ayarlanır.  `char_type` Wchar_t ise, bu, sözcüklerdir.  `char_type`

*_Kimden*\
Kopyalanacak kaynak dizenin veya karakter dizisinin başındaki öğesi.

*biriktirme*\
Kaynak dizeden kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk öğe *hedef* , kopyalanmış karakter dizisini almak için hedeflenen dize veya karakter dizisine kopyalanmış.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef çakışmayabilir.

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

## <a name="not_eof"></a>char_traits::not_eof

Bir karakterin dosya sonu (EOF) karakteri olup olmadığını veya EOF olduğunu sınar.

```cpp
static int_type not_eof(const int_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
EOF karakteri olup olmadığı için `int_type` sınanacak olarak temsil edilen karakter.

### <a name="return-value"></a>Dönüş Değeri

Karakterin ,`int_type` EOF karakteriyle aynı değere eşit olmaması halinde, sınanan karakterin temsili.`int_type`

Karakter `int_type` değeri EOF `int_type` değerine eşitse, **false**olarak ayarlanır.

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

## <a name="off_type"></a>char_traits::off_type

Akıştaki konumlar arasındaki uzaklıkları temsil eden bir tamsayı türü.

```cpp
typedef streamoff off_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, çeşitli akış konumlandırma işlemlerinde yer alan bayt sapmasını depolayabilen bir nesneyi tanımlayan işaretli bir tamsayıdır. Genellikle [streamoff](../standard-library/ios-typedefs.md#streamoff)için bir eş anladır, ancak temelde bu türle aynı özelliklere sahiptir.

## <a name="pos_type"></a>char_traits::p os_type

Akıştaki pozisyonları temsil eden bir tamsayı türü.

```cpp
typedef streampos pos_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir akış içinde rastgele bir dosya konumu göstergesini geri yüklemek için gereken tüm bilgileri depolayabilen bir nesneyi tanımlar. Genellikle [streampos](../standard-library/ios-typedefs.md#streampos)için bir eş anladır, ancak herhangi bir durumda temelde bu türle aynı özelliklere sahiptir.

## <a name="state_type"></a>char_traits::state_type

Akıştaki çok baytlı karakterler için dönüştürme durumunu temsil eden bir tür.

```cpp
typedef implementation-defined state_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir dönüştürme durumunu temsil eden bir nesneyi tanımlar. Genellikle için `mbstate_t`bir eş anlamlı olur, ancak herhangi bir durumda bu tür ile temelde aynı özelliklere sahiptir.

## <a name="to_char_type"></a>char_traits::to_char_type

Karakteri karşılık gelen `char_type` karaktere dönüştürür ve sonucu döndürür. `int_type`

```cpp
static char_type to_char_type(const int_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Olarak temsil edilecek `int_type`karakter. `char_type`

### <a name="return-value"></a>Dönüş Değeri

`int_type` Karaktere karşılık gelen karakter. `char_type`

Belirtilemeyen bir sonuç veren bir *_Ch* değeri.

### <a name="remarks"></a>Açıklamalar

Dönüştürme işlemleri [to_int_type](#to_int_type) ve `to_char_type` birbirlerine ters, böylece:

`to_int_type` ( `to_char_type` ( *x* ) ) == *x*

herhangi bir `int_type` *x* ve

`to_char_type` ( `to_int_type` ( *x* ) ) == *x*

herhangi bir `char_type` *x*için.

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

## <a name="to_int_type"></a>char_traits::to_int_type

Karakteri karşılık gelen `int_type` karaktere dönüştürür ve sonucu döndürür. `char_type`

```cpp
static int_type to_int_type(const char_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Olarak temsil edilecek `char_type`karakter. `int_type`

### <a name="return-value"></a>Dönüş Değeri

`char_type` Karaktere karşılık gelen karakter. `int_type`

### <a name="remarks"></a>Açıklamalar

Dönüştürme işlemleri `to_int_type` ve [to_char_type](#to_char_type) birbirlerine ters kaydedilir, böylece:

`to_int_type` ( `to_char_type` ( *x* ) ) == *x*

herhangi bir `int_type` *x*için ve

`to_char_type` ( `to_int_type` ( *x* ) ) == *x*

herhangi bir `char_type` *x*için.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
