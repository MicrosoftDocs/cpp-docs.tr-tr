---
title: '&lt;Regex&gt; işlevleri'
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: 47b3ae9d59db7c39d7b9667038d216f24530d5dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369611"
---
# <a name="ltregexgt-functions"></a>&lt;Regex&gt; işlevleri

|||
|-|-|
|[regex_match](#regex_match)|Tüm hedef dizenin bir normal ifade eşleşip eşleşmediğini test eder.|
|[regex_replace](#regex_replace)|Normal ifadeler değiştirir eşleşti.|
|[regex_search](#regex_search)|Bir normal ifade eşleştirmesi arar.|
|[değiştirme](#swap)|İki değiştirir `basic_regex` veya `match_results` nesneleri.|

## <a name="regex_match"></a>  regex_match

Tüm hedef dizenin bir normal ifade eşleşip eşleşmediğini test eder.

```cpp
// (1)
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (2)
template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (3)
template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (4)
template <class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (5)
template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (6)
template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Parametreler

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü. Bu bir ortak durumda `string::const_iterator`, `wstring::const_iterator`, `const char*` veya `const wchar_t*`.

*Ayırma*<br/>
Eşleştirme sonuçları ayırıcı sınıf.

*Elem*<br/>
Eşleşecek öğelerin türü. Sık karşılaşılan bu durumda olan `string`, `wstring`, `char*` veya `wchar_t*`.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

*Alloc2*<br/>
Normal ifade ayırıcı sınıf.

*IOtraits*<br/>
Dize nitelikler sınıfı.

*IOalloc*<br/>
Dize ayırıcı sınıf.

*bayrakları*<br/>
Eşleşme bayrakları.

*ilk*<br/>
Eşleştirilecek sıralı başlangıcı.

*Son*<br/>
Eşleştirilecek sıralı sonu.

*match*<br/>
Eşleştirme sonuçları. Elem türüne karşılık gelen: [smatch](../standard-library/regex-typedefs.md#smatch) için `string`, [wsmatch](../standard-library/regex-typedefs.md#wsmatch) için `wstring`, [cmatch](../standard-library/regex-typedefs.md#cmatch) için `char*` veya [wcmatch](../standard-library/regex-typedefs.md#wcmatch) için `wchar_t*`.

*ptr*<br/>
Eşleştirilecek sıralı başlangıcını işaretçisi. Varsa *ptr* olduğu `char*`, ardından `cmatch` ve `regex`. Varsa *ptr* olduğu `wchar_t*` ardından `wcmatch` ve `wregex`.

*RE*<br/>
Eşleştirilecek normal ifade. Tür `regex` için `string` ve `char*`, veya `wregex` için `wstring` ve `wchar_t*`.

*str*<br/>
Eşleştirilecek dize. Türüne karşılık gelen *Elem*.

### <a name="remarks"></a>Açıklamalar

Her şablon işlevi ise true değerini döndürür ve tüm işlenen sırasının *str* normal ifade bağımsız değişkeni tam olarak eşleşen *re*. Kullanım [regex_search](../standard-library/regex-functions.md#regex_search) bir alt dizesi içinde bir hedef dizisiyle eşleşecek şekilde ve `regex_iterator` birden çok eşleşme bulunamadı. Almayan işlevleri bir `match_results` nesne üyelerini eşleşmenin başarılı olup olmadığını ve bu durumda, çeşitli grupları yakalanan ve normal ifadedeki yakalama yansıtacak şekilde ayarlayın.

Almayan işlevleri bir `match_results` nesne üyelerini eşleşmenin başarılı olup olmadığını ve bu durumda, çeşitli grupları yakalanan ve normal ifadedeki yakalama yansıtacak şekilde ayarlayın.

### <a name="example"></a>Örnek

```cpp
// std__regex__regex_match.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    // (1) with char*
    // Note how const char* requires cmatch and regex
    const char *first = "abc";
    const char *last = first + strlen(first);
    cmatch narrowMatch;
    regex rx("a(b)c");

    bool found = regex_match(first, last, narrowMatch, rx);
    if (found)
        wcout << L"Regex found in abc" << endl;

    // (2) with std::wstring
    // Note how wstring requires wsmatch and wregex.
    // Note use of const iterators cbegin() and cend().
    wstring target(L"Hello");
    wsmatch wideMatch;
    wregex wrx(L"He(l+)o");

    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))
        wcout << L"The matching text is:" << wideMatch.str() << endl;

    // (3) with std::string
    string target2("Drizzle");
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal

    found = regex_match(target2.cbegin(), target2.cend(), rx2);
    if (found)
        wcout << L"Regex found in Drizzle" << endl;

    // (4) with wchar_t*
    const wchar_t* target3 = L"2014-04-02";
    wcmatch wideMatch2;

    // LR"(...)" is a  raw wide-string literal. Open and close parens
    // are delimiters, not string elements.
    wregex wrx2(LR"(\d{4}(-|/)\d{2}(-|/)\d{2})");
    if (regex_match(target3, wideMatch2, wrx2))
    {
        wcout << L"Matching text: " << wideMatch2.str() << endl;
    }

     return 0;
}
```

```Output
Regex found in abc
The matching text is: Hello
Regex found in Drizzle
The matching text is: 2014-04-02
```

## <a name="regex_replace"></a>  regex_replace

Normal ifadeler değiştirir eşleşti.

```cpp
template <class OutIt, class BidIt, class RXtraits, class Alloc, class Elem>
OutIt regex_replace(
    OutIt out,
    BidIt first,
    BidIt last,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);

template <class RXtraits, class Alloc, class Elem>
basic_string<Elem> regex_replace(
    const basic_string<Elem>& str,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Parametreler

*OutIt*<br/>
Değişiklik yineleyici türü.

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

*Ayırma*<br/>
Normal ifade ayırıcı sınıf.

*Elem*<br/>
Eşleşecek öğelerin türü.

*bayrakları*<br/>
Eşleşme bayrakları.

*ilk*<br/>
Eşleştirilecek sıralı başlangıcı.

*FMT*<br/>
Değişiklik biçimi.

*Son*<br/>
Eşleştirilecek sıralı sonu.

*out*<br/>
Çıkış yineleyici.

*RE*<br/>
Eşleştirilecek normal ifade.

*str*<br/>
Eşleştirilecek dize.

### <a name="remarks"></a>Açıklamalar

İlk işlev oluşturur bir [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) nesne `iter(first, last, re, flags)` ve kendi giriş aralığındaki bölmek için kullandığı `[first, last)` sıraları bir dizi `T0 M0 T1 M1...TN-1 MN-1 TN`burada `Mn` n. eşleşme tarafından algılanan Yineleyici. Herhangi bir eşleşme bulunursa `T0` tüm giriş aralığı ve `N` sıfırdır. Varsa `(flags & format_first_only) != 0` yalnızca ilk eşleşme kullanıldığında, `T1` tüm eşleştirmeden giriş metni ve `N` 1'dir. Her `i` aralığında `[0, N)`, `(flags & format_no_copy) == 0` aralığında metin kopyalar `Ti` yineleyiciye *kullanıma*. Ardından `m.format(out, fmt, flags)`burada `m` olduğu `match_results` yineleyici nesnesi tarafından döndürülen nesne `iter` alt diziyi için `Mi`. Son olarak, `(flags & format_no_copy) == 0` aralığında metin kopyalar `TN` yineleyiciye *kullanıma*. İşlev döndürür *kullanıma*.

İkinci işlev yerel bir değişken oluşturur `result` türü `basic_string<charT>` ve çağrıları `regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)`. Döndürür `result`.

### <a name="example"></a>Örnek

```cpp
// std__regex__regex_replace.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    char buf[20];
    const char *first = "axayaz";
    const char *last = first + strlen(first);
    std::regex rx("a");
    std::string fmt("A");
    std::regex_constants::match_flag_type fonly =
        std::regex_constants::format_first_only;

    *std::regex_replace(&buf[0], first, last, rx, fmt) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    *std::regex_replace(&buf[0], first, last, rx, fmt, fonly) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    std::string str("adaeaf");
    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt) << std::endl;

    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt, fonly) << std::endl;

    return (0);
}
```

```Output
replacement == AxAyAz
replacement == Axayaz
replacement == AdAeAf
replacement == Adaeaf
```

## <a name="regex_search"></a>  regex_search

Bir normal ifade eşleştirmesi arar.

```cpp
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Parametreler

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü.

*Ayırma*<br/>
Eşleştirme sonuçları ayırıcı sınıf.

*Elem*<br/>
Eşleşecek öğelerin türü.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

*Alloc2*<br/>
Normal ifade ayırıcı sınıf.

*IOtraits*<br/>
Dize nitelikler sınıfı.

*IOalloc*<br/>
Dize ayırıcı sınıf.

*bayrakları*<br/>
Eşleşme bayrakları.

*ilk*<br/>
Eşleştirilecek sıralı başlangıcı.

*Son*<br/>
Eşleştirilecek sıralı sonu.

*match*<br/>
Eşleştirme sonuçları.

*ptr*<br/>
Eşleştirilecek sıralı başlangıcını işaretçisi.

*RE*<br/>
Eşleştirilecek normal ifade.

*str*<br/>
Eşleştirilecek dize.

### <a name="remarks"></a>Açıklamalar

Her şablon işlevi yalnızca bir arama, normal ifade bağımsız değişkeni için true döndürür *re* kendi işlenen dizisi başarılı olur. Almayan işlevleri bir `match_results` nesne üyelerini arama başarılı olup olmadığını ve bu durumda, çeşitli grupları yakalanan ve normal ifadedeki yakalama yansıtacak şekilde ayarlayın.

### <a name="example"></a>Örnek

```cpp
// std__regex__regex_search.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    const char *first = "abcd";
    const char *last = first + strlen(first);
    std::cmatch mr;
    std::regex rx("abc");
    std::regex_constants::match_flag_type fl =
        std::regex_constants::match_default;

    std::cout << "search(f, f+1, \"abc\") == " << std::boolalpha
        << regex_search(first, first + 1, rx, fl) << std::endl;

    std::cout << "search(f, l, \"abc\") == " << std::boolalpha
        << regex_search(first, last, mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(\"a\", \"abc\") == " << std::boolalpha
        << regex_search("a", rx) << std::endl;

    std::cout << "search(\"xabcd\", \"abc\") == " << std::boolalpha
        << regex_search("xabcd", mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(std::string("a"), rx) << std::endl;

    std::string str("abcabc");
    std::match_results<std::string::const_iterator> mr2;
    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(str, mr2, rx) << std::endl;
    std::cout << "  matched: \"" << mr2.str() << "\"" << std::endl;

    return (0);
}
```

```Output
search(f, f+1, "abc") == false
search(f, l, "abc") == true
  matched: "abc"
search("a", "abc") == false
search("xabcd", "abc") == true
  matched: "abc"
search(string, "abc") == false
search(string, "abc") == true
  matched: "abc"
```

## <a name="swap"></a>  değiştirme

İki değiştirir `basic_regex` veya `match_results` nesneleri.

```cpp
template <class Elem, class RXtraits>
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,
    basic_regex<Elem, RXtraits>& right) noexcept;

template <class Elem, class IOtraits, class BidIt, class Alloc>
void swap(
    match_results<BidIt, Alloc>& left,
    match_results<BidIt, Alloc>& right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Eşleşecek öğelerin türü.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri, Sabit sürede ilgili kendi bir bağımsız değişken içeriğini değiştirme ve özel durum oluşturması beklenmiyor.

### <a name="example"></a>Örnek

```cpp
// std__regex__swap.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx0("c(a*)|(b)");
    std::regex rx1;
    std::cmatch mr0;
    std::cmatch mr1;

    swap(rx0, rx1);
    std::regex_search("xcaaay", mr1, rx1);
    swap(mr0, mr1);

    std::csub_match sub = mr0[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;
    std::cout << "string == " << sub << std::endl;

    return (0);
}
```

```Output
matched == true
length == 3
string == aaa
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
