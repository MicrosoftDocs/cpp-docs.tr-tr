---
title: regex_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
ms.openlocfilehash: d9d2baf99b1e2334132f54aeace3d8197b1e73da
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217590"
---
# <a name="regex_iterator-class"></a>regex_iterator Sınıfı

Eşleşmeler için Yineleyici sınıfı.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için Yineleyici türü.

*Elem*\
Eşleşecek öğelerin türü.

*Rxnitelikler*\
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, sabit bir ileri yineleyici nesnesi tanımlar. `match_results<BidIt>`Normal ifade nesnesini `*pregex` , yineleyici aralığı tarafından tanımlanan karakter dizisine sürekli olarak uygulayarak türündeki nesneleri ayıklar `[begin, end)` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_iterator](#regex_iterator)|Yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iterator_category](#iterator_category)|Yineleyici kategorisinin türü.|
|[pointer](#pointer)|Bir eşleşme işaretçisinin türü.|
|[başvurunun](#reference)|Bir eşleşme başvurusunun türü.|
|[regex_type](#regex_type)|Eşleştirilecek normal ifadenin türü.|
|[value_type](#value_type)|Eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](#op_neq)|Eşitsizlik için yineleyiciler karşılaştırır.|
|[işlecinde](#op_star)|Belirlenen eşleştirmeye erişir.|
|[işleç + +](#op_add_add)|Yineleyiciyi artırır.|
|[işleç =](#op_eq)|Yineleyiciler eşitlik için karşılaştırılmaktadır.|
|[operator->](#op_arrow)|Belirlenen eşleştirmeye erişir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<regex>

**Ad alanı:** std

## <a name="examples"></a>Örnekler

Normal ifadelerle ilgili örnekler için aşağıdaki konulara bakın:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [Kur](../standard-library/regex-functions.md#swap)

```cpp
// std__regex__regex_iterator.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

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
match == a
match == a
match == a
```

## <a name="regex_iteratordifference_type"></a><a name="difference_type"></a>regex_iterator::d ifference_type

Yineleyici farkının türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `std::ptrdiff_t` .

## <a name="regex_iteratoriterator_category"></a><a name="iterator_category"></a>regex_iterator:: iterator_category

Yineleyici kategorisinin türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `std::forward_iterator_tag` .

## <a name="regex_iteratoroperator"></a><a name="op_neq"></a>regex_iterator:: operator! =

Eşitsizlik için yineleyiciler karşılaştırır.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `!(*this == right)` .

## <a name="regex_iteratoroperator"></a><a name="op_star"></a>regex_iterator:: operator *

Belirlenen eşleştirmeye erişir.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan değeri döndürür `match` .

## <a name="regex_iteratoroperator"></a><a name="op_add_add"></a>regex_iterator:: operator + +

Yineleyiciyi artırır.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Geçerli eşleşmenin ilk operatör çağrısı olmayan bir karakteri yoksa, `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)` `begin` geçerli eşleşmesinden sonra ilk karakteri işaret etmek için saklanan değeri ilerletir `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)` . Her iki durumda da, arama başarısız olursa işleç nesneyi bir dizi son yineleyicisi olarak ayarlar. İşleci nesnesini döndürür.

İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

## <a name="regex_iteratoroperator"></a><a name="op_eq"></a>regex_iterator:: operator =

Yineleyiciler eşitlik için karşılaştırılmaktadır.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, **`*this`** ve *sağ* sıralı yineleyiciler ise true döndürür ya da ikisi de sıralı bir yineleyici ve,,, `begin == right.begin` ve ise `end == right.end` `pregex == right.pregex` `flags == right.flags` . Aksi takdirde false döndürür.

## <a name="regex_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_iterator:: operator-&gt;

Belirlenen eşleştirmeye erişir.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan değerin adresini döndürür `match` .

## <a name="regex_iteratorpointer"></a><a name="pointer"></a>regex_iterator::p oınter

Bir eşleşme işaretçisinin türü.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü, için bir eş anlam, `match_results<BidIt>*` burada `BidIt` şablon parametresidir.

## <a name="regex_iteratorreference"></a><a name="reference"></a>regex_iterator:: Reference

Bir eşleşme başvurusunun türü.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, için bir eş anlam, `match_results<BidIt>&` burada `BidIt` şablon parametresidir.

## <a name="regex_iteratorregex_iterator"></a><a name="regex_iterator"></a>regex_iterator:: regex_iterator

Yineleyici oluşturur.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
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

İlk Oluşturucu bir dizi son yineleyicisi oluşturur. İkinci Oluşturucu, saklı değeri `begin` *ilki*, Last değeri, ile depolanan değer `end` *last* `pregex` `&re` ve `flags` *f*ile depolanan değer ile başlatır. Ardından çağırır `regex_search(begin, end, match, *pregex, flags)` . Arama başarısız olursa, Oluşturucu nesneyi bir dizi son yineleyiciye ayarlar.

## <a name="regex_iteratorregex_type"></a><a name="regex_type"></a>regex_iterator:: regex_type

Eşleştirilecek normal ifadenin türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için bir eş anlamlı `basic_regex<Elem, RXtraits>` .

## <a name="regex_iteratorvalue_type"></a><a name="value_type"></a>regex_iterator:: value_type

Eşleşme türü.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, için bir eş anlam, `match_results<BidIt>` burada `BidIt` şablon parametresidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<regex>lerdir](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex>işletmenlerinin](../standard-library/regex-operators.md)\
[regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex>tür tanımları](../standard-library/regex-typedefs.md)
