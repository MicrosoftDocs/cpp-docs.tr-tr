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
ms.openlocfilehash: 035cc4e7b9cfac262979509bf7b4570e2c55336c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377421"
---
# <a name="money_put-class"></a>money_put Sınıfı

Sınıf şablonu, parasal değerlerin tür `CharType`dizilerine dönüşümlerini denetlemek için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*OutputIterator*\
Parasal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_put](#money_put)|Tür `money_put`nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|Tür `CharType`karakterleri içeren bir dize açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[Koymak](#put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="money_putchar_type"></a><a name="char_type"></a>money_put:char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **CharType**ile eş anlamlıdır.

## <a name="money_putdo_put"></a><a name="do_put"></a>money_put::do_put

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

*Sonraki*\
Eklenen dizenin ilk öğesini ele alan bir yineleyici.

*_Intl*\
Sırayla beklenen para birimi sembolü türünü gösteren bir Boolean değeri: **doğru** eğer uluslararası, **yanlış** eğer yerli.

*_Iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gerekli

*_Fill*\
Boşluk için kullanılan bir karakter.

*Val*\
Dönüştürülecek bir dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıktı yineleyici, üretilen son öğenin ötesindeki konumu ele alır.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye [işlev, string_type](#string_type) nesne *val'den*parasal bir çıkış alanı oluşturmak için *yanından* başlayarak sıralı elemanlar oluşturur. *Val* tarafından denetlenen dizi, isteğe bağlı olarak miktarı temsil eden bir eksi işareti (-) ile önce gelen bir veya daha fazla ondalık basamakla başlamalıdır. İşlev, oluşturulan parasal çıktı alanının ötesindeki ilk öğeyi ataan bir yineleyici döndürür.

İkinci sanal korumalı üye işlevi, val'i ilk olarak isteğe bağlı olarak eksi işaretinden önce gelen ondalık basamaklar *dizisine* dönüştürmesi ve sonra bu sırayı yukarıdaki gibi dönüştürmesi dışında ilk işlevi görür.

Parasal çıkış alanının biçimi (etkili)[moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **intl**> > **(iosbase)** [use_facet](../standard-library/locale-functions.md#use_facet) < çağrı tarafından döndürülen yerel [fac](../standard-library/locale-class.md#facet_class) tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)).

Daha ayrıntılı şekilde belirtmek gerekirse:

- **fac**. [pos_format,](../standard-library/moneypunct-class.md#pos_format) alanın bileşenlerinin negatif olmayan bir değer için oluşturulme sırasını belirler.

- **fac**. [neg_format,](../standard-library/moneypunct-class.md#neg_format) alan bileşenlerinin negatif bir değer için oluşturulme sırasını belirler.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bir para birimi sembolü için oluşturmak için öğelerin sırasını belirler.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) pozitif bir işaret oluşturmak için öğelerin sırasını belirler.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) negatif bir işaret oluşturmak için öğelerin sırasını belirler.

- **fac**. [gruplandırma,](../standard-library/moneypunct-class.md#grouping) basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırılmalarını belirler.

- **fac**. [thousands_sep,](../standard-library/moneypunct-class.md#thousands_sep) basamak gruplarını herhangi bir ondalık noktanın solunda ayıran öğeyi belirler.

- **fac**. [decimal_point,](../standard-library/moneypunct-class.md#decimal_point) tamsayı basamaklarını herhangi bir kesir basamaklarından ayıran öğeyi belirler.

- **fac**. [frac_digits,](../standard-library/moneypunct-class.md#frac_digits) herhangi bir ondalık noktanın sağındaki önemli kesir basamaklarının sayısını belirler.

Eğer işaret dizesi ( **fac**. `negative_sign`veya **fac**. `positive_sign`) birden fazla öğe vardır, yalnızca ilk öğe money_base eşit olduğu **oluşturulur::işareti** biçim deseni görünür ( **fac**. `neg_format`veya **fac**. `pos_format`). Kalan unsurlar parasal çıkış alanının sonunda oluşturulur.

Eğer **iosbase**. [bayraklar](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) sıfır değil, dize **fac**. `curr_symbol`öğenin money_base eşit olduğu yerde **oluşturulur::sembol** biçim deseninde görünür. Aksi takdirde, hiçbir para birimi simgesi oluşturulur.

Fac tarafından gruplandırma kısıtlamaları **fac**uygulanmazsa. **gruplandırma** (ilk öğesi CHAR_MAX değeri vardır), sonra **fac**örnekleri . `thousands_sep`parasal çıktı alanının değer kısmında oluşturulur (öğenin money_base eşit **olduğu::değer** biçim deseninde görünür). Eğer **fac**. `frac_digits`sıfır, sonra **fac**hiçbir örneği . `decimal_point`ondalık basamaklardan sonra oluşturulur. Aksi takdirde, ortaya çıkan parasal çıkış alanı düşük sıralı **fac**yerleştirir. `frac_digits`ondalık noktanın sağındaki ondalık basamaklar.

Dolgu herhangi bir sayısal çıkış alanı için oluşur, **iosbase**dışında . **bayraklar** & **iosbase**. [iç](../standard-library/ios-functions.md#internal) sıfır değildir, herhangi bir iç dolgu nerede eleman money_base eşit **oluşturulur::boşluk** görünürse, biçim deseninde görünür. Aksi takdirde, iç dolgu oluşturulan sıraönce oluşur. Dolgu karakteri **doldurulur.**

Fonksiyon **iosbase**çağırır. **alan genişliğini**sıfırlamak için genişlik (0)

### <a name="example"></a>Örnek

[Koymak](#put)için örneğe bakın , sanal üye işlevi **put**tarafından çağrılır.

## <a name="money_putiter_type"></a><a name="iter_type"></a>money_put:iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **OutputIterator** ile eş anlamlıdır.

## <a name="money_putmoney_put"></a><a name="money_put"></a>money_put:money_put

Tür `money_put`nesneleri için oluşturucu.

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_refs*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \>1: bu değerler tanımlı değildir.

Yıkıcı korunduğundan, doğrudan örnek yoktur.

Kurucu, temel nesnesini yerel olarak başlaşır:: **locale::**[fason](../standard-library/locale-class.md#facet_class)( ). `_Refs`

## <a name="money_putput"></a><a name="put"></a>money_put::put

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

*Sonraki*\
Eklenen dizenin ilk öğesini ele alan bir yineleyici.

*_Intl*\
Sırayla beklenen para birimi sembolü türünü gösteren bir Boolean değeri: **doğru** eğer uluslararası, **yanlış** eğer yerli.

*_Iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gerekli

*_Fill*\
Boşluk için kullanılan bir karakter.

*Val*\
Dönüştürülecek bir dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıktı yineleyici, üretilen son öğenin ötesindeki konumu ele alır.

### <a name="remarks"></a>Açıklamalar

Her iki üye `next`işlev `_Intl` `_Iosbase`de `_Fill` `val` [do_put](#do_put)döndürer ( , , , , .

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

## <a name="money_putstring_type"></a><a name="string_type"></a>money_put:string_type

Tür `CharType`karakterleri içeren bir dize açıklayan bir tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, nesneleri kaynak diziden öğelerin dizilerini depolayabilen sınıf [şablonu basic_string](../standard-library/basic-string-class.md) bir uzmanlık açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[fateks Sınıf](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
