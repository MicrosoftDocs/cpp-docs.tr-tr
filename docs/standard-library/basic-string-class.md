---
title: basic_string Sınıfı
ms.date: 11/12/2019
f1_keywords:
- xstring/std::basic_string
- xstring/std::basic_string::allocator_type
- xstring/std::basic_string::const_iterator
- xstring/std::basic_string::const_pointer
- xstring/std::basic_string::const_reference
- xstring/std::basic_string::const_reverse_iterator
- xstring/std::basic_string::difference_type
- xstring/std::basic_string::iterator
- xstring/std::basic_string::npos
- xstring/std::basic_string::pointer
- xstring/std::basic_string::reference
- xstring/std::basic_string::reverse_iterator
- xstring/std::basic_string::size_type
- xstring/std::basic_string::traits_type
- xstring/std::basic_string::value_type
- xstring/std::basic_string::append
- xstring/std::basic_string::assign
- xstring/std::basic_string::at
- xstring/std::basic_string::back
- xstring/std::basic_string::begin
- xstring/std::basic_string::c_str
- xstring/std::basic_string::capacity
- xstring/std::basic_string::cbegin
- xstring/std::basic_string::cend
- xstring/std::basic_string::clear
- xstring/std::basic_string::compare
- xstring/std::basic_string::copy
- xstring/std::basic_string::crbegin
- xstring/std::basic_string::crend
- xstring/std::basic_string::_Copy_s
- xstring/std::basic_string::data
- xstring/std::basic_string::empty
- xstring/std::basic_string::end
- xstring/std::basic_string::erase
- xstring/std::basic_string::find
- xstring/std::basic_string::find_first_not_of
- xstring/std::basic_string::find_first_of
- xstring/std::basic_string::find_last_not_of
- xstring/std::basic_string::find_last_of
- xstring/std::basic_string::front
- xstring/std::basic_string::get_allocator
- xstring/std::basic_string::insert
- xstring/std::basic_string::length
- xstring/std::basic_string::max_size
- xstring/std::basic_string::pop_back
- xstring/std::basic_string::push_back
- xstring/std::basic_string::rbegin
- xstring/std::basic_string::rend
- xstring/std::basic_string::replace
- xstring/std::basic_string::reserve
- xstring/std::basic_string::resize
- xstring/std::basic_string::rfind
- xstring/std::basic_string::shrink_to_fit
- xstring/std::basic_string::size
- xstring/std::basic_string::substr
- xstring/std::basic_string::swap
helpviewer_keywords:
- std::basic_string [C++]
- std::basic_string [C++], allocator_type
- std::basic_string [C++], const_iterator
- std::basic_string [C++], const_pointer
- std::basic_string [C++], const_reference
- std::basic_string [C++], const_reverse_iterator
- std::basic_string [C++], difference_type
- std::basic_string [C++], iterator
- std::basic_string [C++], npos
- std::basic_string [C++], pointer
- std::basic_string [C++], reference
- std::basic_string [C++], reverse_iterator
- std::basic_string [C++], size_type
- std::basic_string [C++], traits_type
- std::basic_string [C++], value_type
- std::basic_string [C++], append
- std::basic_string [C++], assign
- std::basic_string [C++], at
- std::basic_string [C++], back
- std::basic_string [C++], begin
- std::basic_string [C++], c_str
- std::basic_string [C++], capacity
- std::basic_string [C++], cbegin
- std::basic_string [C++], cend
- std::basic_string [C++], clear
- std::basic_string [C++], compare
- std::basic_string [C++], copy
- std::basic_string [C++], crbegin
- std::basic_string [C++], crend
- std::basic_string [C++], _Copy_s
- std::basic_string [C++], data
- std::basic_string [C++], empty
- std::basic_string [C++], end
- std::basic_string [C++], erase
- std::basic_string [C++], find
- std::basic_string [C++], find_first_not_of
- std::basic_string [C++], find_first_of
- std::basic_string [C++], find_last_not_of
- std::basic_string [C++], find_last_of
- std::basic_string [C++], front
- std::basic_string [C++], get_allocator
- std::basic_string [C++], insert
- std::basic_string [C++], length
- std::basic_string [C++], max_size
- std::basic_string [C++], pop_back
- std::basic_string [C++], push_back
- std::basic_string [C++], rbegin
- std::basic_string [C++], rend
- std::basic_string [C++], replace
- std::basic_string [C++], reserve
- std::basic_string [C++], resize
- std::basic_string [C++], rfind
- std::basic_string [C++], shrink_to_fit
- std::basic_string [C++], size
- std::basic_string [C++], substr
- std::basic_string [C++], swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: 0aca4e8b8a446eb773f6ba4efaeb4a0a6c9644af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376731"
---
# <a name="basic_string-class"></a>basic_string Sınıfı

