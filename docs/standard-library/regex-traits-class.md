---
title: regex_traits Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_traits
- regex/std::regex_traits::char_type
- regex/std::regex_traits::size_type
- regex/std::regex_traits::string_type
- regex/std::regex_traits::locale_type
- regex/std::regex_traits::char_class_type
- regex/std::regex_traits::length
- regex/std::regex_traits::translate
- regex/std::regex_traits::translate_nocase
- regex/std::regex_traits::transform
- regex/std::regex_traits::transform_primary
- regex/std::regex_traits::lookup_classname
- regex/std::regex_traits::lookup_collatename
- regex/std::regex_traits::isctype
- regex/std::regex_traits::value
- regex/std::regex_traits::imbue
- regex/std::regex_traits::getloc
helpviewer_keywords:
- std::regex_traits [C++]
- std::regex_traits [C++], char_type
- std::regex_traits [C++], size_type
- std::regex_traits [C++], string_type
- std::regex_traits [C++], locale_type
- std::regex_traits [C++], char_class_type
- std::regex_traits [C++], length
- std::regex_traits [C++], translate
- std::regex_traits [C++], translate_nocase
- std::regex_traits [C++], transform
- std::regex_traits [C++], transform_primary
- std::regex_traits [C++], lookup_classname
- std::regex_traits [C++], lookup_collatename
- std::regex_traits [C++], isctype
- std::regex_traits [C++], value
- std::regex_traits [C++], imbue
- std::regex_traits [C++], getloc
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
ms.openlocfilehash: 8879336c48d0fec8a20411abf1c07d570a1575e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366389"
---
# <a name="regex_traits-class"></a>regex_traits Sınıfı

Eşleştirme için öğelerin özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class Elem>
class regex_traits
```

## <a name="parameters"></a>Parametreler

*Elem*\
Tanımlamak için karakter öğesi türü.

## <a name="remarks"></a>Açıklamalar

Sınıf *şablonu, Elem*türü için çeşitli düzenli ifade özelliklerini açıklar. [Sınıf şablonu basic_regex Sınıf,](../standard-library/basic-regex-class.md) *Elem*türündeki öğeleri işlemek için bu bilgileri kullanır.

Her `regex_traits` nesne, bazı `regex_traits::locale` üye işlevleri tarafından kullanılan bir tür nesnesi tutar. Varsayılan yerel `regex_traits::locale()`alan, ''nin bir kopyasıdır. Üye işlev `imbue` yerel nesnenin yerini alır ve `getloc` üye işlev yerel nesnenin bir kopyasını döndürür.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_traits](#regex_traits)|Nesneyi inşa eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_class_type](#char_class_type)|Karakter sınıfı ataakatörlerinin türü.|
|[Char_type](#char_type)|Öğenin türü.|
|[locale_type](#locale_type)|Depolanan yerel nesnenin türü.|
|[size_type](#size_type)|Sıra uzunluğunun türü.|
|[string_type](#string_type)|Bir öğe dizisinin türü.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[getloc](#getloc)|Depolanan yerel nesneyi döndürür.|
|[imbue](#imbue)|Depolanan yerel nesneyi değiştirir.|
|[isctype](#isctype)|Sınıf üyeliği için testler.|
|[Uzun -luğu](#length)|Null-sonlandırılan dizinin uzunluğunu verir.|
|[lookup_classname](#lookup_classname)|Bir diziyi karakter sınıfıyla eşler.|
|[lookup_collatename](#lookup_collatename)|Bir diziyi bir harmanlama öğesiyle eşler.|
|[Dönüştürmek](#transform)|Eşdeğer sıralı sıraya dönüştürür.|
|[transform_primary](#transform_primary)|Eşdeğer örneksiz sıralı sıraya dönüştürür.|
|[Çevir](#translate)|Eşdeğer eşleştirme öğesine dönüştürür.|
|[translate_nocase](#translate_nocase)|Eşdeğer örneksiz eşleştirme öğesine dönüştürür.|
|[Değer](#value)|Bir öğeyi basamak değerine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

**Ad alanı:** std

## <a name="example"></a>Örnek

```cpp
// std__regex__regex_traits.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_traits<char> Mytr;
int main()
    {
    Mytr tr;

    Mytr::char_type ch = tr.translate('a');
    std::cout << "translate('a') == 'a' == " << std::boolalpha
        << (ch == 'a') << std::endl;

    std::cout << "nocase 'a' == 'A' == " << std::boolalpha
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))
        << std::endl;

    const char *lbegin = "abc";
    const char *lend = lbegin + strlen(lbegin);
    Mytr::size_type size = tr.length(lbegin);
    std::cout << "length(\"abc\") == " << size <<std::endl;

    Mytr::string_type str = tr.transform(lbegin, lend);
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha
        << (str < "abc") << std::endl;

    const char *ubegin = "ABC";
    const char *uend = ubegin + strlen(ubegin);
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha
        << (tr.transform_primary(ubegin, uend) <
            tr.transform_primary(lbegin, lend))
        << std::endl;

    const char *dig = "digit";
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);
    std::cout << "class digit == d == " << std::boolalpha
        << (cl == tr.lookup_classname(dig, dig + 1))
        << std::endl;

    std::cout << "'3' is digit == " <<std::boolalpha
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))
        << std::endl;

    std::cout << "hex C == " << tr.value('C', 16) << std::endl;

