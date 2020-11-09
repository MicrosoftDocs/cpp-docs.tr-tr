---
title: basic_string Sınıfı
description: Standart C++ dize sınıfı için API başvurusu `basic_string` .
ms.date: 10/26/2020
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
- xstring/std::basic_string::ends_with
- xstring/std::basic_string::starts_with
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
- std::basic_string [C++], starts_with
- std::basic_string [C++], ends_with
- std::basic_string [C++], substr
- std::basic_string [C++], swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: 87eda4064ff63a22add49b2872a26c76ac15bc6a
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381655"
---
# <a name="basic_string-class"></a>`basic_string` Sınıfı

Türünde bir nesne tarafından denetlenen sıralar `basic_string` Standart C++ dize sınıfıdır ve genellikle dizeler olarak adlandırılır, ancak C++ standart kitaplığı boyunca kullanılan null ile sonlandırılmış C stili dizeleriyle karıştırılmamalıdır. Standart C++ dizesi; karşılaştırma ve birleştirme işlemleri, yineleyiciler, C++ standart kitaplık algoritmaları ve sınıf ayırıcısı tarafından yönetilen bellek kopyalama ve atama gibi normal türler olarak dizelerin kullanımını sağlayan bir kapsayıcıdır. Standart bir C++ dizesini null ile sonlandırılmış bir C stili dizeye dönüştürmeniz gerekiyorsa [basic_string:: c_str](#c_str) üyesini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_string;
```

### <a name="parameters"></a>Parametreler

*`CharType`*\
Dizedeki depolanacak tek bir karakterin veri türü. C++ standart kitaplığı, bu sınıf şablonunun uzmanlıklarını,, for, ve için türündeki öğeler için tür tanımlarıyla birlikte sunar [`string`](../standard-library/string-typedefs.md#string) `char` [`wstring`](../standard-library/string-typedefs.md#wstring) `wchar_t` [`u16string`](../standard-library/string-typedefs.md#u16string) `char16_t` [`u32string`](../standard-library/string-typedefs.md#u32string) `char32_t` .

*`Traits`*\
`CharType`Basic_string uzmandaki öğelerin çeşitli önemli özellikleri, sınıfı tarafından açıklanmıştır `Traits` . Varsayılan değer `char_traits` < `CharType`>.

*`Allocator`*\
Dizenin bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. `allocator<CharType>` varsayılan değerdir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[`basic_string`](#basic_string)|Boş veya belirli karakterler tarafından başlatılan veya bir diğer dize nesnesinin veya C dizesinin tümünün veya bir kısmının kopyası olan bir dize oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[`allocator_type`](#allocator_type)|`allocator`Bir dize nesnesinin sınıfını temsil eden bir tür.|
|[`const_iterator`](#const_iterator)|Dizedeki bir öğeye erişebilen ve okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `const` .|
|[`const_pointer`](#const_pointer)|Dizedeki bir öğeye işaretçi sağlayan bir tür `const` .|
|[`const_reference`](#const_reference)|`const`İşlem okumak ve gerçekleştirmek için bir dizede depolanan öğeye başvuru sağlayan bir tür `const` .|
|[`const_reverse_iterator`](#const_reverse_iterator)|Dizedeki herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `const` .|
|[`difference_type`](#difference_type)|Aynı dize içindeki öğelere başvuran iki yineleyiciler arasındaki farkı sağlayan bir tür.|
|[`iterator`](#iterator)|Bir dizedeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir rasgele erişim yineleyicisi sağlayan bir tür.|
|[`npos`](#npos)|Bir arama işlevi başarısız olduğunda "bulunamadı" veya "tüm kalan karakterler" i gösteren-1 ' e başlatılan işaretsiz bir tamsayı değeri.|
|[`pointer`](#pointer)|Bir dize veya karakter dizisinde bir karakter öğesi işaretçisi sağlayan bir tür.|
|[`reference`](#reference)|Bir dizede depolanan bir öğeye başvuru sağlayan bir tür.|
|[`reverse_iterator`](#reverse_iterator)|Ters çevrilen bir dizedeki bir öğeyi okuyabilen veya değiştirebilen bir rastgele erişim yineleyici sağlayan bir tür.|
|[`size_type`](#size_type)|Dizedeki öğe sayısı için işaretsiz integral türü.|
|[`traits_type`](#traits_type)|Bir dizede depolanan öğelerin karakter nitelikleri için bir tür.|
|[`value_type`](#value_type)|Bir dizede depolanan karakterlerin türünü temsil eden bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[`append`](#append)|Dizenin sonuna karakter ekler.|
|[`assign`](#assign)|Bir dizenin içeriğine yeni karakter değerleri atar.|
|[`at`](#at)|Dizedeki belirtilen konumdaki öğeye bir başvuru döndürür.|
|[`back`](#back)||
|[`begin`](#begin)|Dizedeki ilk öğeyi adresleyen bir yineleyici döndürür.|
|[`c_str`](#c_str)|Bir dizenin içeriğini C stili, null sonlandırılmış, dize olarak dönüştürür.|
|[`capacity`](#capacity)|Dizenin bellek ayırmayı arttırmadan bir dizede depolanabilecek en büyük öğe sayısını döndürür.|
|[`cbegin`](#cbegin)|Dizedeki ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[`cend`](#cend)|Dizedeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[`clear`](#clear)|Bir dizenin tüm öğelerini siler.|
|[`compare`](#compare)|İki dizenin eşit olup olmadığını veya birinin lexıgrafik değerinden daha küçük olduğunu anlamak için belirtilen dizeyle bir dizeyi karşılaştırır.|
|[`copy`](#copy)|Kaynak dizedeki dizinli bir konumdan bir hedef karakter dizisine en çok belirtilen sayıda karakter kopyalar. Kullanım dışı. [`basic_string::_Copy_s`](#copy_s)Bunun yerine kullanın.|
|[`crbegin`](#crbegin)|Ters çevrilen dizedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|
|[`crend`](#crend)|Ters çevrilen dizedeki son öğeden sonraki konumu ele alan bir const yineleyici döndürür.|
|[`_Copy_s`](#copy_s)|Kaynak dizedeki dizinli bir konumdan bir hedef karakter dizisine en çok belirtilen sayıda karakter kopyalar.|
|[`data`](#data)|Bir dizenin içeriğini bir karakter dizisine dönüştürür.|
|[`empty`](#empty)|Dizenin karakter içerip içermediğini test eder.|
|[`end`](#end)|Dizedeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.|
|[`ends_with`](#ends_with)<sup>C++ 20</sup>|Dizenin belirtilen soneke göre sona erip bitmediğini denetler.|
|[`erase`](#erase)|Bir dizedeki bir öğeyi veya öğe aralığını belirtilen konumdan kaldırır.|
|[`find`](#find)|Belirtilen karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için bir dizeyi ileriye doğru yönde arar.|
|[`find_first_not_of`](#find_first_not_of)|Belirtilen bir dizenin herhangi bir öğesi olmayan ilk karakter için bir dizeyi arar.|
|[`find_first_of`](#find_first_of)|Belirtilen dizenin herhangi bir öğesiyle eşleşen ilk karakter için bir dizeyi arar.|
|[`find_last_not_of`](#find_last_not_of)|Belirli bir dizenin herhangi bir öğesi olmayan son karakter için bir dizeyi arar.|
|[`find_last_of`](#find_last_of)|Belirtilen dizenin bir öğesi olan son karakter için bir dizeyi arar.|
|[`front`](#front)|Dizedeki ilk öğeye bir başvuru döndürür.|
|[`get_allocator`](#get_allocator)|`allocator`Dizeyi oluşturmak için kullanılan nesnenin bir kopyasını döndürür.|
|[`insert`](#insert)|Belirli bir konumdaki dizeye bir öğe veya dizi öğe veya öğe aralığı ekler.|
|[`length`](#length)|Dizedeki geçerli öğe sayısını döndürür.|
|[`max_size`](#max_size)|Bir dizenin içerebileceği en fazla karakter sayısını döndürür.|
|[`pop_back`](#pop_back)|Dizenin son öğesini siler.|
|[`push_back`](#push_back)|Dizenin sonuna bir öğesi ekler.|
|[`rbegin`](#rbegin)|Ters çevrilen dizedeki ilk öğeye bir yineleyici döndürür.|
|[`rend`](#rend)|Ters çevrilen dizedeki son öğenin hemen ötesine işaret eden bir yineleyici döndürür.|
|[`replace`](#replace)|Belirli bir konumdaki bir dizedeki öğeleri, belirtilen karakterlerle veya diğer aralıklardan ya da dizelerle veya C dizelerinden kopyalanmış karakterlerle değiştirir.|
|[`reserve`](#reserve)|Dizenin kapasitesini, belirtilen sayı kadar en az bir sayı olarak ayarlar.|
|[`resize`](#resize)|Bir dize için yeni bir boyut belirtir, gerektiğinde öğeleri ekleme veya silme.|
|[`rfind`](#rfind)|Belirtilen karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için bir dizeyi geriye doğru yönde arar.|
|[`shrink_to_fit`](#shrink_to_fit)|Dizenin fazla kapasitesini atar.|
|[`size`](#size)|Dizedeki geçerli öğe sayısını döndürür.|
|[`starts_with`](#starts_with)<sup>C++ 20</sup>|Dizenin belirtilen önekle başlatılıp başlatılmayacağını denetler.|
|[`substr`](#substr)|Belirli bir konumdan başlayarak bir dizeden en fazla sayıda karakter alt dizesini kopyalar.|
|[`swap`](#swap)|İki dizenin içeriğini değiş tokuş edin.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[`operator+=`](#op_add_eq)|Bir dizeye karakter ekler.|
|[`operator=`](#op_eq)|Bir dizenin içeriğine yeni karakter değerleri atar.|
|[`operator`&#91;&#93;](#op_at)|Bir dizedeki belirtilen dizine sahip karaktere bir başvuru sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir işlevin öğelerinden daha uzun bir sıra oluşturması istenirse [`max_size`](#max_size) , işlev, türünde bir nesne oluşturarak bir uzunluk hatası bildiriyor [`length_error`](../standard-library/length-error-class.md) .

Denetlenen diziyi değiştiren bir işleve yapılan herhangi bir çağrıdan sonra veya üye olmayan bir işleve ilk çağrıdan sonra, başvurular, işaretçiler ve yineleyiciler, denetim sırasını değiştiren bir işlev çağrısından sonra geçersiz hale gelebilir `const` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<string>

**Ad alanı:** std

## <a name="basic_stringallocator_type"></a><a name="allocator_type"></a> `basic_string::allocator_type`

Bir dize nesnesi için ayırıcı sınıfını temsil eden bir tür.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Allocator` .

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

## <a name="basic_stringappend"></a><a name="append"></a> `basic_string::append`

Dizenin sonuna karakter ekler.

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

*`ptr`*\
Eklenecek C dizesi.

*`str`*\
Karakterleri eklenecek dize.

*`offset`*\
Eklenecek karakterleri sağlayan kaynak dize bölümünün dizini.

*`count`*\
Kaynak dizeden en fazla eklenecek karakter sayısı.

*`char_value`*\
Eklenecek karakter değeri.

*`first`*\
Eklenecek aralıktaki ilk öğeyi ele almak için bir giriş Yineleyici.

*`last`*\
Bir giriş yineleyicisi, `const_pointer` veya `const_iterator` eklenecek aralıktaki son öğenin ötesinde birinin konumunu ele alıyor.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi tarafından geçirilen karakterlerle eklenen String nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Veya üye işlevleri kullanılarak bir dizeye karakterler eklenebilir [`operator+=`](#op_add_eq) `append` [`push_back`](#push_back) . `operator+=` birden çok bağımsız değişken `append` üye işlevi, bir dizenin belirli bir bölümünün ekleme için belirtilmesini olanaklı tutarken tek bağımsız değişken değerleri ekler.

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

## <a name="basic_stringassign"></a><a name="assign"></a> `basic_string::assign`

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

*`ptr`*\
Hedef dizeye atanacak C dizesinin karakterlerine yönelik bir işaretçi.

*`count`*\
Kaynak dizeden atanacak karakter sayısı.

*`str`*\
Hedef dizeye karakterler atanacak kaynak dize.

*`char_value`*\
Atanacak karakter değeri.

*`first`*\
Hedef aralığa atanacak kaynak dize aralığındaki ilk karakteri adresleyen bir giriş yineleyicisi, const_pointer veya const_iterator.

*`last`*\
Hedef aralığa atanacak kaynak dize aralığındaki son karakterin ötesinde bir giriş yineleyicisi, const_pointer veya const_iterator.

*`off`*\
Yeni karakterlerin atanmak üzere başlayacağı konum.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi tarafından yeni karakterler atanmakta olan String nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dizelere yeni karakter değerleri atanabilir. Yeni değer bir dize ve C dizesi ya da tek bir karakter olabilir. [`operator=`](#op_eq)Yeni değer tek bir parametre tarafından açıklanabileceği durumlarda kullanılabilir; Aksi takdirde, `assign` birden fazla parametreye sahip üye işlevi, dizenin hangi kısmının hedef dizeye atandığını belirtmek için kullanılabilir.

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

## <a name="basic_stringat"></a><a name="at"></a> `basic_string::at`

Bir dizedeki belirtilen dizine sahip karaktere bir başvuru sağlar.

```cpp
const_reference at(size_type offset) const;

reference at(size_type offset);
```

### <a name="parameters"></a>Parametreler

*`offset`*\
Başvurulacak öğenin konumunun dizini.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen konumdaki dizenin karakteriyle bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk öğesi sıfır dizinine sahiptir ve aşağıdaki öğeler pozitif tamsayılar tarafından ardışık olarak dizinlenir, böylece *n* uzunluklu bir dize, n *-* 1 sayısı tarafından dizine alınmış bir *n*. öğesi vardır.

Üye [ `operator`&#91;&#93;](#op_at) , `at` bir dizenin öğelerine okuma ve yazma erişimi sağlamak için üye işlevinden daha hızlıdır.

Üye, `operator[]` parametre olarak geçirilen dizinin geçerli olup olmadığını denetlemez, ancak üye işlevi çalışır durumda değilse bu değer `at` kullanılmalıdır. Bir dizin, dize boyutundan sıfır veya daha büyük ya da buna eşit olan, üye işlevine geçirilen bir `at` [out_of_range sınıfı](../standard-library/out-of-range-class.md) özel durumu oluşturan geçersiz bir dizin. Tanımsız bir davranıştaki sonuçlara geçersiz bir dizin geçirildi `operator[]` , ancak dizenin uzunluğuna eşit olan dizin const dizeler için geçerli bir dizindir ve işleç bu dizine geçirildiğinde null karakteri döndürüyor.

Döndürülen başvuru dize reallocations veya dizeler için değişiklikler tarafından geçersiz kılınabilir `const` .

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

## <a name="basic_stringback"></a><a name="back"></a> `basic_string::back`

Dizedeki son öğeye bir başvuru döndürür.

```cpp
const_reference back() const;

reference back();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin boş olmayan bir son öğesine başvuru.

### <a name="remarks"></a>Açıklamalar

## <a name="basic_stringbasic_string"></a><a name="basic_string"></a> `basic_string::basic_string`

Boş olan, belirli karakterler tarafından başlatılan veya başka bir dize nesnesinin veya C Style (null sonlandırılmış) dizenin tümünün veya bir kısmının kopyası olan bir dize oluşturur.

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

*`ptr`*\
Oluşturulan karakter, karakterlerini başlatmak için kullanılacak olan C dizesi `string` . Bu değer, null bir işaretçi olamaz.

*`alloc_type`*\
Oluşturulan dize nesnesinin depolama ayırıcı sınıfı.

*`count`*\
Başlatılacak karakter sayısı.

*`right`*\
Oluşturulan dizeyi başlatacak dize.

*`right_offset`*\
Oluşturulan dizenin karakter değerlerini başlatmak için ilk kullanılan bir dizedeki bir karakterin dizini.

*`char_value`*\
Oluşturulan dizeye kopyalanacak karakter değeri.

*`first`*\
Eklenecek kaynak aralıktaki ilk öğeyi ele almak için bir giriş yineleyicisi, const_pointer veya const_iterator.

*`last`*\
Kaynak aralıktaki son öğenin ötesinde bir giriş yineleyicisi, const_pointer veya const_iterator.

### <a name="return-value"></a>Dönüş Değeri

Oluşturucular tarafından oluşturulan dize nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir depolar [`basic_string::allocator_type`](#allocator_type) ve denetlenen sırayı başlatır. Ayırıcı nesne varsa bağımsız değişkendir `al` . Kopya Oluşturucu için, bu `right.` [`basic_string::get_allocator`](#get_allocator) `()` . Aksi takdirde, ayırıcı olur `Alloc()` .

Denetlenen sıra, kalan işlenenler tarafından belirtilen işlenen dizisinin bir kopyasına başlatılır. İşlenen dizisi olmayan bir Oluşturucu, boş bir ilk denetimli sırayı belirtir. `InputIterator`Bir şablon oluşturucusunda bir tamsayı türü ise, işlenen sırası `first,  last` ile aynı şekilde davranır `(size_type) first, (value_type) last` .

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

## <a name="basic_stringbegin"></a><a name="begin"></a> `basic_string::begin`

Dizedeki ilk öğeyi adresleyen bir yineleyici döndürür.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ilk öğesini veya boş bir dizinin sonunun ötesinde bir rastgele erişim Yineleyici.

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

## <a name="basic_stringc_str"></a><a name="c_str"></a> `basic_string::c_str`

Bir dizenin içeriğini C stili, null ile sonlandırılmış bir dize olarak dönüştürür.

```cpp
const value_type *c_str() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağırma dizesinin C stili sürümüne yönelik bir işaretçi.  `const`Nesnedeki basic_string sınıfında yıkıcı dahil, işlev olmayan bir işlev çağrıldıktan sonra işaretçi değeri geçerli değil.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonuna ait dize türündeki nesnelerin `basic_string<char>` null olarak sonlandırılması gerekli değildir. ' \ 0 ' null karakteri, dizenin sonunu işaretlemek için bir C dizesinde özel bir karakter olarak kullanılır, ancak String türünde bir nesne içinde özel bir anlamı yoktur ve dizenin bir parçası olan herhangi bir karakterle aynı olabilir. Dizeden bir otomatik dönüştürme vardır `const char *` ancak dize sınıfı, C stili dizelerinden tür nesnelerine otomatik dönüşümler sağlamaz `basic_string<char>` .

Döndürülen C stili dize değiştirilmemesi gerekir, çünkü dize, sınırlı bir yaşam süresine sahip olduğundan ve sınıf dizesine ait olduğundan, bu dize işaretçisini geçersiz kılabilir veya silinir.

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

## <a name="basic_stringcapacity"></a><a name="capacity"></a> `basic_string::capacity`

Dizenin bellek ayırmayı arttırmadan bir dizede depolanabilecek en büyük öğe sayısını döndürür.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizeyi tutmak için şu anda bellekte ayrılan depolama alanı boyutu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, en az bir değer olan denetimli sırayı tutmak için ayrılmış depolama alanını döndürür [`size`](#size) .

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

## <a name="basic_stringcbegin"></a><a name="cbegin"></a> `basic_string::cbegin`

`const`Aralıktaki ilk öğeyi ele alan bir yineleyici döndürür.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`const`Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için) işaret eden bir rastgele erişim Yineleyici `cbegin() == cend()` .

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile `cbegin` , aralıktaki öğeler değiştirilemez.

`begin()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun `const` `begin()` `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="basic_stringcend"></a><a name="cend"></a> `basic_string::cend`

`const`Bir aralıktaki son öğenin ötesinde konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

`const`Yalnızca aralığın sonunu işaret eden bir rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

`cend` , bir yineleyicinin aralığın sonunu geçtiğini test etmek için kullanılır.

`end()`Dönüş değerinin olduğunu garantilemek için üye işlevin yerine bu üye işlevi kullanabilirsiniz `const_iterator` . Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, ve ' ı `Container` destekleyen herhangi bir türde değiştirilebilir (olmayan) bir kapsayıcı olarak göz önünde bulundurun `const` `end()` `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Tarafından döndürülen değer `cend` başvurulmamalıdır.

## <a name="basic_stringclear"></a><a name="clear"></a> `basic_string::clear`

Bir dizenin tüm öğelerini siler.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevin çağrıldığı dize boş olur.

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

## <a name="basic_stringcompare"></a><a name="compare"></a> `basic_string::compare`

İki dizenin eşit olup olmadığını veya birinin lexıgrafik değerinden daha küçük olduğunu anlamak için belirtilen dizeyle büyük küçük harfe duyarlı bir karşılaştırma yapar.

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

*`str`*\
İşlenen dizesiyle Karşılaştırılacak dize.

*`position_1`*\
Karşılaştırma işleminin başladığı işlenen dizesinin dizini.

*`number_1`*\
Karşılaştırılacak işlenen dizeden en fazla karakter sayısı.

*`number_2`*\
Karşılaştırılacak parametre dizesinden en fazla karakter sayısı.

*`offset`*\
Karşılaştırma işleminin başladığı parametre dizesinin dizini.

*`count`*\
Karşılaştırılacak parametre dizesinden en fazla karakter sayısı.

*`ptr`*\
İşlenen dizesiyle Karşılaştırılacak C dizesi.

### <a name="return-value"></a>Dönüş Değeri

İşlenen dizesi parametre dizesinden küçükse negatif bir değer; iki dize eşitse sıfır; veya işlenen dizesi parametre dizesinden büyükse pozitif bir değer.

### <a name="remarks"></a>Açıklamalar

`compare`Üye işlevleri, kullanılan öğesine bağlı olarak parametre ve işlenen dizelerinin tümünü veya bir kısmını karşılaştırır.

Karşılaştırma büyük/küçük harfe duyarlıdır.

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

## <a name="basic_stringconst_iterator"></a><a name="const_iterator"></a> `basic_string::const_iterator`

Dizedeki bir öğeye erişebilen ve okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `const` .

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_iterator` , bir karakterin değerini değiştirmek için kullanılamaz ve bir dizenin ileri yönde yinelemek için kullanılır.

### <a name="example"></a>Örnek

[`begin`](#begin)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `const_iterator` .

## <a name="basic_stringconst_pointer"></a><a name="const_pointer"></a> `basic_string::const_pointer`

Dizedeki bir öğeye işaretçi sağlayan bir tür `const` .

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `allocator_type::const_pointer` .

Türü için değerine `string` eşdeğerdir `char*` .

Const olarak belirtilen işaretçiler, bildirildiği zaman başlatılmalıdır. Const işaretçileri her zaman aynı bellek konumuna işaret edebilir ve sabit veya sabit olmayan verilere işaret edebilir.

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

## <a name="basic_stringconst_reference"></a><a name="const_reference"></a> `basic_string::const_reference`

`const`İşlem okumak ve gerçekleştirmek için bir dizede depolanan öğeye başvuru sağlayan bir tür `const` .

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reference` , bir öğenin değerini değiştirmek için kullanılamaz.

Tür için bir eş anlamlı `allocator_type::const_reference` . Tür için `string` const ile eşdeğerdir `char&` .

### <a name="example"></a>Örnek

[`at`](#at)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `const_reference` .

## <a name="basic_stringconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> `basic_string::const_reverse_iterator`

Dizedeki herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `const` .

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `const_reverse_iterator` , bir karakterin değerini değiştiremez ve ters bir dize üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

[`rbegin`](#rbegin)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `const_reverse_iterator` .

## <a name="basic_stringcopy"></a><a name="copy"></a> `basic_string::copy`

Kaynak dizedeki dizinli bir konumdan bir hedef karakter dizisine en çok belirtilen sayıda karakter kopyalar.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir. [`basic_string::_Copy_s`](#copy_s)Bunun yerine kullanmayı düşünün.

```cpp
size_type copy(
    value_type* ptr,
    size_type count,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*`ptr`*\
Öğelerin kopyalanacağı hedef karakter dizisi.

*`count`* Kaynak dizeden en fazla kopyalanacak olan karakter sayısı.

*`offset`*\
Kopya yapılacak Kaynak dizedeki başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanmış karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kopyanın sonuna null bir karakter eklenmez.

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

## <a name="basic_stringcrbegin"></a><a name="crbegin"></a> `basic_string::crbegin`

Ters çevrilen dizedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin sonunun hemen ötesinde işaret eden bir ters Yineleyici. Konum, ters dizenin başlangıcını belirler.

## <a name="basic_stringcrend"></a><a name="crend"></a> `basic_string::crend`

`const`Ters çevrilen dizedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ters `const` çevrilen bir dizedeki son öğeden sonra gelen konumu ele alan bir ters Yineleyici (geri çevrilmeyen dizedeki ilk öğeden önce gelen konum).

### <a name="remarks"></a>Açıklamalar

## <a name="basic_string_copy_s"></a><a name="copy_s"></a> `basic_string::_Copy_s`

Kaynak dizedeki dizinli bir konumdan bir hedef karakter dizisine en çok belirtilen sayıda karakter kopyalar.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*`dest`*\
Öğelerin kopyalanacağı hedef karakter dizisi.

*`dest_size`*\
*Hedef* boyutu.

*`count`* Kaynak dizeden en fazla kopyalanacak olan karakter sayısı.

*`offset`*\
Kopya yapılacak Kaynak dizedeki başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte kopyalanmış karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kopyanın sonuna null bir karakter eklenmez.

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

## <a name="basic_stringdata"></a><a name="data"></a> `basic_string::data`

Bir dizenin içeriğini null sonlandırılmış bir karakter dizisine dönüştürür.

```cpp
const value_type *data() const noexcept;
value_type *data() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin içeriğini içeren, null ile sonlandırılmış dizinin ilk öğesine yönelik bir işaretçi. Boş bir dize için, işaretçi değerine eşit olan tek bir null karakteri işaret eder `value_type()` .

### <a name="remarks"></a>Açıklamalar

`data`Geçerli bir aralıktaki işaret tarafından döndürülen işaretçi `[data(), data() + size()]` . Aralıktaki her öğe, dizedeki geçerli veriye karşılık gelir. Diğer bir deyişle, aralığındaki her geçerli fark için *`n`* `data() + n == addressof(operator[](n))` .

Aşırı yüklemesiyle döndürülen dizenin içeriğini değiştirirseniz `const` `data` , davranış tanımsızdır. Ayrıca, Terminal null karakteri başka bir değerle değiştirilirse tanımsız bir davranış alırsınız. `const`Dizeye yönelik başvuru olmayan bir standart kitaplık işlevine geçirilmezse döndürülen işaretçi geçersiz kılınabilir. Ayrıca üye olmayan bir işleve yapılan bir çağrı tarafından geçersiz kılınabilir `const` . Üye,,,,,, `at` , ve için çağrılar, `back` `begin` `end` `front` `rbegin` `rend` `operator[]` işaretçiyi geçersiz kılmaz.

C++ 11 ' den önce, `data` döndürülen dizenin null sonlandırılmış olduğunu garanti etmedi. C++ 11 ' den beri `data` ve `c_str` her ikisi de null ile sonlandırılmış bir dize döndürve etkin şekilde aynı.

`const`Aşırı yükleme olmayan c++ 17 ' de yenidir. Kullanmak için, **`/std:c++17`** veya **`/std:c++latest`** derleyici seçeneğini belirtin.

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

## <a name="basic_stringdifference_type"></a><a name="difference_type"></a> `basic_string::difference_type`

Aynı dize içindeki öğelere başvuran iki yineleyiciler arasındaki farkı sağlayan bir tür.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

İmzalanan tamsayı türü, denetlenen dizideki herhangi iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar.

Türü için değerine `string` eşdeğerdir `ptrdiff_t` .

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

## <a name="basic_stringempty"></a><a name="empty"></a> `basic_string::empty`

Dizenin karakter içerip içermediğini test eder.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

`true` dize nesnesi hiçbir karakter içermiyorsa; `false` en az bir karakter varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [sıze](#size) = = 0 ile eşdeğerdir.

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

## <a name="basic_stringend"></a><a name="end"></a> `basic_string::end`

Dizedeki son öğeden sonraki konumu ele alan bir yineleyici döndürür.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Dönüş Değeri

Bir dizedeki son öğeden sonra gelen konumu ele alan bir rastgele erişim yineleyicisi döndürür.

### <a name="remarks"></a>Açıklamalar

`end` genellikle bir yineleyicinin kendi dizesinin sonuna ulaşıp ulaşılmadığını test etmek için kullanılır. Tarafından döndürülen değer `end` başvurulmamalıdır.

Dönüş değeri `end` bir öğesine atanırsa `const_iterator` , dize nesnesi değiştirilemez. Dönüş değeri `end` bir öğesine atanırsa `iterator` , dize nesnesi değiştirilebilir.

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

## <a name="basic_stringends_with"></a><a name="ends_with"></a> `basic_string::ends_with`

Dizenin belirtilen soneke göre sonlanıp bitmediğini denetleyin.

```cpp
bool ends_with(const CharType c) const noexcept;
bool ends_with(const CharType* const x) const noexcept;
bool ends_with(const basic_string_view sv) const noexcept;
```

### <a name="parameters"></a>Parametreler

*`c`*\
Aranacak tek karakter soneki.

*`sv`*\
Aranacak son eki içeren bir dize görünümü. \
Bir `std::basic_string` dize görünümüne dönüştüren bir geçişi yapabilirsiniz.

*`x`*\
Aranacak son eki içeren null ile sonlandırılmış karakter dizesi.

### <a name="return-value"></a>Dönüş Değeri

`true` dize belirtilen soneke biterse; `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

`ends_with()` C++ 20 ' de yenidir. Kullanmak için [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneğini belirtin.

[`starts_with`](#starts_with)Bir dizenin belirtilen önekle çalışmaya başlandığına bakmak için bkz..

### <a name="example"></a>Örnek

```cpp
// Requires /std:c++latest
#include <string>
#include <iostream>

int main()
{
    std::basic_string<char> str = "abcdefg";

    std::cout << std::boolalpha; // so booleans show as 'true'/'false'
    std::cout << str.ends_with('g') << '\n';
    std::cout << str.ends_with("eFg") << '\n';

    std::basic_string<char> str2 = "efg";
    std::cout << str.ends_with(str2);

    return 0;
}
```

```Output
true
false
true
```

## <a name="basic_stringerase"></a><a name="erase"></a> `basic_string::erase`

Bir dizedeki bir öğeyi veya öğe aralığını belirtilen konumdan kaldırır.

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

*`first`*\
Silinecek aralıktaki ilk öğenin konumunu adresleyen bir yineleyici.

*`last`*\
Silinen aralıktaki son öğeden geçen konumu ele aldığı bir yineleyici.

*`iter`*\
Silinecek dizedeki öğenin konumunu adresleyen bir yineleyici.

*`offset`*\
Kaldırılacak dizedeki ilk karakterin dizini.

*`count`*\
İle başlayan dize aralığında çok sayıda varsa, kaldırılacak öğe sayısı *`offset`* .

### <a name="return-value"></a>Dönüş Değeri

İlk iki üye işlev için, üye işlevi tarafından kaldırılan son karakterden sonra ilk karakteri ele alarak bir yineleyici. Üçüncü üye işlevi için, öğelerin silinme String nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üçüncü üye işlevi döndürür `*this` .

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

## <a name="basic_stringfind"></a><a name="find"></a> `basic_string::find`

Belirtilen karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için bir dizeyi ileriye doğru yönde arar.

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

*`char_value`*\
Üye işlevin aranacağı karakter değeri.

*`offset`*\
Aramanın başlayacağı konumun dizini.

*`ptr`*\
Üye işlevin aranacağı C dizesi.

*`count`*\
Üye işlevin aranacağı, C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*`str`*\
Üye işlevin aranacağı dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

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
      cout << "The substring 'sample' was not found in str3 ."
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

## <a name="basic_stringfind_first_not_of"></a><a name="find_first_not_of"></a> `basic_string::find_first_not_of`

Belirtilen dizenin bir öğesi olmayan ilk karakter için bir dizeyi arar.

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

*`char_value`*\
Üye işlevin aranacağı karakter değeri.

*`offset`*\
Aramanın başlayacağı konumun dizini.

*`ptr`*\
Üye işlevin aranacağı C dizesi.

*`count`*\
Üye işlevin aranacağı, C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*`str`*\
Üye işlevin aranacağı dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

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

## <a name="basic_stringfind_first_of"></a><a name="find_first_of"></a> `basic_string::find_first_of`

Belirtilen dizenin herhangi bir öğesiyle eşleşen ilk karakter için bir dizeyi arar.

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

*`char_value`*\
Üye işlevin aranacağı karakter değeri.

*`offset`*\
Aramanın başlayacağı konumun dizini.

*`ptr`*\
Üye işlevin aranacağı C dizesi.

*`count`*\
Üye işlevin aranacağı, C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*`str`*\
Üye işlevin aranacağı dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

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

## <a name="basic_stringfind_last_not_of"></a><a name="find_last_not_of"></a> `basic_string::find_last_not_of`

Belirli bir dizenin herhangi bir öğesi olmayan son karakter için bir dizeyi arar.

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

*`char_value`*\
Üye işlevin aranacağı karakter değeri.

*`offset`*\
Aramanın tamamlanalınacağı konumun dizini.

*`ptr`*\
Üye işlevin aranacağı C dizesi.

*`count`*\
Üye işlevin aranacağı, C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*`str`*\
Üye işlevin aranacağı dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

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

## <a name="basic_stringfind_last_of"></a><a name="find_last_of"></a> `basic_string::find_last_of`

Belirtilen dizenin herhangi bir öğesiyle eşleşen son karakter için bir dizeyi arar.

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

*`char_value`*\
Üye işlevin aranacağı karakter değeri.

*`offset`*\
Aramanın tamamlanalınacağı konumun dizini.

*`ptr`*\
Üye işlevin aranacağı C dizesi.

*`count`*\
Üye işlevin aranacağı, C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*`str`*\
Üye işlevin aranacağı dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin son karakterinin dizini; Aksi takdirde `npos` .

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

## <a name="basic_stringfront"></a><a name="front"></a> `basic_string::front`

Dizedeki ilk öğeye bir başvuru döndürür.

```cpp
const_reference front() const;

reference front();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin, boş olmamalı olması gereken ilk öğesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

## <a name="basic_stringget_allocator"></a><a name="get_allocator"></a> `basic_string::get_allocator`

Dizeyi oluşturmak için kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize tarafından kullanılan ayırıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan ayırıcı nesnesini döndürür.

String sınıfı için ayrıcılar, sınıfın depolamayı nasıl yönettiğini belirtir. Kapsayıcı sınıflarıyla sağlanan varsayılan ayrıcılar çoğu programlama ihtiyacı için yeterlidir. Kendi ayırıcı sınıfınızı yazmak ve kullanmak, gelişmiş bir C++ konudur.

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

## <a name="basic_stringinsert"></a><a name="insert"></a> `basic_string::insert`

Belirli bir konumdaki dizeye bir öğe veya dizi öğe veya öğe aralığı ekler.

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

*`position`*\
Yeni karakterleri ekleme noktasının arkasındaki konumun dizini.

*`ptr`*\
Ya da kısmen dizeye eklenecek olan C dizesi.

*`count`*\
Eklenecek karakter sayısı.

*`str`*\
Hedef dizeye tamamen veya kısmen eklenecek dize.

*`offset`*\
Eklenecek karakterleri sağlayan kaynak dize bölümünün dizini.

*`char_value`*\
Eklenecek öğelerin karakter değeri.

*`iter`*\
Arkasında bir karakter eklenecek konumu ele veren bir yineleyici.

*`first`*\
Bir giriş yineleyicisi, `const_pointer` veya `const_iterator` Eklenecek kaynak aralıktaki ilk öğeyi adresleyen.

*`last`*\
Bir giriş yineleyicisi, `const_pointer` veya `const_iterator` Eklenecek kaynak aralıktaki son öğeden sonraki konumunu adresleyen.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi tarafından yeni karakterler atanmakta olan dize nesnesine veya bağımsız karakter eklemeleri durumunda, belirli üye işlevine bağlı olarak, eklenen karakterin konumunu veya hiçbirini ele alan bir yineleyici.

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

## <a name="basic_stringiterator"></a><a name="iterator"></a> `basic_string::iterator`

Dizedeki bir öğeye erişebilen ve okuyabilen bir rastgele erişim yineleyici sağlayan bir tür `const` .

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `iterator` , bir karakterin değerini değiştirmek için kullanılabilir ve bir dizenin ileri yönde yinelemek için kullanılır.

### <a name="example"></a>Örnek

[`begin`](#begin)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `iterator` .

## <a name="basic_stringlength"></a><a name="length"></a> `basic_string::length`

Dizedeki geçerli öğe sayısını döndürür.

```cpp
size_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ile aynıdır [`size`](#size) .

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

## <a name="basic_stringmax_size"></a><a name="max_size"></a> `basic_string::max_size`

Bir dizenin içerebileceği en fazla karakter sayısını döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir dizenin içerebileceği en fazla karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bir işlem en büyük boyuttan büyük bir dize ürettiğinden [Length_error Class](../standard-library/length-error-class.md) türünde bir özel durum oluşturulur.

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

## <a name="basic_stringnpos"></a><a name="npos"></a> `basic_string::npos`

Bir arama işlevi başarısız olduğunda "bulunamadı" veya "tüm kalan karakterler" i gösteren-1 ' e başlatılan işaretsiz bir tamsayı değeri.

```cpp
static const size_type npos = -1;
```

### <a name="remarks"></a>Açıklamalar

Dönüş değeri değer için denetlendiğinde `npos` , dönüş değeri veya ya da değil, bu durum çalışmayabilir [`size_type`](#size_type) `int` `unsigned` .

### <a name="example"></a>Örnek

[`find`](#find)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `npos` .

## <a name="basic_stringoperator"></a><a name="op_add_eq"></a> `basic_string::operator+=`

Bir dizeye karakter ekler.

```cpp
basic_string<CharType, Traits, Allocator>& operator+=(
    value_type char_value);

basic_string<CharType, Traits, Allocator>& operator+=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator+=(
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*`char_value`*\
Eklenecek karakter.

*`ptr`*\
Eklenecek C dizesinin karakterleri.

*`right`*\
Eklenecek dizenin karakterleri.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi tarafından geçirilen karakterlerle eklenen String nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Veya üye işlevleri kullanılarak bir dizeye karakterler eklenebilir `operator+=` [`append`](#append) [`push_back`](#push_back) . `operator+=`Birden çok bağımsız değişken Append üye işlevi sırasında tek bağımsız değişken değerlerini ekler bir dizenin belirli bir bölümünün ekleme için belirtilmesini sağlar.

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

## <a name="basic_stringoperator"></a><a name="op_eq"></a> `basic_string::operator=`

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

*`char_value`*\
Atanacak karakter değeri.

*`ptr`*\
Hedef dizeye atanacak C dizesinin karakterlerine yönelik bir işaretçi.

*`right`*\
Hedef dizeye karakterler atanacak kaynak dize.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi tarafından yeni karakterler atanmakta olan String nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dizelere yeni karakter değerleri atanmış olabilir. Yeni değer bir dize ve C dizesi ya da tek bir karakter olabilir. `operator=`Yeni değer tek bir parametre tarafından açıklanabileceği durumlarda kullanılabilir, aksi takdirde [`assign`](#assign) birden fazla parametreye sahip üye işlevi, dizenin hangi kısmının hedef dizeye atandığını belirtmek için kullanılabilir.

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

## <a name="basic_stringoperator"></a><a name="op_at"></a> `basic_string::operator[]`

Bir dizedeki belirtilen dizine sahip karaktere bir başvuru sağlar.

```cpp
const_reference operator[](size_type offset) const;
reference operator[](size_type offset);
```

### <a name="parameters"></a>Parametreler

*`offset`*\
Başvurulacak öğenin konumunun dizini.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen konumdaki dizenin karakteriyle bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk öğesi sıfır dizinine sahiptir ve aşağıdaki öğeler pozitif tamsayılar tarafından ardışık olarak dizinlenir, böylece *n* uzunluklu bir dize, *n-1* sayısı tarafından dizine alınmış bir *n*. öğesi vardır.

`operator[]` , [`at`](#at) bir dizenin öğelerine okuma ve yazma erişimi sağlamak için üye işlevinden daha hızlıdır.

`operator[]` parametre olarak geçirilen dizinin geçerli olup olmadığını denetlemez, ancak üye işlevi çalışır `at` ve bu nedenle de geçerlilik kesin olarak kullanılmalıdır. Üye işlevine geçirilen geçersiz bir dizin (dizenin boyutundan sıfır veya daha büyük ya da buna eşit bir dizin) `at` [out_of_range sınıfı](../standard-library/out-of-range-class.md) özel durumu oluşturur. Tanımsız davranışa neden olan geçersiz bir dizin geçirildi `operator[]` , ancak dizenin uzunluğuna eşit dizin const dizeler için geçerli bir dizindir ve işleç bu dizin geçirildiğinde null karakteri döndürüyor.

Döndürülen başvuru dize reallocations veya dizeler için değişiklikler tarafından geçersiz kılınabilir `const` .

[ \_ Yineleyici \_ hata ayıklama \_ düzeyi](../standard-library/iterator-debug-level.md) 1 veya 2 olarak ayarlandığında derleme yaparken, dizenin sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur. Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="basic_stringpointer"></a><a name="pointer"></a> `basic_string::pointer`

Bir dize veya karakter dizisinde bir karakter öğesi işaretçisi sağlayan bir tür.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `allocator_type::pointer` .

Türü için değerine `string` eşdeğerdir `char *` .

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

## <a name="basic_stringpop_back"></a><a name="pop_back"></a> `basic_string::pop_back`

Dizenin son öğesini siler.

```cpp
void pop_back();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi `erase(size() - 1)` , dizinin boş olması gereken son öğeyi silmek için etkin bir şekilde çağırır.

## <a name="basic_stringpush_back"></a><a name="push_back"></a> `basic_string::push_back`

Dizenin sonuna bir öğesi ekler.

```cpp
void push_back(value_type char_value);
```

### <a name="parameters"></a>Parametreler

*`char_value`*\
Dizenin sonuna eklenecek karakter.

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin bir şekilde çağırır [`insert`](#insert) ( [`end`](#end) , *char_value* ).

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

## <a name="basic_stringrbegin"></a><a name="rbegin"></a> `basic_string::rbegin`

Ters çevrilen dizedeki ilk öğeye bir yineleyici döndürür.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen dizedeki ilk öğeye bir rastgele erişim yineleyicisi döndürür, buna karşılık gelen geri alınamaz dizedeki son öğe ne olacağını adresler.

### <a name="remarks"></a>Açıklamalar

`rbegin` bir dize ile kullanıldığı gibi ters bir dize ile birlikte kullanılır [`begin`](#begin) .

Dönüş değeri `rbegin` bir öğesine atanırsa `const_reverse_iterator` , dize nesnesi değiştirilemez. Dönüş değeri `rbegin` öğesine atanırsa `reverse_iterator` , dize nesnesi değiştirilebilir.

`rbegin` bir yinelemeyi geri doğru dize aracılığıyla başlatmak için kullanılabilir.

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

## <a name="basic_stringreference"></a><a name="reference"></a> `basic_string::reference`

Bir dizede depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="remarks"></a>Açıklamalar

Bir türü `reference` , bir öğenin değerini değiştirmek için kullanılabilir.

Tür için bir eş anlamlı `allocator_type::reference` .

Türü için değerine `string` eşdeğerdir `chr&` .

### <a name="example"></a>Örnek

[`at`](#at)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `reference` .

## <a name="basic_stringrend"></a><a name="rend"></a> `basic_string::rend`

Ters çevrilen dizedeki son öğeden sonra gelen konumu ele alan bir yineleyici döndürür.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir dizedeki son öğeden sonraki konumu ele alan ters bir rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend` bir dize ile kullanıldığı gibi ters bir dize ile birlikte kullanılır [`end`](#end) .

Dönüş değeri `rend` bir öğesine atanırsa `const_reverse_iterator` , dize nesnesi değiştirilemez. Dönüş değeri `rend` öğesine atanırsa `reverse_iterator` , dize nesnesi değiştirilebilir.

`rend` , bir ters yineleyicinin kendi dizesinin sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

Tarafından döndürülen değer `rend` başvurulmamalıdır.

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

## <a name="basic_stringreplace"></a><a name="replace"></a> `basic_string::replace`

Belirli bir konumdaki bir dizedeki öğeleri, belirtilen karakterlerle veya diğer aralıklardan ya da dizelerle veya C dizelerinden kopyalanmış karakterlerle değiştirir.

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

*`str`*\
İşlenen dizesinin karakter kaynağı olacak dize.

*`position_1`*\
Değiştirme işleminin başladığı işlenen dizesinin dizini.

*`number_1`*\
İşlenen dizesinde değiştirilmekte olan en fazla karakter sayısı.

*`position_2`*\
Kopyalamanın başladığı parametre dizesinin dizini.

*`number_2`*\
C-String parametresinden kullanılacak en fazla karakter sayısı.

*`ptr`*\
İşlenen dize için bir karakter kaynağı olacak C-dize.

*`char_value`*\
İşlenen dizesine kopyalanacak karakter.

*`first0`*\
İşlenen dizesinde kaldırılacak ilk karakteri adresleyen bir yineleyici.

*`last0`*\
İşlenen dizesinde kaldırılacak son karakteri adresleyen bir yineleyici.

*`first`*\
Bir yineleyici, const_pointer veya const_iterator parametre dizesinde kopyalanacak ilk karakteri adresleyen.

*`last`*\
Parametre dizesinde kopyalanacak bir yineleyici, const_pointer veya const_iterator son karakteri adresleyen.

*`count`*\
*Char_value* işlenen dizesine kopyalandığı zaman sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yerine geçen işlenen dize.

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

## <a name="basic_stringreserve"></a><a name="reserve"></a> `basic_string::reserve`

Dizenin kapasitesini, belirtilen sayı kadar en az bir sayı olarak ayarlar.

```cpp
void reserve(size_type count = 0);
```

### <a name="parameters"></a>Parametreler

*`count`*\
Belleğin ayrıldığı karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Yeterli kapasiteye sahip olma, reallocations zaman alan bir işlemdir ve bir dizedeki karakterlere başvuran tüm başvuruları, işaretçileri ve yineleyiciler geçersiz kılar.

Dize türü nesneler için kapasite kavramı, türündeki nesneler için aynıdır `vector` . Öğesinden farklı olarak `vector` , `reserve` bir nesnenin kapasitesini daraltmak için üye işlevi çağrılabilir. İstek bağlamadışı ve gerçekleşmeyebilir. Parametresinin varsayılan değeri sıfır olduğunda, bir çağrısı, `reserve` dizenin kapasitesini dizedeki şu an karakter sayısına uyacak şekilde daraltmak için bağlama olmayan bir istek olur. Kapasite geçerli karakter sayısının altında hiçbir şekilde azaltılmıştır.

Çağırma, `reserve` bir dizenin kapasitesini daraltmak için mümkün olan tek yoldur. Ancak, yukarıda belirtildiği gibi bu istek bağlamadır ve gerçekleşmeyebilir.

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

## <a name="basic_stringresize"></a><a name="resize"></a> `basic_string::resize`

Bir dize için yeni bir boyut belirtir, gerektiğinde öğeleri ekleme veya silme.

```cpp
void resize(
    size_type count,);

void resize(
    size_type count,
    value_type char_value);
```

### <a name="parameters"></a>Parametreler

*`count`*\
Dizenin yeni boyutu.

*`char_value`*\
Ek öğeler gerekliyse, eklenen karakterlerin değeri ile başlatılır.

### <a name="remarks"></a>Açıklamalar

Elde edilen boyut en fazla karakter sayısını aşarsa, form oluşturur `length_error` .

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

## <a name="basic_stringreverse_iterator"></a><a name="reverse_iterator"></a> `basic_string::reverse_iterator`

Bir dizede depolanan bir öğeye başvuru sağlayan bir tür.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Açıklamalar

Bir tür `reverse_iterator` , bir karakterin değerini değiştirmek için kullanılabilir ve ters bir dize üzerinden yinelemek için kullanılır.

### <a name="example"></a>Örnek

[`rbegin`](#rbegin)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `reverse_iterator` .

## <a name="basic_stringrfind"></a><a name="rfind"></a> `basic_string::rfind`

Belirtilen karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için bir dizeyi geriye doğru yönde arar.

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

*`char_value`*\
Üye işlevin aranacağı karakter değeri.

*`offset`*\
Aramanın başlayacağı konumun dizini.

*`ptr`*\
Üye işlevin aranacağı C dizesi.

*`count`*\
Üye işlevin aranacağı, C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*`str`*\
Üye işlevin aranacağı dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda alt dizenin ilk karakterinin geri arandığı son oluşumun dizini; Aksi takdirde `npos` .

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

## <a name="basic_stringshrink_to_fit"></a><a name="shrink_to_fit"></a> `basic_string::shrink_to_fit`

Dizenin fazla kapasitesini atar.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, kapsayıcıda gereksiz depolamayı ortadan kaldırır.

## <a name="basic_stringsize"></a><a name="size"></a> `basic_string::size`

Dizedeki geçerli öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin uzunluğu.

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

## <a name="basic_stringsize_type"></a><a name="size_type"></a> `basic_string::size_type`

Bir dizedeki öğe ve dizin sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

eşdeğerdir `allocator_type::size_type` .

Türü için değerine `string` eşdeğerdir `size_t` .

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

## <a name="basic_stringstarts_with"></a><a name="starts_with"></a> `basic_string::starts_with`

Dizenin belirtilen önekle başlatılıp başlatılmayacağını denetleyin.

```cpp
bool starts_with(const CharType c) const noexcept;
bool starts_with(const CharType* const x) const noexcept;
bool starts_with(const basic_string_view sv) const noexcept;
```

### <a name="parameters"></a>Parametreler

*`c`*\
Aranacak tek karakter öneki.

*`sv`*\
Aranacak ön eki içeren bir dize görünümü. \
Bir `std::basic_string` dize görünümüne dönüştüren bir geçişi yapabilirsiniz.

*`x`*\
Aranacak ön eki içeren null ile sonlandırılmış karakter dizesi.

### <a name="return-value"></a>Dönüş Değeri

`true` dize belirtilen önekle başlıyorsa; `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

`starts_with()` C++ 20 ' de yenidir. Kullanmak için [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneğini belirtin.

[`ends_with`](#ends_with)Bir dizenin belirtilen soneke göre sona ermediğini görmek için bkz..

### <a name="example"></a>Örnek

```cpp
// Requires /std:c++latest
#include <string>
#include <iostream>

int main()
{
    std::basic_string<char> str = "abcdefg";

    std::cout << std::boolalpha; // so booleans show as 'true'/'false'
    std::cout << str.starts_with('b') << '\n';
    std::cout << str.starts_with("aBc") << '\n';

    std::basic_string<char> str2 = "abc";
    std::cout << str.starts_with(str2);

    return 0;
}
```

```Output
false
false
true
```

## <a name="basic_stringsubstr"></a><a name="substr"></a> `basic_string::substr`

Belirli bir konumdan başlayarak bir dizeden en fazla sayıda karakter alt dizesini kopyalar.

```cpp
basic_string<CharType, Traits, Allocator> substr(
    size_type offset = 0,
    size_type count = npos) const;
```

### <a name="parameters"></a>Parametreler

*`offset`*\
Varsayılan değeri 0 olan, dizenin kopyasının oluşturulduğu konumdaki öğeyi bulmak için bir dizin.

*`count`*\
Varsa, kopyalanacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk bağımsız değişken tarafından belirtilen konumda başlayan dize işleneni öğelerinin bir kopyası olan bir alt dize nesnesi.

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

## <a name="basic_stringswap"></a><a name="swap"></a> `basic_string::swap`

İki dizenin içeriğini değiş tokuş edin.

```cpp
void swap(
    basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*`str`*\
Öğeleri hedef dizede olanlarla değiştirilecek kaynak dize.

### <a name="remarks"></a>Açıklamalar

Takas edilmekte olan dizelerin aynı ayırıcı nesnesi varsa, `swap` üye işlevi:

- Sabit zamanlı olarak gerçekleşir.
- Özel durum oluşturmaz.
- İki dizelerdeki öğeleri belirten başvuruları, işaretçileri veya yineleyiciler geçersiz kılar.

Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı iki denetimli sıranın içindeki öğe sayısıyla orantılı olur.

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

## <a name="basic_stringtraits_type"></a><a name="traits_type"></a> `basic_string::traits_type`

Bir dizede depolanan öğelerin karakter nitelikleri için bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, ikinci şablon parametresinin bir eş anlamlısıdır `Traits` .

Türü için değerine `string` eşdeğerdir `char_traits<char>` .

### <a name="example"></a>Örnek

[`copy`](../standard-library/char-traits-struct.md#copy)Bildirme ve kullanma hakkında bir örnek için örneğe bakın `traits_type` .

## <a name="basic_stringvalue_type"></a><a name="value_type"></a> `basic_string::value_type`

Bir dizede depolanan karakterlerin türünü temsil eden bir tür.

```cpp
typedef typename allocator_type::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

`traits_type::char_type`, Ve `char` türündeki nesneler için eşdeğerdir `string` .

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

[`<string>`](../standard-library/string.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
