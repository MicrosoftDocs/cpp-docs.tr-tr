---
title: "&lt;Regex&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
dev_langs:
- C++
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: 66ad573f2025301a9ab05e798ba69c2e75a9830a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltregexgt-functions"></a>&lt;Regex&gt; işlevleri
||||  
|-|-|-|  
|[regex_match](#regex_match)|[regex_replace](#regex_replace)|[regex_search](#regex_search)|  
|[Değiştirme](#swap)|  
  
##  <a name="regex_match"></a>  regex_match
 Tüm hedef dize normal bir ifadeyle eşleşen olup olmadığını sınar.  
  
```  
 
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
 `BidIt`  
 Submatches yineleyici türü. Bu string::const_iterator, wstring::const_iterator, const char * veya biri const wchar_t ortak durumda\*.  
  
 `Alloc`  
 Eşleşme sonuçları allocator sınıfı.  
  
 `Elem`  
 Eşleşecek öğelerin türü. Dize, wstring, char * veya wchar_t ortak bu durumda olan\*.  
  
 `RXtraits`  
 Öğeler için nitelikler sınıfı.  
  
 `Alloc2`  
 Normal ifade ayırıcısı sınıfı.  
  
 `IOtraits`  
 String nitelikler sınıfı.  
  
 `IOalloc`  
 Dize allocator sınıfı.  
  
 `flags`  
 Eşleşme bayrakları.  
  
 `first`  
 Eşleştirilecek sıralı başlangıcı.  
  
 `last`  
 Eşleştirilecek sıralı sonu.  
  
 `match`  
 Eşleşme sonuçları. Elem türüne karşılık gelen: [smatch](../standard-library/regex-typedefs.md#smatch) dize, [wsmatch](../standard-library/regex-typedefs.md#wsmatch) wstring için [cmatch](../standard-library/regex-typedefs.md#cmatch) için char * veya [wcmatch](../standard-library/regex-typedefs.md#wcmatch) wchar_tiçin\*.  
  
 `ptr`  
 Eşleştirilecek sıralı başlangıcını işaretçi. PTR char * ise, cmatch ve regex kullanın. PTR wchar_t ise\* wcmatch ve wregex kullanın.  
  
 `re`  
 Eşleştirilecek normal ifade. Tür `regex` dize ve char * veya `wregex` wstring ve wchar_t\*.  
  
 `str`  
 Eşleştirilecek dize. Elem. türüne karşılık gelen  
  
### <a name="remarks"></a>Açıklamalar  
 Her şablon işlevi yalnızca varsa true değerini döndürür tüm işleneni dizisi `str` normal ifade bağımsız değişkeni ile tam olarak `re`. Kullanım [regex_search](../standard-library/regex-functions.md#regex_search) hedef sırasını ve birden çok eşleşme bulmak için regex_iterator içindeki bir alt dizenin eşleşecek şekilde. Almayan işlevleri bir `match_results` nesne üyeleri eşleştirmenin başarılı olup olmadığını ve bu durumda çeşitli gruplar yakalanan normal ifadede yakalama yansıtacak şekilde ayarlayın.  
  
 Almayan işlevleri bir `match_results` nesne üyeleri eşleştirmenin başarılı olup olmadığını ve bu durumda çeşitli gruplar yakalanan normal ifadede yakalama yansıtacak şekilde ayarlayın.  
  
 **(1):**  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include "stdafx.h"  
#include <regex>   
#include <iostream>   
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
  
    // (1) with char*  
    // Note how const char* requires cmatch and regex  
    const char *first = "abc";  
    const char *last = first + strlen(first);  
    cmatch narrowMatch;  
    regex rx("a(b)c");  
  
    bool found = regex_match(first, last, narrowMatch, rx);  
  
    // (1) with std::wstring  
    // Note how wstring requires wsmatch and wregex.  
    // Note use of const iterators cbegin() and cend().  
    wstring target(L"Hello");  
    wsmatch wideMatch;  
    wregex wrx(L"He(l+)o");  
  
    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))  
        wcout << L"The matching text is:" << wideMatch.str() << endl;   
  
    // (2) with std::string  
    string target2("Drizzle");  
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal  
    found = regex_match(target2.cbegin(), target2.cend(), rx2);  
  
    // (3) with wchar_t*  
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
  
##  <a name="regex_replace"></a>  regex_replace
 Normal ifadeler değiştirir eşleşmedi.  
  
```  
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
 `OutIt`  
 Değişiklik yineleyici türü.  
  
 `BidIt`  
 Submatches yineleyici türü.  
  
 `RXtraits`  
 Öğeler için nitelikler sınıfı.  
  
 `Alloc`  
 Normal ifade ayırıcısı sınıfı.  
  
 `Elem`  
 Eşleşecek öğelerin türü.  
  
 `flags`  
 Eşleşme bayrakları.  
  
 `first`  
 Eşleştirilecek sıralı başlangıcı.  
  
 `fmt`  
 Değişiklik biçimi.  
  
 `last`  
 Eşleştirilecek sıralı sonu.  
  
 `out`  
 Çıktı yineleyici.  
  
 `re`  
 Eşleştirilecek normal ifade.  
  
 `str`  
 Eşleştirilecek dize.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işlev oluşturur bir [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) nesne `iter(first, last, re, flags)` ve kendi giriş aralığı ayırmak için kullanır `[first, last)` sıraları bir dizi içine `T0M0T1M1...TN-1MN-1TN`, burada `Mn` olan `nth` Yineleyici tarafından algılanan eşleşir. Herhangi bir eşleşme bulunmazsa, `T0` tüm giriş aralığı ve `N` sıfırdır. Varsa `(flags & format_first_only) != 0` yalnızca ilk eşleşmeye kullanılır, `T1` tüm eşleşme izleyen giriş metni ve `N` 1'dir. Her `i` aralığında `[0, N)`, `(flags & format_no_copy) == 0` aralığında metni kopyalar `Ti` yineleyici için `out`. Daha sonra çağırır `m.format(out, fmt, flags)`, burada `m` olan `match_results` yineleyici nesnesi tarafından döndürülen nesne `iter` değişkene için `Mi`. Son olarak, varsa `(flags & format_no_copy) == 0` aralığında metni kopyalar `TN` yineleyici için `out`. İşlevi döndürür `out`.  
  
 İkinci işlev yerel bir değişken oluşturur `result` türü `basic_string<charT>` ve çağrıları `regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)`. Döndürdüğü `result`.  
  
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
  
##  <a name="regex_search"></a>  regex_search
 Normal ifade eşleştirmesi arar.  
  
```  
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
 `BidIt`  
 Submatches yineleyici türü.  
  
 `Alloc`  
 Eşleşme sonuçları allocator sınıfı.  
  
 `Elem`  
 Eşleşecek öğelerin türü.  
  
 `RXtraits`  
 Öğeler için nitelikler sınıfı.  
  
 `Alloc2`  
 Normal ifade ayırıcısı sınıfı.  
  
 `IOtraits`  
 String nitelikler sınıfı.  
  
 `IOalloc`  
 Dize allocator sınıfı.  
  
 `flags`  
 Eşleşme bayrakları.  
  
 `first`  
 Eşleştirilecek sıralı başlangıcı.  
  
 `last`  
 Eşleştirilecek sıralı sonu.  
  
 `match`  
 Eşleşme sonuçları.  
  
 `ptr`  
 Eşleştirilecek sıralı başlangıcını işaretçi.  
  
 `re`  
 Eşleştirilecek normal ifade.  
  
 `str`  
 Eşleştirilecek dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Her şablon işlevi yalnızca bir arama, normal ifade bağımsız değişkeni için true döndürür `re` kendi işlenen sırası başarılı olur. Almayan işlevleri bir `match_results` nesne üyeleri arama başarılı olup olmadığını ve bu durumda çeşitli gruplar yakalanan normal ifadede yakalama yansıtacak şekilde ayarlayın.  
  
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
  
##  <a name="swap">Değiştirme</a>
 İki basic_regex veya match_results nesneleri değiştirir.  
  
```  
template <class Elem, class RXtraits>  
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,  
    basic_regex<Elem, RXtraits>& right) throw();

template <class Elem, class IOtraits, class BidIt, class Alloc>  
void swap(
    match_results<BidIt, Alloc>& left,  
    match_results<BidIt, Alloc>& right) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `Elem`  
 Eşleşecek öğelerin türü.  
  
 `RXtraits`  
 Öğeler için nitelikler sınıfı.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevleri sabit zamanında ilgili kendi bağımsız değişkenleri içeriğini değiştirme ve özel durumlar oluşturmayın.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
[\<regex>](../standard-library/regex.md)  
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)  
[regex_error Sınıfı](../standard-library/regex-error-class.md)  
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)  
[\<Regex > işleçleri](../standard-library/regex-operators.md)  
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)  
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)  
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)  