// other members
    str = tr.lookup_collatename(dig, dig + 5);

    Mytr::locale_type loc = tr.getloc();
    tr.imbue(loc);

    return (0);
    }
```

```Output
translate('a') == 'a' == true
nocase 'a' == 'A' == true
length("abc") == 3
transform("abc") < "abc" == false
primary "ABC" < "abc" == false
class digit == d == true
'3' is digit == true
hex C == 12
```

## <a name="regex_traitschar_class_type"></a><a name="char_class_type"></a>regex_traits:char_class_type

Karakter sınıfı ataakatörlerinin türü.

```cpp
typedef T8 char_class_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, karakter sınıflarını belirleyen belirtilmemiş bir türle eş anlamlıdır. Bu tür değerler, operandlar tarafından belirlenen sınıfların birleşimi olan karakter sınıflarını belirlemek için `|` işleç kullanılarak birleştirilebilir.

## <a name="regex_traitschar_type"></a><a name="char_type"></a>regex_traits:char_type

Öğenin türü.

```cpp
typedef Elem char_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon bağımsız değişkeni `Elem`için eşanlamlıdır.

## <a name="regex_traitsgetloc"></a><a name="getloc"></a>regex_traits::getloc

Depolanan yerel nesneyi döndürür.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev depolanan `locale` nesneyi döndürür.

## <a name="regex_traitsimbue"></a><a name="imbue"></a>regex_traits::imbue

Depolanan yerel nesneyi değiştirir.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametreler

*Loc*\
Depolamak için yerel nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan `locale` nesneye *loca* sıyrık ve depolanan `locale` nesnenin önceki değerinin bir kopyasını döndürür.

## <a name="regex_traitsisctype"></a><a name="isctype"></a>regex_traits::isctype

Sınıf üyeliği için testler.

```cpp
bool isctype(char_type ch, char_class_type cls) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Test etmek için öğe.

*Cls*\
Test etmek için sınıflar.

### <a name="remarks"></a>Açıklamalar

Üye işlev yalnızca *karakter ch* *cls*tarafından belirlenen karakter sınıfında ise doğru döndürür.

## <a name="regex_traitslength"></a><a name="length"></a>regex_traits::uzunluk

Null-sonlandırılan dizinin uzunluğunu verir.

```cpp
static size_type length(const char_type *str);
```

### <a name="parameters"></a>Parametreler

*Str*\
Null-terminated sırası.

### <a name="remarks"></a>Açıklamalar

Statik üye işlev `std::char_traits<char_type>::length(str)`döndürür.

## <a name="regex_traitslocale_type"></a><a name="locale_type"></a>regex_traits:locale_type

Depolanan yerel nesnenin türü.

```cpp
typedef T7 locale_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef, yerel leri kapsayan bir türle eş anlamlıdır. Uzmanlık ve `regex_traits<char>` `regex_traits<wchar_t>` için `std::locale`eşanlamlıdır.

## <a name="regex_traitslookup_classname"></a><a name="lookup_classname"></a>regex_traits:lookup_classname

Bir diziyi karakter sınıfıyla eşler.

```cpp
template <class FwdIt>
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Yukarı bakmak için sıranın başlangıcı.

*Son*\
Bakmak için sıranın sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlev, bağımsız değişkenleri tarafından işaret edilen karakter dizisi tarafından adlandırılmış karakter sınıfını belirleyen bir değer döndürür. Değer, dizideki karakterlerin durumuna bağlı değildir.

Uzmanlık adları `regex_traits<char>` `"d"`tanır , `"s"`, `"w"` `"alnum"` `"alpha"` `"blank"` `"cntrl"` `"digit"` `"space"` `"upper"` `"xdigit"`, , , , , , , , , , , , , , , , ve , tüm durumda bakılmaksızın. `"graph"` `"lower"` `"print"` `"punct"`

Uzmanlık adları `regex_traits<wchar_t>` `L"d"`tanır , `L"s"`, `L"w"` `L"alnum"` `L"alpha"` `L"blank"` `L"cntrl"` `L"digit"` `L"space"` `L"upper"` `L"xdigit"`, , , , , , , , , , , , , , , , ve , tüm durumda bakılmaksızın. `L"graph"` `L"lower"` `L"print"` `L"punct"`

## <a name="regex_traitslookup_collatename"></a><a name="lookup_collatename"></a>regex_traits:lookup_collatename

Bir diziyi bir harmanlama öğesiyle eşler.

