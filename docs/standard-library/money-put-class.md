---
title: money_put Sınıfı
ms.date: 11/01/2018
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
ms.openlocfilehash: 346dd4f681432143c954ca125c3862fc6827db60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383548"
---
# <a name="moneyput-class"></a>money_put Sınıfı

Şablon sınıfı türü dizilerin parasal değerlere denetim dönüştürme bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan `CharType`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*Outputıterator*<br/>
Parasal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_put](#money_put)|Türündeki nesneler için oluşturucu `money_put`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|Türü karakterler içeren dizeyi tanımlayan tür `CharType`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[yerleştirme](#put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  money_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **CharType**.

## <a name="do_put"></a>  money_put::do_put

Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>Parametreler

*Sonraki*<br/>
Eklenen dizenin ilk öğeyi adresleyen bir yineleyici.

*_Intl*<br/>
Beklenen dizide para birimi simgesi türünü gösteren bir Boole değeri: **true** uluslararası varsa **false** yurtiçi durumunda.

*_Iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir

*_Fill*<br/>
Aralığı için kullanılan bir karakter.

*VAL*<br/>
Dönüştürülecek bir dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıkış yineleyici son öğenin ötesinde konumu bir adresleri üretilen.

### <a name="remarks"></a>Açıklamalar

Konumunda başlayan ardışık öğeleri ilk korumalı sanal üye işlevi oluşturur *sonraki* bir parasal çıkış alanını üretmek için [string_type](#string_type) nesne *val*. Tarafından denetlenen dizinin *val* bir eksi miktarını temsil eden işareti (-), isteğe bağlı olarak önünde bir veya daha fazla ondalık basamak ile başlamalıdır. İşlev oluşturulan parasal çıkış alanını ötesindeki ilk öğeyi gösteren bir yineleyici döndürür.

İkinci korumalı sanal üye işlevi, ilk olarak davranır dışındaki olan etkili bir şekilde ilk dönüştürür *val* eksi işareti, isteğe bağlı olarak önünde bir ondalık basamak dizisi sonra o sırada yukarıdaki dönüştürür.

Parasal çıkış alanını biçimi tarafından belirlenen [yerel ayar modeli](../standard-library/locale-class.md#facet_class) (etkin) çağrı tarafından döndürülen fac [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **INTL**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).

Özellikle:

- **Fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format) alan bileşenleri için negatif olmayan bir değer üretilir sırasını belirler.

- **Fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) alan bileşenleri için negatif bir değer üretilir sırasını belirler.

- **Fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bir para birimi sembolünün oluşturmak için öğelerin sırasını belirler.

- **Fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) için bir artı işareti oluşturmak için öğelerin sırasını belirler.

- **Fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) bir eksi işareti için oluşturmak için öğelerin sırasını belirler.

- **Fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) basamakların herhangi bir ondalık noktasının solunda nasıl gruplandığını belirler.

- **Fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) herhangi bir ondalık noktasının solunda rakamlar grupları ayıran belirler.

- **Fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) herhangi kesir basamaklardan tamsayı basamakları ayıran öğeyi belirler.

- **Fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) önemli basamağını herhangi bir ondalık noktasının sağındaki basamak sayısını belirler.

Varsa oturum dize ( **fac**. `negative_sign` veya **fac**. `positive_sign`) sahip birden fazla öğesi, yalnızca ilk öğesi oluşturulduğu eşit öğesi **money_base::sign** biçim deseni görünür ( **fac**. `neg_format` veya **fac**. `pos_format`). Kalan öğeler parasal çıkış alanını sonunda oluşturulur.

Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) sıfır değilse, dize **fac**. `curr_symbol` oluşturulduğu eşit öğesi **money_base::symbol** biçim deseni görünür. Aksi takdirde, hiçbir para birimi simgesi oluşturulur.

Gruplandırma kısıtlamalar tarafından uygulanan varsa **fac**. **Gruplandırma** (ilk öğesi CHAR_MAX değer varsa), ardından hiçbir örneklerini **fac**. `thousands_sep` parasal çıkış alanını değer kısmı oluşturulur (burada eşit öğesi **money_base::value** biçim deseni görünür). Varsa **fac**. `frac_digits` sıfır, ardından hiçbir örneği **fac**. `decimal_point` ondalık basamak oluşturulur. Aksi halde, sonuç parasal çıkış alanını düşük düzey yerleştirir **fac**. `frac_digits` Ondalık ayırıcının sağında ondalık basamaklar.

Doldurma gerçekleşir olması durumunda dışında herhangi bir sayısal çıkış alan sunamıyoruz **iosbase**. **bayrakları** & **iosbase**. [iç](../standard-library/ios-functions.md#internal) sıfır olmayan, her iç doldurma olan oluşturulduğu eşit öğesi **money_base::space** görünüyorsa biçim deseni görünür. Aksi takdirde, oluşturulan sıralı önce iç doldurma gerçekleşir. Doldurma karakteri **dolgu**.

İşlev çağrıları **iosbase**. **Genişlik**alan genişliği sıfırlamak için (0).

### <a name="example"></a>Örnek

İçin örneğe bakın [put](#put), sanal üye işlevi çağıran burada **put**.

## <a name="iter_type"></a>  money_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **Outputıterator.**

## <a name="money_put"></a>  money_put::money_put

Türündeki nesneler için oluşturucu `money_put`.

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*<br/>
Bellek yönetimi için nesne türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: nesne ömrü onu içeren yerel ayarlar tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerler tanımlanmadı.

Yok edici korumalı olduğundan doğrudan örnek mümkündür.

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="put"></a>  money_put::Put

Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürür.

```cpp
iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>Parametreler

*Sonraki*<br/>
Eklenen dizenin ilk öğeyi adresleyen bir yineleyici.

*_Intl*<br/>
Beklenen dizide para birimi simgesi türünü gösteren bir Boole değeri: **true** uluslararası varsa **false** yurtiçi durumunda.

*_Iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir

*_Fill*<br/>
Aralığı için kullanılan bir karakter.

*VAL*<br/>
Dönüştürülecek bir dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıkış yineleyici son öğenin ötesinde konumu bir adresleri üretilen.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlev dönüş [do_put](#do_put)( `next`, `_Intl`, `_Iosbase`, `_Fill`, `val`).

### <a name="example"></a>Örnek

```cpp
// money_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

int main()
{
    std::locale loc( "german_germany" );
    std::basic_stringstream<char> psz;

    psz.imbue(loc);
    psz.flags(psz.flags() | std::ios_base::showbase); // force the printing of the currency symbol
    std::use_facet<std::money_put<char> >(loc).put(std::basic_ostream<char>::_Iter(psz.rdbuf()), true, psz, ' ', 100012);
    if (psz.fail())
        std::cout << "money_put() FAILED" << std::endl;
    else
        std::cout << "money_put() = \"" << psz.rdbuf()->str() << "\"" << std::endl;
}
```

```Output
money_put() = "EUR1.000,12"
```

## <a name="string_type"></a>  money_put::string_type

Türü karakterler içeren dizeyi tanımlayan tür `CharType`.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_string](../standard-library/basic-string-class.md) kaynak dizisindeki öğelerin sıralarının, nesneleri depolayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
