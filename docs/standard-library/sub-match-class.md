---
title: sub_match sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::sub_match
- regex/std::sub_match::matched
- regex/std::sub_match::compare
- regex/std::sub_match::length
- regex/std::sub_match::str
- regex/std::sub_match::difference_type
- regex/std::sub_match::iterator
- regex/std::sub_match::value_type
dev_langs:
- C++
helpviewer_keywords:
- std::sub_match [C++]
- std::sub_match [C++], matched
- std::sub_match [C++], compare
- std::sub_match [C++], length
- std::sub_match [C++], str
- std::sub_match [C++], difference_type
- std::sub_match [C++], iterator
- std::sub_match [C++], value_type
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 740ebe26dd36dd89786806c3960e6184b117daeb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="submatch-class"></a>sub_match Sınıfı

Bir submatch açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt>
class sub_match
 : public std::pair<BidIt, BidIt> {
public:
    bool matched;
    int compare(const sub_match& right) const;
    int compare(const basic_string<value_type>& right) const;
    int compare(const value_type *right) const;
    difference_type length() const;
    operator basic_string<value_type>() const;
    basic_string<value_type> str() const;

    // typedefs
    typedef typename iterator_traits<BidIt>::value_type value_type;
    typedef typename iterator_traits<BidIt>::difference_type difference_type;
    typedef BidIt iterator;
 };
```

### <a name="parameters"></a>Parametreler

`BidIt` Submatches yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Çağrı yakalama grubunda eşleşen bir karakter dizisi atayan bir nesne şablonu sınıf tanımlar [regex_match](../standard-library/regex-functions.md#regex_match) veya [regex_search](../standard-library/regex-functions.md#regex_search). Nesne türü [match_results sınıfı](../standard-library/match-results-class.md) bu nesneler, bir aramada kullanılan normal ifade her yakalama grup için bir dizi tutun.

Yakalama Grup olmadıysa nesnenin veri üyesi eşleşen `matched` false ve iki yineleyiciler tutan `first` ve `second` (taban devralınan `std::pair`) eşit. Yakalama grubun eşleşen, `matched` true, yineleyici tutan `first` ilk karakter, yakalama grubu ve yineleyici eşleşen hedef sırası işaret `second` hedef son karakteri aşan bir konuma işaret eder Yakalama grubun eşleşen dizisi. Sıfır uzunluklu için üye eşleşen unutmayın `matched` tutan true, iki yineleyiciler eşit olur ve hem eşleşen konumunu işaret edecek.

Sıfır uzunluklu eşleşen bir onaylama işlemi yalnızca bir yakalama Grup oluşur veya sıfır yineler sağlayan bir yinelenmesinin oluşabilir. Örneğin:

"^" hedef sırası eşleşen "a"; `sub_match` tutan yineleyiciler Grup 0 yakalamak için karşılık gelen nesne her ikisi de ilk karakter dizisi, üzerine gelin.

hedef sırası "bb"; "b(a*) b" ile eşleşir `sub_match` tutan yineleyiciler grubu 1 yakalamak için karşılık gelen nesne hem de sıralı ikinci karakter üzerine gelin.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

## <a name="compare"></a>  sub_match::COMPARE

Bir dizi karşı submatch karşılaştırın.

```cpp
int compare(const sub_match& right) const;
int compare(const basic_string<value_type>& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

`right` Karşılaştırma yapılacak submatch.

`str` Karşılaştırma yapılacak dizesi.

`ptr` Karşılaştırma yapılacak null ile sonlandırılmış dizisi.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi eşleşen dizisi karşılaştırır `[first, second)` eşleşen dizisine `[right.first, right.second)`. İkinci üye işlevi eşleşen dizisi karşılaştırır `[first, second)` karakter dizisi için `[right.begin(), right.end())`. Eşleşen dizisi üçüncü üye işlevi karşılaştırır `[first, second)` karakter dizisi için `[right, right + std::char_traits<value_type>::length(right))`.

Her işlevi döndürür:

eşleşen sıradaki ilk farklı değeri işleneni dizisi karşılık gelen öğe sayısından az karşılaştırır, negatif bir değer (tarafından belirlenen `std::char_traits<value_type>::compare`), ya da iki ortak bir önek varsa, ancak hedef sırası uzun

iki öğe eşit karşılaştırın ve aynı uzunlukta varsa sıfır

Aksi takdirde pozitif bir değer

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_compare.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="difference_type"></a>  sub_match::difference_type

Yineleyici fark türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef eşanlamlısı olduğu `iterator_traits<BidIt>::difference_type`.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_difference_type.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="iterator"></a>  sub_match::iterator

Yineleyici türü.

```cpp
typedef BidIt iterator;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon tür bağımsız değişkeni için eş anlamlı olduğundan `Bidit`.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_iterator.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="length"></a>  sub_match::length

Bir submatch uzunluğunu döndürür.

```cpp
difference_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Eşleşen hiçbir sıra olduysa üye fonksiyonu eşleşen dizisi ya da sıfır uzunluğunu döndürür.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_length.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="matched"></a>  sub_match::matched

Eşleşme başarılı olup olmadığını gösterir.

```cpp
bool matched;
```

### <a name="remarks"></a>Açıklamalar

Üye tutan `true` yakalama Grup ilişkilendirilen yalnızca `*this` normal ifade eşleştirmesi parçası.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_matched.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="op_basic_string_lt_value_type_gt"></a>  sub_match::operator basic_string&lt;value_type&gt;

Bir dize submatch atamaları.

```cpp
operator basic_string<value_type>() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `str()`.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_operator_str.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="str"></a>  sub_match::Str

Bir dize submatch dönüştürür.

```cpp
basic_string<value_type> str() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `basic_string<value_type>(first, second)`.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_str.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="value_type"></a>  sub_match::value_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef eşanlamlısı olduğu `iterator_traits<BidIt>::value_type`.

### <a name="example"></a>Örnek

```cpp
// std__regex__sub_match_value_type.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::csub_match sub = mr[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;

    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);
    std::cout << "difference == " << dif << std::endl;

    std::csub_match::iterator first = sub.first;
    std::csub_match::iterator last = sub.second;
    std::cout << "range == " << std::string(first, last)
        << std::endl;
    std::cout << "string == " << sub << std::endl;

    std::csub_match::value_type *ptr = "aab";
    std::cout << "compare(\"aab\") == "
        << sub.compare(ptr) << std::endl;
    std::cout << "compare(string) == "
        << sub.compare(std::string("AAA")) << std::endl;
    std::cout << "compare(sub) == "
        << sub.compare(sub) << std::endl;

    return (0);
    }

```

```Output
matched == true
length == 3
difference == 3
range == aaa
string == aaa
compare("aab") == -1
compare(string) == 1
compare(sub) == 0
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[sub_match](../standard-library/sub-match-class.md)<br/>
