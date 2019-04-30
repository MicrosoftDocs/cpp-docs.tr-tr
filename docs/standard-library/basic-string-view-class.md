---
title: basic_string_view sınıfı
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
ms.openlocfilehash: 0ac5e3d528881f7b1caa0a1dcdae0161a6777e57
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346637"
---
# <a name="basicstringview-class"></a>basic_string_view sınıfı

Sınıf şablonu `basic_string_view<charT>` üzerinde bu türleri şablonlaştırılacak işlevine olmadan, güvenli ve verimli bir şekilde çeşitli kabul etmek bir işlev için dize türleri ilgisiz olarak sunmak için C ++ 17 eklenmiştir. Sınıfı, karakter verileri sırayla karakter sayısını belirten bir uzunluk ve bitişik bir diziye sahip olmayan bir işaretçi tutar. Hiçbir varsayım dizisi null ile sonlandırılmış olmasına göre yapılır.

Standart kitaplık, öğe türüne göre birkaç uzmanlık tanımlar:

-  `string_view`
-  `wstring_view`
-  `u16string_view`
-  `u32string_view`

Bu belgede, "string_view" terimi genellikle bu tür tanımlarından birine ifade eder.

Dize verileri okumak gerekli en düşük ortak arabirim bir string_view açıklar. Temel alınan verileri const erişim sağlar; hiçbir kopya kolaylaştırır (dışında `copy` işlevi). Veri olabilir veya herhangi bir konumda null değerleri ('\0') içeremez. Bir string_view nesnenin kullanım ömrü üzerinde denetimi yoktur. Temel dize verileri geçerli olduğundan emin olun çağrı sahibinin sorumluluğundadır.

Tür string_view parametre kabul eden bir işlev, işlev bir şablona yapma veya belirli bir alt dize türleri işleve sınırlama olmadan herhangi bir dize benzeri türü ile çalışmak için yapılabilir. Örtük bir dönüştürme için string_view dize türü var olduğunu tek gereksinim olmasıdır. Tüm standart dize türleri aynı öğe türünü içeren bir string_view örtük olarak dönüştürülebilir. Diğer bir deyişle, bir `std::string` dönüştürülebilen bir `string_view` değil bir `wstring_view`.

Aşağıdaki örnek, bir şablon olmayan işlev gösterir. `f` türünde bir parametre almayan `wstring_view`. Türünde bağımsız değişkenlerle çağrılabilir `std::wstring`, `wchar_t*`, ve `winrt::hstring`.

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

*CharType*<br/>
String_view içinde depolanan karakter türüdür. C++ Standart kitaplığı, bu şablon uzmanlıkları için aşağıdaki tür tanımları sağlar.
- [string_view](../standard-library/string-view-typedefs.md#string_view) türü öğeler için **char**
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), için **wchar_t**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) için **char16_t**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) için **char32_t**.

