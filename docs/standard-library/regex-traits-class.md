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
ms.openlocfilehash: a34346b4fc15beb605836037ef8a05a541562f33
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451514"
---
# <a name="regextraits-class"></a>regex_traits Sınıfı

Eşleme için öğelerin özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class Elem>
class regex_traits
```

## <a name="parameters"></a>Parametreler

*Elem*\
Tanımlayacak karakter öğesi türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, *Eled*türü için çeşitli normal ifade nitelikleri tanımlar. Şablon sınıfı [Basic_regex sınıfı](../standard-library/basic-regex-class.md) , *eled*türünde öğeleri işlemek için bu bilgileri kullanır.

Her `regex_traits` nesne, bazı üye işlevleri tarafından `regex_traits::locale` kullanılan türünde bir nesne barındırır. Varsayılan yerel ayar bir kopyasıdır `regex_traits::locale()`. Üye işlevi `imbue` yerel ayar nesnesinin yerini alır ve üye işlevi `getloc` yerel ayar nesnesinin bir kopyasını döndürür.

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
|[length](#length)|Null ile sonlandırılmış sıranın uzunluğunu döndürür.|
|[lookup_classname](#lookup_classname)|Bir diziyi bir karakter sınıfıyla eşleştirir.|
|[lookup_collatename](#lookup_collatename)|Bir diziyi harmanlama öğesiyle eşleştirir.|
|[transform](#transform)|Eşit sıralı diziye dönüştürür.|
|[transform_primary](#transform_primary)|Eşit caseless sıralı dizisine dönüştürür.|
|[Çevir](#translate)|Eşdeğer eşleştirme öğesine dönüştürür.|
|[translate_nocase](#translate_nocase)|Eşdeğer caseless eşleştirme öğesine dönüştürür.|
|[value](#value)|Bir öğeyi basamak değerine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Regex >

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

Tür, karakter sınıfları atayan belirtilmemiş bir türün eşanlamlısıdır. Bu türün değerleri, işlenenler tarafından atanan sınıfların birleşimi `|` olan karakter sınıflarını belirlemek için işleci kullanılarak birleştirilebilir.

## <a name="char_type"></a>regex_traits::char_type

Öğenin türü.

```cpp
typedef Elem char_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, şablon bağımsız değişkeninin `Elem`eşanlamlısıdır.

## <a name="getloc"></a>regex_traits:: getloc

Depolanan yerel ayar nesnesini döndürür.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı `locale` nesneyi döndürür.

## <a name="imbue"></a>regex_traits:: imbue

Depolanan yerel ayar nesnesini değiştirir.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametreler

*çerçeve*\
Depolanacak yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *loc* öğesini saklı `locale` nesnesine kopyalar ve saklanan `locale` nesnenin önceki değerinin bir kopyasını döndürür.

## <a name="isctype"></a>regex_traits:: SCC türü

Sınıf üyeliğini sınar.

