---
description: 'Hakkında daha fazla bilgi edinin: regex_token_iterator sınıfı'
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
ms.openlocfilehash: 752ff44864b435100bacb83250a5c6a792cab502
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243893"
---
# <a name="regex_token_iterator-class"></a>regex_token_iterator Sınıfı

Alt eşleşmeler için Yineleyici sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için Yineleyici türü.

*Elem*\
Eşleşecek öğelerin türü.

*Rxnitelikler*\
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, sabit bir ileri yineleyici nesnesi tanımlar. Kavramsal olarak, `regex_iterator` bir karakter dizisindeki normal ifade eşleşmelerini aramak için kullandığı bir nesneyi barındırır. `sub_match<BidIt>` `subs` Her normal ifade eşleşmesi için depolanan vektörde dizin değerleriyle tanımlanan alt eşleşmeleri temsil eden türündeki nesneleri ayıklar.

-1 ' in bir dizin değeri, önceki normal ifade eşleşmesinden hemen sonra başlayan veya bir önceki normal ifade eşleşmesi yoksa karakter dizisinin başlangıcında başlayan veya geçerli bir eşleşme yoksa karakter sırasının sonuna kadar olan karakter sırasını belirler. Bu değer, geçerli normal ifade eşleşmesinden sonra ya da herhangi bir geçerli eşleşme yoksa karakter dizisinin sonuna kadar bir kez başlar. Diğer herhangi bir dizin değeri, `idx` içinde tutulan yakalama grubunun içeriğini belirler `it.match[idx]` .

### <a name="members"></a>Üyeler

