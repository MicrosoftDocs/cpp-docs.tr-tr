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
ms.openlocfilehash: 460f79fe0f23643fafcebb64aecf2988bdb0debe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376579"
---
# <a name="sub_match-class"></a>sub_match Sınıfı

Bir alt eşleşmeyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt>
class sub_match
    : public std::pair<BidIt, BidIt>
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, [regex_match](../standard-library/regex-functions.md#regex_match) veya [regex_search](../standard-library/regex-functions.md#regex_search)için yapılan bir çağrıda yakalama grubuyla eşleşen bir karakter dizisini belirten bir nesneyi açıklar. Sınıf türü [match_results](../standard-library/match-results-class.md) nesneleri, aramada kullanılan normal ifadedeki her yakalama grubu için bir dizi bu nesnelere sahip olur.

Yakalama grubu eşleştirilmediyse, nesnenin `matched` veri üyesi false tutar ve `first` `second` iki yineleyici ve `std::pair`(temelden devralınan) eşittir. Yakalama grubu eşleştiyse, `matched` doğru tutarsa, yineleyici hedef dizisinde yakalama grubuyla eşleşen ilk karaktere `first` işaret eder `second` ve yineleyici, yakalama grubuyla eşleşen hedef dizisindeki son karakteri bir pozisyonu işaret eder. Üyenin geçerli `matched` tuttuğu sıfır uzunluktaki bir eşleşme için iki yineleyicinin eşit olacağını ve her ikisinin de maçın konumunu işaret edeceğini unutmayın.

Bir yakalama grubu yalnızca bir iddiadan veya sıfır yinelemeye izin veren bir yinelemeden oluştuğunda sıfır uzunlukta bir eşleşme oluşabilir. Örneğin:

"^" hedef sıra "a" ile eşleşir; yakalama `sub_match` grubu 0'a karşılık gelen nesne, her ikisi de dizideki ilk karaktere işaret eden yineleyicileri tutar.

"b(a*)b" hedef sırası "bb" ile eşleşir; yakalama `sub_match` grubu 1'e karşılık gelen nesne, her ikisi de dizideki ikinci nesneyi işaret eden yineleyicileri tutar.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[Yineleyici](#iterator)|Bir yineleyici türü.|
|[value_type](#value_type)|Öğenin türü.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Karşılaştırmak](#compare)|Alt eşleşmeyi bir diziyle karşılaştırın.|
|[Uzun -luğu](#length)|Alt eşleşmenin uzunluğunu verir.|
|[Eşleşen](#matched)|Eşleşmenin başarılı olup olmadığını gösterir.|
|[Str](#str)|Submatch'i bir dize dönüştürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operatör basic_string<value_type>](#op_basic_string_lt_value_type_gt)|Alt eşleşmeyi bir dize atar.|

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

**Üstbilgi:** \<regex>

**Ad alanı:** std

## <a name="sub_matchcompare"></a><a name="compare"></a>sub_match::karşılaştır

Alt eşleşmeyi bir diziyle karşılaştırın.

```cpp
int compare(const sub_match& right) const;
int compare(const basic_string<value_type>& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırmak için alt maç.

*Str*\
Karşılaştırılacak dize.

*Ptr*\
Karşılaştırmak için null-sonlandırılan sıra.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev eşleşen diziyle `[first, second)` eşleşen sırayı `[right.first, right.second)`karşılaştırır. İkinci üye işlev eşleşen diziyi `[first, second)` karakter dizisiyle `[right.begin(), right.end())`karşılaştırır. Üçüncü üye işlev eşleşen diziyi `[first, second)` karakter dizisiyle `[right, right + std::char_traits<value_type>::length(right))`karşılaştırır.

Her işlev döner:

eşleşen dizideki ilk farklı değer operand dizisindeki karşılık gelen öğeden (belirlenen) `std::char_traits<value_type>::compare`daha az ise veya ikisinin ortak bir önek varsa ancak hedef sırası daha uzunsa negatif bir değer

sıfır eğer iki eleman ait eşit öğeyi karşılaştırın ve aynı uzunluğa sahip

aksi takdirde olumlu bir değer

## <a name="sub_matchdifference_type"></a><a name="difference_type"></a>sub_match::difference_type

Yineleyici farkının türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef için `iterator_traits<BidIt>::difference_type`eşanlamlıdır.

## <a name="sub_matchiterator"></a><a name="iterator"></a>sub_match::iterator

Bir yineleyici türü.

```cpp
typedef BidIt iterator;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon türü bağımsız değişkeni `Bidit`için eşanlamlıdır.

## <a name="sub_matchlength"></a><a name="length"></a>sub_match::uzunluk

Alt eşleşmenin uzunluğunu verir.

```cpp
difference_type length() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev eşleşen dizinin uzunluğunu veya eşleşen bir sıra yoksa sıfır'ı döndürür.

## <a name="sub_matchmatched"></a><a name="matched"></a>sub_match::eşleşti

Eşleşmenin başarılı olup olmadığını gösterir.

```cpp
bool matched;
```

### <a name="remarks"></a>Açıklamalar

Üye, yalnızca ilişkili `*this` yakalama grubu normal ifade eşleşmesinin bir parçasıysa **geçerlidir.**

## <a name="sub_matchoperator-basic_stringltvalue_typegt"></a><a name="op_basic_string_lt_value_type_gt"></a>sub_match::operatör&lt;basic_string value_type&gt;

Alt eşleşmeyi bir dize atar.

```cpp
operator basic_string<value_type>() const;
```

### <a name="remarks"></a>Açıklamalar

Üye operatör `str()`döndürür.

## <a name="sub_matchstr"></a><a name="str"></a>sub_match::str

Submatch'i bir dize dönüştürür.

```cpp
basic_string<value_type> str() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev `basic_string<value_type>(first, second)`döndürür.

## <a name="sub_matchvalue_type"></a><a name="value_type"></a>sub_match:value_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef için `iterator_traits<BidIt>::value_type`eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[Sub_match](../standard-library/sub-match-class.md)
