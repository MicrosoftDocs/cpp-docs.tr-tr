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
ms.openlocfilehash: 2a04e0f1c202717bb6d40a10f07475d78453ffd7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689042"
---
# <a name="regex_traits-class"></a>regex_traits Sınıfı

Eşleme için öğelerin özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class Elem>
class regex_traits
```

## <a name="parameters"></a>Parametreler

*Eled* \
Tanımlayacak karakter öğesi türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, *Eled*türü için çeşitli normal ifade nitelikleri tanımlar. Sınıf şablonu [Basic_regex sınıfı](../standard-library/basic-regex-class.md) , *eled*türündeki öğeleri işlemek için bu bilgileri kullanır.

Her `regex_traits` nesnesi, bazı üye işlevleri tarafından kullanılan `regex_traits::locale` türünde bir nesne barındırır. Varsayılan yerel ayar `regex_traits::locale()` kopyasıdır. Üye işlevi `imbue` locale nesnesinin yerini alır ve `getloc` üye işlevi, yerel ayar nesnesinin bir kopyasını döndürür.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_traits](#regex_traits)|Nesnesini oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_class_type](#char_class_type)|Karakter sınıfı gösterimlerinin türü.|
|[char_type](#char_type)|Öğenin türü.|
|[locale_type](#locale_type)|Depolanan yerel ayar nesnesinin türü.|
|[size_type](#size_type)|Dizi uzunluğunun türü.|
|[string_type](#string_type)|Öğelerin dize türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[getloc](#getloc)|Depolanan yerel ayar nesnesini döndürür.|
|[imbue](#imbue)|Depolanan yerel ayar nesnesini değiştirir.|
|[isctype](#isctype)|Sınıf üyeliğini sınar.|
|[uzunluklu](#length)|Null ile sonlandırılmış sıranın uzunluğunu döndürür.|
|[lookup_classname](#lookup_classname)|Bir diziyi bir karakter sınıfıyla eşleştirir.|
|[lookup_collatename](#lookup_collatename)|Bir diziyi harmanlama öğesiyle eşleştirir.|
|[Dönüşümler](#transform)|Eşit sıralı diziye dönüştürür.|
|[transform_primary](#transform_primary)|Eşit caseless sıralı dizisine dönüştürür.|
|[Çevir](#translate)|Eşdeğer eşleştirme öğesine dönüştürür.|
|[translate_nocase](#translate_nocase)|Eşdeğer caseless eşleştirme öğesine dönüştürür.|
|[value](#value)|Bir öğeyi basamak değerine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<regex >

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

## <a name="char_class_type"></a>regex_traits::char_class_type

Karakter sınıfı gösterimlerinin türü.

```cpp
typedef T8 char_class_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, karakter sınıfları atayan belirtilmemiş bir türün eşanlamlısıdır. Bu türün değerleri, işlenenler tarafından atanan sınıfların birleşimi olan karakter sınıflarını belirlemek için `|` işleci kullanılarak birleştirilebilir.

## <a name="char_type"></a>regex_traits::char_type

Öğenin türü.

```cpp
typedef Elem char_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, `Elem` şablon bağımsız değişkeninin eşanlamlısıdır.

## <a name="getloc"></a>regex_traits:: getloc

Depolanan yerel ayar nesnesini döndürür.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan `locale` nesnesini döndürür.

## <a name="imbue"></a>regex_traits:: imbue

Depolanan yerel ayar nesnesini değiştirir.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametreler

*loc* \
Depolanacak yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *loc* öğesini depolanan `locale` nesnesine kopyalar ve depolanan `locale` nesnesinin önceki değerinin bir kopyasını döndürür.

## <a name="isctype"></a>regex_traits:: SCC türü

Sınıf üyeliğini sınar.

```cpp
bool isctype(char_type ch, char_class_type cls) const;
```

### <a name="parameters"></a>Parametreler

*ch* \
Sınanacak öğe.

*cls* \
Sınanacak sınıflar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, yalnızca karakter *ch* , *CLS*tarafından belirlenen karakter sınıfında ise true değerini döndürür.

## <a name="length"></a>regex_traits:: length

Null ile sonlandırılmış sıranın uzunluğunu döndürür.

```cpp
static size_type length(const char_type *str);
```

### <a name="parameters"></a>Parametreler

*str* \
Null ile sonlandırılmış dizi.

### <a name="remarks"></a>Açıklamalar

Statik üye işlevi `std::char_traits<char_type>::length(str)` döndürür.

## <a name="locale_type"></a>regex_traits::locale_type

Depolanan yerel ayar nesnesinin türü.

```cpp
typedef T7 locale_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, yerel ayarları kapsülleyen bir türün eşanlamlısıdır. Özelleştirilmiş `regex_traits<char>` ve `regex_traits<wchar_t>` `std::locale` için bir eş anlamlı.

## <a name="lookup_classname"></a>regex_traits::lookup_classname

Bir diziyi bir karakter sınıfıyla eşleştirir.

```cpp
template <class FwdIt>
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*ilk* \
Aranacak sıra başlangıcı.

*son* \
Aranacak sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bağımsız değişkenlerine işaret eden karakter dizisi tarafından adlandırılan karakter sınıfını atayan bir değer döndürür. Değer dizideki karakterlerin durumuna bağlı değildir.

Özelleşme `regex_traits<char>` `"d"`, `"s"`, `"w"`, `"alnum"`, `"alpha"`, `"blank"`, `"cntrl"`, `"digit"`, `"graph"`, 0, 1, 2, 3 adlarını tanır , 4 ve 5, tümü büyük/küçük harf olmadan.

Özelleşme `regex_traits<wchar_t>` `L"d"`, `L"s"`, `L"w"`, `L"alnum"`, `L"alpha"`, `L"blank"`, `L"cntrl"`, `L"digit"`, `L"graph"`, 0, 1, 2, 3 adlarını tanır , 4 ve 5, tümü büyük/küçük harf olmadan.

## <a name="lookup_collatename"></a>regex_traits::lookup_collatename

Bir diziyi harmanlama öğesiyle eşleştirir.

```cpp
template <class FwdIt>
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*ilk* \
Aranacak sıra başlangıcı.

