---
description: 'Hakkında daha fazla bilgi edinin: basic_regex sınıfı'
title: basic_regex Sınıfı
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 450f3945faeb088c975bb1657d69496bcf078ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325632"
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

*Rxnitelikler*\
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, normal bir ifadeyi tutan bir nesneyi tanımlar. Bu sınıf şablonunun nesneleri, normal ifadeyle eşleşen metni aramak için uygun metin dizesi bağımsız değişkenleriyle birlikte [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)ve [regex_replace](../standard-library/regex-functions.md#regex_replace)şablon işlevlerine geçirilebilir. Bu sınıf şablonunun iki uzmanlığını vardır; tür tanımları, türü öğeler için [Regex](../standard-library/regex-typedefs.md#regex) **`char`** , ve türündeki öğeler için de [wregex](../standard-library/regex-typedefs.md#wregex) **`wchar_t`** .

*Rxnitelikler* şablon bağımsız değişkeni, sınıf şablonunun desteklediği normal ifadelerin sözdiziminin çeşitli önemli özelliklerini açıklar. Bu normal ifade niteliklerini belirten bir sınıf, [regex_traits Class](../standard-library/regex-traits-class.md)türünde bir nesne ile aynı dış arabirime sahip olmalıdır.

Bazı işlevler, normal bir ifade tanımlayan bir bir işlenen dizisi alır. Böyle bir işleç sırasını birkaç şekilde belirtebilirsiniz:

`ptr`--  **`char`** `ptr` öğesinden başlayan (bir boş işaretçi olmaması gereken), `value_type()` null ile sonlandırılmış bir sıra (bir ' on ' türü için bir C dizesi).

`ptr`, `count` --öğesinden başlayan bir `count` öğe dizisi `ptr` (null işaretçi olmamalıdır)

`str`--nesne tarafından belirtilen sıra `basic_string``str`

`first`, `last` --yineleyiciler `first` ve Aralık içinde ayrılmış bir öğe dizisi `last``[first, last)`

`right` -- `basic_regex` nesne `right`

Bu üye işlevleri `flags` , *rxnitelikler* türü tarafından açıklananlara ek olarak normal ifade yorumu için çeşitli seçenekleri belirten bir bağımsız değişken alır.

### <a name="members"></a>Üyeler

|Üye|Varsayılan değer|
|-|-|
|ortak statik const flag_type icase|regex_constants:: icase|
|ortak statik const flag_type NoSubs|regex_constants:: NoSubs|
|ortak statik const flag_type optimize|regex_constants:: optimize et|
|ortak statik const flag_type harmanlama|regex_constants:: COLLATE|
|ortak statik const flag_type ECMAScript|regex_constants:: ECMAScript|
|ortak statik const flag_type temel|regex_constants:: temel|
|ortak statik const flag_type genişletilmiş|regex_constants:: Extended|
|ortak statik const flag_type awk|regex_constants:: awk|
|ortak statik const flag_type grep|regex_constants:: grep|
|ortak statik const flag_type egrep|regex_constants:: egrep|
|Özel Rxnitelikler nitelikleri||

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_regex](#basic_regex)|Normal ifade nesnesi oluşturun.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[flag_type](#flag_type)|Sözdizimi seçenek bayraklarının türü.|
|[locale_type](#locale_type)|Depolanan yerel ayar nesnesinin türü.|
|[value_type](#value_type)|Öğe türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[assign (atamak)](#assign) |Normal ifade nesnesine bir değer atar.|
|[bayraklar](#flags)|Sözdizimi seçenek bayraklarını döndürür.|
|[getloc](#getloc)|Depolanan yerel ayar nesnesini döndürür.|
|[imbue](#imbue)|Depolanan yerel ayar nesnesini değiştirir.|
|[mark_count](#mark_count)|Eşleşen alt ifade sayısını döndürür.|
|[Kur](#swap)|İki normal ifade nesnesini değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Normal ifade nesnesine bir değer atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<regex>

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

## <a name="basic_regexassign"></a><a name="assign"></a> basic_regex:: Assign

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

*Stnitelikler*\
Dize kaynağı için nitelikler sınıfı.

*Stayırma*\
Bir dize kaynağı için ayırıcı sınıfı.

*Dengeleyici*\
Bir Aralık kaynağı için giriş Yineleyici türü.

*Right*\
Kopyalanacak Regex kaynağı.

*kaydetmeye*\
Kopyalanacak dizinin başlangıcına yönelik işaretçi.

*larına*\
Kopyalama sırasında eklenecek sözdizimi seçeneği bayrakları.

*Len/TD>*\
Kopyalanacak sıranın uzunluğu.

*üstbilgisine*\
Kopyalanacak dize.

*adı*\
Kopyalanacak sıra başlangıcı.

*soyadına*\
Kopyalanacak sıra sonu.

*IList*\
Kopyalanacak initializer_list.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerinin her biri tarafından tarafından tutulan normal ifade, **`*this`** işlenen sırası tarafından tanımlanan normal ifadeyle değiştirilir ve ardından döndürülür **`*this`** .

## <a name="basic_regexbasic_regex"></a><a name="basic_regex"></a> basic_regex:: basic_regex

Normal ifade nesnesi oluşturun.

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

*Stnitelikler*\
Dize kaynağı için nitelikler sınıfı.

*Stayırma*\
Bir dize kaynağı için ayırıcı sınıfı.

*Dengeleyici*\
Bir Aralık kaynağı için giriş Yineleyici türü.

*Right*\
Kopyalanacak Regex kaynağı.

*kaydetmeye*\
Kopyalanacak dizinin başlangıcına yönelik işaretçi.

*larına*\
Kopyalama sırasında eklenecek sözdizimi seçeneği bayrakları.

*Len/TD>*\
Kopyalanacak sıranın uzunluğu.

*üstbilgisine*\
Kopyalanacak dize.

*adı*\
Kopyalanacak sıra başlangıcı.

*soyadına*\
Kopyalanacak sıra sonu.

*IList*\
Kopyalanacak initializer_list.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular, türünde varsayılan olarak oluşturulmuş bir nesne depolar `RXtraits` .

İlk Oluşturucu boş bir nesne oluşturur `basic_regex` . Diğer oluşturucular, `basic_regex` işlenen sırası tarafından tanımlanan normal ifadeyi tutan bir nesnesi oluşturur.

Boş bir `basic_regex` nesne [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)veya [regex_replace](../standard-library/regex-functions.md#regex_replace)geçirildiğinde hiçbir karakter dizisiyle eşleşmez.

## <a name="basic_regexflag_type"></a><a name="flag_type"></a> basic_regex:: flag_type

Sözdizimi seçenek bayraklarının türü.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, [regex_constants:: syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type)için bir eş anlamlı.

## <a name="basic_regexflags"></a><a name="flags"></a> basic_regex:: Flags

Sözdizimi seçenek bayraklarını döndürür.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `flag_type` en son çağrıya geçirilen bağımsız değişkenin değerini döndürür [basic_regex::](#assign) üye işlevlerini atama işlevleri veya böyle bir çağrı yapılmezse, oluşturucuya geçirilen değer.

## <a name="basic_regexgetloc"></a><a name="getloc"></a> basic_regex:: getloc

Depolanan yerel ayar nesnesini döndürür.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `traits.` [regex_traits:: getloc](../standard-library/regex-traits-class.md#getloc)döndürür `()` .

## <a name="basic_regeximbue"></a><a name="imbue"></a> basic_regex:: imbue

Depolanan yerel ayar nesnesini değiştirir.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametreler

*çerçeve*\
Depolanacak yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, **`*this`** `traits.` [regex_traits:: imbue](../standard-library/regex-traits-class.md#imbue)öğesini boşaltır ve döndürür `(loc)` .

## <a name="basic_regexlocale_type"></a><a name="locale_type"></a> basic_regex:: locale_type

Depolanan yerel ayar nesnesinin türü.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, [regex_traits:: locale_type](../standard-library/regex-traits-class.md#locale_type)için bir eş anlamlı.

## <a name="basic_regexmark_count"></a><a name="mark_count"></a> basic_regex:: mark_count

Eşleşen alt ifade sayısını döndürür.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Normal ifadedeki yakalama gruplarının sayısını döndürür.

## <a name="basic_regexoperator"></a><a name="op_eq"></a> basic_regex:: operator =

Normal ifade nesnesine bir değer atar.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Parametreler

*Stnitelikler*\
Dize kaynağı için nitelikler sınıfı.

*Stayırma*\
Bir dize kaynağı için ayırıcı sınıfı.

*Right*\
Kopyalanacak Regex kaynağı.

*üstbilgisine*\
Kopyalanacak dize.

### <a name="remarks"></a>Açıklamalar

İşleçler her biri tarafından tarafından tutulan normal ifade, **`*this`** işlenen sırası tarafından tanımlanan normal ifadeyle değiştirilir ve ardından döndürülür **`*this`** .

## <a name="basic_regexswap"></a><a name="swap"></a> basic_regex:: swap

İki normal ifade nesnesini değiştirir.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Parametreler

*Right*\
İle takas edilecek normal ifade nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, ve sağ arasındaki normal ifadeleri **`*this`** değiştirir . Bu, sabit zamanlı olarak yapar ve özel durum oluşturmaz.

## <a name="basic_regexvalue_type"></a><a name="value_type"></a> basic_regex:: value_type

Öğe türü.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *Eled* şablon parametresinin bir eş anlamlısıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_match](../standard-library/regex-functions.md#regex_match)\
[regex_search](../standard-library/regex-functions.md#regex_search)\
[regex_replace](../standard-library/regex-functions.md#regex_replace)\
[Regex](../standard-library/regex-typedefs.md#regex)\
[wregex](../standard-library/regex-typedefs.md#wregex)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)
