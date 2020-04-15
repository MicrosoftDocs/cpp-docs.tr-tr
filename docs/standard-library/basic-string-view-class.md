---
title: basic_string_view Sınıfı
ms.date: 04/20/2019
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: ac65dca931f821c717e9c081c8d3479fd0b3bb0e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364900"
---
# <a name="basic_string_view-class"></a>basic_string_view Sınıfı

C++17'de sınıf şablonu, `basic_string_view<charT>` bir işlevin bu türlerüzerinde baştan çıkarıcı olması gerekmeden çeşitli ilgisiz dize türlerini kabul etmesi için güvenli ve verimli bir yol olarak eklenmiştir. Sınıf, bitişik karakter veri dizisine sahip olmayan bir işaretçi ve dizideki karakter sayısını belirten bir uzunluk tutar. Dizinin geçersiz olarak sonlandırılıp sonlandırılmadığı konusunda herhangi bir varsayımda bulunulmadı.

Standart kitaplık, öğelerin türüne göre çeşitli uzmanlıklar tanımlar:

- `string_view`
- `wstring_view`
- `u16string_view`
- `u32string_view`

Bu belgede, "string_view" terimi genellikle bu tür lerden herhangi birini ifade eder.

Bir string_view dize verilerini okumak için gereken en az ortak arabirimi açıklar. Temel verilere const erişim sağlar; kopya `copy` (fonksiyon hariç) yapar. Veriler herhangi bir konumda null değerleri ('\0') içerebilir veya içermeyebilir. Bir string_view nesnenin ömrü üzerinde hiçbir kontrolü yoktur. Temel dize verilerinin geçerli olduğundan emin olmak arayanın sorumluluğundadır.

Bir tür parametresini kabul eden bir işlev string_view, işlevi şablona dönüştürmeden veya işlevi dize türlerinin belirli bir alt kümesiyle zorlamadan, herhangi bir dize benzeri türle çalışmak için yapılabilir. Tek gereksinim, dize türünden string_view örtük bir dönüştürme nin bulunmasıdır. Tüm standart dize türleri örtülü olarak aynı öğe türünü içeren bir string_view dönüştürülebilir. Başka bir deyişle, a `std::string` dönüştürülebilir ama bir `string_view` `wstring_view`.

Aşağıdaki örnek, bir tür `f` `wstring_view`parametresi alan şablon olmayan bir işlevi gösterir. Bu tür `std::wstring`argümanlar ile çağrılabilir , `wchar_t*`ve `winrt::hstring`.

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
string_view depolanan karakterlerin türü. C++ Standart Kitaplığı, bu şablonun uzmanlıkları için aşağıdaki typedefs'i sağlar.

