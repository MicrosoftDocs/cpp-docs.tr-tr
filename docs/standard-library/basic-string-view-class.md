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
ms.openlocfilehash: 6609f8e8ee8ccb0d14dbdf11cefc29f4b0dfa6f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219189"
---
# <a name="basic_string_view-class"></a>basic_string_view sınıfı

Sınıf şablonu, işlevin `basic_string_view<charT>` bu türlerde şablonlanmasına gerek kalmadan, çeşitli ilişkisiz dize türlerini kabul etmesi için güvenli ve etkili bir yol olarak kullanılacak şekilde c++ 17 ' ye eklenmiştir. Sınıfı, bir dizi karakter verisi dizisine sahip olmayan bir işaretçi ve dizideki karakter sayısını belirten bir uzunluk içerir. Dizinin null sonlandırılmış olup olmadığı ile ilgili bir varsayım yapılmaz.

Standart Kitaplık, öğelerin türüne göre çeşitli uzmanlık tanımlar:

- `string_view`
- `wstring_view`
- `u16string_view`
- `u32string_view`

Bu belgede, "string_view" terimi genellikle bu tür türtanımlarının herhangi birine başvurur.

String_view dize verilerini okumak için gereken en düşük ortak arabirimi açıklar. Temel alınan verilere const erişimi sağlar; hiçbir kopya yapmaz ( `copy` işlev hariç). Veriler herhangi bir konumda null değer (' \ 0 ') içerebilir veya içermeyebilir. String_view nesnenin ömrü boyunca denetim yoktur. Bu, temeldeki dize verilerinin geçerli olduğundan emin olmak için çağıranın sorumluluğundadır.

String_view türünde bir parametreyi kabul eden bir işlev, herhangi bir dize benzeri tür ile çalışabilir, bu işlevi bir şablona veya bir dizi dize türünün belirli bir alt kümesine sınırlama. Tek gereksinim, dize türünden string_view örtük bir dönüştürmenin mevcut olması. Tüm standart dize türleri, aynı öğe türünü içeren bir string_view örtük olarak dönüştürülebilir. Diğer bir deyişle, a `std::string` dönüştürülebilir `string_view` ancak öğesine dönüştürülemez `wstring_view` .

Aşağıdaki örnek, `f` türünde bir parametre alan şablon olmayan bir işlevi gösterir `wstring_view` . , Ve türündeki bağımsız değişkenlerle çağrılabilir `std::wstring` `wchar_t*` `winrt::hstring` .

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

## <a name="syntax"></a>Söz dizimi

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>Parametreler

*CharType*\
String_view depolanan karakterlerin türü. C++ standart kitaplığı, bu şablonun özelleştirilmiş oluşturmaları için aşağıdaki tür tanımlarını sağlar.

