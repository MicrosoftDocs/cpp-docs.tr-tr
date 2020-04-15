---
title: money_get Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
ms.openlocfilehash: ac85e99bfb834fd970a804269f25ec9f20960a23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375910"
---
# <a name="money_get-class"></a>money_get Sınıfı

Sınıf şablonu, tür `CharType` dizilerinin parasal değerlere dönüşümlerini denetlemek için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*GirişIterator*\
Alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_get](#money_get)|Parasal değerleri temsil eden `money_get` dizilerden sayısal değerleri ayıklamak için kullanılan tür nesnelerinin oluşturucusu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|Tür `CharType`karakterleri içeren bir dize açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[do_get](#do_get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="money_getchar_type"></a><a name="char_type"></a>money_get:char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *CharType*ile eş anlamlıdır.

## <a name="money_getdo_get"></a><a name="do_get"></a>money_get::do_get

Parasal değeri temsil eden bir karakter dizisinden sayısal bir değer ayıklamak için çağrılan sanal işlev.

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*ıntl*\
Sırayla beklenen para birimi sembolü türünü gösteren bir Boolean değeri: **doğru** eğer uluslararası, **yanlış** eğer yerli.

*Iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmaske öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*Val*\
Dönüştürülen sırayı depolayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanının ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi, tam, boş olmayan `first` `last`parasal giriş alanını tanıyana kadar sıralı öğeleri ilk sırada [, ) olarak eşleştirmeye çalışır. Başarılı olursa, bu alanı bir veya daha fazla ondalık basamak tan oluşan bir sıraya `-`dönüştürür, isteğe bağlı olarak bir eksi işareti (), miktarı temsil eder ve sonucu [string_type](#string_type) nesne *val.'de*depolar. Parasal giriş alanının ötesindeki ilk öğeyi ataan bir yineleyici döndürür. Aksi takdirde, işlev *val* boş bir `ios_base::failbit` sıra yı depolar ve *Durum*ayarlar. Geçerli bir parasal giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade `last`değeri eşitse, işlev . `ios_base::eofbit` `State`

İkinci sanal korumalı üye işlevi, başarılı olursa isteğe bağlı olarak imzalanan basamak sırasını **uzun** çift tip bir değere dönüştürmesi ve bu değeri *val'de*depolaması dışında, ilkişlevi görür.

Parasal giriş alanının biçimi,[moneypunct](../standard-library/moneypunct-class.md) \< **CharType**( **intl**>> **(iosbase)** [use_facet](../standard-library/locale-functions.md#use_facet) < etkili çağrı ile**döndürülen** [yerel fac](../standard-library/locale-class.md#facet_class)tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)).

Daha ayrıntılı şekilde belirtmek gerekirse:

- **fac**. [neg_format,](../standard-library/moneypunct-class.md#neg_format) alanın bileşenlerinin oluşma sırasını belirler.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) para birimi sembolü oluşturan öğelerin sırasını belirler.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) pozitif bir işaret oluşturan öğelerin dizisini belirler.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) negatif bir işaret oluşturan öğelerin dizisini belirler.

- **fac**. [gruplandırma,](../standard-library/moneypunct-class.md#grouping) basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırılmalarını belirler.

- **fac**. [thousands_sep,](../standard-library/moneypunct-class.md#thousands_sep) basamak gruplarını herhangi bir ondalık noktanın solunda ayıran öğeyi belirler.

- **fac**. [decimal_point,](../standard-library/moneypunct-class.md#decimal_point) tamsayı basamaklarını kesir basamaklarından ayıran öğeyi belirler.

- **fac**. [frac_digits,](../standard-library/moneypunct-class.md#frac_digits) herhangi bir ondalık noktanın sağındaki önemli kesir basamaklarının sayısını belirler. Parasal bir tutarı, çağrıldığı ndan daha fazla kesir basamaklı `frac_digits`ayrıştırken, `do_get` çoğu `frac_digits` karakterde tüketen para ayrıştını durdurur.

Eğer işaret dizesi ( **fac**. `negative_sign`veya **fac**. `positive_sign`) birden fazla öğe vardır, sadece ilk öğe money_base eşit eleman **eşleştirilir::işareti** biçim deseni görünür ( **fac**. `neg_format`). Kalan unsurlar parasal giriş alanının sonunda eşleşir. Her iki dize de parasal giriş alanında bir sonraki öğeyle eşleşen ilk öğeye sahip değilse, işaret dizesi boş olarak alınır ve işaret pozitiftir.

Eğer **iosbase**. [bayraklar](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) sıfır değil, dize **fac**. `curr_symbol`öğenin money_base eşit olduğu yerle **eşleşmelidir::sembol** biçim deseninde görünür. Aksi takdirde, **money_base::sembol** biçim deseninin sonunda oluşursa ve işaret dizesinin hiçbir öğesi eşleşmeye devam ederse, para birimi simgesi eşleşmez. Aksi takdirde, para birimi simgesi isteğe bağlı olarak eşleşir.

Fac örnekleri **fac**yoksa . `thousands_sep`parasal giriş alanının değer kısmında (öğenin money_base eşit olduğu **durumlarda::değer** biçim deseninde görünür), gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, **fac**tarafından dayatılan herhangi bir gruplama kısıtlamaları. **gruplandırma** uygulanır. Elde edilen basamak dizisinin, düşük sıralı **fac'ı**olan bir karşıcıyı temsil ettiğini unutmayın. `frac_digits`ondalık basamaklar ondalık noktanın sağında kabul edilir.

Rasgele beyaz boşluk, öğenin money_base eşit olduğu yerde **eşleştirilir::boşluk** biçim deseninin sonundan başka bir yerde görünüyorsa biçim deseninde görünür. Aksi takdirde, hiçbir iç beyaz boşluk eşleşir. Bir eleman *ch* beyaz boşluk olarak kabul edilir eğer [use_facet](../standard-library/locale-functions.md#use_facet) < [ctype](../standard-library/ctype-class.md) \< **CharType**> > ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). [(](../standard-library/ctype-class.md#is) **ctype_base::boşluk**, *ch*) **doğrudur.**

### <a name="example"></a>Örnek

[Get](#get)için örneğe bakın `do_get`, hangi çağrıları .

## <a name="money_getget"></a><a name="get"></a>money_get::get

Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.

```cpp
iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*ıntl*\
Sırayla beklenen para birimi sembolü türünü gösteren bir Boolean değeri: **doğru** eğer uluslararası, **yanlış** eğer yerli.

*Iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gerekli

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*Val*\
Dönüştürülen sırayı depolayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanının ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlev de [do_get](#do_get)`(first, last, Intl, Iosbase, State, val)`döndürer.

### <a name="example"></a>Örnek

```cpp
// money_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;

int main( )
{
   locale loc( "german_germany" );

   basic_stringstream< char > psz;
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";
   basic_stringstream< char > psz2;
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();

   ios_base::iostate st = 0;
   long double fVal;

   psz.flags( psz.flags( )|ios_base::showbase );
   // Which forced the READING the currency symbol
   psz.imbue(loc);
   use_facet < money_get < char > >( loc ).
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"
           << endl;
   else
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "
           << fVal/100.0 << endl;

   use_facet < money_get < char > >( loc ).
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"
           << endl;
   else
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "
           << fVal/100.0 << endl;
};
```

## <a name="money_getiter_type"></a><a name="iter_type"></a>money_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür şablon parametre **InputIterator**için eşanlamlıdır.

## <a name="money_getmoney_get"></a><a name="money_get"></a>money_get:money_get

Parasal değerleri temsil eden `money_get` dizilerden sayısal değerleri ayıklamak için kullanılan tür nesnelerinin oluşturucusu.

```cpp
explicit money_get(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_refs*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Yıkıcı korunduğundan, doğrudan örnek yoktur.

Oluşturucu, temel nesnesini yerel olarak başlatleştirir:: **locale::**[fason](../standard-library/locale-class.md#facet_class)*(_Refs).*

## <a name="money_getstring_type"></a><a name="string_type"></a>money_get:string_type

**CharType**türünde karakterler içeren bir dize açıklayan bir tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü sınıf şablonu [basic_string](../standard-library/basic-string-class.md)bir uzmanlık açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[fateks Sınıf](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
