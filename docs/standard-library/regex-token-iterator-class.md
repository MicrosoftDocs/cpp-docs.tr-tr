---
title: regex_token_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_token_iterator
- regex/std::regex_token_iterator::regex_type
- regex/std::regex_token_iterator::value_type
- regex/std::regex_token_iterator::iterator_category
- regex/std::regex_token_iterator::difference_type
- regex/std::regex_token_iterator::pointer
- regex/std::regex_token_iterator::reference
- regex/std::regex_token_iterator::operator==
- regex/std::regex_token_iterator::operator!=
- regex/std::regex_token_iterator::operator*
- regex/std::regex_token_iterator::operator->
- regex/std::regex_token_iterator::operator++
helpviewer_keywords:
- std::regex_token_iterator [C++]
- std::regex_token_iterator [C++], regex_type
- std::regex_token_iterator [C++], value_type
- std::regex_token_iterator [C++], iterator_category
- std::regex_token_iterator [C++], difference_type
- std::regex_token_iterator [C++], pointer
- std::regex_token_iterator [C++], reference
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
ms.openlocfilehash: 5ada2ad69cbcac15e09968045e54095dfb2623d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366408"
---
# <a name="regex_token_iterator-class"></a>regex_token_iterator Sınıfı

Alt eşleşmeler için iterator sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için yineleyici türü.

*Elem*\
Eşleşecek öğelerin türü.

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu sabit bir ileri yineleme nesnesi açıklar. Kavramsal olarak, bir `regex_iterator` karakter dizisinde normal ifade eşleşmeleri aramak için kullandığı bir nesneyi tutar. Her normal ifade eşleşmesi için depolanan vektördeki `sub_match<BidIt>` `subs` dizin değerleri tarafından tanımlanan alt eşleşmeleri temsil eden tür nesneleri ayıklar.

-1'in dizin değeri, önceki normal ifade eşleşmesinin bitiminden hemen sonra başlayan veya önceki normal ifade eşleşmesi yoksa karakter dizisinin başında başlayan ve geçerli normal ifade eşleşmesinin ilk karakterini veya geçerli eşleşme yoksa karakter dizisinin sonuna kadar uzanan ancak dahil olmayan karakter dizisini belirtir. Başka bir `idx` dizin değeri, 'de `it.match[idx]`tutulan yakalama grubunun içeriğini belirler.

### <a name="members"></a>Üyeler