```cpp
bool isctype(char_type ch, char_class_type cls) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Sınanacak öğe.

*CLS*\
Sınanacak sınıflar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, yalnızca karakter *ch* , *CLS*tarafından belirlenen karakter sınıfında ise true değerini döndürür.

## <a name="length"></a>regex_traits:: length

Null ile sonlandırılmış sıranın uzunluğunu döndürür.

```cpp
static size_type length(const char_type *str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Null ile sonlandırılmış dizi.

### <a name="remarks"></a>Açıklamalar

Statik üye işlevi döndürür `std::char_traits<char_type>::length(str)`.

## <a name="locale_type"></a>regex_traits::locale_type

Depolanan yerel ayar nesnesinin türü.

```cpp
typedef T7 locale_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, yerel ayarları kapsülleyen bir türün eşanlamlısıdır. Uzmanlıklar `regex_traits<char>` ve `regex_traits<wchar_t>` için `std::locale`bir eş anlamlı.

## <a name="lookup_classname"></a>regex_traits::lookup_classname

Bir diziyi bir karakter sınıfıyla eşleştirir.

```cpp
template <class FwdIt>
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak sıra başlangıcı.

*soyadına*\
Aranacak sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bağımsız değişkenlerine işaret eden karakter dizisi tarafından adlandırılan karakter sınıfını atayan bir değer döndürür. Değer dizideki karakterlerin durumuna bağlı değildir.

Özelleşme `regex_traits<char>` ,,, `"d"`,,,, `"alpha"`, `"blank"` `"s"`,, adlarını`"digit"`tanır `"w"` `"alnum"` `"cntrl"` `"graph"` `"lower"` ,`"print"`,,ve ,tümübüyük/`"xdigit"`küçük harf olmadan. `"punct"` `"space"` `"upper"`

Özelleşme `regex_traits<wchar_t>` ,,, `L"d"`,,,, `L"alpha"`, `L"blank"` `L"s"`,, adlarını`L"digit"`tanır `L"w"` `L"alnum"` `L"cntrl"` `L"graph"` `L"lower"` ,`L"print"`,,ve ,tümübüyük/`L"xdigit"`küçük harf olmadan. `L"punct"` `L"space"` `L"upper"`

## <a name="lookup_collatename"></a>regex_traits::lookup_collatename

Bir diziyi harmanlama öğesiyle eşleştirir.

```cpp
template <class FwdIt>
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak sıra başlangıcı.

*soyadına*\
Aranacak sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, diziye karşılık gelen `[first, last)`harmanlama öğesini içeren bir dize nesnesi veya dizi geçerli bir harmanlama öğesi değilse boş bir dize döndürür.

## <a name="regex_traits"></a>regex_traits::regex_traits

Nesnesini oluşturur.

```cpp
regex_traits();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, saklı `locale` nesnesi varsayılan yerel ayara başlatılmış bir nesne oluşturur.

## <a name="size_type"></a>regex_traits::size_type

Dizi uzunluğunun türü.

```cpp
typedef T6 size_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, işaretsiz integral türü için bir eş anlamlı. Uzmanlıklar `regex_traits<char>` ve `regex_traits<wchar_t>` için `std::size_t`bir eş anlamlı.

TypeDef, için `std::size_t`bir eş anlamlı.

## <a name="string_type"></a>regex_traits::string_type

Öğelerin dize türü.

```cpp
typedef basic_string<Elem> string_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, için `basic_string<Elem>`bir eş anlamlı.

## <a name="transform"></a>regex_traits:: Transform

Eşit sıralı diziye dönüştürür.

```cpp
template <class FwdIt>
string_type transform(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcı.

*soyadına*\
Dönüştürülecek sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı `locale` nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir dize döndürür. Yineleyici aralıkları `[first1, last1)` tarafından belirlenen iki karakter dizisi için `transform(first1, last1) < transform(first2, last2)` ve `[first2, last2)`yineleyici aralığı `[first1, last1)` tarafından belirlenen karakter sırası, yineleyici aralığı tarafından belirlenen karakter sırasından önce sıralarıyorsa `[first2, last2)`.

## <a name="transform_primary"></a>regex_traits::transform_primary

Eşit caseless sıralı dizisine dönüştürür.

```cpp
template <class FwdIt>
string_type transform_primary(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcı.

*soyadına*\
Dönüştürülecek sıra sonu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı `locale` nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir dize döndürür. Yineleyici aralıkları `[first1, last1)` tarafından belirlenen iki karakter dizisi için `transform_primary(first1, last1) < transform_primary(first2, last2)` ve `[first2, last2)`yineleyici aralığı `[first1, last1)` tarafından belirlenen karakter sırası, yineleyici aralığı tarafından belirlenen karakter sırasından önce sıralarıyorsa `[first2, last2)` büyük/küçük harf veya aksan olmadan.

## <a name="translate"></a>regex_traits:: translate

Eşdeğer eşleştirme öğesine dönüştürür.

```cpp
char_type translate(char_type ch) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Dönüştürülecek öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı `locale` nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir karakter döndürür. İki `char_type` nesne `ch1` için ve`ch2`, `ch1`yalnızcabir normal ifade tanımında meydana gelirse ve hedefte karşılık gelen bir konumda gerçekleşiyorsa eşleşmesi gerekir `ch2` `translate(ch1) == translate(ch2)` yerel ayara duyarlı eşleşme sırası.

## <a name="translate_nocase"></a>regex_traits::translate_nocase

Eşdeğer caseless eşleştirme öğesine dönüştürür.

```cpp
char_type translate_nocase(char_type ch) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Dönüştürülecek öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı `locale` nesneye bağlı bir dönüştürme kuralı kullanarak oluşturduğu bir karakter döndürür. İki `char_type` nesne `ch1` için ve`ch2`, `ch1`yalnızcabir normal ifade tanımında meydana gelirse ve hedefte karşılık gelen bir konumda gerçekleşiyorsa eşleşmesi gerekir `ch2` `translate_nocase(ch1) == translate_nocase(ch2)` büyük/küçük harf duyarsız eşleşme için sıra.

## <a name="value"></a>regex_traits:: Value

Bir öğeyi basamak değerine dönüştürür.

```cpp
int value(Elem ch, int radix) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Dönüştürülecek öğe.

*taban*\
Kullanılacak aritmetik temel.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, taban yarıçapına *karakter olarak* temsil edilen değeri döndürür veya *ch* , taban *taban*içinde geçerli bir basamak değilse-1. İşlev yalnızca, 8, 10 veya 16 bir *taban* bağımsız değişkeniyle çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<Regex > işlevleri](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<Regex > işleçleri](../standard-library/regex-operators.md)\
[regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[\<tür tanımları > Regex](../standard-library/regex-typedefs.md)\
[regex_traits\<char > sınıfı](../standard-library/regex-traits-char-class.md)\
[regex_traits\<wchar_t > sınıfı](../standard-library/regex-traits-wchar-t-class.md)
