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
ms.openlocfilehash: 3d707ff963170b6b4f14ad1f04e9420b8062b520
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366699"
---
# <a name="char_traits-struct"></a>char_traits Yapısı

char_traits yapı, bir karakterle ilişkili öznitelikleri açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
struct char_traits;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Öğe veri türü.

## <a name="remarks"></a>Açıklamalar

Şablon yapı türü `CharType`için çeşitli karakter özelliklerini açıklar. Sınıf şablonu [basic_string](../standard-library/basic-string-class.md) yanı sıra [basic_ios](../standard-library/basic-ios-class.md)de dahil olmak üzere çeşitli iostream sınıfı `CharType`şablonları, türü öğeleri işlemek için bu bilgileri kullanın. Böyle bir eleman türü açık inşaat veya yıkım gerektirmemelidir. Varsayılan bir oluşturucu, bir kopya oluşturucu ve beklenen semantik ile bir atama işleci sağlaması gerekir. Bityönünde bir kopya, atamayla aynı etkiye sahip olmalıdır. Yapı char_traits üye işlevlerinin hiçbiri özel durum atamaz.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir karakter türü.|
|[Int_type](#int_type)|Bir tür `char_type` karakterini veya dosya sonu (EOF) karakterini temsil eden bir tamsayı türü.|
|[off_type](#off_type)|Akıştaki konumlar arasında uzaklıkları temsil edebilen bir tamsayı türü.|
|[pos_type](#pos_type)|Akıştaki pozisyonları temsil edebilen bir tamsayı türü.|
|[state_type](#state_type)|Akıştaki çok bayt karakterleri için dönüşüm durumunu temsil eden tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Atamak](#assign)|Bir karakter değerini diğerine atar.|
|[Karşılaştırmak](#compare)|İki dizedeki belirli sayıda karakterle karşılaştırır.|
|[Kopya](#copy)|Belirli sayıda karakteri bir dizeden diğerine kopyalar. Kullanım dışı. Bunun yerine [char_traits::_Copy_s](#copy_s) kullanın.|
|[_Copy_s](#copy_s)|Belirli sayıda karakteri bir dizeden diğerine kopyalar.|
|[eof](#eof)|Dosya sonu (EOF) karakterini döndürür.|
|[Eq](#eq)|İki `char_type` karakterin eşit olup olmadığını test eder.|
|[eq_int_type](#eq_int_type)|S olarak `int_type`temsil edilen iki karakterin eşit olup olmadığını test eder.|
|[find](#find)|Bir karakter aralığında belirli bir karakterin ilk oluşumunu arar.|
|[Uzun -luğu](#length)|Dize uzunluğunu döndürür.|
|[Teğmen](#lt)|Bir karakterin diğerinden küçük olup olmadığını sınar.|
|[Hareket](#move)|Belirli sayıda karakteri bir dizideki başka bir deyişle, olası çakışma, sırayla kopyalar. Kullanım dışı. bunun yerine [char_traits::_Move_s](#move_s) kullanın.|
|[_Move_s](#move_s)|Belirli sayıda karakteri bir dizideki başka bir deyişle, olası çakışma, sırayla kopyalar.|
|[not_eof](#not_eof)|Bir karakterin dosya sonu (EOF) karakteri olup olmadığını sınar.|
|[to_char_type](#to_char_type)|Bir `int_type` karakteri ilgili `char_type` karaktere dönüştürür ve sonucu döndürür.|
|[to_int_type](#to_int_type)|Bir `char_type` karakteri ilgili `int_type` karaktere dönüştürür ve sonucu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<dize>

**Ad alanı:** std

## <a name="char_traitsassign"></a><a name="assign"></a>char_traits::atama

Bir karakter değerini diğerine veya bir dizedeki bir dizi öğeye atar.

```cpp
static void assign(char_type& _CharTo,
    const char_type& _CharFrom);

static char_type *assign(char_type* strTo,
    size_t _Num,
    char_type _CharFrom);
```

### <a name="parameters"></a>Parametreler

**_** *CharFrom* Değeri atanacak karakter.

*_CharTo*\
Karakter değeri atanacak öğe.

*strTo*\
İlk öğeleri karakter değerleri atanacak dize veya karakter dizisi.

*_Num*\
Değerler atanacak öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

İkinci üye işlev, ilk *_Num* öğeleri *_CharFrom*değerleri atanmış dize için bir işaretçi döndürür.

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

## <a name="char_traitschar_type"></a><a name="char_type"></a>char_traits:char_type

Bir karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

### <a name="example"></a>Örnek

Nasıl bildirilir [copy](#copy) ve kullanılacağına `char_type`bir örnek için kopya örneği bakın.

## <a name="char_traitscompare"></a><a name="compare"></a>char_traits::karşılaştır

İki dizedeki belirli sayıda karakterle karşılaştırır.

```cpp
static int compare(const char_type* str1,
    const char_type* str2,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

*str1*\
İki dizenin ilki birbiriyle karşılaştırılır.

*str2*\
İki dizenin ikincisi birbiriyle karşılaştırılır.

*_Num*\
Karşılanacak dizelerdeki öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk dize ikinci dizeden küçükse negatif değer, iki dize eşitse 0 veya ilk dize ikinci dizeden büyükse pozitif değer.

### <a name="remarks"></a>Açıklamalar

Dizeleri arasındaki karşılaştırma eleman tarafından eleman, eşitlik için ilk test yapılır ve daha sonra, dizi testleri elemanları bir çift eşit değilse, daha az için test edilir.

İki dize bir aralık üzerinde eşit karşılaştırır, ancak biri diğerinden daha uzunsa, ikinin kısası daha uzunolandan daha azdır.

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

## <a name="char_traitscopy"></a><a name="copy"></a>char_traits::kopyala

Belirli sayıda karakteri bir dizeden diğerine kopyalar.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir. bunun [yerine char_traits::_Copy_s](#copy_s) kullanmayı düşünün.

```cpp
static char_type *copy(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

*_To*\
Kopyalanan karakter dizisini almayı hedefleyen dize veya karakter dizisinin başındaki öğe.

*_From*\
Kopyalanacak kaynak dize veya karakter dizisinin başındaki öğe.

*_Num*\
Kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter dizisini almak için hedeflenen dize veya karakter dizisine kopyalanan ilk öğe.

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

## <a name="char_traits_copy_s"></a><a name="copy_s"></a>char_traits:_Copy_s

Belirli sayıda karakteri bir dizeden diğerine kopyalar.

```cpp
static char_type *_Copy_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Parametreler

*Dest*\
Kopyalanan karakter dizisini almayı hedefleyen dize veya karakter dizisi.

*dest_size*\
*Dest*boyutu . Char `char_type` **char**ise, o zaman bu boyutta bayt olduğunu. Wchar_t `char_type` **wchar_t**ise, bu boyut kelimelerle ifade edilir.

*_From*\
Kopyalanacak kaynak dize veya karakter dizisi.

*Sayısı*\
Kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter dizisini almayı hedefleyen dize veya karakter dizisi.

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

## <a name="char_traitseof"></a><a name="eof"></a>char_traits::eof

Dosya sonu (EOF) karakterini döndürür.

```cpp
static int_type eof();
```

### <a name="return-value"></a>Dönüş Değeri

EOF karakteri.

### <a name="remarks"></a>Açıklamalar

Dosya sonunu temsil eden bir değer (EOF veya WEOF gibi).

C++ standardı, bu değerin geçerli `char_type` bir değere karşılık olmaması gerektiğini belirtir. Microsoft C++ derleyicisi bu kısıtlamayı tür **char**için zorlar, ancak tür **wchar_t**için değil. Aşağıdaki örnek bunu gösterir.

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

## <a name="char_traitseq"></a><a name="eq"></a>char_traits::eq

İki `char_type` karakterin eşit olup olmadığını test eder.

```cpp
static bool eq(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

*_Ch1*\
Eşitlik için test edilecek iki karakterden ilki.

*_Ch2*\
Eşitlik için test edilecek iki karakterden ikincisi.

### <a name="return-value"></a>Dönüş Değeri

ilk karakter ikinci karaktere eşitse **doğrudur;** aksi takdirde **yanlış**.

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

## <a name="char_traitseq_int_type"></a><a name="eq_int_type"></a>char_traits:eq_int_type

S olarak `int_type`temsil edilen iki karakterin eşit olup olmadığını test eder.

```cpp
static bool eq_int_type(const int_type& _Ch1, const int_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

*_Ch1*\
S olarak `int_type`eşitlik için test edilecek iki karakterden ilki.

*_Ch2*\
S olarak `int_type`eşitlik için test edilecek iki karakterden ikincisi.

### <a name="return-value"></a>Dönüş Değeri

ilk karakter ikinci karaktere eşitse **doğrudur;** aksi takdirde **yanlış**.

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

## <a name="char_traitsfind"></a><a name="find"></a>char_traits::bul

Bir karakter aralığında belirli bir karakterin ilk oluşumunu arar.

```cpp
static const char_type* find(const char_type* str,
    size_t _Num,
    const char_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*Str*\
Dizedeki ilk karakter aranır.

*_Num*\
Aranacak aralıktaki ilk konum sayısı.

*_Ch*\
Aralıkta aranacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Bir eşleşme bulunursa, aralıkta belirtilen karakterin ilk oluşumuna işaretçi; aksi takdirde, null işaretçi.

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

## <a name="char_traitsint_type"></a><a name="int_type"></a>char_traits:int_type

Bir tür `char_type` karakterini veya dosya sonu (EOF) karakterini temsil eden bir tamsayı türü.

```cpp
typedef long int_type;
```

### <a name="remarks"></a>Açıklamalar

Orijinal değeri `CharType` `int_type` `CharType` değiştirmeden sonra geri için türünün bir değeri yazmak mümkün olmalıdır.

### <a name="example"></a>Örnek

Nasıl bildirilir [eq_int_type](#eq_int_type) ve kullanılacağına `int_type`ilgili bir örnek için eq_int_type örneğine bakın.

## <a name="char_traitslength"></a><a name="length"></a>char_traits::uzunluk

Dize uzunluğunu döndürür.

```cpp
static size_t length(const char_type* str);
```

### <a name="parameters"></a>Parametreler

*Str*\
Uzunluğu ölçülecek olan C-dizesi.

### <a name="return-value"></a>Dönüş Değeri

Null terminator dahil değil, ölçülen dizideki öğelerin sayısı.

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

## <a name="char_traitslt"></a><a name="lt"></a>char_traits::lt

Bir karakterin diğerinden küçük olup olmadığını sınar.

```cpp
static bool lt(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Parametreler

*_Ch1*\
Daha az test edilecek iki karakter ilk.

*_Ch2*\
Daha az test edilecek iki karakterden ikincisi.

### <a name="return-value"></a>Dönüş Değeri

ilk karakter ikinci karakterden daha azise **doğrudur;** aksi takdirde **yanlış**.

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

## <a name="char_traitsmove"></a><a name="move"></a>char_traits::hareket et

Belirli sayıda karakteri bir dizideki başka bir, muhtemelen çakışan sıraya kopyalar.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir. Bunun yerine [char_traits::_Move_s](#move_s) kullanmayı düşünün.

```cpp
static char_type *move(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Parametreler

*_To*\
Kopyalanan karakter dizisini almayı hedefleyen dize veya karakter dizisinin başındaki öğe.

*_From*\
Kopyalanacak kaynak dize veya karakter dizisinin başındaki öğe.

*_Num*\
Kaynak dizeden kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter dizisini almak için hedeflenen dize veya karakter dizisine kopyalanan ilk öğe *_To.*

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

## <a name="char_traits_move_s"></a><a name="move_s"></a>char_traits::_Move_s

Belirli sayıda karakteri bir dizideki başka bir, muhtemelen çakışan sıraya kopyalar.

```cpp
static char_type *_Move_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Parametreler

*Dest*\
Kopyalanan karakter dizisini almayı hedefleyen dize veya karakter dizisinin başındaki öğe.

*dest_size*\
*Dest*boyutu . Char `char_type` **char**ise, o zaman bu bayt olduğunu. Eğer `char_type` **wchar_t**ise, o zaman bu kelimelerle.

*_From*\
Kopyalanacak kaynak dize veya karakter dizisinin başındaki öğe.

*Sayısı*\
Kaynak dizeden kopyalanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter dizisini almak için hedeflenen dize veya karakter dizisine *kopyalanan* ilk öğe.

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

## <a name="char_traitsnot_eof"></a><a name="not_eof"></a>char_traits:not_eof

Bir karakterin dosya sonu (EOF) karakteri mi yoksa EOF mi olduğunu sınar.

```cpp
static int_type not_eof(const int_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Karakter, EOF `int_type` karakteri olup olmadığı konusunda test edilecek bir karakter olarak temsil edilir.

### <a name="return-value"></a>Dönüş Değeri

Karakterin `int_type` temsili, eof `int_type` karakterine eşit değilse, test edilir.

Karakter `int_type` değeri EOF `int_type` değerine eşitse, **yanlış**.

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

## <a name="char_traitsoff_type"></a><a name="off_type"></a>char_traits::off_type

Akıştaki konumlar arasında uzaklıkları temsil edebilen bir tamsayı türü.

```cpp
typedef streamoff off_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, çeşitli akış konumlandırma işlemlerinde yer alan bir bayt ofset depolayabilir bir nesne açıklayan imzalı bir tamsayıdır. Genellikle [streamoff](../standard-library/ios-typedefs.md#streamoff)için eşanlamlı, ama aslında bu tür aynı özelliklere sahiptir.

## <a name="char_traitspos_type"></a><a name="pos_type"></a>char_traits::pos_tipi

Akıştaki pozisyonları temsil edebilen bir tamsayı türü.

```cpp
typedef streampos pos_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir akış içinde rasgele bir dosya konumu göstergesini geri yüklemek için gereken tüm bilgileri depolayabilen bir nesneyi açıklar. Genellikle [streampos](../standard-library/ios-typedefs.md#streampos)için eşanlamlı, ancak her durumda aslında bu tür olarak aynı özelliklere sahiptir.

## <a name="char_traitsstate_type"></a><a name="state_type"></a>char_traits:state_type

Akıştaki çok bayt karakterlerin dönüşüm durumunu temsil eden tür.

```cpp
typedef implementation-defined state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, dönüşüm durumunu temsil eden bir nesneyi açıklar. Genellikle bir eşanlamlı `mbstate_t`, ama her durumda aslında bu tür olarak aynı özelliklere sahiptir.

## <a name="char_traitsto_char_type"></a><a name="to_char_type"></a>char_traits:to_char_type

Bir `int_type` karakteri ilgili `char_type` karaktere dönüştürür ve sonucu döndürür.

```cpp
static char_type to_char_type(const int_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Temsil `int_type` edilecek karakter . `char_type`

### <a name="return-value"></a>Dönüş Değeri

`char_type` Karaktere karşılık gelen `int_type` karakter.

Bu şekilde temsil edilemeyen *_Ch* değeri belirtilmemiş bir sonuç verir.

### <a name="remarks"></a>Açıklamalar

Dönüştürme işlemleri [to_int_type](#to_int_type) to_int_type `to_char_type` ve birbirine ters, böylece:

`to_int_type`( `to_char_type` ( *x* ) ) = = *x*

herhangi `int_type` bir *x* ve

`to_char_type`( `to_int_type` ( *x* ) ) = = *x*

herhangi `char_type` bir *x*için .

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

## <a name="char_traitsto_int_type"></a><a name="to_int_type"></a>char_traits:to_int_type

Bir `char_type` karakteri ilgili `int_type` karaktere dönüştürür ve sonucu döndürür.

```cpp
static int_type to_int_type(const char_type& _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Temsil `char_type` edilecek karakter `int_type`.

### <a name="return-value"></a>Dönüş Değeri

`int_type` Karaktere karşılık gelen `char_type` karakter.

### <a name="remarks"></a>Açıklamalar

Dönüştürme işlemleri `to_int_type` ve [to_char_type](#to_char_type) birbirine terstir, böylece:

`to_int_type`( `to_char_type` ( *x* ) ) = = *x*

herhangi `int_type` bir *x*için , ve

`to_char_type`( `to_int_type` ( *x* ) ) = = *x*

herhangi `char_type` bir *x*için .

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
