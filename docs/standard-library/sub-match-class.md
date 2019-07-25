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
ms.openlocfilehash: 07ec6f0dc9daaec19fa97a6220da4d4ea93b254b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447424"
---
# <a name="submatch-class"></a>sub_match Sınıfı

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

Şablon sınıfı, [regex_match](../standard-library/regex-functions.md#regex_match) veya [regex_search](../standard-library/regex-functions.md#regex_search)için bir çağrıda bir yakalama grubuyla eşleşen bir karakter dizisini belirten bir nesneyi tanımlar. [Match_results sınıfı](../standard-library/match-results-class.md) türündeki nesneler, aramada kullanılan Normal ifadedeki her bir yakalama grubu için bir tane olmak üzere bu nesnelerin bir dizisini tutar.

`matched` Yakalama grubu eşleştirilmamışsa, nesnenin veri üyesi yanlış olur ve iki yineleyiciler `first` ve `second` (tabandan `std::pair`devralınır) eşittir. Yakalama grubu eşleştirildiği `matched` takdirde, yineleyici `first` , yakalama grubuyla eşleşen hedef dizideki ilk karaktere işaret eder ve yineleyici `second` , hedefteki son karakteri aşan bir konumu işaret eder yakalama grubuyla eşleşen sıra. Üyenin `matched` , sıfır uzunluklu eşleşme doğru tuttuğunda, iki yineleyicinin eşit olacağını ve ikisinin de eşleşme konumunu işaret edecek olduğunu unutmayın.

Bir yakalama grubu yalnızca bir onaylama işlemi ya da sıfır tekrarda izin veren bir tekrardan oluştuğunda sıfır uzunluklu eşleşme meydana gelebilir. Örneğin:

"^", "a" hedef dizisiyle eşleşir; yakalama grubu 0 ' a karşılık gelen nesne,herikisidedizidekiilkkarakteriişaretedenyineleyicilerbarındırır.`sub_match`

"b (a *) b", "BB" hedef dizisiyle eşleşir; yakalama grubu 1 ' e karşılık gelen nesne,herikisidedizidekiikincikaraktereişaretedenyineleyicilerbarındırır.`sub_match`

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

**Üst bilgi:** \<Regex >

**Ad alanı:** std

## <a name="compare"></a>sub_match:: Compare

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

İlk üye işlevi eşleşen sırayı `[first, second)` eşleşen sırayla `[right.first, right.second)`karşılaştırır. İkinci üye işlevi eşleşen sırayı `[first, second)` karakter dizisiyle `[right.begin(), right.end())`karşılaştırır. Üçüncü üye işlevi, eşleşen sırayı `[first, second)` karakter dizisiyle `[right, right + std::char_traits<value_type>::length(right))`karşılaştırır.

Her işlev şunu döndürür:

eşleşen dizideki ilk farklı değer, işlenen dizideki (tarafından `std::char_traits<value_type>::compare`belirlendiği şekilde) karşılık gelen öğeden daha az karşılaştırıyorsa veya iki ortak öneki varsa ancak hedef sıra daha uzunsa, negatif bir değer

iki karşılaştırma öğesi öğesine göre eşit ve aynı uzunluğa sahip ise sıfır

Aksi takdirde pozitif bir değer

## <a name="difference_type"></a>  sub_match::difference_type

Yineleyici farkının türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için `iterator_traits<BidIt>::difference_type`bir eş anlamlı.

## <a name="iterator"></a>sub_match:: Yineleyici

Yineleyicinin türü.

```cpp
typedef BidIt iterator;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, şablon türü bağımsız değişkeninin `Bidit`eşanlamlısıdır.

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

Üye yalnızca,  ile `*this` ilişkili yakalama grubu normal ifade eşleşmesinden bir parçasıysa doğru tutar.

## <a name="op_basic_string_lt_value_type_gt"></a>sub_match:: operator basic_string&lt;value_type&gt;

Bir dizeye alt eşleşme yayınlar.

```cpp
operator basic_string<value_type>() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `str()`.

## <a name="str"></a>sub_match:: Str

Alt eşleşmeyi bir dizeye dönüştürür.

```cpp
basic_string<value_type> str() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `basic_string<value_type>(first, second)`.

## <a name="value_type"></a>  sub_match::value_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için `iterator_traits<BidIt>::value_type`bir eş anlamlı.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)\
[sub_match](../standard-library/sub-match-class.md)