|Üye|Varsayılan Değer|
|-|-|
|`private regex_iterator<BidIt, Elem, RXtraits> it`||
|`private vector<int> subs`||
|`private int pos`||

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_token_iterator](#regex_token_iterator)|Yineleyiciyi inşa eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iterator_category](#iterator_category)|Yineleyici kategorisinin türü.|
|[pointer](#pointer)|Eşleşme için işaretçi türü.|
|[Başvuru](#reference)|Bir alt eşleşmeiçin başvuru türü.|
|[regex_type](#regex_type)|Eşleşecek normal ifadenin türü.|
|[value_type](#value_type)|Alt eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç!=](#op_neq)|Eşitsizlik için yineleyicileri karşılaştırır.|
|[işleç*](#op_star)|Belirlenen alt eşleşmeye erişir.|
|[işleç++](#op_add_add)|Yinelemeyi demler.|
|[işleç==](#op_eq_eq)|Eşitlik için yineleyicileri karşılaştırır.|
|[operatör->](#op_arrow)|Belirlenen alt eşleşmeye erişir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

**Ad alanı:** std

## <a name="example"></a>Örnek

```cpp
#include <regex>
#include <iostream>

typedef std::regex_token_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "aaxaayaaz";
    Myiter::regex_type rx("(a)a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

// show whole match
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefix before match
    next = Myiter(pat, pat + strlen(pat), rx, -1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show (a) submatch only
    next = Myiter(pat, pat + strlen(pat), rx, 1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and submatches
    std::vector<int> vec;
    vec.push_back(-1);
    vec.push_back(1);
    next = Myiter(pat, pat + strlen(pat), rx, vec);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and whole matches
    int arr[] = {-1, 0};
    next = Myiter(pat, pat + strlen(pat), rx, arr);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

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
match == aa
match == aa
match == aa

match ==
match == x
match == y
match == z

match == a
match == a
match == a

match ==
match == a
match == x
match == a
match == y
match == a
match == z

match ==
match == aa
match == x
match == aa
match == y
match == aa
match == z
```

## <a name="regex_token_iteratordifference_type"></a><a name="difference_type"></a>regex_token_iterator::difference_type

Yineleyici farkının türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü için `std::ptrdiff_t`eşanlamlıdır.

## <a name="regex_token_iteratoriterator_category"></a><a name="iterator_category"></a>regex_token_iterator:iterator_category

Yineleyici kategorisinin türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Türü için `std::forward_iterator_tag`eşanlamlıdır.

## <a name="regex_token_iteratoroperator"></a><a name="op_neq"></a>regex_token_iterator::operator!=

Eşitsizlik için yineleyicileri karşılaştırır.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev `!(*this == right)`döndürür.

## <a name="regex_token_iteratoroperator"></a><a name="op_star"></a>regex_token_iterator::operatör*

Belirlenen alt eşleşmeye erişir.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, `sub_match<BidIt>` dizin değeri `subs[pos]`tarafından tanımlanan yakalama grubunu temsil eden bir nesne döndürür.

## <a name="regex_token_iteratoroperator"></a><a name="op_add_add"></a>regex_token_iterator::operator++

Yinelemeyi demler.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Depolanan yineleyici bir `it` dizi sonu yineleyici ise, ilk işleç depolanan değeri `pos` değeri ayarlar `subs.size()` (böylece sıra sonu yineleyicisi yapma). Aksi takdirde operatör depolanan değeri `pos`arta meraya; sonuç, depolanan değeri `subs.size()` `pos` sıfıra ayarlar ve depolanan yineleyiciyi artımlı değere `it`eşitse. Depolanan yineleyiciyi artırarak, dizi sonu yineleyicisine eşit değilse, işleç başka bir şey yapmaz. Aksi takdirde, önceki eşleşmenin sonunda karakter dizisinin sonunda olsaydı işleç depolanan `pos` `subs.size()`değeri . Aksi takdirde, işleç depolanan değeri `pos` `pos == subs.size()` sürekli olarak `subs[pos] == -1` veya (böylece indeks değerlerinden biri -1 ise, yineleyicinin bir sonraki dereference'ının karakter dizisinin kuyruğunu döndürmesini sağlamak için) art arda artış gösterir. Her durumda işleç nesneyi döndürür.

İkinci işleç nesnenin bir kopyasını yapar, nesneyi artımlar, sonra kopyayı döndürür.

## <a name="regex_token_iteratoroperator"></a><a name="op_eq_eq"></a>regex_token_iterator::operator==

Eşitlik için yineleyicileri karşılaştırır.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev `it == right.it && subs == right.subs && pos == right.pos`döndürür.

## <a name="regex_token_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_token_iterator::operatör-&gt;

Belirlenen alt eşleşmeye erişir.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, dizin `sub_match<BidIt>` değeri `subs[pos]`tarafından tanımlanan yakalama grubunu temsil eden bir nesneye bir işaretçi döndürür.

## <a name="regex_token_iteratorpointer"></a><a name="pointer"></a>regex_token_iterator::pointer

Eşleşme için işaretçi türü.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `sub_match<BidIt>*`ile `BidIt` eş anlamlıdır.

## <a name="regex_token_iteratorreference"></a><a name="reference"></a>regex_token_iterator::referans

Bir alt eşleşmeiçin başvuru türü.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `sub_match<BidIt>&`ile `BidIt` eş anlamlıdır.

## <a name="regex_token_iteratorregex_token_iterator"></a><a name="regex_token_iterator"></a>regex_token_iterator::regex_token_iterator

Yineleyiciyi inşa eder.

```cpp
regex_token_iterator();

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, int submatch = 0,
    regex_constants::match_flag_type f = regex_constants::match_default);

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const vector<int> submatches,
    regex_constants::match_flag_type f = regex_constants::match_default);

template <std::size_t N>
regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const int (&submatches)[N],
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Eşleşecek sıranın başlangıcı.

*Son*\
Eşleşme sırasının sonu.

*Re*\
Eşleşmeler için normal ifade.

*F*\
Kibrit bayrakları.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu bir dizi sonu yinelemesi inşa eder.

İkinci oluşturucu, `it` depolanan yineleyicisi başharfe çevrilmiş `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, depolanan vektörü `subs` tam olarak `submatch`bir tamsayı tutan, değeri olan ve depolanan değeri `pos` sıfır olan bir nesne yi inşa eder. Not: Ortaya çıkan nesne, her başarılı normal `submatch` ifade eşleşmesi için dizin değeriyle tanımlanan alt eşleşmeyi ayıklar.

`it` Üçüncü oluşturucu, depolanan yineleyicisi ,depolanan `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`vektörü `subs` oluşturucu bağımsız değişkeninin `submatches`bir kopyasını tutan ve `pos` depolanan değeri sıfır olan bir nesne yi inşa eder.

Dördüncü oluşturucu, `it` depolanan yineleyicisi başharfe çevrilen `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, depolanan vektörü `subs` oluşturucu bağımsız değişkeninişaret `N` `submatches`ettiği `pos` değerleri tutan ve depolanan değeri sıfır olan bir nesne inşa eder.

## <a name="regex_token_iteratorregex_type"></a><a name="regex_type"></a>regex_token_iterator:regex_type

Eşleşecek normal ifadenin türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef için `basic_regex<Elem, RXtraits>`eşanlamlıdır.

## <a name="regex_token_iteratorvalue_type"></a><a name="value_type"></a>regex_token_iterator:value_type

Alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `sub_match<BidIt>`ile `BidIt` eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)\
[regex_error Sınıfı](../standard-library/regex-error-class.md)\
[\<regex> fonksiyonları](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
