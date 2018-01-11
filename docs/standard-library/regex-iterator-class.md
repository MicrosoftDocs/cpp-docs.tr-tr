---
title: "regex_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
dev_langs: C++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13744086b9e25c5f3be880885fae624822fd5f73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="regexiterator-class"></a>regex_iterator Sınıfı
Eşleşme için yineleyici sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
```
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator {  
public:  
   typedef basic_regex<Elem, RXtraits> regex_type;  
   typedef match_results<BidIt> value_type;  
   typedef std::forward_iterator_tag iterator_category;  
   typedef std::ptrdiff_t difference_type;  
   typedef const match_results<BidIt>* pointer;  
   typedef const match_results<BidIt>& reference;  

   regex_iterator();
   regex_iterator(
      BidIt first, BidIt last, const regex_type& re,  
      regex_constants::match_flag_type f = regex_constants::match_default);

   bool operator==(const regex_iterator& right);
   bool operator!=(const regex_iterator& right);
   const match_results<BidIt>& operator*();
   const match_results<BidIt> * operator->();
   regex_iterator& operator++();
   regex_iterator& operator++(int);

private:
   BidIt begin; // exposition only  
   BidIt end; // exposition only  
   regex_type *pregex;     // exposition only  
   regex_constants::match_flag_type flags; // exposition only  
   match_results<BidIt> match; // exposition only  
   };  
```  
  
### <a name="parameters"></a>Parametreler  
 `BidIt`  
 Submatches yineleyici türü.  
  
 `Elem`  
 Eşleşecek öğelerin türü.  
  
 `RXtraits`  
 Öğeler için nitelikler sınıfı.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı bir sabit iletme yineleyici nesnesi açıklar. Nesne türü ayıklar `match_results<BidIt>` , normal ifade nesnesi art arda uygulayarak `*pregex` yineleyici aralığına göre tanımlanan bir karakter dizisi için `[begin, end)`.  
  
## <a name="examples"></a>Örnekler  
 Normal ifadeler hakkında örnekler için aşağıdaki konulara bakın:  
  
- [regex_match](../standard-library/regex-functions.md#regex_match)  
  
- [regex_replace](../standard-library/regex-functions.md#regex_replace)  
  
- [regex_search](../standard-library/regex-functions.md#regex_search)  
  
- [değiştirme](../standard-library/regex-functions.md#swap)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<regex >  
  
 **Namespace:** std  
  
##  <a name="difference_type"></a>regex_iterator::difference_type  
 Yineleyici fark türü.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `std::ptrdiff_t`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_difference_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="iterator_category"></a>regex_iterator::iterator_category  
 Yineleyici kategori türü.  
  
```  
typedef std::forward_iterator_tag iterator_category;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `std::forward_iterator_tag`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_iterator_category.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="op_neq"></a>regex_iterator::operator! =  
 Yineleyiciler eşitsizlik açısından karşılaştırır.  
  
```  
bool operator!=(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Karşılaştırma yapılacak yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `!(*this == right)`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="op_star"></a>regex_iterator::operator *  
 Belirlenen eşleşme erişir.  
  
```  
const match_results<BidIt>& operator*();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi saklı değerini döndürür `match`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_operator_star.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="op_add_add"></a>regex_iterator::operator ++  
 Yineleyici artırır.  
  
```  
regex_iterator& operator++();
regex_iterator& operator++(int);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli eşleşme herhangi bir karakter içeriyorsa, ilk işleci çağırır `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`; Aksi takdirde depolanan değer ilerler `begin` geçerli eşledikten sonra sonra çağrıları ilk karakterine işaret edecek şekilde `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. Arama işleci başarısız olursa her iki durumda da, nesne dizisi son yineleyici ayarlar. İşleç nesnesini döndürür.  
  
 İkinci işleci nesne bir kopyasını oluşturur, nesne artırır ve ardından kopya döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_operator_inc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="op_eq"></a>regex_iterator::operator =  
 Yineleyiciler eşitliği karşılaştırır.  
  
```  
bool operator==(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Karşılaştırma yapılacak yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini varsa true değerini döndürür `*this` ve `right` dizisi son yineleyiciler veya bitiş dizisi yineleyici tipleri olup olmadığını ve `begin == right.begin`, `end == right.end`, `pregex == right.pregex`, ve `flags == right.flags`. Aksi takdirde false döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_operator_as.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="regex_iterator__operator-_gt"></a>regex_iterator::operator-&gt;  
 Belirlenen eşleşme erişir.  
  
```  
const match_results<BidIt> * operator->();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini depolanan değer adresini döndürür `match`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_operator_arrow.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="pointer"></a>regex_iterator::pointer  
 Bir eşleşme için bir işaretçi türü.  
  
```  
typedef match_results<BidIt> *pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `match_results<BidIt>*`, burada `BidIt` şablon parametresi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_pointer.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="reference"></a>regex_iterator::Reference  
 Eşleşen bir başvuru türü.  
  
```  
typedef match_results<BidIt>& reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `match_results<BidIt>&`, burada `BidIt` şablon parametresi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="regex_iterator"></a>regex_iterator::regex_iterator  
 Yineleyici oluşturur.  
  
```  
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,  
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```  
  
### <a name="parameters"></a>Parametreler  
 `first`  
 Eşleştirilecek sıralı başlangıcı.  
  
 `last`  
 Eşleştirilecek sıralı sonu.  
  
 `re`  
 Eşleşme için normal ifade.  
  
 `f`  
 Eşleşme bayrakları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bitiş dizisi yineleyici ilk Oluşturucusu oluşturur. İkinci oluşturucu depolanan değer başlatır `begin` ile `first`, depolanan değer `end` ile `last`, depolanan değer `pregex` ile `&re`ve depolanan değer `flags` ile`f`. Daha sonra çağırır `regex_search(begin, end, match, *pregex, flags)`. Arama başarısız olursa, Oluşturucusu nesne dizisi son yineleyici ayarlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="regex_type"></a>regex_iterator::regex_type  
 Eşleştirilecek normal ifade türü.  
  
```  
typedef basic_regex<Elem, RXtraits> regex_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Typedef eşanlamlısı olduğu `basic_regex<Elem, RXtraits>`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_regex_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="value_type"></a>regex_iterator::value_type  
 Bir eşleşme türü.  
  
```  
typedef match_results<BidIt> value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `match_results<BidIt>`, burada `BidIt` şablon parametresi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_iterator_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[\<Regex >](../standard-library/regex.md)  
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)  
[regex_error Sınıfı](../standard-library/regex-error-class.md)  
[\<Regex > işlevleri](../standard-library/regex-functions.md)  
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)  
[\<Regex > işleçleri](../standard-library/regex-operators.md)  
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)  
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)  
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)  

  
