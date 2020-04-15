---
title: '&lt;regex&gt; fonksiyonları'
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
ms.openlocfilehash: ff6ea37208aef19431bf7aefe612dccd589c638b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374539"
---
# <a name="ltregexgt-functions"></a>&lt;regex&gt; fonksiyonları

|||
|-|-|
|[regex_match](#regex_match)|Normal bir ifadenin tüm hedef dizeyle eşleşip eşleşmediğini sınar.|
|[regex_replace](#regex_replace)|Eşleşen normal ifadeleri değiştirir.|
|[regex_search](#regex_search)|Normal bir ifade eşleşmesi arar.|
|[Takas](#swap)|İki `basic_regex` veya `match_results` nesne değiştirir.|

## <a name="regex_match"></a><a name="regex_match"></a>regex_match

Normal bir ifadenin tüm hedef dizeyle eşleşip eşleşmediğini sınar.

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

*BidIt*\
Alt eşleşmeler için yineleyici türü. Yaygın durumlar için `string::const_iterator`bu `wstring::const_iterator` `const char*` biri `const wchar_t*`, veya .

*Ayırma*\
Maç sonuçları allocator sınıfı.

*Elem*\
Eşleşecek öğelerin türü. Yaygın durumlar için `string` `wstring`bu `char*` `wchar_t*`, , veya .

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

*Alloc2*\
Normal ifade ayırıcı sınıfı.

*IOtraits*\
Dize özellikleri sınıf.

*IOalloc*\
Dize ayırıcı sınıfı.

*Bayrak*\
Kibrit bayrakları.

*Ilk*\
Eşleşecek sıranın başlangıcı.

*Son*\
Eşleşme sırasının sonu.

*Maç*\
Maç sonuçları. Elem türüne karşılık gelir: `string` [için smatch](../standard-library/regex-typedefs.md#smatch) , `char*` [wsmatch](../standard-library/regex-typedefs.md#wsmatch) için `wstring`, [cmatch](../standard-library/regex-typedefs.md#cmatch) for veya [wcmatch](../standard-library/regex-typedefs.md#wcmatch) için `wchar_t*`.

*Ptr*\
Eşleşecek sıranın başlangıcına işaretçi. *Ptr* ise, `char*`o `cmatch` `regex`zaman kullanın ve . *Ptr* sonra `wchar_t*` kullanmak `wcmatch` `wregex`ve .

*Re*\
Eşleşmek için normal ifade. Için `regex` `string` ve `char*`, `wregex` `wstring` ya `wchar_t*`da için ve .

*Str*\
Dize maç için. *Elem*türüne karşılık gelir.

### <a name="remarks"></a>Açıklamalar

Her şablon işlevi yalnızca tüm operand dizisi *str* tam olarak normal ifade bağımsız *değişkeni re*eşleşirse doğru döndürür. [Hedef](../standard-library/regex-functions.md#regex_search) diziiçindeki bir alt dizeyle `regex_iterator` eşleştirmek ve birden çok eşleşme bulmak için regex_search kullanın. Bir `match_results` nesneyi alan işlevler, üyelerini eşleşmenin başarılı olup olmadığını ve eğer öyleyse normal ifadedeki çeşitli yakalama gruplarının yakalandığını yansıtacak şekilde ayarlar.

Bir `match_results` nesneyi alan işlevler, üyelerini eşleşmenin başarılı olup olmadığını ve eğer öyleyse normal ifadedeki çeşitli yakalama gruplarının yakalandığını yansıtacak şekilde ayarlar.

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

## <a name="regex_replace"></a><a name="regex_replace"></a>regex_replace

Eşleşen normal ifadeleri değiştirir.

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

*OutIt*\
Değiştirmeler için yineleyici türü.

*BidIt*\
Alt eşleşmeler için yineleyici türü.

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

*Ayırma*\
Normal ifade ayırıcı sınıfı.

*Elem*\
Eşleşecek öğelerin türü.

*Bayrak*\
Kibrit bayrakları.

*Ilk*\
Eşleşecek sıranın başlangıcı.

*Fmt*\
Değiştirmeler için biçim.

*Son*\
Eşleşme sırasının sonu.

*çıkış*\
Çıktı yineleyicisi.

*Re*\
Eşleşmek için normal ifade.

*Str*\
Dize maç için.

### <a name="remarks"></a>Açıklamalar

İlk işlev bir [regex_iterator](../standard-library/regex-iterator-class.md) Sınıf `iter(first, last, re, flags)` nesnesi inşa eder `[first, last)` ve giriş aralığını `T0 M0 T1 M1...TN-1 MN-1 TN`bir `Mn` dizi alt diziye bölmek için kullanır , burada yineleyici tarafından algılanan nth eşleşmesi vardır. Eşleşme bulunmazsa, `T0` giriş aralığının tamamı `N` sıfırdır. Yalnızca `(flags & format_first_only) != 0` ilk eşleşme kullanılırsa, `T1` eşleşmeyi izleyen giriş metninin `N` tümü ve 1'dir. Aralıktaki `i` `[0, N)`her biri `(flags & format_no_copy) == 0` için, aralıktaki `Ti` metni yineleyiciye kopyalarsa. *out* Daha sonra `m.format(out, fmt, flags)`çağırır `m` , `match_results` alt dizi `Mi`için yineleyici `iter` nesne tarafından döndürülen nesne nerede. Son olarak, `(flags & format_no_copy) == 0` aralıktaki `TN` metni yineleyiciye kopyalarsa. *out* İşlev *dışarı döner.*

İkinci işlev, yerel bir `result` tür `basic_string<charT>` değişkeni ve çağrıları `regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)`niçin oluşturuyor. Geri `result`dönüyor.

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

## <a name="regex_search"></a><a name="regex_search"></a>regex_search

Normal bir ifade eşleşmesi arar.

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

*BidIt*\
Alt eşleşmeler için yineleyici türü.

*Ayırma*\
Maç sonuçları allocator sınıfı.

*Elem*\
Eşleşecek öğelerin türü.

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

*Alloc2*\
Normal ifade ayırıcı sınıfı.

*IOtraits*\
Dize özellikleri sınıf.

*IOalloc*\
Dize ayırıcı sınıfı.

*Bayrak*\
Kibrit bayrakları.

*Ilk*\
Eşleşecek sıranın başlangıcı.

*Son*\
Eşleşme sırasının sonu.

*Maç*\
Maç sonuçları.

*Ptr*\
Eşleşecek sıranın başlangıcına işaretçi.

*Re*\
Eşleşmek için normal ifade.

*Str*\
Dize maç için.

### <a name="remarks"></a>Açıklamalar

Her şablon işlevi, yalnızca normal ifade bağımsız değişkeni için bir arama nın operand sırasına göre *yeniden* çalışması başarılı olursa doğru döndürür. Bir `match_results` nesneyi alan işlevler, üyelerini aramanın başarılı olup olmadığını ve eğer öyleyse normal ifadedeki çeşitli yakalama gruplarının yakalandığını yansıtacak şekilde ayarlar.

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

## <a name="swap"></a><a name="swap"></a>Takas

İki `basic_regex` veya `match_results` nesne değiştirir.

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

*Elem*\
Eşleşecek öğelerin türü.

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri, ilgili bağımsız değişkenlerinin içeriğini sürekli olarak değiştirir ve özel durumlar oluşturmaz.

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

[\<regex>](../standard-library/regex.md)\
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)\
[regex_error Sınıfı](../standard-library/regex-error-class.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
