---
title: num_get Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_get
- locale/std::num_get::char_type
- locale/std::num_get::iter_type
- locale/std::num_get::do_get
- locale/std::num_get::get
helpviewer_keywords:
- std::num_get [C++]
- std::num_get [C++], char_type
- std::num_get [C++], iter_type
- std::num_get [C++], do_get
- std::num_get [C++], get
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
ms.openlocfilehash: c0984c15e2bf1682fc902264f47f340d0bd3c859
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472767"
---
# <a name="numget-class"></a>num_get Sınıfı

Tür dönüştürülmelerini denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı `CharType` sayısal değerleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*Inputıterator*<br/>
Sayısal alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_get](#num_get)|Türündeki nesneler için oluşturucu `num_get` dizilerden sayısal değerler ayıklamak için kullanılır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_get](#do_get)|Bir karakter dizisinden sayısal veya Boolean değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Bir karakter dizisinden sayısal veya Boolean değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  num_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **CharType**.

## <a name="do_get"></a>  num_get::do_get

Bir karakter dizisinden sayısal veya Boolean değeri ayıklamak için çağrılan sanal işlev.

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Sayı okunacak karakter aralığı başlangıcı.

*Son*<br/>
Sayı okunacak karakter aralığı sonu.

*_Iosbase*<br/>
[İos_base](../standard-library/ios-base-class.md) olan bayrakları dönüştürme tarafından kullanılır.

*Duru_m*<br/>
Hangi failbit durumuna (bkz [ios_base::iostate](../standard-library/ios-base-class.md#iostate)) başarısızlık durumunda eklenir.

*VAL*<br/>
Değer okundu.

### <a name="return-value"></a>Dönüş Değeri

Değer okuduktan sonra yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk korumalı sanal üye işlevi

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;
```

konumunda başlayan ardışık öğeleri eşleşen *ilk* dizideki `[first, last)` tam tanıdığını kadar alan boş olmayan bir tamsayı girin. Başarılı, bu alan eşdeğeri değer türü olarak dönüştürür, **uzun**ve sonuçta depolar *val*. Sayısal giriş alanını ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Aksi takdirde, hiçbir işlev depolar *val* ve ayarlar `ios_base::failbit` içinde `state`. Geçerli bir tamsayı giriş alanının herhangi bir önek ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse `last`, işlev kümeleri `ios_base::eofbit` içinde `state`.

Tamsayı giriş alanı eşleştirme ve bir dizi dönüştürme için tarama işlevleri tarafından kullanılan aynı kurallara göre dönüştürülür **char** dosyasından öğeleri. (Her gibi **char** öğesi türünde eşdeğer bir öğe eşlemek için varsayılır `Elem` basit bir, bire bir, eşleme.) Eşdeğer tarama dönüştürme belirtimi şu şekilde belirlenir:

Varsa `iosbase.` [ios_base::flags](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`[Eki](../standard-library/ios-functions.md#oct), dönüştürme belirtimi `lo`.

Varsa `iosbase.flags() & ios_base::basefield == ios_base::` [onaltılık](../standard-library/ios-functions.md#hex), dönüştürme belirtimi `lx`.

Varsa `iosbase.flags() & ios_base::basefield == 0`, dönüştürme belirtimi `li`.

Aksi takdirde, dönüştürme belirtimidir `ld`.

Daha fazla bir tamsayı giriş alanı biçimi tarafından belirlenir [yerel ayar modeli](../standard-library/locale-class.md#facet_class) `fac` çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet) `<` [numpunct](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [ios_base::getloc](../standard-library/ios-base-class.md#getloc)`())`. Özellikle:

`fac.` [numpunct::Grouping](../standard-library/numpunct-class.md#grouping) `()` basamakların herhangi bir ondalık noktasının solunda nasıl gruplandığını belirler

`fac.` [numpunct::thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran dizeyi belirler.

Örneği, `fac.thousands_sep()` oluşur sayısal giriş alanını hiçbir gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, gruplandırma kısıtlamalardan uygulanan tarafından `fac.grouping()` uygulanır ve ayırıcılar tarama dönüştürme gerçekleşmeden önce kaldırılır.

Dördüncü korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `lu`. Başarılı sayısal giriş alan türü bir değere dönüştürür, **işaretsiz uzun** ve değeri depolar *val*.

Beşinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `lld`. Başarılı sayısal giriş alan türü bir değere dönüştürür, **uzun uzun** ve değeri depolar *val*.

Altıncı korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `llu`. Başarılı sayısal giriş alan türü bir değere dönüştürür, **işaretsiz long long** ve değeri depolar *val*.

Yedinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;
```

bir tam, boş olmayan kayan nokta giriş alanını eşleştirilecek endeavors dışında ilk olarak aynı şekilde davranır. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point) `()` tamsayı basamak kesirli basamaklardan ayıran dizeyi belirler. Eşdeğer tarama dönüştürme belirleyici `lf`.

Sekizinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

bir tam, boş olmayan kayan nokta giriş alanını eşleştirilecek endeavors dışında ilk olarak aynı şekilde davranır. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point) `()` tamsayı basamak kesirli basamaklardan ayıran dizeyi belirler. Eşdeğer tarama dönüştürme belirleyici `lf`.

Dokuzuncu korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyicisine olması dışında sekizinci olarak aynı şekilde davranır `Lf`.

Onuncu korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

eşdeğer tarama dönüştürme belirleyicisine olması dışında ilk davranır `p`.

Son (eleventh) sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

bir tam, boş olmayan Boole giriş alanı eşleştirilecek endeavors dışında ilk olarak aynı şekilde davranır. Başarılı Boole giriş alanı türü bir değere dönüştürür, **bool** ve değeri depolar *val*.

Bir Boole giriş alanı iki biçimlerden birini alır. Varsa `iosbase.flags() & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) false olduğu tamsayı giriş alanını, aynı dışında dönüştürülen değer (false için) 0 veya 1 (true) olmalıdır. Dizi ya da aksi takdirde, eşleşmelidir `fac.` [numpunct::falsename](../standard-library/numpunct-class.md#falsename) `()` (için false), veya `fac.` [numpunct::truename](../standard-library/numpunct-class.md#truename) `()` (için true).

### <a name="example"></a>Örnek

Örneğin bakın [alma](#get), sanal üye işlevi çağıran burada `do_get`.

## <a name="get"></a>  num_get::get

Bir karakter dizisinden sayısal veya Boolean değeri ayıklar.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Sayı okunacak karakter aralığı başlangıcı.

*Son*<br/>
Sayı okunacak karakter aralığı sonu.

*_Iosbase*<br/>
[İos_base](../standard-library/ios-base-class.md) olan bayrakları dönüştürme tarafından kullanılır.

*Duru_m*<br/>
Hangi failbit durumuna (bkz [ios_base::iostate](../standard-library/ios-base-class.md#iostate)) başarısızlık durumunda eklenir.

*VAL*<br/>
Değer okundu.

### <a name="return-value"></a>Dönüş Değeri

Değer okuduktan sonra yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri dönüş [do_get](#do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`).

İlk korumalı sanal üye işlevi dizideki ilk konumunda başlayan ardışık öğeleri eşleştirmeyi dener [ `first`, `last`) tam tanıdığını kadar alan boş olmayan bir tamsayı girin. Başarılı, bu alan eşdeğeri değer türü olarak dönüştürür, **uzun** ve sonuçta depolar *val*. Sayısal giriş alanını ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Aksi takdirde, hiçbir işlev depolar *val* ve ayarlar `ios_base::failbit` _ içinde *durumu*. Geçerli bir tamsayı giriş alanının herhangi bir önek ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse *son*, işlev kümeleri `ios_base::eofbit` içinde *duru_m*.

Tamsayı giriş alanı eşleştirme ve bir dizi dönüştürme için tarama işlevleri tarafından kullanılan aynı kurallara göre dönüştürülür **char** dosyasından öğeleri. Her örneğin **char** öğesi türünde eşdeğer bir öğe eşlemek için varsayılır `CharType` ile basit, bire bir eşleştirerek. Eşdeğer tarama dönüştürme belirtimi şu şekilde belirlenir:

- Varsa `iosbase`. [bayrakları](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[Eki](../standard-library/ios-functions.md#oct), dönüştürme belirtimi `lo`.

- Varsa **iosbase.flags** & **ios_base::basefield** == `ios_base::`[onaltılık](../standard-library/ios-functions.md#hex), dönüştürme belirtimi `lx`.

- Varsa **iosbase.flags** & **ios_base::basefield** == 0, dönüştürme belirtimi `li`.

- Aksi takdirde, dönüştürme belirtimidir `ld`.

Daha fazla bir tamsayı giriş alanı biçimi tarafından belirlenir [yerel ayar modeli](../standard-library/locale-class.md#facet_class)**fac** çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct ](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). Özellikle:

- **Fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) basamakların herhangi bir ondalık noktasının solunda nasıl gruplandığını belirler.

- **Fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran dizeyi belirler.

Örneği, **fac**. `thousands_sep` sayısal giriş alanı ortaya, hiçbir gruplandırma kısıtlama sınırlamasıdır. Aksi takdirde, gruplandırma kısıtlamalardan uygulanan tarafından **fac**. **Gruplandırma** zorlanır ve ayırıcılar tarama dönüştürme gerçekleşmeden önce kaldırılır.

İkinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `lu`. Başarılı, sayısal giriş alanı türü bir değere dönüştürür, **işaretsiz uzun** ve değeri depolar *val*.

Üçüncü korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

bir tam, boş olmayan kayan nokta giriş alanını eşleştirmeye çalışır dışında ilk olarak aynı şekilde davranır. **Fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) tamsayı basamak kesirli basamaklardan ayıran dizeyi belirler. Eşdeğer tarama dönüştürme belirleyici `lf`.

Dördüncü korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyicisine olması dışında aynı şekilde davranır üçüncü `Lf`.

Beşinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

eşdeğer tarama dönüştürme belirleyicisine olması dışında ilk davranır `p`.

Altıncı korumalı sanal üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

bir tam, boş olmayan Boole giriş alanı eşleştirmeye çalışır dışında ilk olarak aynı şekilde davranır. Başarılı Boole giriş alanı türü bir değere dönüştürür, **bool** ve değeri depolar *val*.

Bir Boole giriş alanı iki biçimlerden birini alır. Varsa **iosbase**. **bayrakları** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) olduğu **false**, dönüştürülen değer ya da 0 olmalıdır, bir tamsayı giriş alanı ile aynı olmasıdır (için **false** ) veya 1 (için **true**). Dizi ya da aksi takdirde, eşleşmelidir **fac**. [falsename](../standard-library/numpunct-class.md#falsename) (için **false**), veya **fac**. [truename](../standard-library/numpunct-class.md#truename) (için **true**).

### <a name="example"></a>Örnek

```cpp
// num_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   basic_stringstream<char> psz, psz2;
   psz << "-1000,56";

   ios_base::iostate st = 0;
   long double fVal;
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;

   psz.imbue( loc );
   use_facet <num_get <char> >
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter(0), psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get( ) FAILED" << endl;
   else
      cout << "money_get( ) = " << fVal << endl;
}
```

## <a name="iter_type"></a>  num_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `InputIterator`.

## <a name="num_get"></a>  num_get::num_get

Türündeki nesneler için oluşturucu `num_get` dizilerden sayısal değerler ayıklamak için kullanılır.

```cpp
explicit num_get(size_t _Refs = 0);
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

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
