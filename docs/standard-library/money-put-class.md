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
ms.openlocfilehash: b9dff8a871895eee6774b75ca1c83dca6fd42ff3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460229"
---
# <a name="moneyput-class"></a>money_put Sınıfı

Şablon sınıfı, parasal değerlerin tür `CharType`dizilerine dönüştürmelerini denetlemek için bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*OutputIterator*\
Parasal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_put](#money_put)|Türündeki `money_put`nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|Türünde `CharType`karakterler içeren bir dizeyi tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[konur](#put)|Bir sayı ya da dizeyi parasal bir değeri temsil eden bir karakter dizisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="char_type"></a>money_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType**şablon parametresi için bir eş anlamlı.

## <a name="do_put"></a>money_put::d o_put

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

*ileri*\
Ekli dizenin ilk öğesini adresleyen bir yineleyici.

*_Intl*\
Dizide beklenen para birimi sembolünün türünü belirten bir Boole **değeri: Uluslararası** , yurtiçi ise **false** .

*_Iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir

*_Doldur*\
Aralık için kullanılan bir karakter.

*Acil*\
Dönüştürülecek dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi, [string_type](#string_type) nesne *Val*' den parasal bir çıkış alanı üretmek için *Next* ' ten başlayarak ardışık öğeleri oluşturur. *Val* tarafından denetlenen sıra bir veya daha fazla ondalık basamakla başlamalı ve isteğe bağlı olarak, miktarı temsil eden eksi işareti (-) gelmelidir. İşlevi, oluşturulan parasal çıktı alanının ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür.

İkinci sanal korumalı üye işlevi, ilk olarak bir ondalık basamak dizisine, isteğe bağlı olarak eksi işaretine ve  ardından bu sırayı yukarıya dönüştürür.

Parasal çıkış alanının biçimi, (geçerli) çağrısı [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **Intl**> > ( **iosbase**) tarafından döndürülen [yerel ayar modeli](../standard-library/locale-class.md#facet_class) fac tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)).

Engelle

- **fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format) , alanın bileşenlerinin negatif olmayan bir değer için oluşturulma sırasını belirler.

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) , alanın bileşenlerinin negatif bir değer için oluşturulma sırasını belirler.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bir para birimi sembolü için oluşturulacak öğelerin sırasını belirler.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) pozitif bir işaret için oluşturulacak öğelerin sırasını belirler.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) negatif bir işaret için oluşturulacak öğelerin sırasını belirler.

- **fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran öğeyi belirler.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) herhangi bir kesir basamağının tamsayı rakamlarını ayıran öğeyi belirler.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) , herhangi bir ondalık noktanın sağında bulunan önemli kesir basamak sayısını belirler.

İmza dizesi varsa ( **fac**. `negative_sign`or **fac**. `positive_sign`) birden fazla öğe içeriyor, yalnızca ilk öğe, öğe biçim düzeninde ( **fac**. `neg_format`or **fac**. `pos_format`). Kalan öğeler parasal çıktı alanının sonunda oluşturulur.

Eğer **iosbase**ise. [](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) bayrakları sıfır değil, dize **fac**. `curr_symbol`öğe, biçim düzeninde **money_base:: symbol** öğesine eşit olduğunda oluşturulur. Aksi takdirde, para birimi simgesi oluşturulmaz.

**Fac**tarafından gruplandırma kısıtlaması yoksa. **Gruplandırma** (ilk öğesi CHAR_MAX değerine sahiptir), sonra **fac**örneği yoktur. `thousands_sep`, parasal çıktı alanının değer bölümünde oluşturulur (öğe, **money_base:: değeri** , biçim deseninin içinde görünür). **Fac**. `frac_digits`sıfır, sonra **fac**örneği yok. `decimal_point`ondalık basamaklardan sonra oluşturulur. Aksi takdirde, sonuçta elde edilen parasal çıktı alanı düşük sipariş **fac**koyar. `frac_digits`ondalık noktanın sağ tarafındaki ondalık basamaklar.

Doldurma, herhangi bir sayısal çıkış alanı için, yani **iosbase**dışında gerçekleşir. bayraklar & **ıosbase**. [iç](../standard-library/ios-functions.md#internal) sıfır dışı, öğenin **money_base:: boşluk** değerine eşit olduğu her türlü iç doldurma oluşturulur. Aksi halde, iç doldurma üretilen sıra 'dan önce oluşur. Doldurma karakteri **Fill**.

İşlevi **iosbase**'i çağırır. **Genişlik** (0) alanı genişliğini sıfıra sıfırlamak için.

### <a name="example"></a>Örnek

[PUT](#put)için, sanal üye işlevinin **PUT**tarafından çağrıldığı örneğe bakın.

## <a name="iter_type"></a>money_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **OutputIterator** şablon parametresi için bir eş anlamlı.

## <a name="money_put"></a>money_put::money_put

Türündeki `money_put`nesneler için Oluşturucu.

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)( `_Refs`) ile başlatır.

## <a name="put"></a>money_put::p UT

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

*ileri*\
Ekli dizenin ilk öğesini adresleyen bir yineleyici.

*_Intl*\
Dizide beklenen para birimi sembolünün türünü belirten bir Boole **değeri: Uluslararası** , yurtiçi ise **false** .

*_Iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir

*_Doldur*\
Aralık için kullanılan bir karakter.

*Acil*\
Dönüştürülecek dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevi [](#do_put)de do_put `next`döndürür `_Intl`( `_Iosbase` `_Fill`,,,, ).`val`

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

## <a name="string_type"></a>money_put::string_type

Türünde `CharType`karakterler içeren bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, nesneleri kaynak diziden öğe dizilerini depolayabilen [basic_string](../standard-library/basic-string-class.md) şablon sınıfının bir özelleştirmesi tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yerel ayar >](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
