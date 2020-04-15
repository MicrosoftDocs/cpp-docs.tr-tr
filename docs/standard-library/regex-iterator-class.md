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
ms.openlocfilehash: 6bc57d6815fa6f30e26b22e9b7ab758a1ac20e16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374549"
---
# <a name="regex_iterator-class"></a>regex_iterator Sınıfı

Maçlar için iterator sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için yineleyici türü.

*Elem*\
Eşleşecek öğelerin türü.

*RXözellikleri*\
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu sabit bir ileri yineleme nesnesi açıklar. Düzenli ifade nesnesini `match_results<BidIt>` `*pregex` tekrar tekrar yineleyici aralığı `[begin, end)`tarafından tanımlanan karakter dizisine uygulayarak türdeki nesneleri ayıklar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_iterator](#regex_iterator)|Yineleyiciyi inşa eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iterator_category](#iterator_category)|Yineleyici kategorisinin türü.|
|[pointer](#pointer)|Eşleşme için işaretçi türü.|
|[Başvuru](#reference)|Eşleşmeye başvuru türü.|
|[regex_type](#regex_type)|Eşleşecek normal ifadenin türü.|
|[value_type](#value_type)|Eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç!=](#op_neq)|Eşitsizlik için yineleyicileri karşılaştırır.|
|[işleç*](#op_star)|Belirlenen eşleşmeye erişir.|
|[işleç++](#op_add_add)|Yinelemeyi demler.|
|[işleç=](#op_eq)|Eşitlik için yineleyicileri karşılaştırır.|
|[operatör->](#op_arrow)|Belirlenen eşleşmeye erişir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

**Ad alanı:** std

## <a name="examples"></a>Örnekler

Normal ifadelere ilişkin örnekler için aşağıdaki konulara bakın:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [Takas](../standard-library/regex-functions.md#swap)

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

## <a name="regex_iteratordifference_type"></a><a name="difference_type"></a>regex_iterator::difference_type

Yineleyici farkının türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü için `std::ptrdiff_t`eşanlamlıdır.

## <a name="regex_iteratoriterator_category"></a><a name="iterator_category"></a>regex_iterator:iterator_category

Yineleyici kategorisinin türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Türü için `std::forward_iterator_tag`eşanlamlıdır.

## <a name="regex_iteratoroperator"></a><a name="op_neq"></a>regex_iterator::operatör!=

Eşitsizlik için yineleyicileri karşılaştırır.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev `!(*this == right)`döndürür.

## <a name="regex_iteratoroperator"></a><a name="op_star"></a>regex_iterator::operatör*

Belirlenen eşleşmeye erişir.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev depolanan değeri `match`döndürür.

## <a name="regex_iteratoroperator"></a><a name="op_add_add"></a>regex_iterator::operator++

Yinelemeyi demler.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Geçerli eşleşmede karakter yoksa ilk operatör `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`çağırır; aksi takdirde, geçerli `begin` eşleşmeden sonra ilk karakteri işaret etmek `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`için depolanan değeri ilerler ve çağırır. Her iki durumda da, arama başarısız olursa işleç nesneyi dizi sonu yineleyicisine ayarlar. İşleç nesneyi döndürür.

İkinci işleç nesnenin bir kopyasını yapar, nesneyi artımlar, sonra kopyayı döndürür.

## <a name="regex_iteratoroperator"></a><a name="op_eq"></a>regex_iterator::operator=

Eşitlik için yineleyicileri karşılaştırır.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev, her `*this` ikisi de dizinin sonu yinelemecileri yse veya ikisi de dizi sonu yinelemesi `end == right.end` `pregex == right.pregex`ve `flags == right.flags` *right* `begin == right.begin`, , , ve . Aksi takdirde false döndürür.

## <a name="regex_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_iterator::operatör-&gt;

Belirlenen eşleşmeye erişir.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev depolanan değerin `match`adresini döndürür.

## <a name="regex_iteratorpointer"></a><a name="pointer"></a>regex_iterator::pointer

Eşleşme için işaretçi türü.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `match_results<BidIt>*`ile `BidIt` eş anlamlıdır.

## <a name="regex_iteratorreference"></a><a name="reference"></a>regex_iterator::başvuru

Eşleşmeye başvuru türü.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `match_results<BidIt>&`ile `BidIt` eş anlamlıdır.

## <a name="regex_iteratorregex_iterator"></a><a name="regex_iterator"></a>regex_iterator:regex_iterator

Yineleyiciyi inşa eder.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
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

İlk oluşturucu bir dizi sonu yinelemesi inşa eder. İkinci oluşturucu, depolanan `begin` değeri *ilk*, *sonuncu* `end` olan depolanan değer `pregex` ve `&re` `flags` *f*ile depolanan değer ile başlatleştirir. Daha sonra `regex_search(begin, end, match, *pregex, flags)`çağırır. Arama başarısız olursa, oluşturucu nesneyi dizi sonu yineleyicisine ayarlar.

## <a name="regex_iteratorregex_type"></a><a name="regex_type"></a>regex_iterator:regex_type

Eşleşecek normal ifadenin türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef için `basic_regex<Elem, RXtraits>`eşanlamlıdır.

## <a name="regex_iteratorvalue_type"></a><a name="value_type"></a>regex_iterator:value_type

Eşleşme türü.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `match_results<BidIt>`ile `BidIt` eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)\
[regex_error Sınıfı](../standard-library/regex-error-class.md)\
[\<regex> fonksiyonları](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