*Nitelikler*<br/>
Varsayılan olarak [char_traits](char-traits-struct.md)<*CharType*>.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_string_view](#basic_string_view)|Bazı diğer dize nesne verilerinin bir kısmını veya tamamını veya bir C tarzı karakter dizisine işaret yoksa boş bir string_view oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|**const_iterator**|Okuyabilen rasgele erişim yineleyicisi **const** öğeleri.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**Yineleyici**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**İşaretçi**|`using pointer = value_type*;`|
|**Başvuru**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Üye işleçleri

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|İçin başka bir string_view string_view veya dönüştürülebilir bir dize nesnesi atar.|
|[İşleci\[\]](#op_at)|Belirtilen dizindeki öğeyi döndürür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[konumunda](#at)|Belirtilen konumdaki bir öğeye bir const_reference döndürür.|
|[Geri](#back)|Bir const_reference son öğe için döndürür.|
|[başlayın](#begin)|İlk öğeyi adresleyen bir const yineleyici döndürür. (string_views sabittir.)|
|[cbegin](#cbegin)|Aynı [başlamak](#begin).|
|[cend](#cend)|Son öğeden bir öncekine gösteren bir const yineleyici döndürür.|
|[kopyalama](#copy)|En fazla belirtilen sayıda karakteri kaynak string_view dizinli bir konumda bir hedef karakter dizisine kopyalar. (Önerilmez. _Copy_s kullanın.)|
|[_Copy_s](#_copy_s)|CRT kopyalama işlevi için güvenli hale getirin.|
|[Karşılaştırma](#compare)|Bir string_view eşitlerse veya biri diğerinden lexicographically daha küçük olup olmadığını belirlemek için belirtilen bir string_view ile karşılaştırır.|
|[crbegin](#crbegin)|Aynı [rbegin](#rbegin).|
|[crend](#crend)|Aynı [rend](#rend).|
|[Veri](#data)|Karakter dizisine sahip olmayan bir ham işaretçiyi döndürür.|
|[boş](#empty)|String_view karakterler içerip içermediğini test eder.|
|[Son](#end)|Aynı [cend](#cend).|
|[Bul](#find)|Belirli bir karakter dizisi ile eşleşen bir alt dizenin ilk örneği için İleri yönde arar.|
|[find_first_not_of](#find_first_not_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesi herhangi bir öğesi olmayan ilk karakter arar.|
|[find_first_of](#find_first_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesi herhangi bir öğe eşleşen ilk karakter arar.|
|[find_last_not_of](#find_last_not_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesi herhangi bir öğe değil. son karakter arar.|
|[find_last_of](#find_last_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesi bir öğenin son karakter arar.|
|[Ön](#front)|Bir const_reference ilk öğeye döndürür.|
|[Uzunluğu](#length)|Geçerli öğe sayısını döndürür.|
|[max_size](#max_size)|En fazla bir string_view içerebilir karakter sayısını döndürür.|
|[rbegin](#rbegin)|Ters çevrilen string_view ilk öğeyi adresleyen bir const yineleyici döndürür.|
|[remove_prefix](#remove_prefix)|Belirtilen sayıda öğeyi tarafından işaretçiyi ileriye taşır.|
|[remove_suffix](#remove_suffix)|Belirtilen sayıda yeniden başlatma öğelerin görünümün boyutunu azaltır.|
|[rend](#rend)|Ters çevrilen string_view içinde son öğeden bir öncekine işaret eden bir const yineleyici döndürür.|
|[rfind](#rfind)|Bir string_view ters belirli bir karakter dizisi ile eşleşen bir alt dizenin ilk geçtiği yeri arar.|
|[Boyutu](#size)|Geçerli öğe sayısını döndürür.|
|[substr](#substr)|Belirtilen bir dizinden başlayarak belirtilen uzunlukta bir alt dizeyi döndürür.|
|[değiştirme](#swap)|İki string_views içeriğini exchange.|

## <a name="remarks"></a>Açıklamalar

Bir işlev oluşturmak daha uzun bir sıralama istenirse [max_size](#max_size) öğeleri, işlev bir uzunluk hatası bildirir türünde bir nesne [length_error](../standard-library/length-error-class.md).

## <a name="requirements"></a>Gereksinimler

[Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) veya üzeri

**Başlık:** \<string_view >

**Namespace:** std

## <a name="at"></a>  basic_string_view::AT

Bir const_reference 0 tabanlı belirtilen dizindeki karakteri döndürür.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
Başvurulacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Bir const_reference parametre dizini tarafından belirtilen konumdaki karakteri.

### <a name="remarks"></a>Açıklamalar

Dizin sıfır ilk öğeye sahip ve aşağıdaki öğeleri sırayla pozitif tam sayılar tarafından dizine böylece uzunlukta bir string_view *n* sahip bir *n*öğedeki dizine numarasıyla*n -* 1. **konumunda** aksine geçersiz dizinler için bir özel durum oluşturduğunda [işleci\[\]](#op_at). 

Genel olarak, öneririz **adresindeki** dizileri gibi `std::vector` ve string_view hiçbir zaman kullanılmalıdır. Geçirilen bir dizisi geçersiz dizin bulunmalı ve geliştirme sırasında sabit bir mantık hatası var. Bir program, dizinleri geçerli olduğunu kesinlikle emin değilse, bunları test edin, değil at() çağırın ve gerekir dikkatsiz programlama karşı korumak için özel durumlar dayanır.

Bkz: [basic_string_view::operator\[ \] ](#op_at) daha fazla bilgi için.

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

## <a name="back"></a>  basic_string_view::Back

Bir const_reference son öğe için döndürür.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const_reference string_view içindeki son öğeyi.

### <a name="remarks"></a>Açıklamalar

String_view boşsa bir özel durum oluşturur.

Aklınızda bir string_view, örneğin çağırarak değiştirildikten sonra `remove_suffix`, bu işlev tarafından döndürülen öğe artık temel alınan verileri içindeki son öğeden sonra.

### <a name="example"></a>Örnek

C dize değişmez değer ile oluşturulmuş bir string_view Sonlandırıcı null içermez ve dolayısıyla aşağıdaki örnekte `back` 'p' değil '\0' döndürür.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p 
```

Gömülü null değerlere herhangi bir karakter olarak kabul edilir:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_view"></a>  basic_string_view::basic_string_view

Bir string_view oluşturur.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Karakter değerlerini işaretçisi.

*Len*<br/>
Görünümüne dahil edilecek karakter sayısı.

## <a name="remarks"></a>Açıklamalar

Giriş null ile sonlandırılmış olabilir, ancak Sonlandırıcı null string_view içinde yer almayan bir grafik * parametresiyle oluşturucular varsayılır.

Ayrıca, bir sabit değer ile bir string_view oluşturabilirsiniz. Bkz: [işleci "" sv](string-view-operators.md#op_sv).

## <a name="begin"></a>  basic_string_view::Begin

Aynı [cbegin](#cbegin).

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri
İlk öğeyi ele alan bir const_iterator döndürür.

## <a name="cbegin"></a>  basic_string_view::cbegin

Aralıktaki ilk öğeyi ele alan bir const_iterator döndürür.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığı veya konuma boş bir aralığın ilk öğesine, rasgele erişim yineleyicisi (boş bir aralık için `cbegin() == cend()`).

## <a name="cend"></a>  basic_string_view::cend

Konuma bir aralıktaki son öğeyi ele alan bir const_iterator döndürür.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** aralığın hemen sonunu rasgele erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `cend` kaldırılmamalıdır.

## <a name="compare"></a> basic_string_view::COMPARE

İki nesnenin eşit olup olmadığını veya biri diğerinden lexicographically daha küçük olup olmadığını belirlemek için belirtilen string_view (veya dönüştürülebilir dize türünde) ile büyük küçük harfe duyarlı bir karşılaştırma gerçekleştirir. [ \<String_view > işleçleri](string-view-operators.md) karşılaştırmalar yapmak için bu üye işlevini kullanın.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Parametreler

*strv*<br/>
Bu string_view için karşılaştırılması gereken olan string_view.

*POS*<br/>
Karşılaştırma başlar bu string_view dizini.

*sayı*<br/>
Bu string_view Karşılaştırılacak karakter sayısı.

*Num2*<br/>
En fazla sayıda karakteri *strv* karşılaştırılmalıdır.

*uzaklık*<br/>
Dizini *strv* konumundaki karşılaştırma başlar.

*ptr*<br/>
Bu string_view için karşılaştırılması gereken C dizesi.

### <a name="return-value"></a>Dönüş Değeri

Bu string_view ise negatif bir değer küçüktür *strv* veya *ptr*; sıfır iki karakterli dizileri eşittir; ya da pozitif bir değer varsa bu string_view büyükse *strv*veya *ptr*.

### <a name="remarks"></a>Açıklamalar

`compare` Üye işlevleri gerçekleştirmek büyük küçük harfe duyarlı bir karşılaştırma öğesinin tümünün veya her karakter dizisinin bir parçası. 

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

## <a name="copy"></a>  basic_string_view::Copy

En fazla belirtilen sayıda karakteri kaynak string_view dizinli bir konumda bir hedef karakter dizisine kopyalar. Güvenli işlevi kullanmanızı öneririz [basic_string_view::_Copy_s](#_copy_s) yerine.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Öğelerin kopyalanacağı olan hedef karakter dizisi.

*Sayısı*<br/>
En fazla kaynak string_view kopyalanacak karakter sayısı.

*uzaklık*<br/>
Kopyalarıdır yapılacak kaynak string_view başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Aslında kopyalanan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Kopya sonuna null karakteri eklenmemiş.

## <a name="_copy_s"></a>  basic_string_view::_Copy_s

CRT kopyalama işlevi yerine kullanılacak güvenli [kopyalama](#copy).

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Öğelerin kopyalanacağı olan hedef karakter dizisi.

*dest_size*<br/>
Boyutu *dest*.

_ *Sayısı* , en fazla kaynak dizesi kopyalanacak karakter sayısı.

*_Off*<br/>
Kaynak dizesi kopyalarıdır yapılacak başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Aslında kopyalanan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Kopya sonuna null karakteri eklenmemiş.

 Daha fazla bilgi için [c-runtime-library/security-features-in-the-crt](../c-runtime-library/security-features-in-the-crt.md).

## <a name="crbegin"></a>  basic_string_view::crbegin

Ters çevrilen string_view içindeki ilk öğeyi ele alan bir const_reverse_iterator döndürür.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen string_view içindeki ilk öğeyi ele alan const_reverse_iterator. 

## <a name="crend"></a>  basic_string_view::crend

Aynı [rend](#rend). 

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir ters string_view sonunu ele alan bir const_reverse_iterator döndürür.

## <a name="data"></a>  basic_string_view::Data

Sahip olmayan bir ham işaretçi string_view oluşturmak için kullanılan nesne için const karakter dizisini döndürür.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi için-sabit karakter dizisi'öğesinin ilk öğesinin.

### <a name="remarks"></a>Açıklamalar

İşaretçi karakterleri değiştiremezsiniz.

Bir dizi string_view karakteri mutlaka null ile sonlandırılmış değil. İçin dönüş türü `data` hiçbir null karakteri eklenmemiş çünkü geçerli bir C dizesi değil. Null karakteri '\0' türü string_view nesnenin özel bir anlamı yoktur ve string_view nesneyi başka bir karakter olduğu gibi bir parçası olabilir.

## <a name="empty"></a>  basic_string_view::empty

String_view karakterler içerip içermediğini test eder.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** string_view nesne; karakter içeriyorsa **false** en az bir karakter varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi eşdeğerdir [boyutu](#size)() == 0.

## <a name="end"></a>  basic_string_view::End

Son öğeden bir öncekine işaret eden bir rastgele erişim const_iterator döndürür.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Son öğeden bir öncekine işaret eden bir rastgele erişim const_iterator döndürür.

### <a name="remarks"></a>Açıklamalar

`end` bir const_iterator kendi string_view sonuna ulaştı olup olmadığını sınamak için kullanılır. Tarafından döndürülen değer `end` kaldırılmamalıdır.

## <a name="find"></a>  basic_string_view::Find

Bir string_view bir ileri yönde bir karakter ya da belirli bir karakter dizisi ile eşleşen alt dizenin ilk geçtiği yeri arar.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Üye işlevi arama gerçekleştirmektir string_view.

*chVal*<br/>
Üye işlevi arama gerçekleştirmektir karakter değeri.

*uzaklık*<br/>
Aramaya başlamak için olduğu dizini.

*ptr*<br/>
C dize üye işlevi arama gerçekleştirmektir.

*Sayısı*<br/>
Karakter sayısı *ptr*, İleri ilk karakter sayma.

### <a name="return-value"></a>Dönüş Değeri

Alt dizenin ilk karakter dizinini başarılı olduğunda aranabilir; Aksi takdirde `npos`.

## <a name="find_first_not_of"></a>  basic_string_view::find_first_not_of

Belirtilen string_view veya dönüştürülebilir dize nesnesi bir öğesi olmayan ilk karakter arar.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Üye işlevi arama gerçekleştirmektir string_view.

*chVal*<br/>
Üye işlevi arama gerçekleştirmektir karakter değeri.

*uzaklık*<br/>
Aramaya başlamak için olduğu dizini.

*ptr*<br/>
C dize üye işlevi arama gerçekleştirmektir.

*Sayısı*<br/>
Üye işlevi arama gerçekleştirmektir C dizedeki ilk karakter İleri sayım karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Alt dizenin ilk karakter dizinini başarılı olduğunda aranabilir; Aksi takdirde `npos`.

## <a name="find_first_of"></a>  basic_string_view::find_first_of

Herhangi bir öğe belirtilen string_view eşleşen ilk karakter arar.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*chVal*<br/>
Üye işlevi arama gerçekleştirmektir karakter değeri.

*uzaklık*<br/>
Aramaya başlamak için olduğu dizini.

*ptr*<br/>
C dize üye işlevi arama gerçekleştirmektir.

*Sayısı*<br/>
Üye işlevi arama gerçekleştirmektir C dizedeki ilk karakter İleri sayım karakter sayısı.

*str*<br/>
Üye işlevi arama gerçekleştirmektir string_view.

### <a name="return-value"></a>Dönüş Değeri

Alt dizenin ilk karakter dizinini başarılı olduğunda aranabilir; Aksi takdirde `npos`.

## <a name="find_last_not_of"></a>  basic_string_view::find_last_not_of

Belirtilen string_view herhangi bir öğe değil. son karakter arar.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Üye işlevi arama gerçekleştirmektir string_view.

*chVal*<br/>
Üye işlevi arama gerçekleştirmektir karakter değeri.

*uzaklık*<br/>
Dizin arama son sağlamaktır.

*ptr*<br/>
C dize üye işlevi arama gerçekleştirmektir.

*Sayısı*<br/>
İleri ilk karakter de sayım karakter sayısını *ptr*.

### <a name="return-value"></a>Dönüş Değeri

Alt dizenin ilk karakter dizinini başarılı olduğunda aranabilir; Aksi takdirde `string_view::npos`.

## <a name="find_last_of"></a>  basic_string_view::find_last_of

Herhangi bir öğe belirtilen string_view eşleşen son karakter arar.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Üye işlevi arama gerçekleştirmektir string_view.

*chVal*<br/>
Üye işlevi arama gerçekleştirmektir karakter değeri.

*uzaklık*<br/>
Dizin arama son sağlamaktır.

*ptr*<br/>
C dize üye işlevi arama gerçekleştirmektir.

*Sayısı*<br/>
Üye işlevi arama gerçekleştirmektir C dizedeki ilk karakter İleri sayım karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Dizenin son karakter dizinini başarılı olduğunda aranabilir; Aksi takdirde `npos`.

## <a name="front"></a>  basic_string_view::Front

Bir const_reference ilk öğeye döndürür.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğeye bir const_reference.

### <a name="remarks"></a>Açıklamalar

String_view boşsa bir özel durum oluşturur.

## <a name="length"></a> basic_string_view::length

Geçerli öğe sayısını döndürür.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi aynı olan [boyutu](#size).

## <a name="max_size"></a>  basic_string_view::max_size

En fazla bir string_view içerebilir karakter sayısını döndürür.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir string_view içerebilir karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Türünde bir özel durum [length_error](../standard-library/length-error-class.md) işleminin büyük bir uzunlukla bir string_view üretir çağırınca `max_size()`.

## <a name="op_eq"></a>  basic_string_view::operator =

İçin başka bir string_view string_view veya dönüştürülebilir bir dize nesnesi atar.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```
### <a name="example"></a>Örnek

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```
## <a name="op_at"></a>  basic_string_view::operator]

İle belirtilen bir dizinden bir const_reference karaktere sağlar.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
Başvurulacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Bir const_reference parametre dizini tarafından belirtilen konumdaki karakteri.

### <a name="remarks"></a>Açıklamalar

Dizin sıfır ilk öğeye sahip ve aşağıdaki öğeleri sırayla pozitif tam sayılar tarafından dizine böylece uzunlukta bir string_view *n* sahip bir *n*öğedeki dizine numarasıyla*n* - 1.

`operator[]` üye işlevini hızlıdır [adresindeki](#at) bir string_view öğelerini okuma erişimi sağlamak için.

`operator[]` bağımsız değişken olarak geçirilen dizinin geçerli olup olmadığını denetlemez. Geçersiz dizin geçirilen `operator[]` tanımsız davranışlara neden olur.

Temel dize verileri ise veya silinmesi sahip olan bir nesne tarafından döndürülen başvuru geçersiz.

İle derlerken [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md) 1 veya 2 olarak ayarlanırsa, string_view sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur. Daha fazla bilgi için [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="rbegin"></a>  basic_string_view::rbegin

Ters çevrilen string_view içindeki ilk öğeye sabit bir yineleyici döndürür.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir rastgele erişim yineleyici karşılık gelen bir ters çevrilmeyen string_view içindeki son öğeden ne olacağını ele alan bir ters string_view içindeki ilk öğeye döndürür.

### <a name="remarks"></a>Açıklamalar

`rbegin` ters çevrilen bir string_view ile kullanılan gibi [başlamak](#begin) bir string_view ile kullanılır. `rbegin` Geriye dönük bir yineleme başlatmak için kullanılabilir.

## <a name="remove_prefix"></a> basic_string_view::remove_prefix

Belirtilen sayıda öğeyi tarafından işaretçiyi ileriye taşır.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Açıklamalar

Temel alınan verilerin değişmeden kalır. N öğeleri tarafından string_view işaretçi ileriye taşır ve özel ayarlar `size` boyuta - n veri üyesi.

## <a name="remove_suffix"></a> basic_string_view::remove_suffix

Belirtilen sayıda yeniden başlatma öğelerin görünümün boyutunu azaltır.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Açıklamalar

Temel alınan veriler ve işaretçiyi, değiştirmeden bırakır. Özel ayarlar `size` boyuta - n veri üyesi.

## <a name="rend"></a>  basic_string_view::rend

Ters çevrilen string_view içinde son öğeden bir öncekine işaret eden bir const yineleyici döndürür.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir const tersine çevrilen string_view içindeki son öğeden bir öncekine rasgele erişim yineleyicisi.

### <a name="remarks"></a>Açıklamalar

`rend` ters çevrilen bir string_view ile kullanılan gibi [son](#end) bir string_view ile kullanılır. `rend` Ters yineleyici kendi string_view sonuna ulaştı olup olmadığını test etmek için kullanılabilir. Tarafından döndürülen değer `rend` kaldırılmamalıdır.

## <a name="rfind"></a>  basic_string_view::rfind

Ters for belirli bir karakter dizisi ile eşleşen bir alt dizenin bir string_view arar.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*chVal*<br/>
Üye işlevi arama gerçekleştirmektir karakter değeri.

*uzaklık*<br/>
Aramaya başlamak için olduğu dizini.

*ptr*<br/>
C dize üye işlevi arama gerçekleştirmektir.

*Sayısı*<br/>
Üye işlevi arama gerçekleştirmektir C dizedeki ilk karakter İleri sayım karakter sayısı.

*str*<br/>
Üye işlevi arama gerçekleştirmektir string_view.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda alt dizenin ilk karakter dizinini; Aksi takdirde `npos`.

## <a name="size"></a>  basic_string_view::size

String_view öğelerin sayısını döndürür.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

String_view uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bir string_view uzunluğu, örneğin değiştirebilirsiniz `remove_prefix` ve `remove_suffix`. Temel dize verileri değiştirmez, çünkü bir string_view boyutunu temel alınan verilerin boyutunu değil.

## <a name="substr"></a>  basic_string_view::SUBSTR

(En fazla) belirtilen konumdan başlayarak belirtilen sayıdaki karakterini temsil eden bir string_view döndürür.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
Bir dizini öğesi içinden kopyası, 0 varsayılan değeri ile oluşturulan bir konumda bulunuyor.

*Sayısı*<br/>
Mevcut değilse, strB içerecek şekilde karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alt öğelerini temsil string_view nesnesi.

## <a name="swap"></a>  basic_string_view::Swap

Diğer bir deyişle temel dize verileri ve boyutu değerlerinin işaretçileri olan iki string_views birbiriyle değiştirir.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Parametreler

*sv*<br/>
İşaretçiyi ve boyut değerleri, hedef string_view ile değiştirilecek olan kaynak string_view.

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
