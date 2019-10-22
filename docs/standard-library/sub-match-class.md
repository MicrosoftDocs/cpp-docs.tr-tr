---
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
ms.openlocfilehash: 776dfe67367b932435f76af94880111cad61341d
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685840"
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

*BidIt* \
Alt eşleşmeler için Yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, [regex_match](../standard-library/regex-functions.md#regex_match) veya [regex_search](../standard-library/regex-functions.md#regex_search)için bir çağrıda bir yakalama grubuyla eşleşen bir karakter dizisini belirten bir nesneyi tanımlar. [Match_results sınıfı](../standard-library/match-results-class.md) türündeki nesneler, aramada kullanılan Normal ifadedeki her bir yakalama grubu için bir tane olmak üzere bu nesnelerin bir dizisini tutar.

Yakalama grubu eşleştirilmamışsa, nesnenin veri üyesi `matched` yanlış olur ve iki yineleyiciler `first` ve `second` (taban `std::pair` devralınmış) eşittir. Yakalama grubu eşleştirildiği `matched`, yineleyici `first`, hedef dizide yakalama grubuyla eşleşen ilk karakteri işaret eder ve yineleyici, eşleşen hedef dizideki son karakteri aşan bir konum `second` yakalama grubu. Üyenin `matched` bir sıfır uzunluğa sahip olduğunu, iki yineleyicinin eşit olacağını ve her ikisinin de eşleşme konumunu işaret edecek olduğunu unutmayın.

Bir yakalama grubu yalnızca bir onaylama işlemi ya da sıfır tekrarda izin veren bir tekrardan oluştuğunda sıfır uzunluklu eşleşme meydana gelebilir. Örneğin:

"^", "a" hedef dizisiyle eşleşir; 0 yakalama grubuna karşılık gelen `sub_match` nesnesi, her ikisi de dizideki ilk karakteri işaret eden yineleyiciler barındırır.

"b (a *) b", "BB" hedef dizisiyle eşleşir; `sub_match` yakalama grubuna karşılık gelen nesne, her ikisi de dizideki ikinci karaktere işaret eden yineleyiciler barındırır.

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
|[uzunluklu](#length)|Alt eşleşmenin uzunluğunu döndürür.|
|[eşleşen](#matched)|Eşleşmenin başarılı olup olmadığını gösterir.|
|[üstbilgisine](#str)|Alt eşleşmeyi bir dizeye dönüştürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator basic_string < value_type >](#op_basic_string_lt_value_type_gt)|Bir dizeye alt eşleşme yayınlar.|

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

**Üst bilgi:** \<regex >

**Ad alanı:** std

## <a name="compare"></a>sub_match:: Compare

Alt eşleşmeyi bir diziye göre karşılaştırın.

```cpp
int compare(const sub_match& right) const;
int compare(const basic_string<value_type>& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*sağ* \
Karşılaştırılacak alt eşleşme.

*str* \
Karşılaştırılacak dize.

*ptr* \
Karşılaştırılacak null ile sonlandırılmış dizi.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi eşleşen sırayı `[first, second)` eşleşen sıra `[right.first, right.second)` karşılaştırır. İkinci üye işlevi, eşleşen sırayı `[first, second)` `[right.begin(), right.end())` karakter dizisi ile karşılaştırır. Üçüncü üye işlevi, eşleşen sırayı `[first, second)` `[right, right + std::char_traits<value_type>::length(right))` karakter dizisi ile karşılaştırır.

Her işlev şunu döndürür:

eşleşen dizideki ilk farklı değer, işlenen dizideki (`std::char_traits<value_type>::compare` tarafından belirlendiği şekilde) karşılık gelen öğeden daha az karşılaştırıyorsa veya iki ortak öneki varsa ancak hedef sıra daha uzunsa, negatif bir değer

iki karşılaştırma öğesi öğesine göre eşit ve aynı uzunluğa sahip ise sıfır

Aksi takdirde pozitif bir değer

## <a name="difference_type"></a>sub_match::d ifference_type

Yineleyici farkının türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef `iterator_traits<BidIt>::difference_type` için bir eş anlamlı.

## <a name="iterator"></a>sub_match:: Yineleyici

Yineleyicinin türü.

```cpp
typedef BidIt iterator;
```

### <a name="remarks"></a>Açıklamalar

TypeDef `Bidit` şablon türü bağımsız değişkeni için bir eş anlamlı.

## <a name="length"></a>sub_match:: length

Alt eşleşmenin uzunluğunu döndürür.

```cpp
difference_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, eşleşen sıranın uzunluğunu veya eşleşen bir sıra yoksa sıfır değerini döndürür.

## <a name="matched"></a>sub_match:: eşleşti

Eşleşmenin başarılı olup olmadığını gösterir.

```cpp
bool matched;
```

### <a name="remarks"></a>Açıklamalar

Üye yalnızca, `*this` ilişkili yakalama grubu normal ifade eşleşmesinden bir parçasıysa **doğru** tutar.

## <a name="op_basic_string_lt_value_type_gt"></a>sub_match:: operator basic_string &lt;value_type &gt;

Bir dizeye alt eşleşme yayınlar.

```cpp
operator basic_string<value_type>() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işleci `str()` döndürür.

## <a name="str"></a>sub_match:: Str

Alt eşleşmeyi bir dizeye dönüştürür.

```cpp
basic_string<value_type> str() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `basic_string<value_type>(first, second)` döndürür.

## <a name="value_type"></a>sub_match::value_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef `iterator_traits<BidIt>::value_type` için bir eş anlamlı.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex >](../standard-library/regex.md) \
[sub_match](../standard-library/sub-match-class.md)