Bir tür `basic_string` nesnesi tarafından denetlenir diziler Standart C++ dize sınıfıdır ve genellikle dizeleri olarak adlandırılır, ancak C++ Standart Kitaplığı boyunca kullanılan null-sonlandırılan C stili dizeleri ile karıştırılmamalıdır. Standart C++ dizesi, karşılaştırma ve concatenation işlemleri, yinelemeler, C++ Standart Kitaplık algoritmaları ve sınıf ayırıcı sıyrık yönetilen bellekile kopyalama ve atama gibi dizelerin normal türler olarak kullanılmasını sağlayan bir kapsayıcıdır. Standart C++ dizesini null-terminatedli C stili dizesine dönüştürmeniz gerekiyorsa, [basic_string:c_str](#c_str) üyesini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_string;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Dizede depolanacak tek bir karakterin veri türü. C++ Standart Kitaplığı, bu sınıf şablonunun uzmanlıklarını sağlar, **türü**char , [wstring](../standard-library/string-typedefs.md#wstring), **wchar_t**için `char16_t` [, u16string](../standard-library/string-typedefs.md#u16string) `char32_t`için , ve [u32string](../standard-library/string-typedefs.md#u32string) için öğeler için tür tanımları [dize](../standard-library/string-typedefs.md#string) ile .

*Özellik*\
Bir basic_string uzmanlık `CharType` öğelerinin çeşitli önemli özellikleri sınıf `Traits`tarafından açıklanmıştır. Varsayılan değer `char_traits` <  `CharType`>.

*Ayırıcı*\
Dize ayırma ve bellek deallocation hakkında ayrıntıları kapsülleyen depolanan ayırıcı nesneyi temsil eden türü. Varsayılan değer **tahsis>.** <  `CharType`

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_string](#basic_string)|Boş veya belirli karakterler tarafından başharfe çevrilmiş veya başka bir dize nesnesinin veya C dizesinin tamamının veya bir kısmının kopyası olan bir dize oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Dize nesnesinin `allocator` sınıfını temsil eden bir tür.|
|[const_iterator](#const_iterator)|Dizedeki bir **const** öğesine erişebilen ve okuyabilen rasgele erişim yineleyici sağlayan bir tür.|
|[Const_pointer](#const_pointer)|Bir dizedeki **const** öğesine işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|**Const** işlemleri okumak ve gerçekleştirmek için bir dizede depolanan **bir const** öğesine başvuru sağlayan bir tür.|
|[Const_reverse_iterator](#const_reverse_iterator)|Dizedeki herhangi bir **const** öğeyi okuyabilen rasgele erişim yinelemesi sağlayan bir tür.|
|[difference_type](#difference_type)|Aynı dize içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür.|
|[Yineleyici](#iterator)|Bir dizedeki herhangi bir öğeyi okuyabilen veya değiştirebilen rasgele erişim yineleyici sağlayan bir tür.|
|[npos](#npos)|Bir arama işlevi başarısız olduğunda "bulunamadı" veya "kalan tüm karakterleri" gösteren -1'e başlalaşım bir integral değeri.|
|[pointer](#pointer)|Dize veya karakter dizisindeki bir karakter öğesine işaretçi sağlayan tür.|
|[Başvuru](#reference)|Dizede depolanan bir öğeye başvuru sağlayan bir tür.|
|[Reverse_iterator](#reverse_iterator)|Ters dizedeki bir öğeyi okuyabilen veya değiştirebilen rasgele erişim yineleyicisağlayan bir tür.|
|[size_type](#size_type)|Bir dizedeki öğe sayısı için imzalanmamış integral türü.|
|[traits_type](#traits_type)|Bir dize de depolanan öğelerin karakter özellikleri için bir tür.|
|[value_type](#value_type)|Dizede depolanan karakter türünü temsil eden bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Ekleme](#append)|Bir dize sonuna karakterler ekler.|
|[Atamak](#assign)|Bir dizenin içeriğine yeni karakter değerleri atar.|
|[at](#at)|Dizede belirli bir konumda öğeye bir başvuru verir.|
|[Geri](#back)||
|[Başlamak](#begin)|Dizedeki ilk öğeyi ele alan bir yineleyici döndürür.|
|[c_str](#c_str)|Bir dize içeriğini C stili, null-sonlandırılan dize olarak dönüştürür.|
|[Kapasite](#capacity)|Dize bellek ayırma artırmadan bir dize depolanabilir elemanların en büyük sayısını döndürür.|
|[cbegin](#cbegin)|Dizedeki ilk öğeyi ele alan bir const yineleyici döndürür.|
|[cend](#cend)|Bir dizedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[Temizleyin](#clear)|Dizedeki tüm öğeleri siler.|
|[Karşılaştırmak](#compare)|İki dizenin eşit mi yoksa biri lexicographically diğerinden daha az mı olduğunu belirlemek için bir dize yi belirtilen dizeyle karşılaştırır.|
|[Kopya](#copy)|Kaynak dizedeki dizilenmiş bir konumdan hedef karakter dizisine en fazla belirli sayıda karakter kopyalar. Kullanım dışı. bunun yerine [basic_string::_Copy_s](#copy_s) kullanın.|
|[crbegin](#crbegin)|Ters dizedeki ilk öğeyi ele alan bir const yineleyici döndürür.|
|[crend](#crend)|Ters dizedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.|
|[_Copy_s](#copy_s)|Kaynak dizedeki dizilenmiş bir konumdan hedef karakter dizisine en fazla belirli sayıda karakter kopyalar.|
|[Veri](#data)|Bir dizenin içeriğini bir karakter dizisine dönüştürür.|
|[empty](#empty)|Dize karakter içerip içermesini sızır|
|[Son -unda](#end)|Bir dizedeki son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.|
|[Silmek](#erase)|Bir dizedeki bir öğeyi veya dizi öğeyi belirli bir konumdan kaldırır.|
|[find](#find)|Belirli bir karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için bir dizeyi ileri yönde arar.|
|[find_first_not_of](#find_first_not_of)|Belirli bir dize herhangi bir öğe olmayan ilk karakter için bir dize ile arar.|
|[find_first_of](#find_first_of)|Belirtilen dizedeki herhangi bir öğeyle eşleşen ilk karakteri bir dize de arar.|
|[find_last_not_of](#find_last_not_of)|Belirli bir dize herhangi bir öğesi olmayan son karakter için bir dize ile arar.|
|[find_last_of](#find_last_of)|Belirtilen bir dize öğesi olan son karakteri bir dize ile arar.|
|[Ön](#front)|Bir dizedeki ilk öğeye başvuru verir.|
|[Get_allocator](#get_allocator)|Dize oluşturmak `allocator` için kullanılan nesnenin bir kopyasını döndürür.|
|[Ekle](#insert)|Belirli bir konumda dize içine bir öğe veya bir dizi öğe veya öğe aralığı ekler.|
|[Uzun -luğu](#length)|Bir dizedeki geçerli öğe sayısını döndürür.|
|[max_size](#max_size)|Bir dize içerebileceği maksimum karakter sayısını döndürür.|
|[pop_back](#pop_back)|Dize son öğesini siler.|
|[push_back](#push_back)|Dize sonuna bir öğe ekler.|
|[rbegin](#rbegin)|Ters dizedeki ilk öğeye bir yineleyici döndürür.|
|[Rend](#rend)|Ters bir dizedeki son öğenin hemen ötesine işaret eden bir yineleyici döndürür.|
|[Değiştirmek](#replace)|Belirli bir konumdaki bir dizedeki öğeleri, diğer aralıklardan veya dizeleri veya C dizelerinden kopyalanan belirtilen karakterler veya karakterlerle değiştirir.|
|[Rezerve et](#reserve)|Dize kapasitesini en az belirtilen sayı kadar büyük bir sayıya ayarlar.|
|[Yeni -den boyutlandırmak](#resize)|Bir dize için yeni bir boyut belirtir, gerektiğinde öğeleri ekler veya siler.|
|[rfind](#rfind)|Belirli bir karakter dizisiyle eşleşen bir alt dizeilk oluşumu için geriye doğru bir yönde bir dize arar.|
|[shrink_to_fit](#shrink_to_fit)|Dizenin fazla kapasitesini atar.|
|[Boyutu](#size)|Bir dizedeki geçerli öğe sayısını döndürür.|
|[Substr](#substr)|Belirli bir konumdan başlayarak bir dizeden en fazla belirli sayıda karakterin bir alt dizesini kopyalar.|
|[Takas](#swap)|İki dizenin içeriğini değiştirin.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç+=](#op_add_eq)|Karakterleri bir dize ekler.|
|[işleç=](#op_eq)|Bir dizenin içeriğine yeni karakter değerleri atar.|
|[operatör&#91;&#93;](#op_at)|Bir dize içinde belirtilen bir dizin ile karaktere bir başvuru sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir [işlevden max_size](#max_size) öğelerden daha uzun bir dizi oluşturması istenirse, işlev [length_error](../standard-library/length-error-class.md)türünden bir nesne atarak bir uzunluk hatası bildirir.

Denetlenmeyen dizinin öğelerini belirleyen başvurular, işaretçiler ve yineleyiciler, denetlenmeyen sırayı değiştiren bir işleve yapılan herhangi bir çağrıdan veya **const** olmayan bir üye işleve ilk çağrıdan sonra geçersiz olabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<dize>

**Ad alanı:** std

## <a name="basic_stringallocator_type"></a><a name="allocator_type"></a>basic_string:allocator_type

Bir dize nesnesi için ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Allocator`ile eş anlamlıdır.

### <a name="example"></a>Örnek

```cpp
// basic_string_allocator_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects
   // that use the default allocator.
   string s1;
   basic_string <char>::allocator_type xchar = s1.get_allocator( );
   // You can now call functions on the allocator class xchar used by s1
}
```

## <a name="basic_stringappend"></a><a name="append"></a>basic_string::ek

Bir dize sonuna karakterler ekler.

```cpp
basic_string<CharType, Traits, Allocator>& append(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& append(
    const value_type* ptr,
    size_type count);

basic_string<CharType, Traits, Allocator>& append(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset,
    size_type count);

basic_string<CharType, Traits, Allocator>& append(
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& append(
    size_type count,
    value_type char_value);

template <class InputIterator>
basic_string<CharType, Traits, Allocator>& append(
    InputIterator first,
    InputIterator last);

basic_string<CharType, Traits, Allocator>& append(
    const_pointer first,
    const_pointer last);

basic_string<CharType, Traits, Allocator>& append(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
C-dizesi eklenecek.

*Str*\
Karakterleri eklenecek dize.

*Uzaklık*\
Kaynak dizesinin karakterleri sağlayan bölümünün dizini eklenecek.

*Sayısı*\
Kaynak dizesinden en fazla eklenecek karakter sayısı.

*char_value*\
Eklenecek karakter değeri.

*Ilk*\
Aralıktaki ilk öğeyi ele alan bir giriş yineleyicisi eklenecek.

*Son*\
Bir giriş yineleyici, const_pointer veya const_iterator, eklenecek aralıktaki son öğenin ötesindeki öğenin konumunu ele alıyor.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev tarafından geçirilen karakterlerle eklenen dize nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Karakterler [işleç+=](#op_add_eq) veya üye işlevler `append` veya [push_back](#push_back)kullanılarak bir dize eklenebilir. `operator+=`birden çok bağımsız değişkenli üye `append` işlev eklemek için dize belirli bir bölümünün belirtilmesine izin verirken, tek bağımsız değişken değerleri ekler.

### <a name="example"></a>Örnek

```cpp
// basic_string_append.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // appending a C-string to a string
   string str1a ( "Hello " );
   cout << "The original string str1 is: " << str1a << endl;
   const char *cstr1a = "Out There ";
   cout << "The C-string cstr1a is: " << cstr1a << endl;
   str1a.append ( cstr1a );
   cout << "Appending the C-string cstr1a to string str1 gives: "
        << str1a << "." << endl << endl;

   // The second member function
   // appending part of a C-string to a string
   string str1b ( "Hello " );
   cout << "The string str1b is: " << str1b << endl;
   const char *cstr1b = "Out There ";
   cout << "The C-string cstr1b is: " << cstr1b << endl;
   str1b.append ( cstr1b , 3 );
   cout << "Appending the 1st part of the C-string cstr1b "
        << "to string str1 gives: " << str1b << "."
        << endl << endl;

   // The third member function
   // appending part of one string to another
   string str1c ( "Hello " ), str2c ( "Wide World " );
   cout << "The string str2c is: " << str2c << endl;
   str1c.append ( str2c , 5 , 5 );
   cout << "The appended string str1 is: "
        << str1c << "." << endl << endl;

   // The fourth member function
   // appending one string to another in two ways,
   // comparing append and operator [ ]
   string str1d ( "Hello " ), str2d ( "Wide " ), str3d ( "World " );
   cout << "The  string str2d is: " << str2d << endl;
   str1d.append ( str2d );
   cout << "The appended string str1d is: "
        << str1d << "." << endl;
   str1d += str3d;
   cout << "The doubly appended strig str1 is: "
        << str1d << "." << endl << endl;

   // The fifth member function
   // appending characters to a string
   string str1e ( "Hello " );
   str1e.append ( 4 , '!' );
   cout << "The string str1 appended with exclamations is: "
        << str1e << endl << endl;

   // The sixth member function
   // appending a range of one string to another
   string str1f ( "Hello " ), str2f ( "Wide World " );
   cout << "The string str2f is: " << str2f << endl;
   str1f.append ( str2f.begin ( ) + 5 , str2f.end ( ) - 1 );
   cout << "The appended string str1 is: "
        << str1f << "." << endl << endl;
}
```

```Output
The original string str1 is: Hello
The C-string cstr1a is: Out There
Appending the C-string cstr1a to string str1 gives: Hello Out There .

The string str1b is: Hello
The C-string cstr1b is: Out There
Appending the 1st part of the C-string cstr1b to string str1 gives: Hello Out.

The string str2c is: Wide World
The appended string str1 is: Hello World.

The  string str2d is: Wide
The appended string str1d is: Hello Wide .
The doubly appended strig str1 is: Hello Wide World .

The string str1 appended with exclamations is: Hello !!!!

The string str2f is: Wide World
The appended string str1 is: Hello World.
```

## <a name="basic_stringassign"></a><a name="assign"></a>basic_string::atama

Bir dizenin içeriğine yeni karakter değerleri atar.

```cpp
basic_string<CharType, Traits, Allocator>& assign(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& assign(
    const value_type* ptr,
    size_type count);

basic_string<CharType, Traits, Allocator>& assign(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type off,
    size_type count);

basic_string<CharType, Traits, Allocator>& assign(
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& assign(
    size_type count,
    value_type char_value);

template <class InIt>
basic_string<CharType, Traits, Allocator>& assign(
    InputIterator first,
    InputIterator last);

basic_string<CharType, Traits, Allocator>& assign(
    const_pointer first,
    const_pointer last);

basic_string<CharType, Traits, Allocator>& assign(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Hedef dize atanacak C dizesinin karakterlerine işaretçi.

*Sayısı*\
Kaynak dizeden atanacak karakter sayısı.

*Str*\
Karakterleri hedef dize atanacak kaynak dize.

*char_value*\
Atanacak karakter değeri.

*Ilk*\
Hedef aralığına atanacak kaynak dize aralığındaki ilk karaktere hitap eden bir giriş yineleyici, const_pointer veya const_iterator.

*Son*\
Hedef aralığına atanacak kaynak dize aralığındaki son karakterin ötesindekine hitap eden bir giriş yineleyici, const_pointer veya const_iterator.

*kapalı*\
Yeni karakterlerin atanmaya başlayacağı konum.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev tarafından yeni karakterler atanan dize nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Dizeleri yeni karakter değerleri atanabilir. Yeni değer bir dize ve C-string veya tek bir karakter olabilir. Yeni değer tek bir parametre ile açıklanabilirse [işleç=](#op_eq) kullanılabilir; aksi takdirde, `assign`birden çok parametreye sahip olan üye işlev, dizenin hangi bölümünün hedef dizeye atanacak olduğunu belirtmek için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// basic_string_assign.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function assigning the
   // characters of a C-string to a string
   string str1a;
   const char *cstr1a = "Out There";
   cout << "The C-string cstr1a is: " << cstr1a <<  "." << endl;
   str1a.assign ( cstr1a );
   cout << "Assigning the C-string cstr1a to string str1 gives: "
        << str1a << "." << endl << endl;

   // The second member function assigning a specific
   // number of the of characters a C-string to a string
   string  str1b;
   const char *cstr1b = "Out There";
   cout << "The C-string cstr1b is: " << cstr1b << endl;
   str1b.assign ( cstr1b , 3 );
   cout << "Assigning the 1st part of the C-string cstr1b "
        << "to string str1 gives: " << str1b << "."
        << endl << endl;

   // The third member function assigning a specific number
   // of the characters from one string to another string
   string str1c ( "Hello " ), str2c ( "Wide World " );
   cout << "The string str2c is: " << str2c << endl;
   str1c.assign ( str2c , 5 , 5 );
   cout << "The newly assigned string str1 is: "
        << str1c << "." << endl << endl;

   // The fourth member function assigning the characters
   // from one string to another string in two equivalent
   // ways, comparing the assign and operator =
   string str1d ( "Hello" ), str2d ( "Wide" ), str3d ( "World" );
   cout << "The original string str1 is: " << str1d << "." << endl;
   cout << "The string str2d is: " << str2d << endl;
   str1d.assign ( str2d );
   cout << "The string str1 newly assigned with string str2d is: "
        << str1d << "." << endl;
   cout << "The string str3d is: " << str3d << "." << endl;
   str1d = str3d;
   cout << "The string str1 reassigned with string str3d is: "
        << str1d << "." << endl << endl;

   // The fifth member function assigning a specific
   // number of characters of a certain value to a string
   string str1e ( "Hello " );
   str1e.assign ( 4 , '!' );
   cout << "The string str1 assigned with eclamations is: "
        << str1e << endl << endl;

   // The sixth member function assigning the value from
   // the range of one string to another string
   string str1f ( "Hello " ), str2f ( "Wide World " );
   cout << "The string str2f is: " << str2f << endl;
   str1f.assign ( str2f.begin ( ) + 5 , str2f.end ( ) - 1 );
   cout << "The string str1 assigned a range of string str2f is: "
        << str1f << "." << endl << endl;
}
```

```Output
The C-string cstr1a is: Out There.
Assigning the C-string cstr1a to string str1 gives: Out There.

The C-string cstr1b is: Out There
Assigning the 1st part of the C-string cstr1b to string str1 gives: Out.

The string str2c is: Wide World
The newly assigned string str1 is: World.

The original string str1 is: Hello.
The string str2d is: Wide
The string str1 newly assigned with string str2d is: Wide.
The string str3d is: World.
The string str1 reassigned with string str3d is: World.

The string str1 assigned with eclamations is: !!!!

The string str2f is: Wide World
The string str1 assigned a range of string str2f is: World.
```

## <a name="basic_stringat"></a><a name="at"></a>basic_string::at

Bir dize içinde belirtilen bir dizin ile karaktere bir başvuru sağlar.

```cpp
const_reference at(size_type offset) const;

reference at(size_type offset);
```

### <a name="parameters"></a>Parametreler

*Uzaklık*\
Başvurulacak öğenin konumunun dizin.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen pozisyonda dize karakterine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dizeilk öğesi sıfır dizini vardır ve aşağıdaki öğeler pozitif tamsayılar tarafından ardışık olarak dizine alınır, böylece *n* uzunluk dizesi *n* - 1 sayısı ile indekslenmiş bir *n*th öğesine sahiptir.

Üye [operatör&#91;&#93;,](#op_at) bir dize öğelerine okuma yazma erişimi sağlamak için üye işlevden `at` daha hızlıdır.

Üye, `operator[]` parametre olarak geçirilen dizin geçerli olup olmadığını `at` denetlemez, ancak geçerlilik kesin değilse üye işlevi kullanılır. Üye işleve `at` geçirilen, daha az sıfır veya daha büyük veya dize boyutuna eşit bir dizin olan geçersiz dizin, [bir out_of_range Sınıfı](../standard-library/out-of-range-class.md) özel durum atar. Tanımlanmamış davranışta `operator[]` sonuçlara geçirilen geçersiz dizin, ancak dize dize sinin uzunluğuna eşit const dizeleri için geçerli bir dizindir ve işleç bu dizini geçtiğinde null karakterini döndürür.

Döndürülen başvuru, **const** olmayan dizeleri için dize gerçekleştirilmiş veya değişiklikler tarafından geçersiz kılınabilir.

### <a name="example"></a>Örnek

```cpp
// basic_string_at.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello world" ), str2 ( "Goodbye world" );
   const string  cstr1 ( "Hello there" ), cstr2 ( "Goodbye now" );
   cout << "The original string str1 is: " << str1 << endl;
   cout << "The original string str2 is: " << str2 << endl;

   // Element access to the non const strings
   basic_string <char>::reference refStr1 = str1 [6];
   basic_string <char>::reference refStr2 = str2.at ( 3 );

   cout << "The character with an index of 6 in string str1 is: "
        << refStr1 << "." << endl;
   cout << "The character with an index of 3 in string str2 is: "
        << refStr2 << "." << endl;

   // Element access to the const strings
   basic_string <char>::const_reference crefStr1 = cstr1 [ cstr1.length ( ) ];
   basic_string <char>::const_reference crefStr2 = cstr2.at ( 8 );

   if ( crefStr1 == '\0' )
      cout << "The null character is returned as a valid reference."
           << endl;
   else
      cout << "The null character is not returned." << endl;
   cout << "The character with index 8 in the const string cstr2 is: "
        << crefStr2 << "." << endl;
}
```

## <a name="basic_stringback"></a><a name="back"></a>basic_string::geri

Dizedeki son öğeye bir başvuru verir.

```cpp
const_reference back() const;

reference back();
```

### <a name="return-value"></a>Dönüş Değeri

Dize, boş olmayan olması gereken son öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

## <a name="basic_stringbasic_string"></a><a name="basic_string"></a>basic_string:basic_string

Boş, belirli karakterler tarafından başharfe çevrilmiş veya başka bir dize nesnesinin veya C stilinin (null-sonlandırılan) dizesinin tamamının veya bir bölümünün kopyası olan bir dize oluşturuyor.

```cpp
basic_string();

explicit basic_string(
    const allocator_type& alloc_type);

basic_string(
    const basic_string& right);

basic_string(
    basic_string&& right);

basic_string(
    const basic_string& right,
    size_type right_offset,
    size_type count = npos);

basic_string(
    const basic_string& right,
    size_type right_offset,
    size_type count,
    const allocator_type& alloc_type);

basic_string(
    const value_type* ptr,
    size_type count);

basic_string(
    const value_type* ptr,
    size_type count,
    const allocator_type& alloc_type);

basic_string(
    const value_type* ptr);

basic_string(
    const value_type* ptr,
    const allocator_type& alloc_type);

basic_string(
    size_type count,
    value_type char_value);

basic_string(
    size_type count,
    value_type char_value,
    const allocator_type& alloc_type);

template <class InputIterator>
basic_string(
    InputIterator first,
    InputIterator last);

template <class InputIterator>
basic_string(
    InputIterator first,
    InputIterator last,
    const allocator_type& alloc_type);

basic_string(
    const_pointer first,
    const_pointer last);

basic_string(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
C-string olan karakterler imal `string` başlatılması için kullanılacaktır. Bu değer null işaretçi olamaz.

*alloc_type*\
Oluşturulmakta olan dize nesnesinin depolama ayırıcı sınıfı.

*Sayısı*\
Başharfe çevrilecek karakter sayısı.

*Doğru*\
Oluşturulmakta olan dizeyi başlatma dizesi.

*right_offset*\
Yapılan dize için karakter değerlerini başharfe getirmek için ilk kez kullanılan bir dizdeki bir karakterin dizini.

*char_value*\
Oluşturulmakta olan dize içine kopyalanacak karakter değeri.

*Ilk*\
Kaynak aralığında eklenecek ilk öğeyi ele alan bir giriş yineleyici, const_pointer veya const_iterator.

*Son*\
Kaynak aralığında eklenecek son öğenin ötesindeki öğenin konumunu ele alan bir giriş yineleyici, const_pointer veya const_iterator.

### <a name="return-value"></a>Dönüş Değeri

Oluşturucular tarafından oluşturulmakta olan dize nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Tüm yapıcılar bir [basic_string depolar::allocator_type](#allocator_type) ve denetitilen sırayı başlatir. Ayırıcı nesne, varsa `al`bağımsız değişkendir. Kopya oluşturucu için, `right.` [basic_string::get_allocator](#get_allocator)`()`. Aksi takdirde, ayırıcı . `Alloc()`

Kontrollü dizi, kalan operandlar tarafından belirtilen operand dizisinin bir kopyasına başharflenir. Operand dizisi olmayan bir yapıcı boş bir ilk kontrollü sıra belirtir. Bir `InputIterator` şablon oluşturucubir tamsayı türü ise, operand dizisi `first,  last` aynı `(size_type) first, (value_type) last`şekilde olur.

### <a name="example"></a>Örnek

```cpp
// basic_string_ctor.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function initializing with a C-string
   const char *cstr1a = "Hello Out There.";
   basic_string <char> str1a ( cstr1a , 5);
   cout << "The string initialized by C-string cstr1a is: "
        << str1a << "." << endl;

   // The second member function initializing with a string
   string  str2a ( "How Do You Do" );
   basic_string <char> str2b ( str2a , 7 , 7 );
   cout << "The string initialized by part of the string cstr2a is: "
        << str2b << "." << endl;

   // The third member function initializing a string
   // with a number of characters of a specific value
   basic_string <char> str3a ( 5, '9' );
   cout << "The string initialized by five number 9s is: "
        << str3a << endl;

   // The fourth member function creates an empty string
   // and string with a specified allocator
   basic_string <char> str4a;
   string str4b;
   basic_string <char> str4c ( str4b.get_allocator( ) );
   if (str4c.empty ( ) )
      cout << "The string str4c is empty." << endl;
   else
      cout << "The string str4c is not empty." << endl;

   // The fifth member function initializes a string from
   // another range of characters
   string str5a ( "Hello World" );
   basic_string <char> str5b ( str5a.begin ( ) + 5 , str5a.end ( ) );
   cout << "The string initialized by another range is: "
        << str5b << "." << endl;
}
```

## <a name="basic_stringbegin"></a><a name="begin"></a>basic_string::başla

Dizedeki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesini veya boş bir dizinin sonunun hemen ötesine hitap eden rasgele erişim yineleyici.

### <a name="example"></a>Örnek

```cpp
// basic_string_begin.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( ) {
   using namespace std;
   string str1 ( "No way out." ), str2;
   basic_string <char>::iterator strp_Iter, str1_Iter, str2_Iter;
   basic_string <char>::const_iterator str1_cIter;

   str1_Iter = str1.begin ( );
   cout << "The first character of the string str1 is: "
        << *str1_Iter << endl;
   cout << "The full original string str1 is: " << str1 << endl;

   // The dereferenced iterator can be used to modify a character
*str1_Iter = 'G';
   cout << "The first character of the modified str1 is now: "
        << *str1_Iter << endl;
   cout << "The full modified string str1 is now: " << str1 << endl;

   // The following line would be an error because iterator is const
   // *str1_cIter = 'g';

   // For an empty string, begin is equivalent to end
   if (  str2.begin ( ) == str2.end ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The string str2 is not empty." << endl;
}
```

## <a name="basic_stringc_str"></a><a name="c_str"></a>basic_string:c_str

Bir dize içeriğini C stili, null-sonlandırılmış dize olarak dönüştürür.

```cpp
const value_type *c_str() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağıran dizecin C stili sürümüne işaretçi.  İşaretçi değeri, nesnenin basic_string sınıfında yıkıcı da dahil olmak üzere const olmayan bir işlevi çağırdıktan sonra geçerli değildir.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonuna ait tür\<dize nesneleri basic_string char> mutlaka null sonlandırılmayız. Null karakter ' \0 ' dize sonunu işaretlemek için c dizeözel bir karakter olarak kullanılır ama tür dize bir nesne özel bir anlamı vardır ve dize başka bir karakter gibi bir parçası olabilir. **Const char'dan** <strong>\*</strong> dizeleri otomatik olarak dönüştürme vardır, ancak string sınıfı C stili dizeleri türü **basic_string\<char>** nesneleri için otomatik dönüşümler sağlamaz.

Döndürülen C stili dize değiştirilmemelidir, çünkü bu dize işaretçisini geçersiz kılabilir veya silinebilir, çünkü dize sınırlı bir kullanım ömrüne sahiptir ve sınıf dizesine aittir.

### <a name="example"></a>Örnek

```cpp
// basic_string_c_str.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string  str1 ( "Hello world" );
   cout << "The original string object str1 is: "
        << str1 << endl;
   cout << "The length of the string object str1 = "
        << str1.length ( ) << endl << endl;

   // Converting a string to an array of characters
   const char *ptr1 = 0;
   ptr1= str1.data ( );
   cout << "The modified string object ptr1 is: " << ptr1
        << endl;
   cout << "The length of character array str1 = "
        << strlen ( ptr1) << endl << endl;

   // Converting a string to a C-style string
   const char *c_str1 = str1.c_str ( );
   cout << "The C-style string c_str1 is: " << c_str1
        << endl;
   cout << "The length of C-style string str1 = "
        << strlen ( c_str1) << endl << endl;
}
```

```Output
The original string object str1 is: Hello world
The length of the string object str1 = 11

The modified string object ptr1 is: Hello world
The length of character array str1 = 11

The C-style string c_str1 is: Hello world
The length of C-style string str1 = 11
```

## <a name="basic_stringcapacity"></a><a name="capacity"></a>basic_string::kapasite

Dize bellek ayırma artırmadan bir dize depolanabilir elemanların en büyük sayısını döndürür.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizeyi tutmak için bellekte şu anda ayrılmış depolama boyutu.

### <a name="remarks"></a>Açıklamalar

Üye işlev, en az boyut kadar büyük bir değer olan, denetlenen sırayı tutmak için ayrılan depolamayı [döndürür.](#size)

### <a name="example"></a>Örnek

```cpp
// basic_string_capacity.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string  str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size (  );
   lenStr1 = str1.length (  );
   capStr1 = str1.capacity (  );
   max_sizeStr1 = str1.max_size (  );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="basic_stringcbegin"></a><a name="cbegin"></a>basic_string::cbegin

Aralıktaki ilk öğeyi ele alan bir **const** yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın ilk öğesini veya boş aralığın sonundaki konumu işaret eden **bir const** rasgele erişim yineleyicisi `cbegin() == cend()`(boş bir aralık için).

### <a name="remarks"></a>Açıklamalar

İade değeri ile `cbegin`aralıktaki öğeler değiştirilemez.

Bu üye `begin()` işlevini, iade değerinin `const_iterator`. Genellikle, aşağıdaki örnekte gösterildiği gibi [otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, herhangi `Container` bir tür değiştirilebilir (non-const) kapsayıcı ve `begin()` destekler `cbegin()`düşünün. **const**

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="basic_stringcend"></a><a name="cend"></a>basic_string::cend

Bir aralıktaki son öğenin hemen ötesinde konuma hitap eden bir **const** yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın sonuna işaret eden **bir const** rasgele erişim yineleyici.

### <a name="remarks"></a>Açıklamalar

`cend`bir yineleyicinin aralığının sonundan geçip geçmediğini test etmek için kullanılır.

Bu üye `end()` işlevini, iade değerinin `const_iterator`. Genellikle, aşağıdaki örnekte gösterildiği gibi [otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, herhangi `Container` bir tür değiştirilebilir (non-const) kapsayıcı ve `end()` destekler `cend()`düşünün. **const**

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Döndürülen `cend` değer dereferenced olmamalıdır.

## <a name="basic_stringclear"></a><a name="clear"></a>basic_string::açık

Dizedeki tüm öğeleri siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevin çağrıldığı dize boş olacaktır.

### <a name="example"></a>Örnek

```cpp
// basic_string_clear.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string  str1 ("Hello world"), str2;
   basic_string <char>::iterator str_Iter;
   cout << "The original string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   str1.clear ( );
   cout << "The modified string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   //For an empty string, begin is equivalent to end
   if ( str1.begin ( ) == str1.end ( ) )
      cout << "Nothing printed above because "
           << "the string str1 is empty." << endl;
   else
      cout << "The string str1 is not empty." << endl;
}
```

```Output
The original string str1 is: Hello world
The modified string str1 is:
Nothing printed above because the string str1 is empty.
```

## <a name="basic_stringcompare"></a><a name="compare"></a>basic_string::karşılaştır

İki dize eşit mi yoksa biri lexicographically diğerinden daha az olup olmadığını belirlemek için belirli bir dize ile bir büyük/küçük harf duyarlı karşılaştırma gerçekleştirir.

```cpp
int compare(
    const basic_string<CharType, Traits, Allocator>& str) const;

int compare(
    size_type position_1,
    size_type number_1,
    const basic_string<CharType, Traits, Allocator>& str) const;

int compare(
    size_type position_1,
    size_type number_1,
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset,
    size_type count) const;

int compare(
    const value_type* ptr) const;

int compare(
    size_type position_1,
    size_type number_1,
    const value_type* ptr) const;

int compare(
    size_type position_1,
    size_type number_1,
    const value_type* ptr
    size_type number_2) const;
```

### <a name="parameters"></a>Parametreler

*Str*\
Operand string ile karşılaştırılacak dize.

*position_1*\
Karşılaştırmanın başladığı operand dizesinin dizini.

*number_1*\
Operand dizesinden karşılaştırılacak maksimum karakter sayısı.

*number_2*\
Parametre dizesinden karşılanacak maksimum karakter sayısı.

*Uzaklık*\
Karşılaştırmanın başladığı parametre dizesi dizini.

*Sayısı*\
Parametre dizesinden karşılanacak maksimum karakter sayısı.

*Ptr*\
C-string operand dize ile karşılaştırıldığında.

### <a name="return-value"></a>Dönüş Değeri

Operand dize parametre dizesinden daha az ise negatif bir değer; iki dize eşitse sıfır; veya operand dize parametre dizesinden büyükse pozitif bir değer.

### <a name="remarks"></a>Açıklamalar

Üye `compare` işlevler, kullanılan adedine bağlı olarak parametre ve operand dizeleri tümünü veya bir kısmını karşılaştırır.

Gerçekleştirilen karşılaştırma büyük/küçük harf duyarlıdır.

### <a name="example"></a>Örnek

```cpp
// basic_string_compare.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function compares
   // an operand string to a parameter string
   int comp1;
   string s1o ( "CAB" );
   string s1p ( "CAB" );
   cout << "The operand string is: " << s1o << endl;
   cout << "The parameter string is: " << s1p << endl;
   comp1 = s1o.compare ( s1p );
   if ( comp1 < 0 )
      cout << "The operand string is less than "
           << "the parameter string." << endl;
   else if ( comp1 == 0 )
      cout << "The operand string is equal to "
           << "the parameter string." << endl;
   else
      cout << "The operand string is greater than "
           << "the parameter string." << endl;
   cout << endl;

   // The second member function compares part of
   // an operand string to a parameter string
   int comp2a, comp2b;
   string s2o ( "AACAB" );
   string s2p ( "CAB" );
   cout << "The operand string is: " << s2o << endl;
   cout << "The parameter string is: " << s2p << endl;
   comp2a = s2o.compare (  2 , 3 , s2p );
   if ( comp2a < 0 )
      cout << "The last three characters of "
           << "the operand string\n are less than "
           << "the parameter string." << endl;
   else if ( comp2a == 0 )
      cout << "The last three characters of "
           << "the operand string\n are equal to "
           << "the parameter string." << endl;
   else
      cout << "The last three characters of "
           << "the operand string\n is greater than "
           << "the parameter string." << endl;

   comp2b = s2o.compare (  0 , 3 , s2p );
   if ( comp2b < 0 )
      cout << "The first three characters of "
           << "the operand string\n are less than "
           << "the parameter string." << endl;
   else if ( comp2b == 0 )
      cout << "The first three characters of "
           << "the operand string\n are equal to "
           << "the parameter string." << endl;
   else
      cout << "The first three characters of "
           << "the operand string\n is greater than "
           << "the parameter string." << endl;
   cout << endl;

   // The third member function compares part of
   // an operand string to part of a parameter string
   int comp3a;
   string s3o ( "AACAB" );
   string s3p ( "DCABD" );
   cout << "The operand string is: " << s3o << endl;
   cout << "The parameter string is: " << s3p << endl;
   comp3a = s3o.compare (  2 , 3 , s3p , 1 , 3 );
   if ( comp3a < 0 )
      cout << "The three characters from position 2 of "
           << "the operand string are less than\n "
           << "the 3 characters parameter string "
           << "from position 1." << endl;
   else if ( comp3a == 0 )
      cout << "The three characters from position 2 of "
           << "the operand string are equal to\n "
           << "the 3 characters parameter string "
           << "from position 1." << endl;
   else
      cout << "The three characters from position 2 of "
           << "the operand string is greater than\n "
           << "the 3 characters parameter string "
           << "from position 1." << endl;
   cout << endl;

   // The fourth member function compares
   // an operand string to a parameter C-string
   int comp4a;
   string s4o ( "ABC" );
   const char* cs4p = "DEF";
   cout << "The operand string is: " << s4o << endl;
   cout << "The parameter C-string is: " << cs4p << endl;
   comp4a = s4o.compare ( cs4p );
   if ( comp4a < 0 )
      cout << "The operand string is less than "
           << "the parameter C-string." << endl;
   else if ( comp4a == 0 )
      cout << "The operand string is equal to "
           << "the parameter C-string." << endl;
   else
      cout << "The operand string is greater than "
           << "the parameter C-string." << endl;
   cout << endl;

   // The fifth member function compares part of
   // an operand string to a parameter C-string
   int comp5a;
   string s5o ( "AACAB" );
   const char* cs5p = "CAB";
   cout << "The operand string is: " << s5o << endl;
   cout << "The parameter string is: " << cs5p << endl;
   comp5a = s5o.compare (  2 , 3 , s2p );
   if ( comp5a < 0 )
      cout << "The last three characters of "
           << "the operand string\n are less than "
           << "the parameter C-string." << endl;
   else if ( comp5a == 0 )
      cout << "The last three characters of "
           << "the operand string\n are equal to "
           << "the parameter C-string." << endl;
   else
      cout << "The last three characters of "
           << "the operand string\n is greater than "
           << "the parameter C-string." << endl;
   cout << endl;

   // The sixth member function compares part of
   // an operand string to part of an equal length of
   // a parameter C-string
   int comp6a;
   string s6o ( "AACAB" );
   const char* cs6p = "ACAB";
   cout << "The operand string is: " << s6o << endl;
   cout << "The parameter C-string is: " << cs6p << endl;
   comp6a = s6o.compare (  1 , 3 , cs6p , 3 );
   if ( comp6a < 0 )
      cout << "The 3 characters from position 1 of "
           << "the operand string are less than\n "
           << "the first 3 characters of the parameter C-string."
           << endl;
   else if ( comp6a == 0 )
      cout << "The 3 characters from position 2 of "
           << "the operand string are equal to\n "
           << "the first 3 characters of the parameter C-string."
           <<  endl;
   else
      cout << "The 3 characters from position 2 of "
           << "the operand string is greater than\n "
           << "the first 3 characters of the parameter C-string."
           << endl;
   cout << endl;
}
```

```Output
The operand string is: CAB
The parameter string is: CAB
The operand string is equal to the parameter string.

The operand string is: AACAB
The parameter string is: CAB
The last three characters of the operand string
are equal to the parameter string.
The first three characters of the operand string
are less than the parameter string.

The operand string is: AACAB
The parameter string is: DCABD
The three characters from position 2 of the operand string are equal to
the 3 characters parameter string from position 1.

The operand string is: ABC
The parameter C-string is: DEF
The operand string is less than the parameter C-string.

The operand string is: AACAB
The parameter string is: CAB
The last three characters of the operand string
are equal to the parameter C-string.

The operand string is: AACAB
The parameter C-string is: ACAB
The 3 characters from position 2 of the operand string are equal to
the first 3 characters of the parameter C-string.
```

## <a name="basic_stringconst_iterator"></a><a name="const_iterator"></a>basic_string:const_iterator

Dizedeki bir **const** öğesine erişebilen ve okuyabilen rasgele erişim yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_iterator` tür bir karakterin değerini değiştirmek için kullanılamaz ve ileri yönde bir dize üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir [begin](#begin) ve kullanılacağına `const_iterator`bir örnek için başlangıç örneğine bakın.

## <a name="basic_stringconst_pointer"></a><a name="const_pointer"></a>basic_string:const_pointer

Bir dizedeki **const** öğesine işaretçi sağlayan bir tür.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü için `allocator_type::const_pointer`eşanlamlıdır.

Türü `string`için, `char*`bu eşdeğerdir .

Const olarak bildirilen işaretçiler, beyan edildiklerinde başharflere alınmalıdır. Const işaretçileri her zaman aynı bellek konumunu işaret eder ve sabit veya sabit olmayan verilere işaret edebilir.

### <a name="example"></a>Örnek

```cpp
// basic_string_const_ptr.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   basic_string<char>::const_pointer pstr1a = "In Here";
   const char *cstr1c = "Out There";

   cout << "The string pstr1a is: " << pstr1a <<  "." << endl;
   cout << "The C-string cstr1c is: " << cstr1c << "." << endl;
}
```

```Output
The string pstr1a is: In Here.
The C-string cstr1c is: Out There.
```

## <a name="basic_stringconst_reference"></a><a name="const_reference"></a>basic_string::const_reference

**Const** işlemleri okumak ve gerçekleştirmek için bir dizede depolanan **bir const** öğesine başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reference` tür, bir öğenin değerini değiştirmek için kullanılamaz.

Türü için `allocator_type::const_reference`eşanlamlıdır. Dize `type`için, const `char&`eşdeğerdir.

### <a name="example"></a>Örnek

Nasıl bildirilir [at](#at) ve kullanılır. `const_reference`

## <a name="basic_stringconst_reverse_iterator"></a><a name="const_reverse_iterator"></a>basic_string:const_reverse_iterator

Dizedeki herhangi bir **const** öğeyi okuyabilen rasgele erişim yinelemesi sağlayan bir tür.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `const_reverse_iterator` tür bir karakterin değerini değiştiremez ve bir dize ile ters olarak yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `const_reverse_iterator`bir örnek için [rbegin](#rbegin) örneğine bakın.

## <a name="basic_stringcopy"></a><a name="copy"></a>basic_string::kopyala

Kaynak dizedeki dizilenmiş bir konumdan hedef karakter dizisine en fazla belirli sayıda karakter kopyalar.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir. bunun [yerine basic_string::_Copy_s](#copy_s) kullanmayı düşünün.

```cpp
size_type copy(
    value_type* ptr,
    size_type count,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Öğelerin kopyalanabilmek için hedef karakter dizisi.

*sayısı* En fazla kaynak dizeden kopyalanacak karakter sayısı.

*Uzaklık*\
Kopyaların yapılacağı kaynak dizedeki başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Null karakteri kopyanın sonuna eklenmiyor.

### <a name="example"></a>Örnek

```cpp
// basic_string_copy.cpp
// compile with: /EHsc /W3
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello World" );
   basic_string <char>::iterator str_Iter;
   char array1 [ 20 ] = { 0 };
   char array2 [ 10 ] = { 0 };
   basic_string <char>:: pointer array1Ptr = array1;
   basic_string <char>:: value_type *array2Ptr = array2;

   cout << "The original string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   basic_string <char>:: size_type nArray1;
   // Note: string::copy is potentially unsafe, consider
   // using string::_Copy_s instead.
   nArray1 = str1.copy ( array1Ptr , 12 );  // C4996
   cout << "The number of copied characters in array1 is: "
        << nArray1 << endl;
   cout << "The copied characters array1 is: " << array1 << endl;

   basic_string <char>:: size_type nArray2;
   // Note: string::copy is potentially unsafe, consider
   // using string::_Copy_s instead.
   nArray2 = str1.copy ( array2Ptr , 5 , 6  );  // C4996
   cout << "The number of copied characters in array2 is: "
           << nArray2 << endl;
   cout << "The copied characters array2 is: " << array2Ptr << endl;
}
```

```Output
The original string str1 is: Hello World
The number of copied characters in array1 is: 11
The copied characters array1 is: Hello World
The number of copied characters in array2 is: 5
The copied characters array2 is: World
```

## <a name="basic_stringcrbegin"></a><a name="crbegin"></a>basic_string::crbegin

Ters dizedeki ilk öğeyi ele alan bir const yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize ucunun hemen ötesine işaret eden bir ters yineleyici. Konum, ters dizenin başlangıcını belirtir.

## <a name="basic_stringcrend"></a><a name="crend"></a>basic_string::crend

Ters dizedeki son öğeyi yerine getiren konumu gideren bir const yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters dizedeki son öğeyi başaran konumu gideren bir const ters yineleyici (ters çevrilmemiş dizedeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

## <a name="basic_string_copy_s"></a><a name="copy_s"></a>basic_string:_Copy_s

Kaynak dizedeki dizilenmiş bir konumdan hedef karakter dizisine en fazla belirli sayıda karakter kopyalar.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*Dest*\
Öğelerin kopyalanabilmek için hedef karakter dizisi.

*dest_size*\
*Dest*boyutu .

*sayısı* En fazla kaynak dizeden kopyalanacak karakter sayısı.

*Uzaklık*\
Kopyaların yapılacağı kaynak dizedeki başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Null karakteri kopyanın sonuna eklenmiyor.

### <a name="example"></a>Örnek

```cpp
// basic_string__Copy_s.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
    using namespace std;
    string str1("Hello World");
    basic_string<char>::iterator str_Iter;
    const int array1_size = 20;
    char array1[array1_size] = { 0 };
    const int array2_size = 10;
    char array2[array2_size] = { 0 };
    basic_string<char>:: pointer array1Ptr = array1;
    basic_string<char>:: value_type *array2Ptr = array2;

    cout << "The original string str1 is: ";
    for (str_Iter = str1.begin(); str_Iter != str1.end(); str_Iter++)
        cout << *str_Iter;
    cout << endl;

    basic_string<char>::size_type nArray1;
    nArray1 = str1._Copy_s(array1Ptr, array1_size, 12);
    cout << "The number of copied characters in array1 is: "
         << nArray1 << endl;
    cout << "The copied characters array1 is: " << array1 << endl;

    basic_string<char>:: size_type nArray2;
    nArray2 = str1._Copy_s(array2Ptr, array2_size, 5, 6);
    cout << "The number of copied characters in array2 is: "
         << nArray2 << endl;
    cout << "The copied characters array2 is: " << array2Ptr << endl;
}
```

```Output
The original string str1 is: Hello World
The number of copied characters in array1 is: 11
The copied characters array1 is: Hello World
The number of copied characters in array2 is: 5
The copied characters array2 is: World
```

## <a name="basic_stringdata"></a><a name="data"></a>basic_string::data

Bir dizenin içeriğini null-sonlandırılan bir karakter dizisine dönüştürür.

```cpp
const value_type *data() const noexcept;
value_type *data() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Dize içeriğini içeren null-sonlandırılan dizinin ilk öğesiiçin bir işaretçi. Boş bir dize için işaretçi, .'a eşit tek bir null karaktere `value_type()`işaret eder.

### <a name="remarks"></a>Açıklamalar

İşaretçi geçerli `data` bir aralıktaki `[data(), data() + size()]`noktalarla döndürülür. Aralıktaki her öğe dizedeki geçerli verilere karşılık gelir. Yani, aralıktaki her *n* geçerli ofset `data() + n == addressof(operator[](n))`n için, .

Const aşırı yük tarafından döndürülen **const** dize içeriğini `data`değiştirirseniz, davranış tanımsız. Ayrıca, terminal null karakteri başka bir değere değiştirilirse tanımlanmamış davranış lar da elde elabilirsiniz. Dize const olmayan bir başvuru standart kitaplık işlevine geçirilirse döndürülen işaretçi geçersiz kılınabilir. Const olmayan bir üye işlevine yapılan bir çağrı yla da geçersiz kılınabilir. Üyelere `at`yapılan `back` `begin`aramalar `end` `front`, `rbegin` `rend`, `operator[]` , , , , , ve işaretçiyi geçersiz kılmaz.

C++11'den `data` önce, döndürülen dize nin null-sonlandırıldığını garanti etmedi. Çünkü C++11 `data` `c_str` ve her ikisi de null-terminatedstring döndürür ve etkili bir şekilde aynıdır.

Const olmayan aşırı yük C++17'de yenidir. Kullanmak için **/std:c++17** veya **/std:c++en son** derleyici seçeneğini belirtin.

### <a name="example"></a>Örnek

```cpp
// basic_string_data.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string str1 ( "Hello world" );
   cout << "The original string object str1 is: "
        << str1 << endl;
   cout << "The length of the string object str1 = "
        << str1.length ( ) << endl << endl;

   // Converting a string to an array of characters
   const char *ptr1 = 0;
   ptr1= str1.data ( );
   cout << "The modified string object ptr1 is: " << ptr1
        << endl;
   cout << "The length of character array str1 = "
        << strlen ( ptr1) << endl << endl;

   // Converting a string to a C-style string
   const char *c_str1 = str1.c_str ( );
   cout << "The C-style string c_str1 is: " << c_str1
        << endl;
   cout << "The length of C-style string str1 = "
        << strlen ( c_str1) << endl << endl;
}
```

```Output
The original string object str1 is: Hello world
The length of the string object str1 = 11

The modified string object ptr1 is: Hello world
The length of character array str1 = 11

The C-style string c_str1 is: Hello world
The length of C-style string str1 = 11
```

## <a name="basic_stringdifference_type"></a><a name="difference_type"></a>basic_string::difference_type

Aynı dize içindeki öğelere başvuran iki yineleyici arasındaki farkı sağlayan bir tür.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalı bir sonraki gün türü, denetlenebilir sırada herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi açıklar.

Türü `string`için, `ptrdiff_t`bu eşdeğerdir .

### <a name="example"></a>Örnek

```cpp
// basic_string_diff_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "quintillion" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexChFi, indexChLi;

   indexChFi = str1.find_first_of ( "i" );
   indexChLi = str1.find_last_of ( "i" );
   basic_string<char>::difference_type diffi = indexChLi - indexChFi;

   cout << "The first character i is at position: "
        << indexChFi << "." << endl;
   cout << "The last character i is at position: "
        << indexChLi << "." << endl;
   cout << "The difference is: " << diffi << "." << endl;
}
```

```Output
The original string str1 is: quintillion
The first character i is at position: 2.
The last character i is at position: 8.
The difference is: 6.
```

## <a name="basic_stringempty"></a><a name="empty"></a>basic_string::boş

Dize karakter içerip içermediğini sızıntır.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

dize nesnesi karakter içermisse **doğru;** en az bir karakteri varsa **yanlış.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [boyut](#size) == 0'a eşdeğerdir.

### <a name="example"></a>Örnek

```cpp
// basic_string_empty.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main() {
   using namespace std;

   bool b1, b2;

   string str1 ("Hello world");
   cout << "The original string object str1 is: " << str1 << endl;
   b1 = str1.empty();
   if (b1)
      cout << "The string object str1 is empty." << endl;
   else
      cout << "The string object str1 is not empty." << endl;
   cout << endl;

   // An example of an empty string object
   string str2;
   b2 = str2.empty();
   if (b2)
      cout << "The string object str2 is empty." << endl;
   else
      cout << "The string object str2 is not empty." << endl;
}
```

## <a name="basic_stringend"></a><a name="end"></a>basic_string::sonu

Bir dizedeki son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir dizedeki son öğeyi yerine getiren konumu gideren rasgele erişim yineleyicisi döndürür.

### <a name="remarks"></a>Açıklamalar

`end`genellikle bir yineleyicinin dizesinin sonuna ulaşıp ulaşmadığını test etmek için kullanılır. Döndürülen `end` değer dereferenced olmamalıdır.

Bir `const_iterator`, string `end` nesnesi için return value atanırsa değiştirilemez. Bir `end` `iterator`, dize nesnesi için return value atanırsa değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// basic_string_end.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "No way out." ), str2;
   basic_string <char>::iterator str_Iter, str1_Iter, str2_Iter;
   basic_string <char>::const_iterator str1_cIter;

   str1_Iter = str1.end ( );
   str1_Iter--;
   str1_Iter--;
   cout << "The last character-letter of the string str1 is: " << *str1_Iter << endl;
   cout << "The full original string str1 is: " << str1 << endl;

   // end used to test when an iterator has reached the end of its string
   cout << "The string is now: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   // The dereferenced iterator can be used to modify a character
*str1_Iter = 'T';
   cout << "The last character-letter of the modified str1 is now: "
        << *str1_Iter << endl;
   cout << "The modified string str1 is now: " << str1 << endl;

   // The following line would be an error because iterator is const
   // *str1_cIter = 'T';

   // For an empty string, end is equivalent to begin
   if ( str2.begin( ) == str2.end ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The stringstr2  is not empty." << endl;
}
```

```Output
The last character-letter of the string str1 is: t
The full original string str1 is: No way out.
The string is now: No way out.
The last character-letter of the modified str1 is now: T
The modified string str1 is now: No way ouT.
The string str2 is empty.
```

## <a name="basic_stringerase"></a><a name="erase"></a>basic_string::silme

Bir dizedeki bir öğeyi veya dizi öğeyi belirli bir konumdan kaldırır.

```cpp
iterator erase(
    iterator first,
    iterator last);

iterator erase(
    iterator iter);

basic_string<CharType, Traits, Allocator>& erase(
    size_type offset = 0,
    size_type count = npos);
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Silinecek aralıktaki ilk öğenin konumunu ele alan bir yineleyici.

*Son*\
Silinecek aralıktaki son öğeyi bir geçmiş konuma hitap eden bir yineleyici.

*ıter*\
Silinecek dizedeki öğenin konumunu ele alan bir yineleyici.

*Uzaklık*\
Kaldırılacak dizedeki ilk karakterin dizini.

*Sayısı*\
*Ofset*ile başlayan dize aralığında çok varsa kaldırılacak öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, üye işlev tarafından kaldırılan son karakterden sonra ilk karaktere hitap eden bir yineleyici. Üçüncü üye işlev için, öğelerin silindiği dize nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlev ** \*bu**döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_string_erase.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The 1st member function using a range demarcated
   // by iterators
   string str1 ( "Hello world" );
   basic_string <char>::iterator str1_Iter;
   cout << "The original string object str1 is: "
        << str1 << "." << endl;
   str1_Iter = str1.erase ( str1.begin ( ) + 3 , str1.end ( ) - 1 );
   cout << "The first element after those removed is: "
        << *str1_Iter << "." << endl;
   cout << "The modified string object str1 is: " << str1
           << "." << endl << endl;

   // The 2nd member function erasing a char pointed to
   // by an iterator
   string str2 ( "Hello World" );
   basic_string <char>::iterator str2_Iter;
   cout << "The original string object str2 is: " << str2
        << "." << endl;
   str2_Iter = str2.erase ( str2.begin ( ) + 5 );
   cout << "The first element after those removed is: "
        << *str2_Iter << "." << endl;
   cout << "The modified string object str2 is: " << str2
        << "." << endl << endl;

   // The 3rd member function erasing a number of chars
   // after a char
   string str3 ( "Hello computer" ), str3m;
   basic_string <char>::iterator str3_Iter;
   cout << "The original string object str3 is: "
        << str3 << "." << endl;
   str3m = str3.erase ( 6 , 8 );
   cout << "The modified string object str3m is: "
        << str3m << "." << endl;
}
```

```Output
The original string object str1 is: Hello world.
The first element after those removed is: d.
The modified string object str1 is: Held.

The original string object str2 is: Hello World.
The first element after those removed is: W.
The modified string object str2 is: HelloWorld.

The original string object str3 is: Hello computer.
The modified string object str3m is: Hello .
```

## <a name="basic_stringfind"></a><a name="find"></a>basic_string::bul

Belirli bir karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için bir dizeyi ileri yönde arar.

```cpp
size_type find(
    value_type char_value,
    size_type offset = 0) const;

size_type find(
    const value_type* ptr,
    size_type offset = 0) const;

size_type find(
    const value_type* ptr,
    size_type offset,
    size_type count) const;

size_type find(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*char_value*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı konumun dizini.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranacak olduğu C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin aranacak dize.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

### <a name="example"></a>Örnek

```cpp
// basic_string_find.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "Hello Everyone" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;

   indexCh1a = str1.find ( "e" , 3 );
   if (indexCh1a != string::npos )
      cout << "The index of the 1st 'e' found after the 3rd"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'e' was not found in str1 ." << endl;

   indexCh1b = str1.find ( "x" );
   if (indexCh1b != string::npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The Character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "Let me make this perfectly clear." );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "perfect";
   indexCh2a = str2.find ( cstr2 , 5 );
   if ( indexCh2a != string::npos )
      cout << "The index of the 1st element of 'perfect' "
           << "after\n the 5th position in str2 is: "
           << indexCh2a << endl;
   else
      cout << "The substring 'perfect' was not found in str2 ."
           << endl;

   const char *cstr2b = "imperfectly";
   indexCh2b = str2.find ( cstr2b , 0 );
   if (indexCh2b != string::npos )
      cout << "The index of the 1st element of 'imperfect' "
           << "after\n the 5th position in str3 is: "
           << indexCh2b << endl;
   else
      cout << "The substring 'imperfect' was not found in str2 ."
           << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "This is a sample string for this program" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "sample";
   indexCh3a = str3.find ( cstr3a );
   if ( indexCh3a != string::npos )
      cout << "The index of the 1st element of sample "
           << "in str3 is: " << indexCh3a << endl;
   else
      cout << "The substring 'perfect' was not found in str3 ."
           << endl;

   const char *cstr3b = "for";
   indexCh3b = str3.find ( cstr3b , indexCh3a + 1 , 2 );
   if (indexCh3b != string::npos )
      cout << "The index of the next occurrence of 'for' is in "
           << "str3 begins at: " << indexCh3b << endl << endl;
   else
      cout << "There is no next occurrence of 'for' in str3 ."
           << endl << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "clearly this perfectly unclear." );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "clear" );
   indexCh4a = str4.find ( str4a , 5 );
   if ( indexCh4a != string::npos )
      cout << "The index of the 1st element of 'clear' "
           << "after\n the 5th position in str4 is: "
           << indexCh4a << endl;
   else
      cout << "The substring 'clear' was not found in str4 ."
           << endl;

   string str4b ( "clear" );
   indexCh4b = str4.find ( str4b );
   if (indexCh4b != string::npos )
      cout << "The index of the 1st element of 'clear' "
           << "in str4 is: "
           << indexCh4b << endl;
   else
      cout << "The substring 'clear' was not found in str4 ."
           << endl << endl;
}
```

```Output
The original string str1 is: Hello Everyone
The index of the 1st 'e' found after the 3rd position in str1 is: 8
The Character 'x' was not found in str1.

The original string str2 is: Let me make this perfectly clear.
The index of the 1st element of 'perfect' after
the 5th position in str2 is: 17
The substring 'imperfect' was not found in str2 .

The original string str3 is: This is a sample string for this program
The index of the 1st element of sample in str3 is: 10
The index of the next occurrence of 'for' is in str3 begins at: 24

The original string str4 is: clearly this perfectly unclear.
The index of the 1st element of 'clear' after
the 5th position in str4 is: 25
The index of the 1st element of 'clear' in str4 is: 0
```

## <a name="basic_stringfind_first_not_of"></a><a name="find_first_not_of"></a>basic_string:find_first_not_of

Belirli bir dize öğesi olmayan ilk karakter için bir dize arar.

```cpp
size_type find_first_not_of(
    value_type char_value,
    size_type offset = 0) const;

size_type find_first_not_of(
    const value_type* ptr,
    size_type offset = 0) const;

size_type find_first_not_of(
    const value_type* ptr,
    size_type offset,
    size_type count) const;

size_type find_first_not_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*char_value*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı konumun dizini.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranacak olduğu C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin aranacak dize.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

### <a name="example"></a>Örnek

```cpp
// basic_string_find_first_not_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "xddd-1234-abcd" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_first_not_of ( "d" , 2 );
   if ( indexCh1a != npos )
      cout << "The index of the 1st 'd' found after the 3rd"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'd' was not found in str1 ." << endl;

   indexCh1b = str1.find_first_not_of  ( "x" );
   if (indexCh1b != npos )
      cout << "The index of the 'non x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'non x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "BBB-1111" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_first_not_of ( cstr2 , 6 );
   if ( indexCh2a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'B1' in str2 after\n the 6th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements of the substring 'B1' were not"
           << "\n found in str2 after the 6th position."
           << endl;

   const char *cstr2b = "B2";
   indexCh2b = str2.find_first_not_of ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the 1st element of 'B2' "
           << "after\n the 0th position in str2 is: "
           << indexCh2b << endl << endl;
   else
      cout << "The substring 'B2' was not found in str2 ."
           << endl << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "444-555-GGG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "45G";
   indexCh3a = str3.find_first_not_of ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element in str3\n other than one of the "
           << "characters in '45G' is: " << indexCh3a
           << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string '45G'. "
           << endl;

   const char *cstr3b = "45G";
   indexCh3b = str3.find_first_not_of ( cstr3b , indexCh3a + 1 , 2 );
   if ( indexCh3b != npos )
      cout << "The index of the second occurrence of an "
           << "element of '45G' in str3\n after the 0th "
           << "position is: " << indexCh3b << endl << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string  '45G'. "
           << endl  << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "ba3" );
   indexCh4a = str4.find_first_not_of ( str4a , 5 );
   if (indexCh4a != npos )
      cout << "The index of the 1st non occurrence of an "
           << "element of 'ba3' in str4 after\n the 5th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements other than those in the substring"
           << " 'ba3' were not found in the string str4."
           << endl;

   string str4b ( "12" );
   indexCh4b = str4.find_first_not_of ( str4b  );
   if (indexCh4b != npos )
      cout << "The index of the 1st non occurrence of an "
           << "element of '12' in str4 after\n the 0th "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements other than those in the substring"
           << " '12' were not found in the string str4."
           << endl;
}
```

```Output
The original string str1 is: xddd-1234-abcd
The index of the 1st 'd' found after the 3rd position in str1 is: 4
The index of the 'non x' found in str1 is: 1

The original string str2 is: BBB-1111
Elements of the substring 'B1' were not
found in str2 after the 6th position.
The index of the 1st element of 'B2' after
the 0th position in str2 is: 3

The original string str3 is: 444-555-GGG
The index of the 1st occurrence of an element in str3
other than one of the characters in '45G' is: 3
The index of the second occurrence of an element of '45G' in str3
after the 0th position is: 7

The original string str4 is: 12-ab-12-ab
The index of the 1st non occurrence of an element of 'ba3' in str4 after
the 5th position is: 5
The index of the 1st non occurrence of an element of '12' in str4 after
the 0th position is: 2
```

## <a name="basic_stringfind_first_of"></a><a name="find_first_of"></a>basic_string:find_first_of

Belirtilen dizedeki herhangi bir öğeyle eşleşen ilk karakteri bir dize de arar.

```cpp
size_type find_first_of(
    value_type char_value,
    size_type offset = 0) const;

size_type find_first_of(
    const value_type* ptr,
    size_type offset = 0) const;

size_type find_first_of(
    const value_type* ptr,
    size_type offset,
    size_type count) const;

size_type find_first_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*char_value*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı konumun dizini.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranacak olduğu C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin aranacak dize.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

### <a name="example"></a>Örnek

```cpp
// basic_string_find_first_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "abcd-1234-abcd-1234" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_first_of ( "d" , 5 );
   if ( indexCh1a != npos )
      cout << "The index of the 1st 'd' found after the 5th"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'd' was not found in str1 ." << endl;

   indexCh1b = str1.find_first_of ( "x" );
   if ( indexCh1b != npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for any element of a substring as specified by a C-string
   string str2 ( "ABCD-1234-ABCD-1234" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_first_of ( cstr2 , 6 );
   if ( indexCh2a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'B1' in str2 after\n the 6th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements of the substring 'B1' were not "
           << "found in str2 after the 10th position."
           << endl;

   const char *cstr2b = "D2";
   indexCh2b = str2.find_first_of ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the 1st element of 'D2' "
           << "after\n the 0th position in str2 is: "
           << indexCh2b << endl << endl;
   else
      cout << "The substring 'D2' was not found in str2 ."
           << endl << endl << endl;

   // The third member function searches a string
   // for any element of a substring as specified by a C-string
   string str3 ( "123-abc-123-abc-456-EFG-456-EFG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "5G";
   indexCh3a = str3.find_first_of ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of '5G' in str3 after\n the 0th "
           << "position is: " << indexCh3a << endl;
   else
      cout << "Elements of the substring '5G' were not "
           << "found in str3\n after the 0th position."
           << endl;

   const char *cstr3b = "5GF";
   indexCh3b = str3.find_first_of  ( cstr3b , indexCh3a + 1 , 2 );
   if (indexCh3b != npos )
      cout << "The index of the second occurrence of an "
           << "element of '5G' in str3\n after the 0th "
           << "position is: " << indexCh3b << endl << endl;
   else
      cout << "Elements of the substring '5G' were not "
           << "found in str3\n after the first occurrrence."
           << endl << endl;

   // The fourth member function searches a string
   // for any element of a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "ba3" );
   indexCh4a = str4.find_first_of ( str4a , 5 );
   if ( indexCh4a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'ba3' in str4 after\n the 5th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements of the substring 'ba3' were not "
           << "found in str4\n after the 0th position."
           << endl;

   string str4b ( "a2" );
   indexCh4b = str4.find_first_of ( str4b );
   if ( indexCh4b != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'a2' in str4 after\n the 0th "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements of the substring 'a2' were not "
           << "found in str4\n after the 0th position."
           << endl;
}
```

```Output
The original string str1 is: abcd-1234-abcd-1234
The index of the 1st 'd' found after the 5th position in str1 is: 13
The character 'x' was not found in str1.

The original string str2 is: ABCD-1234-ABCD-1234
The index of the 1st occurrence of an element of 'B1' in str2 after
the 6th position is: 11
The index of the 1st element of 'D2' after
the 0th position in str2 is: 3

The original string str3 is: 123-abc-123-abc-456-EFG-456-EFG
The index of the 1st occurrence of an element of '5G' in str3 after
the 0th position is: 17
The index of the second occurrence of an element of '5G' in str3
after the 0th position is: 22

The original string str4 is: 12-ab-12-ab
The index of the 1st occurrence of an element of 'ba3' in str4 after
the 5th position is: 9
The index of the 1st occurrence of an element of 'a2' in str4 after
the 0th position is: 1
```

## <a name="basic_stringfind_last_not_of"></a><a name="find_last_not_of"></a>basic_string:find_last_not_of

Belirli bir dize herhangi bir öğesi olmayan son karakter için bir dize ile arar.

```cpp
size_type find_last_not_of(
    value_type char_value,
    size_type offset = npos) const;

size_type find_last_not_of(
    const value_type* ptr,
    size_type offset = npos) const;

size_type find_last_not_of(
    const value_type* ptr,
    size_type offset,
    size_type count) const;

size_type find_last_not_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*char_value*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın bitmek üzere olduğu konumun dizini.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranacak olduğu C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin aranacak dize.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

### <a name="example"></a>Örnek

```cpp
// basic_string_find_last_not_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "dddd-1dd4-abdd" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_last_not_of ( "d" , 7 );
   if ( indexCh1a != npos )
      cout << "The index of the last non 'd'\n found before the "
           << "7th position in str1 is: " << indexCh1a << endl;
   else
      cout << "The non 'd' character was not found ." << endl;

   indexCh1b = str1.find_last_not_of  ( "d" );
   if ( indexCh1b != npos )
      cout << "The index of the non 'd' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The Character 'non x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "BBB-1111" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_last_not_of  ( cstr2 , 6 );
   if ( indexCh2a != npos )
      cout << "The index of the last occurrence of a "
           << "element\n not of 'B1' in str2 before the 6th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements not of the substring 'B1' were not "
           << "\n found in str2 before the 6th position."
           << endl;

   const char *cstr2b = "B-1";
   indexCh2b = str2.find_last_not_of  ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the last element not "
           << "in 'B-1'\n is: "
           << indexCh2b << endl << endl;
   else
      cout << "The elements of the substring 'B-1' were "
           << "not found in str2 ."
           << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "444-555-GGG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "45G";
   indexCh3a = str3.find_last_not_of ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the last occurrence of an "
           << "element in str3\n other than one of the "
           << "characters in '45G' is: " << indexCh3a
           << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string  '45G'. "
           << endl;

   const char *cstr3b = "45G";
   indexCh3b = str3.find_last_not_of ( cstr3b , 6 , indexCh3a - 1 );
   if (indexCh3b != npos )
      cout << "The index of the penultimate occurrence of an "
           << "element\n not in '45G' in str3 is: "
           << indexCh3b << endl << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string '45G'. "
           << endl  << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "b-a" );
   indexCh4a = str4.find_last_not_of  ( str4a , 5 );
   if ( indexCh4a != npos )
      cout << "The index of the last occurrence of an "
           << "element not\n in 'b-a' in str4 before the 5th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements other than those in the substring"
           << " 'b-a' were not found in the string str4."
           << endl;

   string str4b ( "12" );
   indexCh4b = str4.find_last_not_of ( str4b  );
   if ( indexCh4b != npos )
      cout << "The index of the last occurrence of an "
           << "element not in '12'\n in str4 before the end "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements other than those in the substring"
           << " '12'\n were not found in the string str4."
           << endl;
}
```

```Output
The original string str1 is: dddd-1dd4-abdd
The index of the last non 'd'
found before the 7th position in str1 is: 5
The index of the non 'd' found in str1 is: 11

The original string str2 is: BBB-1111
The index of the last occurrence of a element
not of 'B1' in str2 before the 6th position is: 3
The elements of the substring 'B-1' were not found in str2 .

The original string str3 is: 444-555-GGG
The index of the last occurrence of an element in str3
other than one of the characters in '45G' is: 7
The index of the penultimate occurrence of an element
not in '45G' in str3 is: 3

The original string str4 is: 12-ab-12-ab
The index of the last occurrence of an element not
in 'b-a' in str4 before the 5th position is: 1
The index of the last occurrence of an element not in '12'
in str4 before the end position is: 10
```

## <a name="basic_stringfind_last_of"></a><a name="find_last_of"></a>basic_string::find_last_of

Belirtilen dizedeki herhangi bir öğeyle eşleşen son karakteri bir dize de arar.

```cpp
size_type find_last_of(
    value_type char_value,
    size_type offset = npos) const;

size_type find_last_of(
    const value_type* ptr,
    size_type offset = npos) const;

size_type find_last_of(
    const value_type* ptr,
    size_type offset,
    size_type count) const;

size_type find_last_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*char_value*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın bitmek üzere olduğu konumun dizini.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranacak olduğu C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin aranacak dize.

### <a name="return-value"></a>Dönüş Değeri

Substring son karakterinin dizin başarılı olduğunda aranır; aksi `npos`takdirde .

### <a name="example"></a>Örnek

```cpp
// basic_string_find_last_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "abcd-1234-abcd-1234" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_last_of ( "d" , 14 );
   if ( indexCh1a != npos )
      cout << "The index of the last 'd' found before the 14th"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'd' was not found in str1 ." << endl;

   indexCh1b = str1.find_first_of ( "x" );
   if ( indexCh1b != npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "ABCD-1234-ABCD-1234" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_last_of  ( cstr2 , 12 );
   if (indexCh2a != npos )
      cout << "The index of the last occurrence of an "
           << "element of 'B1' in str2 before\n the 12th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements of the substring 'B1' were not "
           << "found in str2 before the 12th position."
           << endl;

   const char *cstr2b = "D2";
   indexCh2b = str2.find_last_of  ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the last element of 'D2' "
           << "after\n the 0th position in str2 is: "
           << indexCh2b << endl << endl;
   else
      cout << "The substring 'D2' was not found in str2 ."
           << endl << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "456-EFG-456-EFG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a;

   const char *cstr3a = "5E";
   indexCh3a = str3.find_last_of ( cstr3a , 8 , 8 );
   if ( indexCh3a != npos )
      cout << "The index of the last occurrence of an "
           << "element of '5E' in str3 before\n the 8th "
           << "position is: " << indexCh3a << endl << endl;
   else
      cout << "Elements of the substring '5G' were not "
           << "found in str3\n before the 8th position."
           << endl << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "ba3" );
   indexCh4a = str4.find_last_of  ( str4a , 8 );
   if ( indexCh4a != npos )
      cout << "The index of the last occurrence of an "
           << "element of 'ba3' in str4 before\n the 8th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements of the substring 'ba3' were not "
           << "found in str4\n after the 0th position."
           << endl;

   string str4b ( "a2" );
   indexCh4b = str4.find_last_of ( str4b  );
   if ( indexCh4b != npos )
      cout << "The index of the last occurrence of an "
           << "element of 'a2' in str4 before\n the 0th "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements of the substring 'a2' were not "
           << "found in str4\n after the 0th position."
           << endl;
}
```

```Output
The original string str1 is: abcd-1234-abcd-1234
The index of the last 'd' found before the 14th position in str1 is: 13
The character 'x' was not found in str1.

The original string str2 is: ABCD-1234-ABCD-1234
The index of the last occurrence of an element of 'B1' in str2 before
the 12th position is: 11
The index of the last element of 'D2' after
the 0th position in str2 is: 16

The original string str3 is: 456-EFG-456-EFG
The index of the last occurrence of an element of '5E' in str3 before
the 8th position is: 4

The original string str4 is: 12-ab-12-ab
The index of the last occurrence of an element of 'ba3' in str4 before
the 8th position is: 4
The index of the last occurrence of an element of 'a2' in str4 before
the 0th position is: 9
```

## <a name="basic_stringfront"></a><a name="front"></a>basic_string::ön

Bir dizedeki ilk öğeye başvuru verir.

```cpp
const_reference front() const;

reference front();
```

### <a name="return-value"></a>Dönüş Değeri

Dize ilk öğesiiçin bir başvuru, boş olması gerekir.

### <a name="remarks"></a>Açıklamalar

## <a name="basic_stringget_allocator"></a><a name="get_allocator"></a>basic_string:get_allocator

Dize oluşturmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlev depolanan allocator nesnesini döndürür.

Dize sınıfının ayırıcıları sınıfın depolamayı nasıl yönettiğini belirtir. Kapsayıcı sınıfları ile birlikte verilen varsayılan ayırıcılar çoğu programlama gereksinimleri için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak gelişmiş bir C++ konusudur.

### <a name="example"></a>Örnek

```cpp
// basic_string_get_allocator.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects
   // that use the default allocator.
   string s1;
   basic_string <char> s2;
   basic_string <char, char_traits< char >, allocator< char > > s3;

   // s4 will use the same allocator class as s1
   basic_string <char> s4( s1.get_allocator ( ) );

   basic_string <char>::allocator_type xchar = s1.get_allocator( );
   // You can now call functions on the allocator class xchar used by s1
}
```

## <a name="basic_stringinsert"></a><a name="insert"></a>basic_string::ekle

Belirli bir konumda dize içine bir öğe veya bir dizi öğe veya öğe aralığı ekler.

```cpp
basic_string<CharType, Traits, Allocator>& insert(
    size_type position,
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& insert(
    size_type position,
    const value_type* ptr,
    size_type count);

basic_string<CharType, Traits, Allocator>& insert(
    size_type position,
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& insert(
    size_type position,
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset,
    size_type count);

basic_string<CharType, Traits, Allocator>& insert(
    size_type position,
    size_type count,
    value_type char_value);

iterator insert(
    iterator iter);

iterator insert(
    iterator iter,
    value_type char_value)l
template <class InputIterator>
void insert(
    iterator iter,
    InputIterator first,
    InputIterator last);

void insert(
    iterator iter,
    size_type count,
    value_type char_value);

void insert(
    iterator iter,
    const_pointer first,
    const_pointer last);

void insert(
    iterator iter,
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*Konum*\
Yeni karakterleri ekleme noktasının arkasındaki pozisyonun dizini.

*Ptr*\
C-dizesi tamamen veya kısmen dize içine eklenecek.

*Sayısı*\
Eklenecek karakter sayısı.

*Str*\
Hedef dizeiçine tamamen veya kısmen eklenecek dize.

*Uzaklık*\
Kaynak dizesinin karakterleri sağlayan bölümünün dizini eklenecek.

*char_value*\
Eklenecek öğelerin karakter değeri.

*ıter*\
Bir karakterin eklenmek üzere arkasında yer alan konumu ele alan bir yineleyici.

*Ilk*\
Kaynak aralığında eklenecek ilk öğeyi ele alan bir giriş yineleyici, const_pointer veya const_iterator.

*Son*\
Kaynak aralığında eklenecek son öğenin ötesindeki öğenin konumunu ele alan bir giriş yineleyici, const_pointer veya const_iterator.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev tarafından yeni karakterler atanan dize nesnesine bir başvuru veya tek tek karakter eklemeleri durumunda, eklenen karakterin konumunu ele alan bir yineleyici veya belirli üye işleve bağlı olarak hiçbiri.

### <a name="example"></a>Örnek

```cpp
// basic_string_insert.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function inserting a C-string
   // at a given position
   basic_string <char> str1a ( "way" );
   const char *cstr1a = "a";
   str1a.insert ( 0, cstr1a );
   cout << "The string with a C-string inserted at position 0 is: "
        << str1a << "." << endl;

   // The second member function inserting a C-string
   // at a given position for a specified number of elements
   basic_string <char> str2a ( "Good" );
   const char *cstr2a = "Bye Bye Baby";
   str2a.insert ( 4, cstr2a ,3 );
   cout << "The string with a C-string inserted at the end is: "
        << str2a << "." << endl;

   // The third member function inserting a string
   // at a given position
   basic_string <char> str3a ( "Bye" );
   string str3b ( "Good" );
   str3a.insert ( 0, str3b );
   cout << "The string with a string inserted at position 0 is: "
        << str3a << "." << endl;

   // The fourth member function inserting part of
   // a string at a given position
   basic_string <char> str4a ( "Good " );
   string str4b ( "Bye Bye Baby" );
   str4a.insert ( 5, str4b , 8 , 4 );
   cout << "The string with part of a string inserted at position 4 is: "
        << str4a << "." << endl;

   // The fifth member function inserts a number of characters
   // at a specified position in the string
   string str5 ( "The number is: ." );
   str5.insert ( 15 , 3 , '3' );
   cout << "The string with characters inserted is: "
        << str5 << endl;

   // The sixth member function inserts a character
   // at a specified position in the string
   string str6 ( "ABCDFG" );
   basic_string <char>::iterator str6_Iter = ( str6.begin ( ) + 4 );
   str6.insert ( str6_Iter , 'e' );
   cout << "The string with a character inserted is: "
        << str6 << endl;

   // The seventh member function inserts a range
   // at a specified position in the string
   string str7a ( "ABCDHIJ" );
   string str7b ( "abcdefgh" );
   basic_string <char>::iterator str7a_Iter = (str7a.begin ( ) + 4 );
   str7a.insert ( str7a_Iter , str7b.begin ( ) + 4 , str7b.end ( ) -1 );
   cout << "The string with a character inserted from a range is: "
        << str7a << endl;

   // The eighth member function inserts a number of
   // characters at a specified position in the string
   string str8 ( "ABCDHIJ" );
   basic_string <char>::iterator str8_Iter = ( str8.begin ( ) + 4 );
   str8.insert ( str8_Iter , 3 , 'e' );
   cout << "The string with a character inserted from a range is: "
        << str8 << endl;
}
```

```Output
The string with a C-string inserted at position 0 is: away.
The string with a C-string inserted at the end is: GoodBye.
The string with a string inserted at position 0 is: GoodBye.
The string with part of a string inserted at position 4 is: Good Baby.
The string with characters inserted is: The number is: 333.
The string with a character inserted is: ABCDeFG
The string with a character inserted from a range is: ABCDefgHIJ
The string with a character inserted from a range is: ABCDeeeHIJ
```

## <a name="basic_stringiterator"></a><a name="iterator"></a>basic_string::iterator

Dizedeki bir **const** öğesine erişebilen ve okuyabilen rasgele erişim yineleyici sağlayan bir tür.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `iterator` tür, bir karakterin değerini değiştirmek için kullanılabilir ve bir dize üzerinden ileri yönde yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir [begin](#begin) ve kullanılacağına `iterator`bir örnek için başlangıç örneğine bakın.

## <a name="basic_stringlength"></a><a name="length"></a>basic_string::uzunluk

Bir dizedeki geçerli öğe sayısını döndürür.

```cpp
size_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev [boyutu](#size)yla aynıdır.

### <a name="example"></a>Örnek

```cpp
// basic_string_length.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="basic_stringmax_size"></a><a name="max_size"></a>basic_string:max_size

Bir dize içerebileceği maksimum karakter sayısını döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir dize içerebileceği maksimum karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bir işlem en büyük boyuttan daha uzun bir dize ürettiğinde, sınıf [türü length_error](../standard-library/length-error-class.md) bir özel durum atılır.

### <a name="example"></a>Örnek

```cpp
// basic_string_max_size.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="basic_stringnpos"></a><a name="npos"></a>basic_string::npos

Bir arama işlevi başarısız olduğunda "bulunamadı" veya "kalan tüm karakterleri" gösteren -1'e başlalaşım bir integral değeri.

```cpp
static const size_type npos = -1;
```

### <a name="remarks"></a>Açıklamalar

İade değeri `npos` için işaretlenecek olduğunda, iade değeri size_type türünde olmadığı ve [size_type](#size_type) **int** veya **imzasız**olmadığı sürece çalışmayabilir.

### <a name="example"></a>Örnek

Nasıl bildirin ve kullanacağına `npos`ilgili bir örnek için bkz. [find](#find)

## <a name="basic_stringoperator"></a><a name="op_add_eq"></a>basic_string::operator+=

Karakterleri bir dize ekler.

```cpp
basic_string<CharType, Traits, Allocator>& operator+=(
    value_type char_value);

basic_string<CharType, Traits, Allocator>& operator+=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator+=(
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*char_value*\
Eklenecek karakter.

*Ptr*\
C-dizesinin karakterleri eklenecek.

*Doğru*\
Dize karakterleri eklenecek.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev tarafından geçirilen karakterlerle eklenen dize nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Karakterler, bir dize veya üye `operator+=` işlevleri [ekveya](#append) [push_back](#push_back)kullanılarak eklenebilir. Birden `operator+=` çok bağımsız değişken ek üye işlevi eklemek için dize belirli bir bölümünün belirtilmesine izin verirken, tek bağımsız değişken değerleri ekler.

### <a name="example"></a>Örnek

```cpp
// basic_string_op_app.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // appending a single character to a string
   string str1a ( "Hello" );
   cout << "The original string str1 is: " << str1a << endl;
   str1a +=  '!' ;
   cout << "The string str1 appended with an exclamation is: "
        << str1a << endl << endl;

   // The second member function
   // appending a C-string to a string
   string  str1b ( "Hello " );
   const char *cstr1b = "Out There";
   cout << "The C-string cstr1b is: " << cstr1b << endl;
   str1b +=  cstr1b;
   cout << "Appending the C-string cstr1b to string str1 gives: "
        << str1b << "." << endl << endl;

   // The third member function
   // appending one string to another in two ways,
   // comparing append and operator [ ]
   string str1d ( "Hello " ), str2d ( "Wide " ), str3d ( "World" );
   cout << "The string str2d is: " << str2d << endl;
   str1d.append ( str2d );
   cout << "The appended string str1d is: "
        << str1d << "." << endl;
   str1d += str3d;
   cout << "The doubly appended strig str1 is: "
        << str1d << "." << endl << endl;
}
```

```Output
The original string str1 is: Hello
The string str1 appended with an exclamation is: Hello!

The C-string cstr1b is: Out There
Appending the C-string cstr1b to string str1 gives: Hello Out There.

The string str2d is: Wide
The appended string str1d is: Hello Wide .
The doubly appended strig str1 is: Hello Wide World.
```

## <a name="basic_stringoperator"></a><a name="op_eq"></a>basic_string::operator=

Bir dizenin içeriğine yeni karakter değerleri atar.

```cpp
basic_string<CharType, Traits, Allocator>& operator=(
    value_type char_value);

basic_string<CharType, Traits, Allocator>& operator=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator=(
    const basic_string<CharType, Traits, Allocator>& right);

basic_string<CharType, Traits, Allocator>& operator=(
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>Parametreler

*char_value*\
Atanacak karakter değeri.

*Ptr*\
Hedef dize atanacak C dizesinin karakterlerine işaretçi.

*Doğru*\
Karakterleri hedef dize atanacak kaynak dize.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev tarafından yeni karakterler atanan dize nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Dizeleri yeni karakter değerleri atanabilir. Yeni değer bir dize ve C-string veya tek bir karakter olabilir. Yeni değer tek bir parametre ile açıklanabilirse, aksi takdirde birden çok parametreye sahip olan üye işlev atama, dizenin hangi bölümünün hedef dizeye atanabileceğini belirtmek için kullanılabilir. [assign](#assign) `operator=`

### <a name="example"></a>Örnek

```cpp
// basic_string_op_assign.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function assigning a
   // character of a certain value to a string
   string str1a ( "Hello " );
   str1a = '0';
   cout << "The string str1 assigned with the zero character is: "
        << str1a << endl << endl;

   // The second member function assigning the
   // characters of a C-string to a string
   string  str1b;
   const char *cstr1b = "Out There";
   cout << "The C-string cstr1b is: " << cstr1b <<  "." << endl;
   str1b = cstr1b;
   cout << "Assigning the C-string cstr1a to string str1 gives: "
        << str1b << "." << endl << endl;

   // The third member function assigning the characters
   // from one string to another string in two equivalent
   // ways, comparing the assign and operator =
   string str1c ( "Hello" ), str2c ( "Wide" ), str3c ( "World" );
   cout << "The original string str1 is: " << str1c << "." << endl;
   cout << "The string str2c is: " << str2c << "." << endl;
   str1c.assign ( str2c );
   cout << "The string str1 newly assigned with string str2c is: "
        << str1c << "." << endl;
   cout << "The string str3c is: " << str3c << "." << endl;
   str1c = str3c;
   cout << "The string str1 reassigned with string str3c is: "
        << str1c << "." << endl << endl;
}
```

```Output
The string str1 assigned with the zero character is: 0

The C-string cstr1b is: Out There.
Assigning the C-string cstr1a to string str1 gives: Out There.

The original string str1 is: Hello.
The string str2c is: Wide.
The string str1 newly assigned with string str2c is: Wide.
The string str3c is: World.
The string str1 reassigned with string str3c is: World.
```

## <a name="basic_stringoperator"></a><a name="op_at"></a>basic_string::operatör[]

Bir dize içinde belirtilen bir dizin ile karaktere bir başvuru sağlar.

```cpp
const_reference operator[](size_type offset) const;
reference operator[](size_type offset);
```

### <a name="parameters"></a>Parametreler

*Uzaklık*\
Başvurulacak öğenin konumunun dizin.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen pozisyonda dize karakterine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dize ilk öğesi sıfır bir dizin vardır ve aşağıdaki öğeleri pozitif tamsayılar tarafından ardışık olarak dizine, *n*böylece uzunluk bir dize *n* th öğesi *n* - 1 tarafından indekslenmiş.

`operator[]`bir dize öğelerine okuma ve yazma erişimi sağlamak [için](#at) üye işlevden daha hızlıdır.

`operator[]`parametre olarak geçirilen dizin geçerli olup olmadığını denetlemez, ancak üye işlev `at` geçerliliği nde kullanılması gerekir kesin değildir. Üye işleve `at` geçirilen geçersiz bir dizin (dize, siden sıfırveya daha büyük veya eşit olan bir dizin) [bir out_of_range Sınıfı](../standard-library/out-of-range-class.md) özel durum oluşturur. Tanımlanmamış davranışla `operator[]` sonuçlanan sonuçlara geçirilen geçersiz dizin, ancak dize dize sinin uzunluğuna eşit const dizeleri için geçerli bir dizindir ve işleç bu dizini geçtiğinde null karakterini döndürür.

Döndürülen başvuru, **const** olmayan dizeleri için dize gerçekleştirilmiş veya değişiklikler tarafından geçersiz kılınabilir.

[ \_ITERATOR\_HATA\_AYıKLAMA DÜZEYİ](../standard-library/iterator-debug-level.md) 1 veya 2 olarak ayarlanmış olarak derlediğinizde, dize sınırları dışında bir öğeye erişmeye çalışırsanız bir çalışma zamanı hatası oluşur. Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

```cpp
// basic_string_op_ref.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello world" ), str2 ( "Goodbye world" );
   const string cstr1 ( "Hello there" ), cstr2 ( "Goodbye now" );
   cout << "The original string str1 is: " << str1 << endl;
   cout << "The original string str2 is: " << str2 << endl;

   // Element access to the non-const strings
   basic_string <char>::reference refStr1 = str1 [6];
   basic_string <char>::reference refStr2 = str2.at ( 3 );

   cout << "The character with an index of 6 in string str1 is: "
        << refStr1 << "." << endl;
   cout << "The character with an index of 3 in string str2 is: "
        << refStr2 << "." << endl;

   // Element access to the const strings
   basic_string <char>::const_reference crefStr1 = cstr1 [ cstr1.length ( ) ];
   basic_string <char>::const_reference crefStr2 = cstr2.at ( 8 );

   if ( crefStr1 == '\0' )
      cout << "The null character is returned as a valid reference."
           << endl;
   else
      cout << "The null character is not returned." << endl;
   cout << "The character with index of 8 in the const string cstr2 is: "
        << crefStr2 << "." << endl;
}
```

## <a name="basic_stringpointer"></a><a name="pointer"></a>basic_string::pointer

Dize veya karakter dizisindeki bir karakter öğesine işaretçi sağlayan tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü için `allocator_type::pointer`eşanlamlıdır.

Türü `string`için, **bu char**<strong>\*</strong>eşdeğerdir.

### <a name="example"></a>Örnek

```cpp
// basic_string_pointer.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   basic_string<char>::pointer pstr1a = "In Here";
   char *cstr1b = "Out There";
   cout << "The string pstr1a is: " << pstr1a <<  "." << endl;
   cout << "The C-string cstr1b is: " << cstr1b << "." << endl;
}
```

```Output
The string pstr1a is: In Here.
The C-string cstr1b is: Out There.
```

## <a name="basic_stringpop_back"></a><a name="pop_back"></a>basic_string::pop_back

Dize son öğesini siler.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, `erase(size() - 1)` boş olmayan sıranın son öğesini silmek için etkin bir şekilde çağırır.

## <a name="basic_stringpush_back"></a><a name="push_back"></a>basic_string::push_back

Dize sonuna bir öğe ekler.

```cpp
void push_back(value_type char_value);
```

### <a name="parameters"></a>Parametreler

*char_value*\
Dize sonuna eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

Üye işlev etkili bir şekilde [insert](#insert)çağırır ( [end](#end), *char_value* ).

### <a name="example"></a>Örnek

```cpp
// basic_string_push_back.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "abc" );
   basic_string <char>::iterator str_Iter, str1_Iter;

   cout << "The original string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   // str1.push_back ( 'd' );
   str1_Iter = str1.end ( );
   str1_Iter--;
   cout << "The last character-letter of the modified str1 is now: "
        << *str1_Iter << endl;

   cout << "The modified string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;
}
```

```Output
The original string str1 is: abc
The last character-letter of the modified str1 is now: c
The modified string str1 is: abc
```

## <a name="basic_stringrbegin"></a><a name="rbegin"></a>basic_string::rbegin

Ters dizedeki ilk öğeye bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters bir dizedeki ilk öğeye rasgele erişim yineleyicidöndürerek, karşılık gelen geri çevrilmemiş dizedeki son öğenin ne olacağını ele alar.

### <a name="remarks"></a>Açıklamalar

`rbegin`bir dize ile kullanılan [begin](#begin) gibi ters bir dize ile kullanılır.

Bir `const_reverse_iterator`, string `rbegin` nesnesi için return value atanırsa değiştirilemez. Bir `rbegin` `reverse_iterator`, dize nesnesi için atanır.

`rbegin`bir yinelemeyi geriye doğru bir dize üzerinden başlatmak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
// basic_string_rbegin.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Able was I ere I saw Elba" ), str2;
   basic_string <char>::reverse_iterator str_rIter, str1_rIter, str2_rIter;
   basic_string <char>::const_reverse_iterator str1_rcIter;

   str1_rIter = str1.rbegin ( );
   // str1_rIter--;
   cout << "The first character-letter of the reversed string str1 is: "
        << *str1_rIter << endl;
   cout << "The full reversed string str1 is:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The dereferenced iterator can be used to modify a character
*str1_rIter = 'A';
   cout << "The first character-letter of the modified str1 is now: "
        << *str1_rIter << endl;
   cout << "The full modified reversed string str1 is now:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The following line would be an error because iterator is const
   // *str1_rcIter = 'A';

   // For an empty string, begin is equivalent to end
   if ( str2.rbegin( ) == str2.rend ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The stringstr2  is not empty." << endl;
}
```

```Output
The first character-letter of the reversed string str1 is: a
The full reversed string str1 is:
ablE was I ere I saw elbA
The first character-letter of the modified str1 is now: A
The full modified reversed string str1 is now:
AblE was I ere I saw elbA
The string str2 is empty.
```

## <a name="basic_stringreference"></a><a name="reference"></a>basic_string::referans

Dizede depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Bir `reference` tür, bir öğenin değerini değiştirmek için kullanılabilir.

Türü için `allocator_type::reference`eşanlamlıdır.

Türü `string`için, `chr&`bu eşdeğerdir .

### <a name="example"></a>Örnek

Nasıl bildirilir [at](#at) ve kullanılır. `reference`

## <a name="basic_stringrend"></a><a name="rend"></a>basic_string::rend

Ters dizedeki son öğeyi yerine getiren konumu adresleyen bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters dizedeki son öğeyi yerine getiren konumu gideren bir ters rasgele erişim yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir dize ile kullanıldığı gibi ters bir dize ile kullanılır.

Bir `const_reverse_iterator`, string `rend` nesnesi için return value atanırsa değiştirilemez. Bir `rend` `reverse_iterator`, dize nesnesi için atanır.

`rend`bir ters yineleyicinin dizesinin sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

Döndürülen `rend` değer dereferenced olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// basic_string_rend.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Able was I ere I saw Elba"), str2;
   basic_string <char>::reverse_iterator str_rIter, str1_rIter, str2_rIter;
   basic_string <char>::const_reverse_iterator str1_rcIter;

   str1_rIter = str1.rend ( );
   str1_rIter--;
   cout << "The last character-letter of the reversed string str1 is: "
        << *str1_rIter << endl;
   cout << "The full reversed string str1 is:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The dereferenced iterator can be used to modify a character
*str1_rIter = 'o';
   cout << "The last character-letter of the modified str1 is now: "
        << *str1_rIter << endl;
   cout << "The full modified reversed string str1 is now:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The following line would be an error because iterator is const
   // *str1_rcIter = 'T';

   // For an empty string, end is equivalent to begin
   if ( str2.rbegin( ) == str2.rend ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The stringstr2  is not empty." << endl;
}
```

```Output
The last character-letter of the reversed string str1 is: A
The full reversed string str1 is:
ablE was I ere I saw elbA
The last character-letter of the modified str1 is now: o
The full modified reversed string str1 is now:
ablE was I ere I saw elbo
The string str2 is empty.
```

## <a name="basic_stringreplace"></a><a name="replace"></a>basic_string::değiştir

Belirli bir konumdaki bir dizedeki öğeleri, diğer aralıklardan veya dizeleri veya C dizelerinden kopyalanan belirtilen karakterler veya karakterlerle değiştirir.

```cpp
basic_string<CharType, Traits, Allocator>& replace(
    size_type position_1,
    size_type number_1,
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& replace(
    size_type position_1,
    size_type number_1,
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& replace(
    size_type position_1,
    size_type number_1,
    const value_type* ptr,
    size_type number_2);

basic_string<CharType, Traits, Allocator>& replace(
    size_type position_1,
    size_type number_1,
    const basic_string<CharType, Traits, Allocator>& str,
    size_type position_2,
    size_type number_2);

basic_string<CharType, Traits, Allocator>& replace(
    size_type position_1,
    size_type number_1,
    size_type count,
    value_type char_value);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const value_type* ptr,
    size_type number_2);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    size_type number_2,
    value_type char_value);

template <class InputIterator>
basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    InputIterator first,
    InputIterator last);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const_pointer first,
    const_pointer last);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parametreler

*Str*\
Operand string için karakter kaynağı olacak dize.

*position_1*\
Değiştirmenin başladığı operand dizesinin dizini.

*number_1*\
Operand dizedeğiştirilecek karakter maksimum sayısı.

*position_2*\
Kopyalamanın başladığı parametre dizesinin dizini.

*number_2*\
C-string parametresinden kullanılacak maksimum karakter sayısı.

*Ptr*\
Operand dize için karakter kaynağı olacak C-string.

*char_value*\
Operand dize içine kopyalanacak karakter.

*ilk0*\
Operand dizesinde kaldırılacak ilk karaktere hitap eden bir yineleyici.

*son0*\
Operand dizesinde kaldırılacak son karaktere hitap eden bir yineleyici.

*Ilk*\
Parametre dizesinde kopyalanacak ilk karakteri ele alan bir yineleyici, const_pointer veya const_iterator.

*Son*\
Parametre dizesinde kopyalanacak son karakteri ele alan bir yineleyici, const_pointer veya const_iterator.

*Sayısı*\
*char_value* sayısı operand dize içine kopyalanır.

### <a name="return-value"></a>Dönüş Değeri

Operand string ile değiştirme yapıldı.

### <a name="example"></a>Örnek

```cpp
// basic_string_replace.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first two member functions replace
   // part of the operand string with
   // characters from a parameter string or C-string
   string result1a, result1b;
   string s1o ( "AAAAAAAA" );
   string s1p ( "BBB" );
   const char* cs1p = "CCC";
   cout << "The operand string s1o is: " << s1o << endl;
   cout << "The parameter string s1p is: " << s1p << endl;
   cout << "The parameter C-string cs1p is: " << cs1p << endl;
   result1a = s1o.replace ( 1 , 3 , s1p );
   cout << "The result of s1o.replace ( 1 , 3 , s1p )\n is "
        << "the string: " << result1a << "." << endl;
   result1b = s1o.replace ( 5 , 3 , cs1p );
   cout << "The result of s1o.replace ( 5 , 3 , cs1p )\n is "
        << "the string: " << result1b << "." << endl;
   cout << endl;

   // The third & fourth member function replace
   // part of the operand string with characters
   // form part of a parameter string or C-string
   string result2a, result2b;
   string s2o ( "AAAAAAAA" );
   string s2p ( "BBB" );
   const char* cs2p = "CCC";
   cout << "The operand string s2o is: " << s2o << endl;
   cout << "The parameter string s1p is: " << s2p << endl;
   cout << "The parameter C-string cs2p is: " << cs2p << endl;
   result2a = s2o.replace ( 1 , 3 , s2p , 1 , 2 );
   cout << "The result of s2o.replace (1, 3, s2p, 1, 2)\n is "
        << "the string: " << result2a << "." << endl;
   result2b = s2o.replace ( 4 , 3 , cs2p , 1 );
   cout << "The result of s2o.replace (4 ,3 ,cs2p)\n is "
        << "the string: " << result2b << "." << endl;
   cout << endl;

   // The fifth member function replaces
   // part of the operand string with characters
   string result3a;
   string s3o ( "AAAAAAAA" );
   char ch3p = 'C';
   cout << "The operand string s3o is: " << s3o << endl;
   cout << "The parameter character c1p is: " << ch3p << endl;
   result3a = s3o.replace ( 1 , 3 , 4 , ch3p );
   cout << "The result of s3o.replace(1, 3, 4, ch3p)\n is "
        << "the string: " << result3a << "." << endl;
   cout << endl;

   // The sixth & seventh member functions replace
   // part of the operand string, delineated with iterators,
   // with a parameter string or C-string
   string s4o ( "AAAAAAAA" );
   string s4p ( "BBB" );
   const char* cs4p = "CCC";
   cout << "The operand string s4o is: " << s4o << endl;
   cout << "The parameter string s4p is: " << s4p << endl;
   cout << "The parameter C-string cs4p is: " << cs4p << endl;
   basic_string<char>::iterator IterF0, IterL0;
   IterF0 = s4o.begin ( );
   IterL0 = s4o.begin ( ) + 3;
   string result4a, result4b;
   result4a = s4o.replace ( IterF0 , IterL0 , s4p );
   cout << "The result of s1o.replace (IterF0, IterL0, s4p)\n is "
        << "the string: " << result4a << "." << endl;
   result4b = s4o.replace ( IterF0 , IterL0 , cs4p );
   cout << "The result of s4o.replace (IterF0, IterL0, cs4p)\n is "
        << "the string: " << result4b << "." << endl;
   cout << endl;

   // The 8th member function replaces
   // part of the operand string delineated with iterators
   // with a number of characters from a parameter C-string
   string s5o ( "AAAAAAAF" );
   const char* cs5p = "CCCBB";
   cout << "The operand string s5o is: " << s5o << endl;
   cout << "The parameter C-string cs5p is: " << cs5p << endl;
   basic_string<char>::iterator IterF1, IterL1;
   IterF1 = s5o.begin ( );
   IterL1 = s5o.begin ( ) + 4;
   string result5a;
   result5a = s5o.replace ( IterF1 , IterL1 , cs5p , 4 );
   cout << "The result of s5o.replace (IterF1, IterL1, cs4p ,4)\n is "
        << "the string: " << result5a << "." << endl;
   cout << endl;

   // The 9th member function replaces
   // part of the operand string delineated with iterators
   // with specified characters
   string s6o ( "AAAAAAAG" );
   char ch6p = 'q';
   cout << "The operand string s6o is: " << s6o << endl;
   cout << "The parameter character ch6p is: " << ch6p << endl;
   basic_string<char>::iterator IterF2, IterL2;
   IterF2 = s6o.begin ( );
   IterL2 = s6o.begin ( ) + 3;
   string result6a;
   result6a = s6o.replace ( IterF2 , IterL2 , 4 , ch6p );
   cout << "The result of s6o.replace (IterF1, IterL1, 4, ch6p)\n is "
        << "the string: " << result6a << "." << endl;
   cout << endl;

   // The 10th member function replaces
   // part of the operand string delineated with iterators
   // with part of a parameter string delineated with iterators
   string s7o ( "OOOOOOO" );
   string s7p ( "PPPP" );
   cout << "The operand string s7o is: " << s7o << endl;
   cout << "The parameter string s7p is: " << s7p << endl;
   basic_string<char>::iterator IterF3, IterL3, IterF4, IterL4;
   IterF3 = s7o.begin ( ) + 1;
   IterL3 = s7o.begin ( ) + 3;
   IterF4 = s7p.begin ( );
   IterL4 = s7p.begin ( ) + 2;
   string result7a;
   result7a = s7o.replace ( IterF3 , IterL3 , IterF4 , IterL4 );
   cout << "The result of s7o.replace (IterF3 ,IterL3 ,IterF4 ,IterL4)\n is "
        << "the string: " << result7a << "." << endl;
   cout << endl;
}
```

```Output
The operand string s1o is: AAAAAAAA
The parameter string s1p is: BBB
The parameter C-string cs1p is: CCC
The result of s1o.replace ( 1 , 3 , s1p )
is the string: ABBBAAAA.
The result of s1o.replace ( 5 , 3 , cs1p )
is the string: ABBBACCC.

The operand string s2o is: AAAAAAAA
The parameter string s1p is: BBB
The parameter C-string cs2p is: CCC
The result of s2o.replace (1, 3, s2p, 1, 2)
is the string: ABBAAAA.
The result of s2o.replace (4 ,3 ,cs2p)
is the string: ABBAC.

The operand string s3o is: AAAAAAAA
The parameter character c1p is: C
The result of s3o.replace(1, 3, 4, ch3p)
is the string: ACCCCAAAA.

The operand string s4o is: AAAAAAAA
The parameter string s4p is: BBB
The parameter C-string cs4p is: CCC
The result of s1o.replace (IterF0, IterL0, s4p)
is the string: BBBAAAAA.
The result of s4o.replace (IterF0, IterL0, cs4p)
is the string: CCCAAAAA.

The operand string s5o is: AAAAAAAF
The parameter C-string cs5p is: CCCBB
The result of s5o.replace (IterF1, IterL1, cs4p ,4)
is the string: CCCBAAAF.

The operand string s6o is: AAAAAAAG
The parameter character ch6p is: q
The result of s6o.replace (IterF1, IterL1, 4, ch6p)
is the string: qqqqAAAAG.

The operand string s7o is: OOOOOOO
The parameter string s7p is: PPPP
The result of s7o.replace (IterF3 ,IterL3 ,IterF4 ,IterL4)
is the string: OPPOOOO.
```

## <a name="basic_stringreserve"></a><a name="reserve"></a>basic_string::rezerv

Dize kapasitesini en az belirtilen sayı kadar büyük bir sayıya ayarlar.

```cpp
void reserve(size_type count = 0);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Belleğin rezerve edildiği karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Gerçekleşmeler zaman alan bir işlem olduğundan ve bir dizedeki karakterlere başvuran tüm başvuruları, işaretçileri ve yineleyicileri geçersiz kıldığı için yeterli kapasiteye sahip olmak önemlidir.

Tür dizeleri nesneleri için kapasite kavramı, tür vektör nesneleri için aynıdır. Vektörün aksine, `reserve` üye işlev bir nesnenin kapasitesini küçültmek için çağrılabilir. İstek bağlayıcı değildir ve gerçekleşebilir veya olmayabilir. Parametrenin varsayılan değeri sıfır olduğundan, dizedeki karakter sayısını sığdırmak için dize kapasitesini küçültmek için bağlayıcı olmayan bir `reserve` istek çağrıdır. Kapasite hiçbir zaman geçerli karakter sayısının altına düşürülmez.

Arama, `reserve` bir dizenin kapasitesini küçültmenin tek olası yoludur. Ancak, yukarıda belirtildiği gibi, bu istek bağlayıcı değildir ve gerçekleşmeyebilir.

### <a name="example"></a>Örnek

```cpp
// basic_string_reserve.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   basic_string <char>::size_type sizeStr1, sizerStr1;
   sizeStr1 = str1.size ( );
   basic_string <char>::size_type capStr1, caprStr1;
   capStr1 = str1.capacity ( );

   // Compare size & capacity of the original string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl << endl;

   // Compare size & capacity of the string
   // with added capacity
   str1.reserve ( 40 );
   sizerStr1 = str1.size ( );
   caprStr1 = str1.capacity ( );

   cout << "The string str1with augmented capacity is: "
        << str1 << endl;
   cout << "The current size of string str1 is: "
        << sizerStr1 << "." << endl;
   cout << "The new capacity of string str1 is: "
        << caprStr1 << "." << endl << endl;

   // Compare size & capacity of the string
   // with downsized capacity
   str1.reserve ( );
   basic_string <char>::size_type sizedStr1;
   basic_string <char>::size_type capdStr1;
   sizedStr1 = str1.size ( );
   capdStr1 = str1.capacity ( );

   cout << "The string str1 with downsized capacity is: "
        << str1 << endl;
   cout << "The current size of string str1 is: "
        << sizedStr1 << "." << endl;
   cout << "The reduced capacity of string str1 is: "
        << capdStr1 << "." << endl << endl;
}
```

```Output
The original string str1 is: Hello world
The current size of original string str1 is: 11.
The capacity of original string str1 is: 15.

The string str1with augmented capacity is: Hello world
The current size of string str1 is: 11.
The new capacity of string str1 is: 47.

The string str1 with downsized capacity is: Hello world
The current size of string str1 is: 11.
The reduced capacity of string str1 is: 47.
```

## <a name="basic_stringresize"></a><a name="resize"></a>basic_string::yeniden boyutlandırma

Bir dize için yeni bir boyut belirtir, gerektiğinde öğeleri ekler veya siler.

```cpp
void resize(
    size_type count,);

void resize(
    size_type count,
    value_type char_value);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Dizenin yeni boyutu.

*char_value*\
Ek öğeler gerekiyorsa eklenen karakterlerin baş harflerle çevrilen değeri.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan boyut maksimum karakter sayısını aşarsa, form `length_error`atar.

### <a name="example"></a>Örnek

```cpp
// basic_string_resize.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string  str1 ( "Hello world" );
   cout << "The original string str1 is: " << str1 << endl;

   basic_string <char>::size_type sizeStr1;
   sizeStr1 = str1.size ( );
   basic_string <char>::size_type capStr1;
   capStr1 = str1.capacity ( );

   // Compare size & capacity of the original string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl << endl;

   // Use resize to increase size by 2 elements: exclamations
   str1.resize ( str1.size ( ) + 2 , '!' );
   cout << "The resized string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   capStr1 = str1.capacity ( );

   // Compare size & capacity of a string after resizing
   cout << "The current size of resized string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of resized string str1 is: "
        << capStr1 << "." << endl << endl;

   // Use resize to increase size by 20 elements:
   str1.resize ( str1.size ( ) + 20 );
   cout << "The resized string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   capStr1 = str1.capacity ( );

   // Compare size & capacity of a string after resizing
   // note capacity increases automatically as required
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl << endl;

   // Use resize to downsize by 28 elements:
   str1.resize ( str1.size ( ) - 28 );
   cout << "The downsized string str1 is: " << str1 << endl;

   sizeStr1 = str1.size (  );
   capStr1 = str1.capacity (  );

   // Compare size & capacity of a string after downsizing
   cout << "The current size of downsized string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of downsized string str1 is: "
        << capStr1 << "." << endl;
}
```

```Output
The original string str1 is: Hello world
The current size of original string str1 is: 11.
The capacity of original string str1 is: 15.

The resized string str1 is: Hello world!!
The current size of resized string str1 is: 13.
The capacity of resized string str1 is: 15.

The resized string str1 is: Hello world!!
The current size of modified string str1 is: 33.
The capacity of modified string str1 is: 47.

The downsized string str1 is: Hello
The current size of downsized string str1 is: 5.
The capacity of downsized string str1 is: 47.
```

## <a name="basic_stringreverse_iterator"></a><a name="reverse_iterator"></a>basic_string:reverse_iterator

Dizede depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir `reverse_iterator` tür bir karakterin değerini değiştirmek için kullanılabilir ve ters bir dize ile yinelemek için kullanılır.

### <a name="example"></a>Örnek

Nasıl bildirilir ve kullanılacağına `reverse_iterator`bir örnek için [rbegin](#rbegin) örneğine bakın.

## <a name="basic_stringrfind"></a><a name="rfind"></a>basic_string::rfind

Belirli bir karakter dizisiyle eşleşen bir alt dizeilk oluşumu için geriye doğru bir yönde bir dize arar.

```cpp
size_type rfind(
    value_type char_value,
    size_type offset = npos) const;

size_type rfind(
    const value_type* ptr,
    size_type offset = npos) const;

size_type rfind(
    const value_type* ptr,
    size_type offset,
    size_type count) const;

size_type rfind(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*char_value*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı konumun dizini.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranacak olduğu C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin aranacak dize.

### <a name="return-value"></a>Dönüş Değeri

Geriye doğru arandığında, substring'in ilk karakterinin başarılı olduğunda son oluşumun dizini; aksi `npos`takdirde .

### <a name="example"></a>Örnek

```cpp
// basic_string_rfind.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "Hello Everyone" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.rfind ( "e" , 9 );
   if ( indexCh1a != npos )
      cout << "The index of the 1st 'e' found before the 9th"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'e' was not found in str1 ." << endl;

   indexCh1b = str1.rfind ( "x" );
   if ( indexCh1b != npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "Let me make this perfectly clear." );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "perfect";
   indexCh2a = str2.rfind ( cstr2 , 30 );
   if ( indexCh2a != npos )
      cout << "The index of the 1st element of 'perfect' "
           << "before\n the 30th position in str2 is: "
           << indexCh2a << endl;
   else
      cout << "The substring 'perfect' was not found in str2 ."
           << endl;

   const char *cstr2b = "imperfectly";
   indexCh2b = str2.rfind ( cstr2b , 30 );
   if ( indexCh2b != npos )
      cout << "The index of the 1st element of 'imperfect' "
           << "before\n the 5th position in str3 is: "
           << indexCh2b << endl;
   else
      cout << "The substring 'imperfect' was not found in str2 ."
           << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "It is a nice day. I am happy." );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "nice";
   indexCh3a = str3.rfind ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the 1st element of 'nice' "
           << "in str3 is: " << indexCh3a << endl;
   else
      cout << "The substring 'nice' was not found in str3 ."
           << endl;

   const char *cstr3b = "am";
   indexCh3b = str3.rfind ( cstr3b , indexCh3a + 25 , 2 );
   if ( indexCh3b != npos )
      cout << "The index of the next occurrence of 'am' in "
           << "str3 begins at: " << indexCh3b << endl << endl;
   else
      cout << "There is no next occurrence of 'am' in str3 ."
           << endl << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "This perfectly unclear." );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "clear" );
   indexCh4a = str4.rfind ( str4a , 15 );
   if (indexCh4a != npos )
      cout << "The index of the 1st element of 'clear' "
           << "before\n the 15th position in str4 is: "
           << indexCh4a << endl;
   else
      cout << "The substring 'clear' was not found in str4 "
           << "before the 15th position." << endl;

   string str4b ( "clear" );
   indexCh4b = str4.rfind ( str4b );
   if ( indexCh4b != npos )
      cout << "The index of the 1st element of 'clear' "
           << "in str4 is: "
           << indexCh4b << endl;
   else
      cout << "The substring 'clear' was not found in str4 ."
           << endl << endl;
}
```

```Output
The original string str1 is: Hello Everyone
The index of the 1st 'e' found before the 9th position in str1 is: 8
The character 'x' was not found in str1.

The original string str2 is: Let me make this perfectly clear.
The index of the 1st element of 'perfect' before
the 30th position in str2 is: 17
The substring 'imperfect' was not found in str2 .

The original string str3 is: It is a nice day. I am happy.
The index of the 1st element of 'nice' in str3 is: 8
The index of the next occurrence of 'am' in str3 begins at: 20

The original string str4 is: This perfectly unclear.
The substring 'clear' was not found in str4 before the 15th position.
The index of the 1st element of 'clear' in str4 is: 17
```

## <a name="basic_stringshrink_to_fit"></a><a name="shrink_to_fit"></a>basic_string::shrink_to_fit

Dizenin fazla kapasitesini atar.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kapsayıcıdaki gereksiz depolama alanını ortadan kaldırır.

## <a name="basic_stringsize"></a><a name="size"></a>basic_string::boyut

Bir dizedeki geçerli öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize uzunluğu.

### <a name="example"></a>Örnek

```cpp
// basic_string_size.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size (  );
   lenStr1 = str1.length (  );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity (  );
   max_sizeStr1 = str1.max_size (  );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="basic_stringsize_type"></a><a name="size_type"></a>basic_string:size_type

Bir dizedeki öğe ve indeks sayısını temsil eden imzasız bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

'ye `allocator_type::size_type`eşdeğerdir.

Türü `string`için, `size_t`bu eşdeğerdir .

### <a name="example"></a>Örnek

```cpp
// basic_string_size_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello world" );

   basic_string <char>::size_type sizeStr1, capStr1;
   sizeStr1 = str1.size (  );
   capStr1 = str1.capacity (  );

   cout << "The current size of string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of string str1 is: " << capStr1
         << "." << endl;
}
```

```Output
The current size of string str1 is: 11.
The capacity of string str1 is: 15.
```

## <a name="basic_stringsubstr"></a><a name="substr"></a>basic_string::substr

Belirli bir konumdan başlayarak bir dizeden en fazla belirli sayıda karakterin bir alt dizesini kopyalar.

```cpp
basic_string<CharType, Traits, Allocator> substr(
    size_type offset = 0,
    size_type count = npos) const;
```

### <a name="parameters"></a>Parametreler

*Uzaklık*\
Varsayılan değeri 0 olan dize, dize kopyasının yapıldığı konumdaöğeyi bulucu.

*Sayısı*\
Varsa kopyalanacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk bağımsız değişkentarafından belirtilen konumdan başlayan dize operand öğelerinin kopyası olan bir alt dize nesnesi.

### <a name="example"></a>Örnek

```cpp
// basic_string_substr.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string  str1 ("Heterological paradoxes are persistent.");
   cout << "The original string str1 is: \n " << str1
        << endl << endl;

   basic_string <char> str2 = str1.substr ( 6 , 7 );
   cout << "The substring str1 copied is: " << str2
        << endl << endl;

   basic_string <char> str3 = str1.substr (  );
   cout << "The default substring str3 is: \n " << str3
        <<  "\n which is the entire original string." << endl;
}
```

```Output
The original string str1 is:
Heterological paradoxes are persistent.

The substring str1 copied is: logical

The default substring str3 is:
Heterological paradoxes are persistent.
which is the entire original string.
```

## <a name="basic_stringswap"></a><a name="swap"></a>basic_string::takas

İki dizenin içeriğini değiştirin.

```cpp
void swap(
    basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
Öğeleri hedef dizedekilerle değiştirilecek kaynak dize.

### <a name="remarks"></a>Açıklamalar

Değiştirilen dizeler aynı ayırıcı nesneye sahipse, `swap` üye işlev:

- Sabit zaman içinde oluşur.

- İstisna lar da etmez.

- İki dizedeki öğeleri belirleyen hiçbir başvuru, işaretçi veya yineleyici geçersiz kılmaz.

Aksi takdirde, bir dizi öğe ataması gerçekleştirir ve yapılandırıcı çağrıları iki denetimli dizideki eleman sayısıyla orantılı olarak gerçekleştirir.

### <a name="example"></a>Örnek

```cpp
// basic_string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << " The basic_string s1 = " << s1 << "." << endl;
   cout << " The basic_string s2 = " << s2 << "." << endl;

   s1.swap ( s2 );
   cout << "After swapping string s1 and s2:" << endl;
   cout << " The basic_string s1 = " << s1 << "." << endl;
   cout << " The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.
After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="basic_stringtraits_type"></a><a name="traits_type"></a>basic_string:traits_type

Bir dize de depolanan öğelerin karakter özellikleri için bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, ikinci şablon parametresi `Traits`ile eş anlamlıdır.

Türü `string`için, **char_traits\<char>** eşdeğerdir.

### <a name="example"></a>Örnek

Nasıl bildirilir [copy](../standard-library/char-traits-struct.md#copy) ve kullanılacağına `traits_type`bir örnek için kopya örneği bakın.

## <a name="basic_stringvalue_type"></a><a name="value_type"></a>basic_string:value_type

Dizede depolanan karakter türünü temsil eden bir tür.

```cpp
typedef typename allocator_type::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Bu tür `string`nesneler `traits_type::char_type` için **char** eşdeğerdir ve .

### <a name="example"></a>Örnek

```cpp
// basic_string_value_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   basic_string<char>::value_type ch1 = 'G';

   char ch2 = 'H';

   cout << "The character ch1 is: " << ch1 << "." << endl;
   cout << "The character ch2 is: " << ch2 << "." << endl;
}
```

```Output
The character ch1 is: G.
The character ch2 is: H.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<dize>](../standard-library/string.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
