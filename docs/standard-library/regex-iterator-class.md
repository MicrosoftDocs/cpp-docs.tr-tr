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
ms.openlocfilehash: 937c217cdef6895aaa3adb1499f1fde8f67fd513
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482634"
---
# <a name="regexiterator-class"></a>regex_iterator Sınıfı

İterator sınıfı eşleşmeleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Parametreler

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü.

*Elem*<br/>
Eşleşecek öğelerin türü.

*RXtraits*<br/>
Öğeler için nitelikler sınıfı.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir sabit ileriye doğru yineleyici nesnesi tanımlar. Türündeki nesneler ayıklar `match_results<BidIt>` , normal ifade nesnesi tekrar tekrar uygulayarak `*pregex` yineleyici aralığı tarafından tanımlanan karakter dizisine `[begin, end)`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_iterator](#regex_iterator)|Yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[difference_type](#difference_type)|Bir yineleyicinin fark türü.|
|[iterator_category](#iterator_category)|Yineleyici kategori türü.|
|[İşaretçi](#pointer)|Bir eşleşme için bir işaretçi türü.|
|[Başvuru](#reference)|Bir eşleşme için bir başvuru türü.|
|[regex_type](#regex_type)|Eşleştirilecek normal ifade türü.|
|[value_type](#value_type)|Bir eşleşme türü.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Yineleyiciler eşitsizlik için karşılaştırır.|
|[operator *](#op_star)|Belirlenen eşleşme erişir.|
|[operator ++](#op_add_add)|Bir yineleyiciyi artırır.|
|[operator=](#op_eq)|Yineleyiciler eşitlik için karşılaştırır.|
|[-> işleci](#op_arrow)|Belirlenen eşleşme erişir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

## <a name="examples"></a>Örnekler

Normal ifadelere örnekler için aşağıdaki konulara bakın:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [değiştirme](../standard-library/regex-functions.md#swap)

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

## <a name="difference_type"></a>  regex_iterator::difference_type

Bir yineleyicinin fark türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `std::ptrdiff_t`.

## <a name="iterator_category"></a>  regex_iterator::iterator_category

Yineleyici kategori türü.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `std::forward_iterator_tag`.

## <a name="op_neq"></a>  regex_iterator::operator! =

Yineleyiciler eşitsizlik için karşılaştırır.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Karşılaştırma yapılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `!(*this == right)`.

## <a name="op_star"></a>  regex_iterator::operator *

Belirlenen eşleşme erişir.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi depolanan değeri döndürür `match`.

## <a name="op_add_add"></a>  regex_iterator::operator++

Bir yineleyiciyi artırır.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Açıklamalar

Geçerli eşleşme herhangi bir karakter varsa, ilk işleci çağırır `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`; Aksi takdirde, saklanan değer ilerler `begin` geçerli eşleşen sonra ardından çağrıları ilk karaktere işaret edecek şekilde `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. Arama işleci başarısız olursa her iki durumda da, nesne dizisi bitiş yineleyici ayarlar. İşleci, nesneyi döndürür.

İkinci işleç nesnesinin bir kopyasını getirir, nesne artırır ve sonra kopyayı döndürür.

## <a name="op_eq"></a>  regex_iterator::operator=

Yineleyiciler eşitlik için karşılaştırır.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Karşılaştırma yapılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev true döndürür `*this` ve *doğru* dizisi son yineleyiciler veya birinin diğerinden dizisi bitiş yineleyici olup olmadığını ve `begin == right.begin`, `end == right.end`, `pregex == right.pregex`, ve `flags == right.flags`. Aksi takdirde false döndürür.

## <a name="op_arrow"></a>  regex_iterator::operator-&gt;

Belirlenen eşleşme erişir.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi depolanan değeri adresini döndürür `match`.

## <a name="pointer"></a>  regex_iterator::pointer

Bir eşleşme için bir işaretçi türü.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `match_results<BidIt>*`burada `BidIt` şablon parametresi.

## <a name="reference"></a>  regex_iterator::Reference

Bir eşleşme için bir başvuru türü.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `match_results<BidIt>&`burada `BidIt` şablon parametresi.

## <a name="regex_iterator"></a>  regex_iterator::regex_iterator

Yineleyici oluşturur.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
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

İlk Oluşturucu bir dizisi bitiş yineleyici oluşturur. İkinci oluşturucu depolanmış değere başlatır `begin` ile *ilk*, depolanan değer `end` ile *son*, depolanan değer `pregex` ile `&re`ve depolanan değeri `flags` ile *f*. Ardından `regex_search(begin, end, match, *pregex, flags)`. Arama başarısız olursa, oluşturucu nesne dizisi bitiş yineleyici ayarlar.

## <a name="regex_type"></a>  regex_iterator::regex_type

Eşleştirilecek normal ifade türü.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef eşanlamlıdır `basic_regex<Elem, RXtraits>`.

## <a name="value_type"></a>  regex_iterator::value_type

Bir eşleşme türü.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `match_results<BidIt>`burada `BidIt` şablon parametresi.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
