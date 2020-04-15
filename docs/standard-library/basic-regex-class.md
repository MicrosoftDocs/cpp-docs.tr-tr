---
title: basic_regex Sınıfı
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 74a8684c619e2cfbd5417950aa6108ad93511bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376757"
---
# <a name="basic_regex-class"></a>basic_regex Sınıfı

Normal bir ifadeyi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>Parametreler

*Elem*\
Eşleşecek öğelerin türü.

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, normal bir ifade tutan bir nesneyi açıklar. Bu sınıf şablonundaki nesneler, normal ifadeyle eşleşen metni aramak için uygun metin dize bağımsız değişkenleri ile birlikte [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)ve [regex_replace](../standard-library/regex-functions.md#regex_replace)şablon işlevlerine geçirilebilir. Bu sınıf şablonunun iki uzmanlık vardır, **türü**tanımları char elemanları için [regex](../standard-library/regex-typedefs.md#regex) , ve tip **wchar_t**elemanları için [wregex](../standard-library/regex-typedefs.md#wregex) .

Şablon bağımsız *değişkeni RXtraits* sınıf şablonu desteklediği normal ifadelerin sözdizimi çeşitli önemli özelliklerini açıklar. Bu normal ifade özelliklerini belirten bir [sınıf, sınıf regex_traits](../standard-library/regex-traits-class.md)türündeki bir nesneyle aynı dış arabirime sahip olmalıdır.

Bazı işlevler, normal bir ifade tanımlayan bir bir işlenen dizisi alır. Böyle bir işleç sırasını birkaç şekilde belirtebilirsiniz:

`ptr`-- sonlandırıcı öğenin değer `value_type()` olduğu ve operand dizisinin bir `ptr` parçası olmadığı (null işaretçi olmamalıdır) başlangıç (bir null-sonlanmış dizi, tür **char** *Elem* için C dizesi gibi)

`ptr`, `count` -- başlayan `count` bir `ptr` öğe dizisi (null işaretçi olmamalıdır)

`str`-- `basic_string` nesne tarafından belirtilen sıra`str`

`first`, `last` -- yineleyiciler `first` tarafından sınırlandırılmış bir `last`element dizisi ve , aralığında`[first, last)`

`right`-- `basic_regex` nesne`right`

Bu üye işlevler, `flags` *RXtraits* türü tarafından açıklananlara ek olarak normal ifadenin yorumlanması için çeşitli seçenekler belirten bir bağımsız değişken de alır.

### <a name="members"></a>Üyeler

|Üye|Varsayılan Değer|
|-|-|
|kamu statik const flag_type icase|regex_constants::icase|
|kamu statik const flag_type nosubs|regex_constants::nosubs|
|kamu statik const flag_type optimize|regex_constants::optimize|
|kamu statik const flag_type harmanlama|regex_constants::harman|
|ecmaScript flag_type kamu statik const|regex_constants::ECMAScript|
|kamu statik const flag_type temel|regex_constants::temel|
|kamu statik const flag_type genişletilmiş|regex_constants::genişletilmiş|
|kamu statik const flag_type awk|regex_constants::awk|
|kamu statik const flag_type grep|regex_constants::grep|
|kamu statik const flag_type egrep|regex_constants::egrep|
|özel RXtraits özellikleri||

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_regex](#basic_regex)|Normal ifade nesnesini oluştur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[flag_type](#flag_type)|Sözdizimi seçeneği bayraklarıtürü.|
|[locale_type](#locale_type)|Depolanan yerel nesnenin türü.|
|[value_type](#value_type)|Öğe türü.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Atamak](#assign)|Normal ifade nesnesine bir değer atar.|
|[bayraklar](#flags)|Sözdizimi seçeneği bayraklarını döndürür.|
|[getloc](#getloc)|Depolanan yerel nesneyi döndürür.|
|[imbue](#imbue)|Depolanan yerel nesneyi değiştirir.|
|[mark_count](#mark_count)|Eşleşen alt ifade sayısını döndürür.|
|[Takas](#swap)|İki normal ifade nesnesi değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Normal ifade nesnesine bir değer atar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

**Ad alanı:** std

## <a name="example"></a>Örnek

```cpp
// std__regex__basic_regex.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    regex::value_type elem = 'x';
    regex::flag_type flag = regex::grep;

    elem = elem;  // to quiet "unused" warnings
    flag = flag;

    // constructors
    regex rx0;
    cout << "match(\"abc\", \"\") == " << boolalpha
        << regex_match("abc", rx0) << endl;

    regex rx1("abcd", regex::ECMAScript);
    cout << "match(\"abc\", \"abcd\") == " << boolalpha
        << regex_match("abc", rx1) << endl;

    regex rx2("abcd", 3);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx2) << endl;

    regex rx3(rx2);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx3) << endl;

    string str("abcd");
    regex rx4(str);
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx4) << endl;

    regex rx5(str.begin(), str.end() - 1);
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx5) << endl;
    cout << endl;

    // assignments
    rx0 = "abc";
    rx0 = rx1;
    rx0 = str;

    rx0.assign("abcd", regex::ECMAScript);
    rx0.assign("abcd", 3);
    rx0.assign(rx1);
    rx0.assign(str);
    rx0.assign(str.begin(), str.end() - 1);

    rx0.swap(rx1);

    // mark_count
    cout << "\"abc\" mark_count == "
        << regex("abc").mark_count() << endl;
    cout << "\"(abc)\" mark_count == "
        << regex("(abc)").mark_count() << endl;

    // locales
    regex::locale_type loc = rx0.imbue(locale());
    cout << "getloc == imbued == " << boolalpha
        << (loc == rx0.getloc()) << endl;

    // initializer_list
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);
    cout << "match(\"abc\") == " << boolalpha
        << regex_match("abc", rx6);
    cout << endl;
}
```

```Output
match("abc", "") == false
match("abc", "abcd") == false
match("abc", "abc") == true
match("abc", "abc") == true
match(string("abcd"), "abc") == false
match(string("abc"), "abc") == true

"abc" mark_count == 0
"(abc)" mark_count == 1
getloc == imbued == true
match("abc") == true
```

## <a name="basic_regexassign"></a><a name="assign"></a>basic_regex::atama

Normal ifade nesnesine bir değer atar.

```cpp
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,
    size_type len,
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags = ECMAScript);

template <class InIt>
basic_regex& assign(
    InIt first, InIt last,
    flag_type flags = ECMAScript);
```

### <a name="parameters"></a>Parametreler

*STtraits*\
Bir dize kaynağı için özellikler sınıfı.

*STalloc*\
Bir dize kaynağı için ayırıcı sınıf.

*ınit*\
Bir aralık kaynağı için giriş yineleyici türü.

*Doğru*\
Regex kaynak kopyalamak için.

*Ptr*\
Kopyalama sırasının başına işaretçi.

*Bayrak*\
Sözdizimi seçeneği, kopyalama sırasında eklenecek bayraklar.

*len/TD>*\
Kopyaya sıranın uzunluğu.

*Str*\
Kopyalamak için dize.

*Ilk*\
Kopyalama sırasının başlangıcı.

*Son*\
Kopyalama sırasının sonu.

*ılist*\
Kopyalama initializer_list.

### <a name="remarks"></a>Açıklamalar

Üye işlevleriher operand dizisi `*this` tarafından açıklanan normal ifade ile düzenlenen düzenli `*this`ifade yerine, sonra döndürün.

## <a name="basic_regexbasic_regex"></a><a name="basic_regex"></a>basic_regex:basic_regex

Normal ifade nesnesini oluştur.

```cpp
basic_regex();

explicit basic_regex(
    const Elem* ptr,
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,
    size_type len,
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,
    flag_type flags);

template <class STtraits, class STalloc>
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags);

template <class InIt>
explicit basic_regex(
    InIt first,
    InIt last,
    flag_type flags);
```

### <a name="parameters"></a>Parametreler

*STtraits*\
Bir dize kaynağı için özellikler sınıfı.

*STalloc*\
Bir dize kaynağı için ayırıcı sınıf.

*ınit*\
Bir aralık kaynağı için giriş yineleyici türü.

*Doğru*\
Regex kaynak kopyalamak için.

*Ptr*\
Kopyalama sırasının başına işaretçi.

*Bayrak*\
Sözdizimi seçeneği, kopyalama sırasında eklenecek bayraklar.

*len/TD>*\
Kopyaya sıranın uzunluğu.

*Str*\
Kopyalamak için dize.

*Ilk*\
Kopyalama sırasının başlangıcı.

*Son*\
Kopyalama sırasının sonu.

*ılist*\
Kopyalama initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm kurucular varsayılan olarak oluşturulmuş bir `RXtraits`türü nesnesi depolar.

İlk oluşturucu boş `basic_regex` bir nesne inşa eder. Diğer kurucular, operand dizisi tarafından açıklanan normal ifadeyi tutan bir `basic_regex` nesne inşa eder.

Boş `basic_regex` bir [nesne, regex_match,](../standard-library/regex-functions.md#regex_match) [regex_search](../standard-library/regex-functions.md#regex_search)veya [regex_replace'](../standard-library/regex-functions.md#regex_replace)ye geçirildiğinde herhangi bir karakter dizisiyle eşleşmez.

## <a name="basic_regexflag_type"></a><a name="flag_type"></a>basic_regex:flag_type

Sözdizimi seçeneği bayraklarıtürü.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Açıklamalar

Türü regex_constants için [eşanlamlıdır::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

## <a name="basic_regexflags"></a><a name="flags"></a>basic_regex::bayraklar

Sözdizimi seçeneği bayraklarını döndürür.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, en son `flag_type` çağrıya aktarılan bağımsız değişkenin değerini basic_regex birine döndürür::üye işlevleri [ataveya](#assign) böyle bir çağrı yapılmamışsa, oluşturucuya geçirilen değeri.

## <a name="basic_regexgetloc"></a><a name="getloc"></a>basic_regex::getloc

Depolanan yerel nesneyi döndürür.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev `traits.`regex_traits döndürür::getloc [regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()`.

## <a name="basic_regeximbue"></a><a name="imbue"></a>basic_regex::imbue

Depolanan yerel nesneyi değiştirir.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametreler

*Loc*\
Depolamak için yerel nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `*this` boşaltır `traits.`ve regex_traits döndürür::imbue [regex_traits::imbue](../standard-library/regex-traits-class.md#imbue)`(loc)`.

## <a name="basic_regexlocale_type"></a><a name="locale_type"></a>basic_regex:locale_type

Depolanan yerel nesnenin türü.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Açıklamalar

Türü regex_traits için [eşanlamlıdır::locale_type](../standard-library/regex-traits-class.md#locale_type).

## <a name="basic_regexmark_count"></a><a name="mark_count"></a>basic_regex::mark_count

Eşleşen alt ifade sayısını döndürür.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, normal ifadedeki yakalama gruplarının sayısını döndürür.

## <a name="basic_regexoperator"></a><a name="op_eq"></a>basic_regex::operator=

Normal ifade nesnesine bir değer atar.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Parametreler

*STtraits*\
Bir dize kaynağı için özellikler sınıfı.

*STalloc*\
Bir dize kaynağı için ayırıcı sınıf.

*Doğru*\
Regex kaynak kopyalamak için.

*Str*\
Kopyalamak için dize.

### <a name="remarks"></a>Açıklamalar

İşleçlerin her biri, `*this` operand dizisi tarafından açıklanan normal ifade `*this`ile tutulan normal ifadeyi değiştirir, sonra geri döner.

## <a name="basic_regexswap"></a><a name="swap"></a>basic_regex::takas

İki normal ifade nesnesi değiştirir.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Normal ifade nesnesi ile takas etmek.

### <a name="remarks"></a>Açıklamalar

Üye işlev, normal ifadeleri sağ `*this` ve *arasındaki*ifadeleri değiştirir. Bunu sürekli zaman içinde yapar ve hiçbir istisna atar.

## <a name="basic_regexvalue_type"></a><a name="value_type"></a>basic_regex:value_type

Öğe türü.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *Elem*ile eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_match](../standard-library/regex-functions.md#regex_match)\
[regex_search](../standard-library/regex-functions.md#regex_search)\
[regex_replace](../standard-library/regex-functions.md#regex_replace)\
[Regex](../standard-library/regex-typedefs.md#regex)\
[wregex](../standard-library/regex-typedefs.md#wregex)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)