*son* \
Aranacak sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dizi `[first, last)` karşılık gelen harmanlama öğesini içeren bir dize nesnesi veya dizi geçerli bir harmanlama öğesi değilse boş bir dize döndürür.

## <a name="regex_traits"></a>regex_traits::regex_traits

Nesnesini oluşturur.

```cpp
regex_traits();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, depolanan `locale` nesnesi varsayılan yerel ayara başlatılmış bir nesne oluşturur.

## <a name="size_type"></a>regex_traits::size_type

Dizi uzunluğunun türü.

```cpp
typedef T6 size_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, işaretsiz integral türü için bir eş anlamlı. Özelleştirilmiş `regex_traits<char>` ve `regex_traits<wchar_t>` `std::size_t` için bir eş anlamlı.

TypeDef `std::size_t` için bir eş anlamlı.

## <a name="string_type"></a>regex_traits::string_type

Öğelerin dize türü.

```cpp
typedef basic_string<Elem> string_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef `basic_string<Elem>` için bir eş anlamlı.

## <a name="transform"></a>regex_traits:: Transform

Eşit sıralı diziye dönüştürür.

```cpp
template <class FwdIt>
string_type transform(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*ilk* \
Dönüştürülecek sıranın başlangıcı.

*son* \
Dönüştürülecek sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan `locale` nesnesine bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir dize döndürür. @No__t_0 ve `[first2, last2)` Yineleyici aralıkları tarafından belirlenen iki karakter dizisi için, yineleyici aralığı tarafından belirlenen karakter sırası `[first1, last1)` Yineleyici `[first2, last2)` aralığı tarafından belirlenen karakter sırasından önce sıralarken `transform(first1, last1) < transform(first2, last2)`.

## <a name="transform_primary"></a>regex_traits::transform_primary

Eşit caseless sıralı dizisine dönüştürür.

```cpp
template <class FwdIt>
string_type transform_primary(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*ilk* \
Dönüştürülecek sıranın başlangıcı.

*son* \
Dönüştürülecek sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan `locale` nesnesine bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir dize döndürür. @No__t_0 ve `[first2, last2)` Yineleyici aralıkları tarafından belirlenen iki karakter dizisi için, yineleyici aralığı tarafından belirlenen karakter sırası `[first1, last1)`, yineleyici `[first2, last2)` aralığı tarafından belirtilen karakter dizisinin önüne göre sıralama yapar `transform_primary(first1, last1) < transform_primary(first2, last2)` büyük/küçük harf veya aksan.

## <a name="translate"></a>regex_traits:: translate

Eşdeğer eşleştirme öğesine dönüştürür.

```cpp
char_type translate(char_type ch) const;
```

### <a name="parameters"></a>Parametreler

*ch* \
Dönüştürülecek öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan `locale` nesnesine bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir karakter döndürür. İki `char_type` nesne `ch1` ve `ch2` `translate(ch1) == translate(ch2)` yalnızca, normal ifade tanımında meydana gelirse ve diğeri yerel ayara duyarlı eşleşme için hedef dizide karşılık gelen bir konumda gerçekleşiyorsa `ch1` ve `ch2` eşleşmelidir.

## <a name="translate_nocase"></a>regex_traits::translate_nocase

Eşdeğer caseless eşleştirme öğesine dönüştürür.

```cpp
char_type translate_nocase(char_type ch) const;
```

### <a name="parameters"></a>Parametreler

*ch* \
Dönüştürülecek öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan `locale` nesnesine bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir karakter döndürür. İki `char_type` nesne `ch1` ve `ch2` `translate_nocase(ch1) == translate_nocase(ch2)` yalnızca, normal ifade tanımında meydana gelirse ve diğeri büyük/küçük harfe duyarsız eşleşme için hedef dizide karşılık gelen bir konumda gerçekleştiğinde `ch1` ve `ch2` eşleşmelidir.

## <a name="value"></a>regex_traits:: Value

Bir öğeyi basamak değerine dönüştürür.

```cpp
int value(Elem ch, int radix) const;
```

### <a name="parameters"></a>Parametreler

*ch* \
Dönüştürülecek öğe.

*taban* \
Kullanılacak aritmetik temel.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, taban *yarıçapına* *karakter olarak* temsil edilen değeri döndürür veya *ch* , taban *taban*içinde geçerli bir basamak değilse-1. İşlev yalnızca, 8, 10 veya 16 bir *taban* bağımsız değişkeniyle çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex >](../standard-library/regex.md) \
[Regex_constants sınıfı](../standard-library/regex-constants-class.md) \
[Regex_error sınıfı](../standard-library/regex-error-class.md) \
[\<regex > işlevleri](../standard-library/regex-functions.md) \
[Regex_iterator sınıfı](../standard-library/regex-iterator-class.md) \
[\<regex > işleçleri](../standard-library/regex-operators.md) \
[Regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) \
[\<regex > tür tanımları](../standard-library/regex-typedefs.md) \
[regex_traits \<char > sınıfı](../standard-library/regex-traits-char-class.md) \
[regex_traits \<wchar_t > sınıfı](../standard-library/regex-traits-wchar-t-class.md)