```cpp
template <class FwdIt>
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Yukarı bakmak için sıranın başlangıcı.

*Son*\
Bakmak için sıranın sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlev, diziye `[first, last)`karşılık gelen harmanlama öğesini içeren bir dize nesnesi veya dizi geçerli bir harmanlama öğesi değilse boş bir dize döndürür.

## <a name="regex_traitsregex_traits"></a><a name="regex_traits"></a>regex_traits:regex_traits

Nesneyi inşa eder.

```cpp
regex_traits();
```

### <a name="remarks"></a>Açıklamalar

Kurucu, depolanan `locale` nesnevarsayılan yerel ekime başharfle çevrilmiş bir nesne oluşturuyor.

## <a name="regex_traitssize_type"></a><a name="size_type"></a>regex_traits::size_type

Sıra uzunluğunun türü.

```cpp
typedef T6 size_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef imzasız integral türü için eşanlamlıdır. Uzmanlık ve `regex_traits<char>` `regex_traits<wchar_t>` için `std::size_t`eşanlamlıdır.

Typedef için `std::size_t`eşanlamlıdır.

## <a name="regex_traitsstring_type"></a><a name="string_type"></a>regex_traits:string_type

Bir öğe dizisinin türü.

```cpp
typedef basic_string<Elem> string_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef için `basic_string<Elem>`eşanlamlıdır.

## <a name="regex_traitstransform"></a><a name="transform"></a>regex_traits::dönüşüm

Eşdeğer sıralı sıraya dönüştürür.

```cpp
template <class FwdIt>
string_type transform(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürmek için sıranın başlangıcı.

*Son*\
Dönüşmek için dizinin sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu `locale` bir dize döndürür. `[first1, last1)` Yineleyici aralıkları tarafından belirlenen iki karakter dizisi `[first2, last2)` `transform(first1, last1) < transform(first2, last2)` için ve , eğer yineleyici aralığı `[first1, last1)` tarafından belirlenen karakter dizisi, yineleyici `[first2, last2)`aralığı tarafından belirlenen karakter dizisi önce sıralanır.

## <a name="regex_traitstransform_primary"></a><a name="transform_primary"></a>regex_traits:transform_primary

Eşdeğer örneksiz sıralı sıraya dönüştürür.

```cpp
template <class FwdIt>
string_type transform_primary(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürmek için sıranın başlangıcı.

*Son*\
Dönüşmek için dizinin sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu `locale` bir dize döndürür. Yineleyici `[first1, last1)` aralıkları tarafından belirlenen iki karakter dizileri için ve `[first2, last2)`eğer `transform_primary(first1, last1) < transform_primary(first2, last2)` karakter dizisi yineleme `[first1, last1)` aralığı tarafından belirlenen karakter dizisi büyük/küçük harf veya aksan dikkate almadan yineleyici aralığı `[first2, last2)` tarafından belirlenen karakter dizisi önce sıralanır.

## <a name="regex_traitstranslate"></a><a name="translate"></a>regex_traits::çevir

Eşdeğer eşleştirme öğesine dönüştürür.

```cpp
char_type translate(char_type ch) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Dönüştürülecek öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu `locale` bir karakteri döndürür. İki `char_type` nesne `ch1` için `ch2` `translate(ch1) == translate(ch2)` ve, `ch1` `ch2` yalnızca biri normal ifade tanımında oluşursa ve diğeri yerel duruma duyarlı bir eşleşme için hedef sırada karşılık gelen bir konumda oluşursa eşleşirse.

## <a name="regex_traitstranslate_nocase"></a><a name="translate_nocase"></a>regex_traits:translate_nocase

Eşdeğer örneksiz eşleştirme öğesine dönüştürür.

```cpp
char_type translate_nocase(char_type ch) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Dönüştürülecek öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu `locale` bir karakteri döndürür. İki `char_type` nesne `ch1` için `ch2` `translate_nocase(ch1) == translate_nocase(ch2)` ve, `ch1` `ch2` yalnızca biri normal ifade tanımında oluşursa ve diğeri de büyük/küçük harf duyarsız eşleşmesi için hedef sırada karşılık gelen bir konumda oluşursa eşleşirse.

## <a name="regex_traitsvalue"></a><a name="value"></a>regex_traits::değer

Bir öğeyi basamak değerine dönüştürür.

```cpp
int value(Elem ch, int radix) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Dönüştürülecek öğe.

*Radix*\
Kullanılacak aritmetik taban.

### <a name="remarks"></a>Açıklamalar

Üye işlev, temel radix'teki *ch* karakteri tarafından temsil edilen *ch* değeri veya -1'i temel *radix'te*geçerli bir basamak değilse döndürür. *radix* İşlev yalnızca 8, 10 veya *16'lık bir radiks* bağımsız değişkeniyle çağrılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)\
[regex_error Sınıfı](../standard-library/regex-error-class.md)\
[\<regex> fonksiyonları](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)\
[regex_traits\<char> Sınıfı](../standard-library/regex-traits-char-class.md)\
[regex_traits\<wchar_t> Sınıfı](../standard-library/regex-traits-wchar-t-class.md)