- [tür](../standard-library/string-view-typedefs.md#string_view) **char** elemanları için string_view
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), **wchar_t** için
- **char16_t** için [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)
- **char32_t**için [u32string_view.](../standard-library/string-view-typedefs.md#u32string_view)

*Özellik*\
Varsayılan olarak*CharType*> [char_traits.](char-traits-struct.md)<

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_string_view](#basic_string_view)|Boş bir string_view veya başka bir şekilde başka bir dize nesnesinin verilerinin tamamını veya bir kısmını veya C stili karakter dizisini işaret eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|**const_iterator**|**Const** öğeleri okuyabilen rasgele erişim yinelemesi.|
|**Const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**Const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**Yineleyici**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**pointer**|`using pointer = value_type*;`|
|**Başvuru**|`using reference = value_type&;`|
|**Reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Üye operatörler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Başka bir string_view string_view veya dönüştürülebilir dize nesnesi atar.|
|[Işleç\[\]](#op_at)|Belirtilen dizindeki öğeyi döndürür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[at](#at)|Öğeye belirli bir konumda bir const_reference verir.|
|[Geri](#back)|Son öğeye bir const_reference döndürür.|
|[Başlamak](#begin)|İlk öğeyi ele alan bir const yineleyici döndürür. (string_views değişmezdir.)|
|[cbegin](#cbegin)|[Başlar](#begin)gibi.|
|[cend](#cend)|Son öğeyi geçen bir öğeyi işaret eden bir const yineleyici döndürür.|
|[Kopya](#copy)|Kaynaktaki dizinlenmiş konumdan hedef karakter dizisine string_view en fazla belirli sayıda karakter kopyalar. (Tavsiye edilmez. Bunun yerine _Copy_s kullanın.)|
|[_Copy_s](#_copy_s)|Güvenli CRT kopyalama işlevi.|
|[Karşılaştırmak](#compare)|Bir string_view eşit mi yoksa lexicographically diğerinden daha az mı olduğunu belirlemek için belirli bir string_view ile karşılaştırır.|
|[crbegin](#crbegin)|[Rbegin](#rbegin)ile aynı .|
|[crend](#crend)|[Rend](#rend)ile aynı.|
|[Veri](#data)|Karakter dizisine ham olmayan bir işaretçi verir.|
|[empty](#empty)|string_view karakter isleyip içermediğini sına.|
|[Son -unda](#end)|[Cend](#cend)ile aynı.|
|[find](#find)|Belirli bir karakter dizisiyle eşleşen bir alt dizinin ilk oluşumunu ileri yönde arar.|
|[find_first_not_of](#find_first_not_of)|Belirli bir string_view veya dönüştürülebilir dize nesnesinin herhangi bir öğesi olmayan ilk karakteri arar.|
|[find_first_of](#find_first_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesinin herhangi bir öğesiyle eşleşen ilk karakteri arar.|
|[find_last_not_of](#find_last_not_of)|Belirli bir string_view veya dönüştürülebilir dize nesnesinin herhangi bir öğesi olmayan son karakteri arar.|
|[find_last_of](#find_last_of)|Belirtilen bir string_view veya dönüştürülebilir dize nesnesinin öğesi olan son karakteri arar.|
|[Ön](#front)|İlk öğeye bir const_reference döndürür.|
|[Uzun -luğu](#length)|Geçerli öğe sayısını verir.|
|[max_size](#max_size)|Bir string_view içerebileceği maksimum karakter sayısını döndürür.|
|[rbegin](#rbegin)|Ters string_view ilk öğeyi ele alan bir const yineleyici döndürür.|
|[remove_prefix](#remove_prefix)|İşaretçiyi belirtilen öğe sayısına göre ileri taşır.|
|[remove_suffix](#remove_suffix)|Görünümün boyutunu arkadan başlayarak belirtilen öğe sayısına göre küçültür.|
|[Rend](#rend)|Ters string_view son öğeyi geçmiş bir öğeye işaret eden bir const yineleyici döndürür.|
|[rfind](#rfind)|Belirli bir karakter dizisiyle eşleşen bir alt dizinin ilk oluşumunu ters ten string_view arar.|
|[Boyutu](#size)|Geçerli öğe sayısını verir.|
|[Substr](#substr)|Belirtilen dizinden başlayarak belirtilen uzunlukta bir alt dize döndürür.|
|[Takas](#swap)|İki string_views içeriğini değiştirin.|

## <a name="remarks"></a>Açıklamalar

Bir [işlevden max_size](#max_size) öğelerden daha uzun bir dizi oluşturması istenirse, işlev [length_error](../standard-library/length-error-class.md)türünden bir nesne atarak bir uzunluk hatası bildirir.

## <a name="requirements"></a>Gereksinimler

[std:c++17](../build/reference/std-specify-language-standard-version.md) veya sonrası

**Üstbilgi:** \<string_view>

**Ad alanı:** std

## <a name="basic_string_viewat"></a><a name="at"></a>basic_string_view::at

Belirtilen 0 tabanlı dizindeki karaktere bir const_reference verir.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*Uzaklık*\
Başvurulacak öğenin dizin.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen pozisyondakaraktere const_reference.

### <a name="remarks"></a>Açıklamalar

İlk öğe sıfır dizini vardır ve aşağıdaki öğeler pozitif tamsayılar tarafından art arda dizine alınır, böylece *n* - *1* sayısına göre indekslenmiş *n*th öğesi string_view vardır. **at,** [işleçten\[](#op_at)farklı olarak geçersiz endeksler için bir istisna atar.

Genel olarak, string_view gibi `std::vector` diziler için asla kullanılmaması nı öneririz. **at** Bir diziye geçirilen geçersiz dizin, geliştirme sırasında keşfedilmesi ve düzeltilmesi gereken bir mantık hatasıdır. Bir program endekslerinin geçerli olduğundan kesinlikle emin değilse, onları test etmeli, aramamalı() ve dikkatsiz programlamaya karşı savunmak için özel durumlara güvenmemelidir.

Bkz. [basic_string_view::daha\[ ](#op_at) fazla bilgi için operatör.

### <a name="example"></a>Örnek

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="basic_string_viewback"></a><a name="back"></a>basic_string_view::geri

Son öğeye bir const_reference döndürür.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

string_view son elementine bir const_reference.

### <a name="remarks"></a>Açıklamalar

string_view boşsa bir özel durum atar.

Bir string_view değiştirildikten sonra, örneğin , `remove_suffix`bu işlev tarafından döndürülen öğenin artık temel verilerdeki son öğe olmadığını unutmayın.

### <a name="example"></a>Örnek

C dizesi ile oluşturulmuş bir string_view, sonlandırıcı null'u içermez ve `back` bu nedenle aşağıdaki örnekte '\0' değil 'p' döndürür.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p
```

Katıştılmış nulls başka bir karakter olarak kabul edilir:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_viewbasic_string_view"></a><a name="basic_string_view"></a>basic_string_view:basic_string_view

Bir string_view.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Parametreler

*Str*\
Karakter değerlerinin işaretçisi.

*Len*\
Görünüme dahil edilebilen karakter sayısı.

## <a name="remarks"></a>Açıklamalar

CharT* parametresi olan yapıcılar girişin null-sonlandırıldığını varsayar, ancak sonlandırıcı null string_view dahil edilmez.

Ayrıca bir edebi ile bir string_view oluşturabilirsiniz. Bkz. [operatör""sv](string-view-operators.md#op_sv).

## <a name="basic_string_viewbegin"></a><a name="begin"></a>basic_string_view::başla

[Cbegin](#cbegin)ile aynı .

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğeyi ele alan bir const_iterator döndürür.

## <a name="basic_string_viewcbegin"></a><a name="cbegin"></a>basic_string_view::cbegin

Aralıktaki ilk öğeyi ele alan bir const_iterator döndürür.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın ilk öğesini veya boş aralığın sonundaki konumu işaret eden **bir const** rasgele erişim yineleyicisi `cbegin() == cend()`(boş bir aralık için).

## <a name="basic_string_viewcend"></a><a name="cend"></a>basic_string_view::cend

Bir dizideki son öğenin hemen ötesinde ki konumu adresleyen bir const_iterator döndürür.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Aralığın sonuna işaret eden **bir const** rasgele erişim yineleyici.

### <a name="remarks"></a>Açıklamalar

Döndürülen `cend` değer dereferenced olmamalıdır.

## <a name="basic_string_viewcompare"></a><a name="compare"></a>basic_string_view::karşılaştır

İki nesnenin eşit mi yoksa biri diğerinden daha az mı olduğunu belirlemek için, belirli bir string_view (veya dönüştürülebilir dize türüyle) karşılaştırıldığında büyük/küçük harf duyarlı bir karşılaştırma gerçekleştirir. [ \<string_view> işleçleri](string-view-operators.md) karşılaştırmalar gerçekleştirmek için bu üye işlevi kullanır.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Parametreler

*strv*\
Bu string_view kıyaslanması gereken string_view.

*Pos*\
Karşılaştırmanın başladığı bu string_view dizin.

*Num*\
Bu string_view en fazla karakter sayısı karşılaştırılacak.

*num2*\
*Strv'den* karşılanacak maksimum karakter sayısı.

*Uzaklık*\
Karşılaştırmanın başladığı *strv* dizini.

*Ptr*\
C dizesi bu string_view karşılaştırılabilir.

### <a name="return-value"></a>Dönüş Değeri

Bu string_view *strv* veya *ptr'den*küçükse negatif değer; iki karakter dizisi eşitse sıfır; veya bu string_view *strv* veya *ptr'den*büyükse pozitif bir değer.

### <a name="remarks"></a>Açıklamalar

Üye `compare` işlevler, her karakter dizisinin tamamının veya bir kısmının büyük/küçük harf duyarlı bir karşılaştırmasını gerçekleştirir.

### <a name="example"></a>Örnek

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are"
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are"
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a)
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="basic_string_viewcopy"></a><a name="copy"></a>basic_string_view::kopyala

Kaynaktaki dizinlenmiş konumdan hedef karakter dizisine string_view en fazla belirli sayıda karakter kopyalar. Bunun yerine [basic_string_view::_Copy_s](#_copy_s) güvenli işlevi kullanmanızı öneririz.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Öğelerin kopyalanabilmek için hedef karakter dizisi.

*Sayısı*\
En fazla kaynaktan kopyalanacak karakter sayısı string_view.

*Uzaklık*\
Kaynaktaki başlangıç pozisyonu, kopyaların yapılacağı string_view.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Null karakteri kopyanın sonuna eklenmiyor.

## <a name="basic_string_view_copy_s"></a><a name="_copy_s"></a>basic_string_view::_Copy_s

[Kopya](#copy)yerine kullanılacak güvenli CRT kopyalama işlevi.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parametreler

*Dest*\
Öğelerin kopyalanabilmek için hedef karakter dizisi.

*dest_size*\
*Dest*boyutu .

_ *Sayılacak* karakter sayısı, en fazla kaynak dizesinden kopyalanacak.

*_off*\
Kopyaların yapılacağı kaynak dizedeki başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Null karakteri kopyanın sonuna eklenmiyor.

Daha fazla bilgi için [c-runtime-library/security-features-in-the-crt 'ye](../c-runtime-library/security-features-in-the-crt.md)bakın.

## <a name="basic_string_viewcrbegin"></a><a name="crbegin"></a>basic_string_view::crbegin

Ters string_view ilk öğeyi ele alan bir const_reverse_iterator döndürür.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters string_view ilk öğeyi ele alan bir const_reverse_iterator.

## <a name="basic_string_viewcrend"></a><a name="crend"></a>basic_string_view::crend

[Rend](#rend)ile aynı.

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters string_view sonunu geçen bir const_reverse_iterator döndürür.

## <a name="basic_string_viewdata"></a><a name="data"></a>basic_string_view::data

string_view oluşturmak için kullanılan nesnenin const karakter dizisine ham olmayan bir sahip olmayan işaretçi döndürür.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Karakter dizisinin ilk öğesiiçin bir işaretçi-const.

### <a name="remarks"></a>Açıklamalar

İşaretçi karakterleri değiştiremez.

string_view karakter dizisi mutlaka null-sona erdirilmiş değildir. Null karakter `data` eklenmediği için dönüş türü geçerli bir C dizesi değildir. '\0' null karakteri, string_view türündeki bir nesnede özel bir anlamı yoktur ve diğer karakterler gibi string_view nesnenin bir parçası olabilir.

## <a name="basic_string_viewempty"></a><a name="empty"></a>basic_string_view::boş

string_view karakter isledip içermediğini sınar.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

string_view nesnesi karakter içermisse **doğrudur;** en az bir karakteri varsa **yanlış.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [boyuta](#size)eşdeğerdir () == 0.

## <a name="basic_string_viewend"></a><a name="end"></a>basic_string_view::sonu

Son öğeyi bir öncekiöğe gösteren rasgele erişim const_iterator döndürür.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Son öğeyi bir öncekiöğe gösteren rasgele erişim const_iterator döndürür.

### <a name="remarks"></a>Açıklamalar

`end`bir const_iterator string_view sonuna ulaşıp ulaşmadığını test etmek için kullanılır. Döndürülen `end` değer dereferenced olmamalıdır.

## <a name="basic_string_viewfind"></a><a name="find"></a>basic_string_view::bul

Bir string_view, belirli bir karakter(ler) dizisiyle eşleşen bir karakterin veya alt dizinin ilk oluşumu için ileri yönde arar.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*Str*\
Üye işlevin arama string_view.

*chVal*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı dizin.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
*Ptr'deki*karakter sayısı, ilk karakterden ileri sayma.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

## <a name="basic_string_viewfind_first_not_of"></a><a name="find_first_not_of"></a>basic_string_view::find_first_not_of

Belirtilen bir string_view veya dönüştürülebilir dize nesnesinin öğesi olmayan ilk karakteri arar.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*Str*\
Üye işlevin arama string_view.

*chVal*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı dizin.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranması gereken C dizesinde ilk karakterden ileri sayarak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

## <a name="basic_string_viewfind_first_of"></a><a name="find_first_of"></a>basic_string_view::find_first_of

Belirli bir string_view herhangi bir öğesi eşleşen ilk karakteri arar.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*chVal*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı dizin.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranması gereken C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin arama string_view.

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `npos`takdirde .

## <a name="basic_string_viewfind_last_not_of"></a><a name="find_last_not_of"></a>basic_string_view:find_last_not_of

Belirtilen bir string_view herhangi bir öğesi olmayan son karakteri arar.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*Str*\
Üye işlevin arama string_view.

*chVal*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın bitmek üzere olduğu dizin.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Karakter sayısı, ilk karakterden ileri sayarak, *ptr.*

### <a name="return-value"></a>Dönüş Değeri

Substring ilk karakterin indeksi başarılı olduğunda aranır; aksi `string_view::npos`takdirde .

## <a name="basic_string_viewfind_last_of"></a><a name="find_last_of"></a>basic_string_view:find_last_of

Belirli bir string_view herhangi bir öğesieşleşen son karakteri arar.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*Str*\
Üye işlevin arama string_view.

*chVal*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın bitmek üzere olduğu dizin.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranması gereken C dizesinde ilk karakterden ileri sayarak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Substring son karakterinin dizin başarılı olduğunda aranır; aksi `npos`takdirde .

## <a name="basic_string_viewfront"></a><a name="front"></a>basic_string_view::ön

İlk öğeye bir const_reference döndürür.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğeye const_reference.

### <a name="remarks"></a>Açıklamalar

string_view boşsa bir özel durum atar.

## <a name="basic_string_viewlength"></a><a name="length"></a>basic_string_view::uzunluk

Geçerli öğe sayısını verir.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev [boyutu](#size)yla aynıdır.

## <a name="basic_string_viewmax_size"></a><a name="max_size"></a>basic_string_view:max_size

Bir string_view içerebileceği maksimum karakter sayısını verir.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir string_view içerebileceği maksimum karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bir işlem, 'den büyük bir string_view ürettiğinde, `max_size()` [length_error](../standard-library/length-error-class.md) türünden bir özel durum atılır.

## <a name="basic_string_viewoperator"></a><a name="op_eq"></a>basic_string_view::operator=

Başka bir string_view string_view veya dönüştürülebilir dize nesnesi atar.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```

### <a name="example"></a>Örnek

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```

## <a name="basic_string_viewoperator"></a><a name="op_at"></a>basic_string_view::operatör[]

Belirli bir dizin ile karaktere bir const_reference sağlar.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*Uzaklık*\
Başvurulacak öğenin dizin.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen pozisyondakaraktere const_reference.

### <a name="remarks"></a>Açıklamalar

İlk öğe sıfır dizini vardır ve aşağıdaki öğeler pozitif tamsayılar tarafından art arda dizine alınır, böylece *n* - 1 *sayısına* göre indekslenmiş *n'inci*bir eleman string_view vardır.

`operator[]`bir string_view öğelerine okuma erişimi sağlamak [için](#at) üye işlevden daha hızlıdır.

`operator[]`bağımsız değişken olarak geçirilen dizin geçerli olup olmadığını denetlemez. Geçersiz bir dizin `operator[]` tanımlanmamış davranışla sonuçlanır.

Alttaki dize verileri değiştirilen veya sahip olan nesne tarafından silinirse döndürülen başvuru geçersiz kılınabilir.

[ \_ITERATOR\_HATA\_AYıKLAMA DÜZEYİ](../standard-library/iterator-debug-level.md) 1 veya 2 olarak ayarlanmış olarak derlediğinizde, string_view sınırları dışında bir öğeye erişmeye çalışırsanız çalışma zamanı hatası oluşur. Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

## <a name="basic_string_viewrbegin"></a><a name="rbegin"></a>basic_string_view::rbegin

Ters string_view ilk öğeye bir const yineleyici döndürür.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters string_view ilk öğeye rasgele erişim yineleyicisi döndürür ve karşılık gelen tersine çevrilmemiş string_view son öğenin ne olacağını ele verir.

### <a name="remarks"></a>Açıklamalar

`rbegin`bir string_view ile [başolarak](#begin) olduğu gibi ters string_view kullanılır. `rbegin`bir yinelemeyi geriye doğru başlatmak için kullanılabilir.

## <a name="basic_string_viewremove_prefix"></a><a name="remove_prefix"></a>basic_string_view::remove_prefix

İşaretçiyi belirtilen öğe sayısına göre ileri taşır.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Açıklamalar

Temel verileri değişmeden bırakır. string_view işaretçisini n öğelerine göre `size` ileriye taşır ve özel veri üyesini boyut - n olarak ayarlar.

## <a name="basic_string_viewremove_suffix"></a><a name="remove_suffix"></a>basic_string_view:remove_suffix

Görünümün boyutunu arkadan başlayarak belirtilen öğe sayısına göre küçültür.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Açıklamalar

Temel verileri ve işaretçiyi değişmeden bırakır. Özel `size` veri üyesini boyut - n olarak ayarlar.

## <a name="basic_string_viewrend"></a><a name="rend"></a>basic_string_view::rend

Ters string_view son öğeyi geçmiş bir öğeye işaret eden bir const yineleyici döndürür.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters string_view son öğeyi geçmiş bir öğeye işaret eden const ters rasgele erişim yinelemesi.

### <a name="remarks"></a>Açıklamalar

`rend`[uç](#end) bir string_view ile kullanıldığı gibi ters string_view ile kullanılır. `rend`ters yineleyicinin string_view sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir. Döndürülen `rend` değer dereferenced olmamalıdır.

## <a name="basic_string_viewrfind"></a><a name="rfind"></a>basic_string_view::rfind

Belirli bir karakter dizisiyle eşleşen bir alt dize için bir string_view ters te arar.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*chVal*\
Üye işlevin aranacak karakter değeri.

*Uzaklık*\
Aramanın başlayacağı dizin.

*Ptr*\
Üye işlevin aranacak olduğu C dizesi.

*Sayısı*\
Üye işlevin aranması gereken C dizesinde ilk karakterden ileri sayarak karakter sayısı.

*Str*\
Üye işlevin arama string_view.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda substring ilk karakterin indeksi; aksi `npos`takdirde .

## <a name="basic_string_viewsize"></a><a name="size"></a>basic_string_view::boyut

string_view'daki öğe sayısını verir.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

string_view uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bir string_view, örneğin `remove_prefix` ve. `remove_suffix` Bu, temel dize verilerini değiştirmedığından, string_view boyutu temel deki verilerin boyutu olmak zorunda değildir.

## <a name="basic_string_viewsubstr"></a><a name="substr"></a>basic_string_view::substr

Belirtilen karakter sayısını (en fazla) temsil eden bir string_view verir.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Parametreler

*Uzaklık*\
Varsayılan değeri 0 olan, kopyanın yapıldığı konumdaöğeyi bulucu bir dizin.

*Sayısı*\
Varsa, alt dizeye dahil edilebilen karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Öğelerin belirtilen alt dizisini temsil eden string_view bir nesne.

## <a name="basic_string_viewswap"></a><a name="swap"></a>basic_string_view::takas

İki string_views, diğer bir deyişle temel dize verilerinin işaretçileri ve boyut değerlerini değiştirir.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sv*\
Kaynak, işaretçisi ve boyut değerleri hedef string_view ile değiştirilecek olan string_view.

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
