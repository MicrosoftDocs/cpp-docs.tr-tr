---
description: 'Hakkında daha fazla bilgi edinin: sub_match Sınıfı'
title: sub_match Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::sub_match
- regex/std::sub_match::matched
- regex/std::sub_match::compare
- regex/std::sub_match::length
- regex/std::sub_match::str
- regex/std::sub_match::difference_type
- regex/std::sub_match::iterator
- regex/std::sub_match::value_type
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
ms.openlocfilehash: 683b0bc6cf73a44ce426d5dcab3cdf13221be66b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183405"
---
# <a name="sub_match-class"></a>sub_match Sınıfı

Bir alt eşleşme tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt>
class sub_match
    : public std::pair<BidIt, BidIt>
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için Yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir [regex_match](../standard-library/regex-functions.md#regex_match) veya [regex_search](../standard-library/regex-functions.md#regex_search)çağrısı içindeki bir yakalama grubuyla eşleşen bir karakter dizisini belirten bir nesneyi tanımlar. [Match_results sınıf](../standard-library/match-results-class.md) türündeki nesneler, aramada kullanılan Normal ifadedeki her bir yakalama grubu için bir tane olmak üzere bu nesnelerin bir dizisini tutar.

Yakalama grubu eşleştirilmamışsa, nesnenin veri üyesi `matched` yanlış olur ve iki yineleyiciler `first` ve `second` (tabandan devralınır `std::pair` ) eşittir. Yakalama grubu eşleştirildiği takdirde, `matched` Yineleyici, `first` yakalama grubuyla eşleşen hedef dizideki ilk karaktere işaret eder ve yineleyici, `second` yakalama grubuyla eşleşen hedef dizideki son karakteri aşan bir konumu işaret eder. Üyenin, sıfır uzunluklu eşleşme `matched` doğru tuttuğunda, iki yineleyicinin eşit olacağını ve ikisinin de eşleşme konumunu işaret edecek olduğunu unutmayın.

Bir yakalama grubu yalnızca bir onaylama işlemi ya da sıfır tekrarda izin veren bir tekrardan oluştuğunda sıfır uzunluklu eşleşme meydana gelebilir. Örneğin:

"^", "a" hedef dizisiyle eşleşir; `sub_match` yakalama grubu 0 ' a karşılık gelen nesne, her ikisi de dizideki ilk karakteri işaret eden yineleyiciler barındırır.

"b (a *) b", "BB" hedef dizisiyle eşleşir; `sub_match` yakalama grubu 1 ' e karşılık gelen nesne, her ikisi de dizideki ikinci karaktere işaret eden yineleyiciler barındırır.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iden](#iterator)|Yineleyicinin türü.|
|[value_type](#value_type)|Öğenin türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Karşılaştır](#compare)|Alt eşleşmeyi bir diziye göre karşılaştırın.|
|[length](#length)|Alt eşleşmenin uzunluğunu döndürür.|
|[eşleşen](#matched)|Eşleşmenin başarılı olup olmadığını gösterir.|
|[üstbilgisine](#str)|Alt eşleşmeyi bir dizeye dönüştürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[Operatör basic_string<value_type>](#op_basic_string_lt_value_type_gt)|Bir dizeye alt eşleşme yayınlar.|

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

**Üst bilgi:**\<regex>

**Ad alanı:** std

## <a name="sub_matchcompare"></a><a name="compare"></a> sub_match:: Compare

Alt eşleşmeyi bir diziye göre karşılaştırın.

```cpp
int compare(const sub_match& right) const;
int compare(const basic_string<value_type>& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak alt eşleşme.

*üstbilgisine*\
Karşılaştırılacak dize.

*kaydetmeye*\
Karşılaştırılacak null ile sonlandırılmış dizi.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi eşleşen sırayı `[first, second)` eşleşen sırayla karşılaştırır `[right.first, right.second)` . İkinci üye işlevi eşleşen sırayı `[first, second)` karakter dizisiyle karşılaştırır `[right.begin(), right.end())` . Üçüncü üye işlevi, eşleşen sırayı `[first, second)` karakter dizisiyle karşılaştırır `[right, right + std::char_traits<value_type>::length(right))` .

Her işlev şunu döndürür:

eşleşen dizideki ilk farklı değer, işlenen dizideki (tarafından belirlendiği şekilde) karşılık gelen öğeden daha az karşılaştırıyorsa `std::char_traits<value_type>::compare` veya iki ortak öneki varsa ancak hedef sıra daha uzunsa, negatif bir değer

iki karşılaştırma öğesi öğesine göre eşit ve aynı uzunluğa sahip ise sıfır

Aksi takdirde pozitif bir değer

## <a name="sub_matchdifference_type"></a><a name="difference_type"></a> sub_match::d ifference_type

Yineleyici farkının türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için bir eş anlamlı `iterator_traits<BidIt>::difference_type` .

## <a name="sub_matchiterator"></a><a name="iterator"></a> sub_match:: Yineleyici

Yineleyicinin türü.

```cpp
typedef BidIt iterator;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, şablon türü bağımsız değişkeninin eşanlamlısıdır `Bidit` .

## <a name="sub_matchlength"></a><a name="length"></a> sub_match:: length

Alt eşleşmenin uzunluğunu döndürür.

```cpp
difference_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, eşleşen sıranın uzunluğunu veya eşleşen bir sıra yoksa sıfır değerini döndürür.

## <a name="sub_matchmatched"></a><a name="matched"></a> sub_match:: eşleşti

Eşleşmenin başarılı olup olmadığını gösterir.

```cpp
bool matched;
```

### <a name="remarks"></a>Açıklamalar

Üye **`true`** yalnızca ile ilişkili yakalama grubu **`*this`** normal ifade eşleşmesinden bir parçasıysa barındırır.

## <a name="sub_matchoperator-basic_stringltvalue_typegt"></a><a name="op_basic_string_lt_value_type_gt"></a> sub_match:: operator basic_string &lt; value_type&gt;

Bir dizeye alt eşleşme yayınlar.

```cpp
operator basic_string<value_type>() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `str()` .

## <a name="sub_matchstr"></a><a name="str"></a> sub_match:: Str

Alt eşleşmeyi bir dizeye dönüştürür.

```cpp
basic_string<value_type> str() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `basic_string<value_type>(first, second)` .

## <a name="sub_matchvalue_type"></a><a name="value_type"></a> sub_match:: value_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için bir eş anlamlı `iterator_traits<BidIt>::value_type` .

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[sub_match](../standard-library/sub-match-class.md)
