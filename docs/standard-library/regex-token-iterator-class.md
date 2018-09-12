---
title: regex_token_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- std::regex_token_iterator [C++]
- std::regex_token_iterator [C++], regex_type
- std::regex_token_iterator [C++], value_type
- std::regex_token_iterator [C++], iterator_category
- std::regex_token_iterator [C++], difference_type
- std::regex_token_iterator [C++], pointer
- std::regex_token_iterator [C++], reference
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32a281a3f9b6793047ae10b1d186e6a68002176a
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691490"
---
# <a name="regextokeniterator-class"></a>regex_token_iterator Sınıfı

Alt eşleşmeleri için iterator sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator 
```

## <a name="parameters"></a>Parametreler

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü.

*Elem*<br/>
Eşleşecek öğelerin türü.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir sabit ileriye doğru yineleyici nesnesi tanımlar. Kavramsal olarak, tutan bir `regex_iterator` normal ifade için aranacak kullanan nesne içinde bir karakter dizisiyle eşleşir. Türündeki nesneler ayıklar `sub_match<BidIt>` dizin değerleri saklı vektör tarafından tanımlanan alt eşleşmeleri temsil eden `subs` her bir normal ifade eşleştirmesi için.

Bir dizin değeri-1 karakter dizisi hemen önceki normal ifade eşleştirmesi sonunda başlayan veya önceki normal ifade eşleşme olursa karakter dizisi başlangıcında başlayan ve genişletme ancak belirler. Geçerli eşleşme yoksa ilk karakteri geçerli bir normal ifade eşleştirmesi veya karakter dizisi sonuna dahil. Herhangi bir dizin değeri `idx` tutulan yakalama grubu içeriğini belirler `it.match[idx]`.

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
|[difference_type](#difference_type)|Bir yineleyicinin fark türü.|
|[iterator_category](#iterator_category)|Yineleyici kategori türü.|
|[İşaretçi](#pointer)|Bir eşleşme için bir işaretçi türü.|
|[Başvuru](#reference)|Bir alt eşleşme için bir başvuru türü.|
|[regex_type](#regex_type)|Eşleştirilecek normal ifade türü.|
|[value_type](#value_type)|Bir alt eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Yineleyiciler eşitsizlik için karşılaştırır.|
|[operator *](#op_star)|Belirtilen alt eşleşme erişir.|
|[operator ++](#op_add_add)|Bir yineleyiciyi artırır.|
|[operator==](#op_eq_eq)|Yineleyiciler eşitlik için karşılaştırır.|
|[-> işleci](#op_arrow)|Belirtilen alt eşleşme erişir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

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

Bir yineleyicinin fark türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `std::ptrdiff_t`.

## <a name="iterator_category"></a>  regex_token_iterator::iterator_category

Yineleyici kategori türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `std::forward_iterator_tag`.

## <a name="op_neq"></a>  regex_token_iterator::operator!=

Yineleyiciler eşitsizlik için karşılaştırır.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Karşılaştırma yapılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `!(*this == right)`.

## <a name="op_star"></a>  regex_token_iterator::operator*

Belirtilen alt eşleşme erişir.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür bir `sub_match<BidIt>` dizin değeri tarafından tanımlanan bir yakalama grubunu temsil eden nesne `subs[pos]`.

## <a name="op_add_add"></a>  regex_token_iterator::operator++

Bir yineleyiciyi artırır.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Depolanmış yineleyiciyi `it` dizisi bitiş yineleyici ilk işleç, depolanan değeri ayarlar `pos` değerine `subs.size()` (Bu nedenle bir dizisi bitiş yineleyici yapar). Aksi takdirde işleci depolanan değeri artırır `pos`; sonuç değerine eşitse `subs.size()` depolanan değeri ayarlar `pos` sıfır ve depolanmış yineleyiciyi artırır `it`. Depolanmış yineleyiciyi bırakır artan, son dizi için bir yineleyici işleci eşit, başka hiçbir şey yapmaz. Aksi takdirde önceki eşleşmenin sona karakter dizisi sonunda ise işleci depolanmış değerini ayarlar `pos` için `subs.size()`. İşleç sürekli olarak depolanan değeri artırır Aksi takdirde, `pos` kadar `pos == subs.size()` veya `subs[pos] == -1` (Bu nedenle dizin değerlerinden -1 olması durumunda yineleyicisinin ileri başvuru sonu karakter dizisi döndürür emin olun). Her durumda işleci nesneyi döndürür.

İkinci işleç nesnesinin bir kopyasını getirir, nesne artırır ve sonra kopyayı döndürür.

## <a name="op_eq_eq"></a>  regex_token_iterator::operator ==

Yineleyiciler eşitlik için karşılaştırır.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Karşılaştırma yapılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `it == right.it && subs == right.subs && pos == right.pos`.

## <a name="op_arrow"></a>  regex_token_iterator::operator-&gt;

Belirtilen alt eşleşme erişir.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi işaretçisi döndüren bir `sub_match<BidIt>` dizin değeri tarafından tanımlanan bir yakalama grubunu temsil eden nesne `subs[pos]`.

## <a name="pointer"></a>  regex_token_iterator::pointer

Bir eşleşme için bir işaretçi türü.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `sub_match<BidIt>*`burada `BidIt` şablon parametresi.

## <a name="reference"></a>  regex_token_iterator::reference

Bir alt eşleşme için bir başvuru türü.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `sub_match<BidIt>&`burada `BidIt` şablon parametresi.

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

*ilk*<br/>
Eşleştirilecek sıralı başlangıcı.

*Son*<br/>
Eşleştirilecek sıralı sonu.

*RE*<br/>
Eşleşme için normal ifade.

*f*<br/>
Eşleşme bayrakları.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizisi bitiş yineleyici oluşturur.

İkinci oluşturucu depolanmış yineleyiciyi olan bir nesne oluşturur `it` değerine ayarlanır `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, depolanmış olan vektör `subs` tam olarak bir tamsayı değeri tutan `submatch`ve depolanan değeri `pos` sıfırdır. Not: dizin değeri tarafından tanımlanan alt eşleşme elde edilen nesnenin ayıklar `submatch` her başarılı bir normal ifade eşleştirmesi için.

Üçüncü Oluşturucu, depolanmış yineleyiciyi bir nesne oluşturur `it` değerine ayarlanır `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, depolanmış olan vektör `subs` oluşturucu bağımsız değişkeni bir kopyasını tutan `submatches`ve depolanan değeri `pos` sıfırdır.

Dördüncü Oluşturucu, depolanmış yineleyiciyi bir nesne oluşturur `it` değerine ayarlanır `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, depolanmış olan vektör `subs` tutan `N` değerleri yönlendirmekteydi oluşturucu bağımsız değişkeni tarafından `submatches`ve saklı değer `pos` sıfırdır.

## <a name="regex_type"></a>  regex_token_iterator::regex_type

Eşleştirilecek normal ifade türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef eşanlamlıdır `basic_regex<Elem, RXtraits>`.

## <a name="value_type"></a>  regex_token_iterator::value_type

Bir alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `sub_match<BidIt>`burada `BidIt` şablon parametresi.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
