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
ms.openlocfilehash: fb609df2bf52873dac3cddaa6b12f82ea1b53237
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689086"
---
# <a name="regex_iterator-class"></a>regex_iterator Sınıfı

Eşleşmeler için Yineleyici sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Parametreler

*BidIt* \
Alt eşleşmeler için Yineleyici türü.

*Eled* \
Eşleşecek öğelerin türü.

*Rxnitelikler* \
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, sabit bir ileri yineleyici nesnesi tanımlar. Normal ifade nesnesi `*pregex`, yineleyici aralığı `[begin, end)` tarafından tanımlanan karakter dizisine sürekli olarak uygulayarak `match_results<BidIt>` türündeki nesneleri ayıklar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_iterator](#regex_iterator)|Yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iterator_category](#iterator_category)|Yineleyici kategorisinin türü.|
|[çağrısı](#pointer)|Bir eşleşme işaretçisinin türü.|
|[başvurunun](#reference)|Bir eşleşme başvurusunun türü.|
|[regex_type](#regex_type)|Eşleştirilecek normal ifadenin türü.|
|[value_type](#value_type)|Eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Eşitsizlik için yineleyiciler karşılaştırır.|
|[işlecinde](#op_star)|Belirlenen eşleştirmeye erişir.|
|[işleç + +](#op_add_add)|Yineleyiciyi artırır.|
|[işleç =](#op_eq)|Yineleyiciler eşitlik için karşılaştırılmaktadır.|
|[operator->](#op_arrow)|Belirlenen eşleştirmeye erişir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<regex >

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

## <a name="difference_type"></a>regex_iterator::d ifference_type

Yineleyici farkının türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür `std::ptrdiff_t` için bir eş anlamlı.

## <a name="iterator_category"></a>regex_iterator::iterator_category

Yineleyici kategorisinin türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür `std::forward_iterator_tag` için bir eş anlamlı.

## <a name="op_neq"></a>regex_iterator:: operator! =

Eşitsizlik için yineleyiciler karşılaştırır.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `!(*this == right)` döndürür.

## <a name="op_star"></a>regex_iterator:: operator *

Belirlenen eşleştirmeye erişir.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `match` depolanan değeri döndürür.

## <a name="op_add_add"></a>regex_iterator:: operator + +

Yineleyiciyi artırır.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Geçerli eşleşmenin hiçbir karakteri yoksa, ilk işleç `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)` çağırır; Aksi takdirde, geçerli eşleşmesinden sonra ilk karakteri işaret eden `begin` saklanan değeri ilerletir ve sonra `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)` çağırır. Her iki durumda da, arama başarısız olursa işleç nesneyi bir dizi son yineleyicisi olarak ayarlar. İşleci nesnesini döndürür.

İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

## <a name="op_eq"></a>regex_iterator:: operator =

Yineleyiciler eşitlik için karşılaştırılmaktadır.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Karşılaştırılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `*this` ve *sağ* sıralı yineleyiciler ise true döndürür ya da ikisi de bir dizi yineleyici ve `begin == right.begin`, `end == right.end`, `pregex == right.pregex` ve `flags == right.flags` değilse. Aksi takdirde false döndürür.

## <a name="op_arrow"></a>regex_iterator:: operator-&gt;

Belirlenen eşleştirmeye erişir.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `match` depolanan değerin adresini döndürür.

## <a name="pointer"></a>regex_iterator::p oınter

Bir eşleşme işaretçisinin türü.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, `BidIt` şablon parametresi olduğu `match_results<BidIt>*` için bir eş anladır.

## <a name="reference"></a>regex_iterator:: Reference

Bir eşleşme başvurusunun türü.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, `BidIt` şablon parametresi olduğu `match_results<BidIt>&` için bir eş anladır.

## <a name="regex_iterator"></a>regex_iterator::regex_iterator

Yineleyici oluşturur.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Parametreler

*ilk* \
Eşleştirilecek sıra başlangıcı.

*son* \
Eşleştirilecek sıra sonu.

*yeniden* \
Eşleşmeler için normal ifade.

*f* \
Eşleşmeler için bayraklar.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizi son yineleyicisi oluşturur. İkinci Oluşturucu, depolanan değeri *ilk*`begin` başlatır, depolanan değer *en son*ile `end`, depolanan değer `&re` ile `pregex` ve depolanan değer *f*ile `flags`. Ardından `regex_search(begin, end, match, *pregex, flags)` çağırır. Arama başarısız olursa, Oluşturucu nesneyi bir dizi son yineleyiciye ayarlar.

## <a name="regex_type"></a>regex_iterator::regex_type

Eşleştirilecek normal ifadenin türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef `basic_regex<Elem, RXtraits>` için bir eş anlamlı.

## <a name="value_type"></a>regex_iterator::value_type

Eşleşme türü.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `BidIt` şablon parametresi olduğu `match_results<BidIt>` için bir eş anladır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex >](../standard-library/regex.md) \
[Regex_constants sınıfı](../standard-library/regex-constants-class.md) \
[Regex_error sınıfı](../standard-library/regex-error-class.md) \
[\<regex > işlevleri](../standard-library/regex-functions.md) \
[Regex_iterator sınıfı](../standard-library/regex-iterator-class.md) \
[\<regex > işleçleri](../standard-library/regex-operators.md) \
[Regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) \
[regex_traits sınıfı](../standard-library/regex-traits-class.md) \
[\<regex > tür tanımları](../standard-library/regex-typedefs.md)
