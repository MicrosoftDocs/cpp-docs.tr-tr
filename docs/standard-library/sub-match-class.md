---
title: sub_match sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
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
ms.openlocfilehash: 65d873c4e7188b3000cee65e03c4ce6edcad8046
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235340"
---
# <a name="submatch-class"></a>sub_match Sınıfı

Bir alt eşleşme açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt>
class sub_match
    : public std::pair<BidIt, BidIt>
```

## <a name="parameters"></a>Parametreler

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir çağrıda bir yakalama grubu eşleşen karakter dizisi atayan bir nesneyi tanımlayan [regex_match](../standard-library/regex-functions.md#regex_match) veya [regex_search](../standard-library/regex-functions.md#regex_search). Türündeki nesneler [match_results sınıfı](../standard-library/match-results-class.md) bu nesnelerin her aramaya kullanıldı ve normal ifadedeki yakalama grubu için bir dizi tutun.

Yakalama grubu olmadıysa nesnenin veri üyesi eşleşen `matched` false ve iki yineleyici tutan `first` ve `second` (temelden devralınan `std::pair`) eşit. Yakalama grubu eşleştirildi, `matched` doğru yineleyici tutan `first` yakalama grubu ve yineleyici eşleştirilen hedef dizideki ilk karaktere işaret `second` hedef geçmiş son karakter bir konuma işaret eder Yakalama grubuyla eşleşen dizisi. Sıfır uzunluklu için üyesi ile eşleşmesi gerektiğini unutmayın `matched` tutan true, iki yineleyici eşit olur ve her ikisi de eşleşmeyi konumunu işaret edecek.

Sıfır uzunluklu eşleşen bir onaylama yalnızca bir yakalama grubu oluşur veya sıfır yineleme sağlayan bir tekrarını oluşabilir. Örneğin:

"^" hedef dizisiyle eşleşir "a"; `sub_match` tutan yineleyiciler yakalama grubu 0 karşılık gelen nesne hem de dizideki ilk karakter'ın üzerine gelin.

"b(a*) b", "bb" hedef dizisiyle eşleşir `sub_match` tutan yineleyiciler yakalama grubu 1 için karşılık gelen nesne hem de ikinci karakter dizisi'nın üzerine gelin.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Bir yineleyicinin fark türü.|
|[Yineleyici](#iterator)|Bir yineleyici türü.|
|[value_type](#value_type)|Öğenin türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Karşılaştırma](#compare)|Alt eşleşme karşı bir sıralı karşılaştırma.|
|[Uzunluğu](#length)|Bir alt eşleşme uzunluğunu döndürür.|
|[eşleşen](#matched)|Eşleşme başarılı olup olmadığını gösterir.|
|[str](#str)|Alt eşleşme bir dizeye dönüştürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç basic_string < value_type >](#op_basic_string_lt_value_type_gt)|Yayınları alt eşleşme için bir dize.|

## <a name="example"></a>Örnek

```cpp
// std__regex__sub_match.cpp
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

    std::csub_match::value_type const *ptr = "aab";
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

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

## <a name="compare"></a>  sub_match::COMPARE

Alt eşleşme karşı bir sıralı karşılaştırma.

```cpp
int compare(const sub_match& right) const;
int compare(const basic_string<value_type>& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Karşılaştırma yapılacak alt eşleşme.

*str*<br/>
Karşılaştırma yapılacak dize.

*ptr*<br/>
Karşılaştırmak için null ile sonlandırılmış dizisi.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi eşleşen dizisi karşılaştırır `[first, second)` eşleşen dizisine `[right.first, right.second)`. İkinci üye işlevi eşleşen dizisi karşılaştırır `[first, second)` karakter dizisine `[right.begin(), right.end())`. Üçüncü üye işlevi eşleşen dizisi karşılaştırır `[first, second)` karakter dizisine `[right, right + std::char_traits<value_type>::length(right))`.

Her bir işlevi döndürür:

eşleşen dizideki ilk farklı değer ve işlenen sırasının karşılık gelen öğe sayısından az karşılaştırırsa negatif bir değer (tarafından belirlenen şekilde `std::char_traits<value_type>::compare`), ya da iki ortak bir önek varsa, ancak hedef dizideki uzun

iki öğe eşitse karşılaştırın ve aynı uzunluğa sahip, sıfır

Aksi takdirde pozitif bir değer

## <a name="difference_type"></a>  sub_match::difference_type

Bir yineleyicinin fark türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef eşanlamlıdır `iterator_traits<BidIt>::difference_type`.

## <a name="iterator"></a>  sub_match::iterator

Bir yineleyici türü.

```cpp
typedef BidIt iterator;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon türü bağımsız değişkeni eşanlamlıdır `Bidit`.

## <a name="length"></a>  sub_match::length

Bir alt eşleşme uzunluğunu döndürür.

```cpp
difference_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Eşleşen hiçbir sırası olduysa üye işlevi eşleşen dizisi veya sıfır uzunluğunu döndürür.

## <a name="matched"></a>  sub_match::matched

Eşleşme başarılı olup olmadığını gösterir.

```cpp
bool matched;
```

### <a name="remarks"></a>Açıklamalar

Üye tutan **true** yakalama grubuyla ilişkilendirilen yalnızca `*this` normal ifade eşleştirmesi verilmişti.

## <a name="op_basic_string_lt_value_type_gt"></a>  sub_match::operator basic_string&lt;value_type&gt;

Yayınları alt eşleşme için bir dize.

```cpp
operator basic_string<value_type>() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `str()`.

## <a name="str"></a>  sub_match::Str

Alt eşleşme bir dizeye dönüştürür.

```cpp
basic_string<value_type> str() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `basic_string<value_type>(first, second)`.

## <a name="value_type"></a>  sub_match::value_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef eşanlamlıdır `iterator_traits<BidIt>::value_type`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[sub_match](../standard-library/sub-match-class.md)<br/>
