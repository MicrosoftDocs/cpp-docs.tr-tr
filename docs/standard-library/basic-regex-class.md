---
title: basic_regex Sınıfı
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: e3a38dc186a52c8431442d58bb10e56837396b07
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565457"
---
# <a name="basicregex-class"></a>basic_regex Sınıfı

Normal bir ifadeyi sarar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>Parametreler

*Elem*<br/>
Eşleşecek öğelerin türü.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, normal bir ifade tutan bir nesneyi tanımlar. Bu şablon sınıfının nesneleri şablon işlevlerine geçirilebilir [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search), ve [regex_replace](../standard-library/regex-functions.md#regex_replace), birlikte uygun metin dizesi bağımsız değişkenleri normal ifadeyle eşleşen metni aramak için kullanılır. Tür tanımları içeren bu şablon sınıfının iki uzmanlıklar vardır [regex](../standard-library/regex-typedefs.md#regex) türü öğeler için **char**, ve [wchar_t](../standard-library/regex-typedefs.md#wregex) türü öğeler için  **wchar_t**.

Şablon bağımsız değişkeni *RXtraits* şablon sınıfını destekleyen normal ifadelerin söz diziminin çeşitli önemli özelliklerini açıklar. Bu normal ifade niteliklerini belirten bir sınıfın şablon sınıfının bir nesnesiyle aynı dış arayüze sahip olması gerekir [regex_traits sınıfı](../standard-library/regex-traits-class.md).

Bazı işlevler, normal bir ifade tanımlayan bir bir işlenen dizisi alır. Böyle bir işleç sırasını birkaç şekilde belirtebilirsiniz:

`ptr` --null ile sonlandırılmış bir sıra (C dizesi gibi için *Elem* türü **char**) konumunda başlayan `ptr` (olduğu bir null işaretçi olmamalıdır), burada sonlandıran öğe, değer `value_type()` ve işlenen sırasının parçası değildir

`ptr`, `count` --bir dizi `count` konumunda başlayan öğeleri `ptr` (olmamalıdır bir null işaretçi)

`str` --tarafından belirtilen dizi `basic_string` nesnesi `str`

`first`, `last` --yineleyicileri tarafından sınırlanan öğelerin bir dizisi `first` ve `last`, aralıktaki `[first, last)`

`right` -- `basic_regex` nesnesi `right`

Bu üye işlevleri bağımsız değişken da göz önüne `flags` tarafından tanımlananlara ek olarak normal ifadenin yorumu için çeşitli seçenekler belirten *RXtraits* türü.

### <a name="members"></a>Üyeler

|Üye|Varsayılan Değer|
|-|-|
|Genel statik const flag_type icase|regex_constants::icase|
|Genel statik const flag_type nosubs|regex_constants::nosubs|
|Genel statik const flag_type en iyi duruma getirme|regex_constants::optimize|
|Genel statik const flag_type collate|regex_constants::COLLATE|
|Genel statik const flag_type ECMAScript|regex_constants::ECMAScript|
|Genel statik const flag_type temel|regex_constants::Basic|
|Genel statik const flag_type genişletilmiş|regex_constants::Extended|
|Genel statik const flag_type awk|regex_constants::awk|
|Genel statik const flag_type grep|regex_constants::GREP|
|Genel statik const flag_type egrep|regex_constants::egrep|
|Özel RXtraits nitelikler||

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_regex](#basic_regex)|Normal ifade nesnesi oluşturun.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[flag_type](#flag_type)|Söz dizimi seçeneği bayrakları türü.|
|[locale_type](#locale_type)|Depolanan yerel ayar nesnesi türü.|
|[value_type](#value_type)|Öğe türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Bir değeri normal ifade nesnesine atar.|
|[bayrakları](#flags)|Söz dizimi seçeneği bayrakları döndürür.|
|[getloc](#getloc)|Depolanan yerel ayar nesnesi döndürür.|
|[imbue](#imbue)|Depolanan yerel ayar nesnesini değiştirir.|
|[mark_count](#mark_count)|Eşleşen alt ifadeler sayısını döndürür.|
|[değiştirme](#swap)|İki normal ifade nesneleri değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bir değeri normal ifade nesnesine atar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

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

## <a name="assign"></a>  basic_regex::Assign

Bir değeri normal ifade nesnesine atar.

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

*STtraits*<br/>
Bir dize kaynağı için nitelikler sınıfı.

*STalloc*<br/>
Bir dize kaynağı için ayırıcı sınıf.

*InIt*<br/>
Bir aralık kaynağı için giriş yineleyici türü.

*sağ*<br/>
Kopyalamak için Regex kaynağı.

*ptr*<br/>
Başlangıç dizisi kopyalamak için işaretçi.

*bayrakları*<br/>
Kopyalanırken eklemek için söz dizimi seçeneği bayraklar.

*Len/TD >*<br/>
Kopyalanacak sırası uzunluğu.

*str*<br/>
Kopyalamak için dize.

*ilk*<br/>
Kopyalamak için bir dizi başlangıcı.

*Son*<br/>
Son sırasının kopyalamak için.

*IList*<br/>
Kopyalanacağı initializer_list.

### <a name="remarks"></a>Açıklamalar

Her üye işlevleri tarafından tutulan bir normal ifade değiştirin `*this` ve işlenen sırasının tarafından tanımlanan normal ifade ile çıkacak `*this`.

## <a name="basic_regex"></a>  basic_regex::basic_regex

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

*STtraits*<br/>
Bir dize kaynağı için nitelikler sınıfı.

*STalloc*<br/>
Bir dize kaynağı için ayırıcı sınıf.

*InIt*<br/>
Bir aralık kaynağı için giriş yineleyici türü.

*sağ*<br/>
Kopyalamak için Regex kaynağı.

*ptr*<br/>
Başlangıç dizisi kopyalamak için işaretçi.

*bayrakları*<br/>
Kopyalanırken eklemek için söz dizimi seçeneği bayraklar.

*Len/TD >*<br/>
Kopyalanacak sırası uzunluğu.

*str*<br/>
Kopyalamak için dize.

*ilk*<br/>
Kopyalamak için bir dizi başlangıcı.

*Son*<br/>
Son sırasının kopyalamak için.

*IList*<br/>
Kopyalanacağı initializer_list.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak oluşturulmuş bir nesne türünün tüm oluşturucular depolamak `RXtraits`.

İlk Oluşturucu boş bir yapıları `basic_regex` nesne. Diğer oluşturucular oluşturmak bir `basic_regex` ve işlenen sırasının tarafından açıklanan normal bir ifade tutan nesne.

Boş bir `basic_regex` nesne için geçirildiğinde karakter dizisi eşleşmiyor [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search), veya [regex_replace](../standard-library/regex-functions.md#regex_replace).

## <a name="flag_type"></a>  basic_regex::flag_type

Söz dizimi seçeneği bayrakları türü.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

## <a name="flags"></a>  basic_regex::Flags

Söz dizimi seçeneği bayrakları döndürür.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi değerini döndürür `flag_type` birine en son çağrısına geçirilen bağımsız değişken [basic_regex::assign](#assign) üye işlevleri veya böyle bir çağrı yapıldı, oluşturucuya geçirilen değer.

## <a name="getloc"></a>  basic_regex::getloc

Depolanan yerel ayar nesnesi döndürür.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `traits.` [regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()`.

## <a name="imbue"></a>  basic_regex::imbue

Depolanan yerel ayar nesnesini değiştirir.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametreler

*LOC*<br/>
Saklamak için yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi boşaltır `*this` ve döndürür `traits.` [regex_traits::imbue](../standard-library/regex-traits-class.md#imbue)`(loc)`.

## <a name="locale_type"></a>  basic_regex::locale_type

Depolanan yerel ayar nesnesi türü.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type).

## <a name="mark_count"></a>  basic_regex::mark_count

Eşleşen alt ifadeler sayısını döndürür.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi içindeki bir normal ifade yakalama gruplarının sayısını döndürür.

## <a name="op_eq"></a>  basic_regex::operator =

Bir değeri normal ifade nesnesine atar.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Parametreler

*STtraits*<br/>
Bir dize kaynağı için nitelikler sınıfı.

*STalloc*<br/>
Bir dize kaynağı için ayırıcı sınıf.

*sağ*<br/>
Kopyalamak için Regex kaynağı.

*str*<br/>
Kopyalamak için dize.

### <a name="remarks"></a>Açıklamalar

Her işleçleri tarafından tutulan bir normal ifade değiştirin `*this` ve işlenen sırasının tarafından tanımlanan normal ifade ile çıkacak `*this`.

## <a name="swap"></a>  basic_regex::Swap

İki normal ifade nesneleri değiştirir.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
İle takas için normal ifade nesnesi.

### <a name="remarks"></a>Açıklamalar

Normal ifadeler arasındaki üye işlevi değiştirir `*this` ve *doğru*. Bu sabit sürede yazılabilmesine ve hiçbir özel durum oluşturur.

## <a name="value_type"></a>  basic_regex::value_type

Öğe türü.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *Elem*.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_match](../standard-library/regex-functions.md#regex_match)<br/>
[regex_search](../standard-library/regex-functions.md#regex_search)<br/>
[regex_replace](../standard-library/regex-functions.md#regex_replace)<br/>
[regex](../standard-library/regex-typedefs.md#regex)<br/>
[wchar_t](../standard-library/regex-typedefs.md#wregex)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
