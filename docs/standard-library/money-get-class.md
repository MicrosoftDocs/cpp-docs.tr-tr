---
title: money_get sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
dev_langs:
- C++
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cae819ccffae37ca27d1e062ae9a766e7acba1f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201757"
---
# <a name="moneyget-class"></a>money_get Sınıfı

Şablon sınıfı türü dönüştürülmelerini denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan `CharType` parasal değerleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
 Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*Inputıterator*<br/>
 Alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_get](#money_get)|Türündeki nesneler için oluşturucu `money_get` parasal değerleri temsil eden dizilerden sayısal değerler ayıklamak için kullanılır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|Türü karakterler içeren dizeyi tanımlayan tür `CharType`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_get](#do_get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  money_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *CharType*.

## <a name="do_get"></a>  money_get::do_get

İçin çağrılan sanal işlev parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.

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

*ilk*<br/>
 Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
 Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*Uluslararası*<br/>
 Beklenen dizide para birimi simgesi türünü gösteren bir Boole değeri: **true** uluslararası varsa **false** yurtiçi durumunda.

*iosbase*<br/>
 Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*State*<br/>
 İşlemleri veya başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*VAL*<br/>
 Dönüştürülmüş sıralı depolamak için bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk korumalı sanal üye işlevi dizideki ilk konumunda başlayan ardışık öğeleri eşleştirmeyi dener [ `first`, `last`) tam tanıdığını kadar alan boş olmayan parasal giriş. Başarılı, bu alan isteğe bağlı bir eksi işareti koyarak bir veya daha fazla ondalık basamak dizisi dönüştürür, ( `-`), miktarını temsil eder ve sonuçta depolar [string_type](#string_type) nesne *val*. Parasal giriş alanını ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Aksi takdirde, boş bir dizi işlev depolar *val* ve ayarlar `ios_base::failbit` içinde *durumu*. Geçerli bir parasal giriş alanını herhangi bir önek ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse `last`, işlev kümeleri `ios_base::eofbit` içinde `State`.

Başarılı olursa isteğe bağlı olarak imzalı bir basamak dizisi türü bir değere dönüştürür dışında ikinci korumalı sanal üye işlevi, ilk olarak davranır **uzun çift** ve değeri depolar *val*.

Bir parasal giriş alanını biçimi tarafından belirlenen [yerel ayar modeli](../standard-library/locale-class.md#facet_class)**fac** etkili çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet)  <  [ moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **INTL**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).

Özellikle:

- **Fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) alan bileşenleri oluşabilen sırasını belirler.

- **Fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) oluşturan bir para birimi simgesi öğelerin sırasını belirler.

- **Fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) oluşturan bir artı işareti öğelerin sırasını belirler.

- **Fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) oluşturan bir eksi işareti öğelerin sırasını belirler.

- **Fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) basamakların herhangi bir ondalık noktasının solunda nasıl gruplandığını belirler.

- **Fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) herhangi bir ondalık noktasının solunda rakamlar grupları ayıran belirler.

- **Fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) tamsayı basamak kesirli basamaklardan ayıran öğeyi belirler.

- **Fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) önemli basamağını herhangi bir ondalık noktasının sağındaki basamak sayısını belirler. İçin çağrılır daha fazla kesir basamağı ile bir parasal miktarını ayrıştırılırken `frac_digits`, `do_get` en fazla tükettikten sonra ayrıştırma durdurur `frac_digits` karakter.

Varsa oturum dize ( **fac**. `negative_sign` veya **fac**. `positive_sign`) sahip birden fazla öğe, yalnızca ilk öğeyi burada eşleşen öğe eşit **money_base::sign** biçim deseni görünür ( **fac**. `neg_format`). Kalan öğeler parasal giriş alanını sonunda eşleştirilir. Her iki dize parasal giriş alanını sonraki öğeyle eşleşen bir ilk öğe varsa, oturum dize boş olarak alınır ve oturum pozitiftir.

Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) sıfır değilse, dize **fac**. `curr_symbol` WHERE eşleşmelidir eşit öğesi **money_base::symbol** biçim deseni görünür. Aksi takdirde **money_base::symbol** biçim deseni sonunda gerçekleşir ve hiçbir öğe oturum dizenin eşleştirilecek kalırsa, para birimi simgesi yok eşleştirilir. Aksi takdirde, para birimi simgesi isteğe bağlı olarak eşleştirilir.

Örneği, **fac**. `thousands_sep` parasal giriş alanını değer kısmı oluşur (burada eşit öğesi **money_base::value** biçim deseni görünür), hiçbir gruplandırma kısıtlama sınırlamasıdır. Aksi takdirde, gruplandırma kısıtlamalardan uygulanan tarafından **fac**. **Gruplandırma** zorlanır. Sonuçta elde edilen basamak dizisi düşük sıralı bir tamsayı temsil ettiğini Not **fac**. `frac_digits` Ondalık ayırıcının sağında, ondalık basamak olarak kabul edilir.

Rastgele boşluk eşleşir yeri eşit öğesi **money_base::space** biçim deseni sonunda göründüğü dışındaki biçim deseni görüntülenir. Aksi takdirde, hiçbir iç boşluk eşleştirilir. Bir öğe *ch* boşluk kabul edildiği [use_facet](../standard-library/locale-functions.md#use_facet) < [ctype](../standard-library/ctype-class.md) \< **CharType**>> () **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). [olan](../standard-library/ctype-class.md#is)( **ctype_base::space**, *ch*) olan **true**.

### <a name="example"></a>Örnek

Örneğin bakın [alma](#get), çağıran `do_get`.

## <a name="get"></a>  money_get::get

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

*ilk*<br/>
 Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
 Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*Uluslararası*<br/>
 Beklenen dizide para birimi simgesi türünü gösteren bir Boole değeri: **true** uluslararası varsa **false** yurtiçi durumunda.

*iosbase*<br/>
 Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir

*State*<br/>
 İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*VAL*<br/>
 Dönüştürülmüş sıralı depolamak için bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlev dönüş [do_get](#do_get)`(first, last, Intl, Iosbase, State, val)`.

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

## <a name="iter_type"></a>  money_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **Inputıterator**.

## <a name="money_get"></a>  money_get::money_get

Türündeki nesneler için oluşturucu `money_get` parasal değerleri temsil eden dizilerden sayısal değerler ayıklamak için kullanılır.

```cpp
explicit money_get(size_t _Refs = 0);
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

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)(*_Refs*).

## <a name="string_type"></a>  money_get::string_type

Türü karakterler içeren dizeyi tanımlayan tür **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_string](../standard-library/basic-string-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