- türündeki öğeler için [string_view](../standard-library/string-view-typedefs.md#string_view)**`char`**
- için [wstring_view](../standard-library/string-view-typedefs.md#wstring_view),**`wchar_t`**
- için [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)**`char16_t`**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) için u32string_view **`char32_t`** .

*Lerdir*\
[Char_traits](char-traits-struct.md) < *CharType*> varsayılan olarak belirlenmiştir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_string_view](#basic_string_view)|Boş veya başka bir dize nesnesinin verilerinin tümünü veya bir kısmını ya da C stili karakter dizisine işaret eden bir string_view oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|**const_iterator**|Öğeleri okuyabileceğiniz Rastgele erişimli Yineleyici **`const`** .|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**iden**|`using iterator = const_iterator;`|
|**nPos**|`static constexpr size_type npos = size_type(-1);`|
|**pointer**|`using pointer = value_type*;`|
|**başvurunun**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Üye işleçleri

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Başka bir string_view string_view veya dönüştürülebilir dize nesnesi atar.|
|[işleç\[\]](#op_at)|Belirtilen dizindeki öğeyi döndürür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[hızı](#at)|Belirtilen konumdaki öğesine const_reference döndürür.|
|[Geri](#back)|Son öğeye bir const_reference döndürür.|
|[başladı](#begin)|İlk öğeyi adresleyen bir const yineleyici döndürür. (string_views sabittir.)|
|[cbegin](#cbegin)|[Begin](#begin)ile aynı.|
|[cend](#cend)|Son öğeyi aşan bir sabitten oluşan const yineleyici döndürür.|
|[kopya](#copy)|Kaynak string_view dizinli bir konumdan bir hedef karakter dizisine en çok belirtilen sayıda karakteri kopyalar. (Önerilmez. Bunun yerine _Copy_s kullanın.)|
|[_Copy_s](#_copy_s)|Güvenli CRT kopyalama işlevi.|
|[Karşılaştır](#compare)|Eşit olup olmadığını veya birinin sözcüıgrafik değerinden daha küçük olduğunu anlamak için string_view belirtilen string_view karşılaştırır.|
|[crbegin](#crbegin)|[Rbegin](#rbegin)ile aynı.|
|[crend](#crend)|[Rend](#rend)ile aynı.|
|[data](#data)|Karakter dizisine ait ham sahip olmayan bir işaretçi döndürür.|
|[empty](#empty)|String_view karakter içerip içermediğini sınar.|
|[erer](#end)|[Cend](#cend)ile aynı.|
|[find](#find)|Belirtilen karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için ileriye doğru yönde arar.|
|[find_first_not_of](#find_first_not_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesinin herhangi bir öğesi olmayan ilk karakteri arar.|
|[find_first_of](#find_first_of)|Belirtilen string_view veya dönüştürülebilir dize nesnesinin herhangi bir öğesiyle eşleşen ilk karakteri arar.|
|[find_last_not_of](#find_last_not_of)|Belirtilen bir string_view veya dönüştürülebilir dize nesnesinin herhangi bir öğesi olmayan son karakteri arar.|
|[find_last_of](#find_last_of)|Belirtilen bir string_view veya dönüştürülebilir dize nesnesinin bir öğesi olan son karakteri arar.|
|[yapılan](#front)|İlk öğeye bir const_reference döndürür.|
|[uzunluklu](#length)|Geçerli öğe sayısını döndürür.|
|[max_size](#max_size)|String_view içerebileceği en fazla karakter sayısını döndürür.|
|[rbegin](#rbegin)|Ters çevrilen string_view ilk öğeyi ele alan bir const yineleyici döndürür.|
|[remove_prefix](#remove_prefix)|İşaretçiyi belirtilen sayıda öğe kadar ileri kaydırır.|
|[remove_suffix](#remove_suffix)|Görünümün boyutunu, kayıttan başlayarak belirtilen sayıda öğe kadar azaltır.|
|[rend](#rend)|Ters çevrilen string_view en son öğeden birini işaret eden bir const yineleyici döndürür.|
|[rfind](#rfind)|Belirtilen karakter dizisiyle eşleşen bir alt dizenin ilk oluşumu için string_view ters arar.|
|[boyutla](#size)|Geçerli öğe sayısını döndürür.|
|[substr](#substr)|Belirtilen dizinden başlayarak belirtilen uzunluktaki alt dizeyi döndürür.|
|[Kur](#swap)|İki string_views içeriğini Exchange.|

## <a name="remarks"></a>Açıklamalar

Bir işleve [max_size](#max_size) öğelerinden daha uzun bir sıra oluşturması istenirse, işlev [length_error](../standard-library/length-error-class.md)türünde bir nesne oluşturarak bir uzunluk hatası bildiriyor.

## <a name="requirements"></a>Gereksinimler

[std: c++ 17](../build/reference/std-specify-language-standard-version.md) veya üzeri

**Üst bilgi:**\<string_view>

**Ad alanı:** std

## <a name="basic_string_viewat"></a><a name="at"></a>basic_string_view:: at

Belirtilen 0 tabanlı dizindeki karaktere bir const_reference döndürür.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*konumu*\
Başvurulacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen konumdaki karaktere const_reference.

### <a name="remarks"></a>Açıklamalar

İlk öğe sıfır dizinine sahiptir ve aşağıdaki öğeler pozitif tamsayılar tarafından ardışık olarak dizinlenir, böylece *n* uzunluğu bir string_view n *-* 1 sayısı tarafından dizine alınmış bir *n*. öğesi vardır. , [ \[ işlecinin \] ](#op_at)aksine geçersiz dizinler için bir özel **durum oluşturur.**

Genel olarak, ve string_view gibi **at** diziler `std::vector` asla kullanılmamalıdır. Bir diziye geçirilen geçersiz dizin, geliştirme sırasında bulunması ve düzeltilmesi gereken bir mantık hatasıdır. Bir program, dizinlerinin geçerli olduğundan kesinlikle emin olmazsa, () çağrısı değil, onları test etmelidir ve daha az programlamaya karşı savunması için özel durumlara güvenmelidir.

Daha fazla bilgi için bkz. [basic_string_view:: işleci \[ \] ](#op_at) .

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

## <a name="basic_string_viewback"></a><a name="back"></a>basic_string_view:: Back

Son öğeye bir const_reference döndürür.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

String_view son öğeye const_reference.

### <a name="remarks"></a>Açıklamalar

String_view boşsa bir özel durum oluşturur.

String_view değiştirildikten sonra, örneğin çağırarak `remove_suffix` , bu işlev tarafından döndürülen öğe, temel alınan verilerde artık son öğe değil.

### <a name="example"></a>Örnek

C dize değişmez değeri ile oluşturulan string_view, Sonlandırıcı null değerini içermez ve bu nedenle aşağıdaki örnekte ' `back` p ' ve ' \ 0 ' değil ' p ' döndürülür.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p
```

Gömülü null değerler diğer bir karakter olarak kabul edilir:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_viewbasic_string_view"></a><a name="basic_string_view"></a>basic_string_view:: basic_string_view

Bir string_view oluşturur.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Karakter değerlerine yönelik işaretçi.

*tepe*\
Görünüme eklenecek karakter sayısı.

## <a name="remarks"></a>Açıklamalar

Grafik * parametresi olan oluşturucular, girişin null sonlandırılmış olduğunu varsayar, ancak sonlandırma null değeri string_view dahil değildir.

Ayrıca, sabit değerli bir string_view oluşturabilirsiniz. ["" ZF işlecine](string-view-operators.md#op_sv)bakın.

## <a name="basic_string_viewbegin"></a><a name="begin"></a>basic_string_view:: Begin

[Cbegin](#cbegin)ile aynı.

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğeyi adresleyen bir const_iterator döndürür.

## <a name="basic_string_viewcbegin"></a><a name="cbegin"></a>basic_string_view:: cbegin

Aralıktaki ilk öğeyi ele alan bir const_iterator döndürür.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Aralığın ilk öğesine veya boş bir aralığın sonundaki konuma (boş bir Aralık için) işaret eden bir rastgele erişim Yineleyici `cbegin() == cend()` .

## <a name="basic_string_viewcend"></a><a name="cend"></a>basic_string_view:: cend

Bir aralıktaki son öğeden hemen sonra gelen konumu ele alan bir const_iterator döndürür.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Yalnızca aralığın sonunu işaret eden bir rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `cend` başvurulmamalıdır.

## <a name="basic_string_viewcompare"></a><a name="compare"></a>basic_string_view:: Compare

İki nesnenin eşit olup olmadığını veya birinin lexıgrafik değerinden daha küçük olduğunu anlamak için belirtilen string_view (veya dönüştürülebilir dize türü) ile büyük/küçük harfe duyarlı bir karşılaştırma gerçekleştirir. [ \<string_view> İşleçler](string-view-operators.md) , karşılaştırmaları gerçekleştirmek için bu üye işlevini kullanır.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Parametreler

*Strv*\
Bu string_view Karşılaştırılacak string_view.

*'un*\
Bu string_view karşılaştırmanın başladığı dizin.

*numaraları*\
Bu string_view Karşılaştırılacak en fazla karakter sayısı.

*num2*\
*Strv* 'nin karşılaştırılacağı maksimum karakter sayısı.

*konumu*\
Karşılaştırma işleminin başladığı *Strv* dizini.

*kaydetmeye*\
Bu string_view Karşılaştırılacak C dizesi.

### <a name="return-value"></a>Dönüş Değeri

Bu string_view *Strv* veya *PTR*'den küçükse negatif bir değer; iki karakter dizisi eşitse sıfır; ya da bu string_view *Strv* veya *PTR*'den büyükse pozitif bir değer.

### <a name="remarks"></a>Açıklamalar

`compare`Üye işlevleri, her bir karakter dizisinin tümü veya bir kısmı için büyük/küçük harfe duyarlı bir karşılaştırma gerçekleştirir.

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

## <a name="basic_string_viewcopy"></a><a name="copy"></a>basic_string_view:: Copy

Kaynak string_view dizinli bir konumdan bir hedef karakter dizisine en çok belirtilen sayıda karakteri kopyalar. Bunun yerine [basic_string_view:: _Copy_s](#_copy_s) güvenli işlevini kullanmanızı öneririz.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Öğelerin kopyalanacağı hedef karakter dizisi.

*biriktirme*\
Kaynak string_view en fazla kopyalanacak karakter sayısı.

*konumu*\
Kaynak string_view kopyaların oluşturulacağı başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte kopyalanmış karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kopyanın sonuna bir null karakter eklenmez.

## <a name="basic_string_view_copy_s"></a><a name="_copy_s"></a>basic_string_view:: _Copy_s

[Kopyalama](#copy)yerine kullanılacak güvenli CRT kopyalama işlevi.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parametreler

*HD*\
Öğelerin kopyalanacağı hedef karakter dizisi.

*dest_size*\
*Hedef*boyutu.

_ Kaynak dizeden, en fazla kopyalanacak karakter sayısını *say* .

*_Off*\
Kopya yapılacak Kaynak dizedeki başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte kopyalanmış karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kopyanın sonuna bir null karakter eklenmez.

Daha fazla bilgi için bkz. [c-Runtime-Library/Security---CRT](../c-runtime-library/security-features-in-the-crt.md).

## <a name="basic_string_viewcrbegin"></a><a name="crbegin"></a>basic_string_view:: crbegin

Ters çevrilen bir string_view ilk öğeyi ele alan bir const_reverse_iterator döndürür.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir string_view ilk öğeyi ele alan bir const_reverse_iterator.

## <a name="basic_string_viewcrend"></a><a name="crend"></a>basic_string_view:: crend

[Rend](#rend)ile aynı.

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir string_view sonunun sonundaki bir const_reverse_iterator döndürür.

## <a name="basic_string_viewdata"></a><a name="data"></a>basic_string_view::d ata

String_view oluşturmak için kullanılan nesnenin const karakter dizisine ait ham sahip olmayan bir işaretçi döndürür.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Karakter dizisinin ilk öğesine-const işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşaretçi karakterleri değiştiremiyor.

String_view karakterlerin bir dizisi null ile Sonlandırılmamış olması gerekmez. `data`Hiçbir null karakter eklenmediğinden, için dönüş türü geçerli bir C dizesi değil. ' \ 0 ' null karakterinin string_view türünde bir nesne için özel bir anlamı yoktur ve başka bir karakter gibi string_view nesnesinin bir parçası olabilir.

## <a name="basic_string_viewempty"></a><a name="empty"></a>basic_string_view:: boş

String_view karakter içerip içermediğini sınar.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** string_view nesne karakter içermiyorsa; **`false`** en az bir karakter varsa.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [size](#size)() = = 0 ile eşdeğerdir.

## <a name="basic_string_viewend"></a><a name="end"></a>basic_string_view:: End

En son öğeyi aşan bir rastgele erişim const_iterator döndürür.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

En son öğeyi aşan bir rastgele erişim const_iterator döndürür.

### <a name="remarks"></a>Açıklamalar

`end`, bir const_iterator string_view sonuna gelip ulaşmadığını test etmek için kullanılır. Tarafından döndürülen değer `end` başvurulmamalıdır.

## <a name="basic_string_viewfind"></a><a name="find"></a>basic_string_view:: Find

Belirtilen karakter dizisiyle eşleşen bir karakter veya alt dizenin ilk oluşumu için bir string_view ileri yönde arar.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Üye işlevin aranacağı string_view.

*chVal*\
Üye işlevin aranacağı karakter değeri.

*konumu*\
Aramanın başlayacağı dizin.

*kaydetmeye*\
Üye işlevin aranacağı C dizesi.

*biriktirme*\
İlk karakterden itibaren sayarak, *PTR*içindeki karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

## <a name="basic_string_viewfind_first_not_of"></a><a name="find_first_not_of"></a>basic_string_view:: find_first_not_of

Belirtilen string_view veya dönüştürülebilir dize nesnesinin bir öğesi olmayan ilk karakteri arar.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Üye işlevin aranacağı string_view.

*chVal*\
Üye işlevin aranacağı karakter değeri.

*konumu*\
Aramanın başlayacağı dizin.

*kaydetmeye*\
Üye işlevin aranacağı C dizesi.

*biriktirme*\
Üye işlevin aranacağı C dizesindeki ilk karakterden ileri sayım karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

## <a name="basic_string_viewfind_first_of"></a><a name="find_first_of"></a>basic_string_view:: find_first_of

Belirtilen string_view herhangi bir öğesiyle eşleşen ilk karakteri arar.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Parametreler

*chVal*\
Üye işlevin aranacağı karakter değeri.

*konumu*\
Aramanın başlayacağı dizin.

*kaydetmeye*\
Üye işlevin aranacağı C dizesi.

*biriktirme*\
Üye işlevin aranacağı C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*üstbilgisine*\
Üye işlevin aranacağı string_view.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

## <a name="basic_string_viewfind_last_not_of"></a><a name="find_last_not_of"></a>basic_string_view:: find_last_not_of

Belirtilen string_view hiçbir öğe olmayan son karakteri arar.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Üye işlevin aranacağı string_view.

*chVal*\
Üye işlevin aranacağı karakter değeri.

*konumu*\
Aramanın tamamlanalınacağı dizin.

*kaydetmeye*\
Üye işlevin aranacağı C dizesi.

*biriktirme*\
*PTR*içindeki ilk karakterden sonra gelen karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin ilk karakterinin dizini; Aksi takdirde `string_view::npos` .

## <a name="basic_string_viewfind_last_of"></a><a name="find_last_of"></a>basic_string_view:: find_last_of

Belirtilen string_view herhangi bir öğesiyle eşleşen son karakteri arar.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Üye işlevin aranacağı string_view.

*chVal*\
Üye işlevin aranacağı karakter değeri.

*konumu*\
Aramanın tamamlanalınacağı dizin.

*kaydetmeye*\
Üye işlevin aranacağı C dizesi.

*biriktirme*\
Üye işlevin aranacağı C dizesindeki ilk karakterden ileri sayım karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda Aranan alt dizenin son karakterinin dizini; Aksi takdirde `npos` .

## <a name="basic_string_viewfront"></a><a name="front"></a>basic_string_view:: Front

İlk öğeye bir const_reference döndürür.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğe için bir const_reference.

### <a name="remarks"></a>Açıklamalar

String_view boşsa bir özel durum oluşturur.

## <a name="basic_string_viewlength"></a><a name="length"></a>basic_string_view:: length

Geçerli öğe sayısını döndürür.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [boyutla](#size)aynıdır.

## <a name="basic_string_viewmax_size"></a><a name="max_size"></a>basic_string_view:: max_size

String_view içerebileceği en fazla karakter sayısını döndürür.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

String_view içerebileceği en fazla karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Bir işlem, uzunluğu daha büyük olan bir string_view üretirse [length_error](../standard-library/length-error-class.md) türünde bir özel durum oluşturulur `max_size()` .

## <a name="basic_string_viewoperator"></a><a name="op_eq"></a>basic_string_view:: operator =

Başka bir string_view string_view veya dönüştürülebilir dize nesnesi atar.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```

### <a name="example"></a>Örnek

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```

## <a name="basic_string_viewoperator"></a><a name="op_at"></a>basic_string_view:: operator []

Belirtilen dizine sahip karaktere bir const_reference sağlar.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Parametreler

*konumu*\
Başvurulacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Parametre dizini tarafından belirtilen konumdaki karaktere const_reference.

### <a name="remarks"></a>Açıklamalar

İlk öğe sıfır dizinine sahiptir ve aşağıdaki öğeler pozitif tamsayılar tarafından ardışık olarak dizinlenir, böylece *n* uzunluğu bir string_view *n-1* sayısı tarafından dizine alınmış bir *n*. öğesi vardır.

`operator[]`, string_view öğelerine okuma erişimi sağlamak için [konumundaki](#at) member işlevinden daha hızlıdır.

`operator[]`bağımsız değişken olarak geçirilen dizinin geçerli olup olmadığını denetlemez. `operator[]`Tanımsız davranışa neden olan geçersiz bir dizin geçirildi.

Temeldeki dize verileri, sahip olan nesne tarafından değiştirilirse veya silinirse, döndürülen başvuru geçersiz kılınabilir.

[ \_ Yineleyici \_ hata ayıklama \_ düzeyiyle](../standard-library/iterator-debug-level.md) derlenirken, 1 veya 2 ' ye ayarlı olduğunda, string_view sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur. Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="basic_string_viewrbegin"></a><a name="rbegin"></a>basic_string_view:: rbegin

Ters çevrilen string_view ilk öğesine bir const yineleyici döndürür.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir string_view ilk öğesine bir rastgele erişim yineleyicisi döndürür ve buna karşılık gelen geri alınamaz string_view son öğe ne olacağını adreslemesini sağlar.

### <a name="remarks"></a>Açıklamalar

`rbegin`, [Başlangıç](#begin) olarak bir string_view ile birlikte kullanılan bir ters string_view ile kullanılır. `rbegin`, bir yinelemeyi geriye doğru başlatmak için kullanılabilir.

## <a name="basic_string_viewremove_prefix"></a><a name="remove_prefix"></a>basic_string_view:: remove_prefix

İşaretçiyi belirtilen sayıda öğe kadar ileri kaydırır.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Açıklamalar

Temel alınan verileri değiştirmeden bırakır. String_view işaretçisini n öğesi tarafından ileri kaydırır ve özel `size` veri üyesini-n olarak ayarlar.

## <a name="basic_string_viewremove_suffix"></a><a name="remove_suffix"></a>basic_string_view:: remove_suffix

Görünümün boyutunu, kayıttan başlayarak belirtilen sayıda öğe kadar azaltır.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Açıklamalar

Temel alınan verileri ve işaretçi değişmeden bırakır. Özel `size` veri üyesini boyut-n olarak ayarlar.

## <a name="basic_string_viewrend"></a><a name="rend"></a>basic_string_view:: rend

Ters çevrilen string_view en son öğeden birini işaret eden bir const yineleyici döndürür.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Ters çevrilen bir string_view en son öğeden birini işaret eden bir const ters rastgele erişim Yineleyici.

### <a name="remarks"></a>Açıklamalar

`rend`, [End](#end) bir string_view ile kullanıldığı gibi ters bir string_view kullanılır. `rend`, ters bir yineleyicinin string_view sonuna kadar ulaştığı konusunda test etmek için kullanılabilir. Tarafından döndürülen değer `rend` başvurulmamalıdır.

## <a name="basic_string_viewrfind"></a><a name="rfind"></a>basic_string_view:: rfind

Belirtilen karakter dizisiyle eşleşen bir alt dize için ters bir string_view arar.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parametreler

*chVal*\
Üye işlevin aranacağı karakter değeri.

*konumu*\
Aramanın başlayacağı dizin.

*kaydetmeye*\
Üye işlevin aranacağı C dizesi.

*biriktirme*\
Üye işlevin aranacağı C dizesindeki ilk karakterden ileri sayım karakter sayısı.

*üstbilgisine*\
Üye işlevin aranacağı string_view.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda alt dizenin ilk karakterinin dizini; Aksi takdirde `npos` .

## <a name="basic_string_viewsize"></a><a name="size"></a>basic_string_view:: size

String_view öğe sayısını döndürür.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

String_view uzunluğu.

### <a name="remarks"></a>Açıklamalar

String_view, ve gibi uzunluğunu değiştirebilir `remove_prefix` `remove_suffix` . Bu, temel alınan dize verilerini değiştirmediğinden, string_view boyutu temeldeki verilerin boyutu değildir.

## <a name="basic_string_viewsubstr"></a><a name="substr"></a>basic_string_view:: substr

Belirtilen konumdan belirtilen sayıda karakteri temsil eden bir string_view döndürür.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Parametreler

*konumu*\
Varsayılan değeri 0 olan, kopyanın oluşturulduğu konumdaki öğeyi bulmak için bir dizin.

*biriktirme*\
Varsa, alt dizeye eklenecek karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Öğelerin belirtilen alt dizisini temsil eden bir string_view nesnesi.

## <a name="basic_string_viewswap"></a><a name="swap"></a>basic_string_view:: swap

Diğer bir deyişle, temel alınan dize verilerine yönelik işaretçileri ve boyut değerlerini iki string_views değiş tokuş eder.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Parametreler

*v*\
İşaretçi ve boyut değerlerini hedef string_view ile değiş tokuş edilecek kaynak string_view.

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
