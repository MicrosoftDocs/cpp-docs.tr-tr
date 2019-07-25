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
ms.openlocfilehash: 78d01ed8606e65e55af7e0c8dc24c02b51c53a39
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451550"
---
# <a name="regextokeniterator-class"></a>regex_token_iterator Sınıfı

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

Şablon sınıfı, sabit bir ileri yineleyici nesnesi tanımlar. Kavramsal olarak, bir karakter `regex_iterator` dizisindeki normal ifade eşleşmelerini aramak için kullandığı bir nesneyi barındırır. Her normal ifade eşleşmesi için `sub_match<BidIt>` depolanan vektörde `subs` dizin değerleriyle tanımlanan alt eşleşmeleri temsil eden türündeki nesneleri ayıklar.

-1 ' in bir dizin değeri, önceki normal ifade eşleşmesinden hemen sonra başlayan karakter sırasını, önceki normal ifade eşleşmesi yoksa ' a ve ' a genişleterek, karakter dizisinin başlangıcından itibaren belirler. Geçerli normal ifade eşleşmesinden ilk karakteri veya geçerli eşleşme yoksa karakter dizisinin sonuna dahil. Diğer herhangi bir dizin `idx` değeri, içinde `it.match[idx]`tutulan yakalama grubunun içeriğini belirler.

### <a name="members"></a>Üyeler

|Üye|Varsayılan Değer|
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
|[çağrısı](#pointer)|Bir eşleşme işaretçisinin türü.|
|[Başvuru](#reference)|Bir alt eşleşme başvurusunun türü.|
|[regex_type](#regex_type)|Eşleştirilecek normal ifadenin türü.|
|[value_type](#value_type)|Alt eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Eşitsizlik için yineleyiciler karşılaştırır.|
|[işlecinde](#op_star)|Belirlenen alt eşleştirmeye erişir.|
|[işleç + +](#op_add_add)|Yineleyiciyi artırır.|
|[operator==](#op_eq_eq)|Yineleyiciler eşitlik için karşılaştırılmaktadır.|
|[operator->](#op_arrow)|Belirlenen alt eşleştirmeye erişir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Regex >

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

## <a name="difference_type"></a>  regex_token_iterator::difference_type

Yineleyici farkının türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için `std::ptrdiff_t`bir eş anlamlı.

## <a name="iterator_category"></a>regex_token_iterator::iterator_category

Yineleyici kategorisinin türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür için `std::forward_iterator_tag`bir eş anlamlı.

## <a name="op_neq"></a>  regex_token_iterator::operator!=

Eşitsizlik için yineleyiciler karşılaştırır.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `!(*this == right)`.

## <a name="op_star"></a>  regex_token_iterator::operator*

Belirlenen alt eşleştirmeye erişir.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dizin değeri `sub_match<BidIt>` `subs[pos]`tarafından tanımlanan yakalama grubunu temsil eden bir nesne döndürür.

## <a name="op_add_add"></a>  regex_token_iterator::operator++

Yineleyiciyi artırır.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Saklı Yineleyici `it` bir dizi dizilim ise, ilk operatör depolanan değeri `pos` değerine `subs.size()` ayarlar (Bu nedenle, bir dizi yineleyiciyi yapar). Aksi takdirde işleç depolanan `pos`değeri artırır; sonuç değere `subs.size()` eşitse, depolanan `pos` değeri sıfıra ayarlar ve depolanan yineleyiciyi `it`arttırır. Saklı yineleyicinin arttırılmaları, bir dizi son yineleyiciye eşit olarak bırakırsa, işleç başka bir şey yapmaz. Aksi takdirde, önceki eşleşmenin sonu karakter dizisinin sonunda ise işleç, saklı değerini `pos` olarak `subs.size()`ayarlar. Aksi takdirde, işleç saklı değeri `pos` `pos == subs.size()` bir kez veya `subs[pos] == -1` olarak arttırır (Bu nedenle, Dizin değerlerinden biri-1 ise, yineleyicinin bir sonraki başvurmasının karakter dizisinin kuyruğunu döndürmesini sağlar). Her durumda, işleç nesneyi döndürür.

İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

## <a name="op_eq_eq"></a>regex_token_iterator:: operator = =

Yineleyiciler eşitlik için karşılaştırılmaktadır.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `it == right.it && subs == right.subs && pos == right.pos`.

## <a name="op_arrow"></a>  regex_token_iterator::operator-&gt;

Belirlenen alt eşleştirmeye erişir.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dizin değeri `sub_match<BidIt>` `subs[pos]`tarafından tanımlanan yakalama grubunu temsil eden nesnesine bir işaretçi döndürür.

## <a name="pointer"></a>regex_token_iterator::p oınter

Bir eşleşme işaretçisinin türü.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, için `sub_match<BidIt>*`bir eş anlam, burada `BidIt` şablon parametresidir.

## <a name="reference"></a>  regex_token_iterator::reference

Bir alt eşleşme başvurusunun türü.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, için `sub_match<BidIt>&`bir eş anlam, burada `BidIt` şablon parametresidir.

## <a name="regex_token_iterator"></a>  regex_token_iterator::regex_token_iterator

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

İkinci Oluşturucu, saklı Yineleyici `it` tarafından `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`başlatılan bir nesne oluşturur, saklı vektör `subs` , değeri `submatch`olan ve depolanan değeri `pos` sıfır olan bir tam sayı tutar. Note: elde edilen nesne, başarılı olan her normal ifade eşleşmesi için Dizin `submatch` değeri tarafından tanımlanan alt eşleşmeyi ayıklar.

Üçüncü Oluşturucu, `it` saklı Yineleyici `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` `subs` bir Oluşturucu bağımsız değişkeninin `submatches`kopyasını tutan ve depolanmış değeri `pos` sıfır olan bir nesne oluşturur.

Dördüncü Oluşturucu, `it` saklı Yineleyici `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` `subs` , Oluşturucu bağımsız değişkeni `submatches`tarafından işaret edilen `N` değerleri tutan ve depolanan bir nesne olan değer `pos` sıfır.

## <a name="regex_type"></a>  regex_token_iterator::regex_type

Eşleştirilecek normal ifadenin türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için `basic_regex<Elem, RXtraits>`bir eş anlamlı.

## <a name="value_type"></a>regex_token_iterator::value_type

Alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, için `sub_match<BidIt>`bir eş anlam, burada `BidIt` şablon parametresidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<Regex > işlevleri](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<Regex > işleçleri](../standard-library/regex-operators.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<tür tanımları > Regex](../standard-library/regex-typedefs.md)