|Üye|Varsayılan değer|
|-|-|
|`private regex_iterator<BidIt, Elem, RXtraits> it`||
|`private vector<int> subs`||
|`private int pos`||

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_token_iterator](#regex_token_iterator)|Yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iterator_category](#iterator_category)|Yineleyici kategorisinin türü.|
|[pointer](#pointer)|Bir eşleşme işaretçisinin türü.|
|[başvurunun](#reference)|Bir alt eşleşme başvurusunun türü.|
|[regex_type](#regex_type)|Eşleştirilecek normal ifadenin türü.|
|[value_type](#value_type)|Alt eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](#op_neq)|Eşitsizlik için yineleyiciler karşılaştırır.|
|[işlecinde](#op_star)|Belirlenen alt eşleştirmeye erişir.|
|[işleç + +](#op_add_add)|Yineleyiciyi artırır.|
|[işleç = =](#op_eq_eq)|Yineleyiciler eşitlik için karşılaştırılmaktadır.|
|[operator->](#op_arrow)|Belirlenen alt eşleştirmeye erişir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<regex>

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

## <a name="regex_token_iteratordifference_type"></a><a name="difference_type"></a> regex_token_iterator::d ifference_type

Yineleyici farkının türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `std::ptrdiff_t` .

## <a name="regex_token_iteratoriterator_category"></a><a name="iterator_category"></a> regex_token_iterator:: iterator_category

Yineleyici kategorisinin türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `std::forward_iterator_tag` .

## <a name="regex_token_iteratoroperator"></a><a name="op_neq"></a> regex_token_iterator:: operator! =

Eşitsizlik için yineleyiciler karşılaştırır.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `!(*this == right)` .

## <a name="regex_token_iteratoroperator"></a><a name="op_star"></a> regex_token_iterator:: operator *

Belirlenen alt eşleştirmeye erişir.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `sub_match<BidIt>` Dizin değeri tarafından tanımlanan yakalama grubunu temsil eden bir nesne döndürür `subs[pos]` .

## <a name="regex_token_iteratoroperator"></a><a name="op_add_add"></a> regex_token_iterator:: operator + +

Yineleyiciyi artırır.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Saklı Yineleyici `it` bir dizi dizilim ise, ilk operatör depolanan değeri `pos` değerine ayarlar (Bu nedenle, `subs.size()` bir dizi yineleyiciyi yapar). Aksi takdirde işleç depolanan değeri artırır `pos` ; sonuç değere eşitse, `subs.size()` depolanan değeri `pos` sıfıra ayarlar ve depolanan yineleyiciyi arttırır `it` . Saklı yineleyicinin arttırılmaları, bir dizi son yineleyiciye eşit olarak bırakırsa, işleç başka bir şey yapmaz. Aksi takdirde, önceki eşleşmenin sonu karakter dizisinin sonunda ise işleç, saklı değerini `pos` olarak ayarlar `subs.size()` . Aksi takdirde, işleç saklı değeri bir kez veya olarak arttırır `pos` `pos == subs.size()` `subs[pos] == -1` (Bu nedenle, Dizin değerlerinden biri-1 ise, yineleyicinin bir sonraki başvurmasının karakter dizisinin kuyruğunu döndürmesini sağlar). Her durumda, işleç nesneyi döndürür.

İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

## <a name="regex_token_iteratoroperator"></a><a name="op_eq_eq"></a> regex_token_iterator:: operator = =

Yineleyiciler eşitlik için karşılaştırılmaktadır.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `it == right.it && subs == right.subs && pos == right.pos` .

## <a name="regex_token_iteratoroperator-gt"></a><a name="op_arrow"></a> regex_token_iterator:: operator-&gt;

Belirlenen alt eşleştirmeye erişir.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `sub_match<BidIt>` Dizin değeri tarafından tanımlanan yakalama grubunu temsil eden nesnesine bir işaretçi döndürür `subs[pos]` .

## <a name="regex_token_iteratorpointer"></a><a name="pointer"></a> regex_token_iterator::p oınter

Bir eşleşme işaretçisinin türü.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, için bir eş anlam, `sub_match<BidIt>*` burada `BidIt` şablon parametresidir.

## <a name="regex_token_iteratorreference"></a><a name="reference"></a> regex_token_iterator:: Reference

Bir alt eşleşme başvurusunun türü.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, için bir eş anlam, `sub_match<BidIt>&` burada `BidIt` şablon parametresidir.

## <a name="regex_token_iteratorregex_token_iterator"></a><a name="regex_token_iterator"></a> regex_token_iterator:: regex_token_iterator

Yineleyici oluşturur.

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

*adı*\
Eşleştirilecek sıra başlangıcı.

*soyadına*\
Eşleştirilecek sıra sonu.

*değerlendirmeyi*\
Eşleşmeler için normal ifade.

*vadeli*\
Eşleşmeler için bayraklar.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizi son yineleyicisi oluşturur.

İkinci Oluşturucu, saklı Yineleyici tarafından başlatılan bir nesne oluşturur `it` `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` , saklı vektör, `subs` değeri olan `submatch` ve depolanan değeri sıfır olan bir tam sayı tutar `pos` . Note: elde edilen nesne, `submatch` başarılı olan her normal ifade eşleşmesi için dizin değeri tarafından tanımlanan alt eşleşmeyi ayıklar.

Üçüncü Oluşturucu, saklı Yineleyici `it` `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` `subs` bir Oluşturucu bağımsız değişkeninin kopyasını tutan `submatches` ve depolanmış değeri `pos` sıfır olan bir nesne oluşturur.

Dördüncü Oluşturucu, saklı Yineleyici, `it` `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` `subs` `N` Oluşturucu bağımsız değişkeni tarafından işaret edilen değerleri tutan `submatches` ve depolanmış değeri `pos` sıfır olan depolanan bir nesne oluşturur.

## <a name="regex_token_iteratorregex_type"></a><a name="regex_type"></a> regex_token_iterator:: regex_type

Eşleştirilecek normal ifadenin türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için bir eş anlamlı `basic_regex<Elem, RXtraits>` .

## <a name="regex_token_iteratorvalue_type"></a><a name="value_type"></a> regex_token_iterator:: value_type

Alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, için bir eş anlam, `sub_match<BidIt>` burada `BidIt` şablon parametresidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<regex> lerdir](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> işletmenlerinin](../standard-library/regex-operators.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> tür tanımları](../standard-library/regex-typedefs.md)
