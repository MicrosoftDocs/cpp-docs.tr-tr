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
ms.openlocfilehash: 67aef1ce52b6717ce6d6381429982cf660aa5e20
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457652"
---
# <a name="numget-class"></a>num_get Sınıfı

Tür `CharType` dizilerinin dize dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*InputIterator*\
Sayısal alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_get](#num_get)|Dizilerden sayısal değerler ayıklamak için `num_get` kullanılan türündeki nesneler için Oluşturucu.|

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

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="char_type"></a>  num_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType**şablon parametresi için bir eş anlamlı.

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

*adı*\
Sayının okunacağı karakter aralığının başlangıcı.

*soyadına*\
Sayının okunacağı karakter aralığının sonu.

*_Iosbase*\
Bayrakları dönüştürme tarafından kullanılan [ios_base](../standard-library/ios-base-class.md) .

*_Durum*\
Failbit durumu (bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate)) hata üzerine eklenir.

*Acil*\
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra Yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi,

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;
```

bir tam, boş olmayan  tamsayı giriş alanı tanınana kadar dizideki `[first, last)` ilk başlayan sıralı öğeleri eşleştirir. Başarılı olursa, bu alanı **Long**türünde eşdeğer değerine dönüştürür ve sonucu *Val*içinde depolar. İlk öğeyi sayısal giriş alanından daha fazla tanımlayarak bir yineleyici döndürür. Aksi takdirde, işlevi içinde `state` *değer* ve ayarlar `ios_base::failbit` ' da hiçbir şey depolar. Geçerli bir tamsayı giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri eşitse `last`, işlevi ' de `state`ayarlanır `ios_base::eofbit` .

Tamsayı girişi alanı, tarama işlevleri tarafından bir dosyadaki **karakter** öğelerinin serisini eşleştirmek ve dönüştürmek için kullanılan kurallara göre dönüştürülür. (Örneğin, her bir **char** öğesi basit, bire-bir, eşleme ile `Elem` türünde denk bir öğe ile eşlenir varsayılır.) Eşdeğer tarama dönüştürme belirtimi aşağıdaki şekilde belirlenir:

[](../standard-library/ios-functions.md#oct) `lo` [](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`İos_base:: Flags Oct ise, dönüştürme belirtimi olur. `iosbase.`

Onaltılı `iosbase.flags() & ios_base::basefield == ios_base::`ise, dönüştürme belirtimi olur. [](../standard-library/ios-functions.md#hex) `lx`

İse `iosbase.flags() & ios_base::basefield == 0`, dönüştürme belirtimi olur `li`.

Aksi takdirde, dönüştürme belirtimi olur `ld`.

Bir tamsayı girişi alanının biçimi, Call [use_facet](../standard-library/locale-functions.md#use_facet) `<` [PIN](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [ios_base:: getloc](../standard-library/ios-base-class.md#getloc)`())`çağrısı tarafından döndürülen [yerel ayar modeli](../standard-library/locale-class.md#facet_class) `fac` tarafından daha fazla belirlenir. Engelle

`fac.`[tuş takımı unct:: Grouping](../standard-library/numpunct-class.md#grouping) `()` basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler

`fac.`[tuş takımı unct:: thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran Sırayı belirler.

Sayısal giriş alanında hiçbir `fac.thousands_sep()` örnek gerçekleşmiyor ise, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, tarafından `fac.grouping()` uygulanan gruplandırma kısıtlamaları zorlanır ve ayırıcılar, tarama dönüştürme gerçekleşmeden önce kaldırılır.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `lu`aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **işaretsiz Long** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `lld`aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **Long Long** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `llu`aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **işaretsiz Long** Long türünde bir değere dönüştürür ve bu değeri *Val*içinde depolar.

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;
```

, tam, boş olmayan kayan nokta giriş alanı ile eşleşmesi endeavors hariç, ilki ile aynı şekilde davranır. `fac.`[tuş takımı unct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()` , tamsayı basamaklarını kesir basamaklarından ayıran diziyi belirler. Eşdeğer tarama dönüştürme belirticisi `lf`.

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

, tam, boş olmayan kayan nokta giriş alanı ile eşleşmesi endeavors hariç, ilki ile aynı şekilde davranır. `fac.`[tuş takımı unct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()` , tamsayı basamaklarını kesir basamaklarından ayıran diziyi belirler. Eşdeğer tarama dönüştürme belirticisi `lf`.

Dokuzuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyicisi `Lf`olması dışında, sekizinci ile aynı şekilde davranır.

Onuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

, eşdeğer tarama dönüştürme belirleyicisi `p`olması dışında, ilki ile aynı şekilde davranır.

Son (Eleventh) sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

, tüm endeavors, boş olmayan bir Boole girişi alanıyla eşleşmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, Boole giriş alanını **bool** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Boole girişi alanı iki formdan birini alır. Boolalpha false ise, dönüştürülmüş değerin 0 (false için) veya 1 (true için) olması dışında bir tamsayı girişi alanı ile aynıdır. [](../standard-library/ios-functions.md#boolalpha) `iosbase.flags() & ios_base::` `fac.`Aksi takdirde, dizi, bir Inor [unct:: falsename](../standard-library/numpunct-class.md#falsename) `()` (false için) veya [](../standard-library/numpunct-class.md#truename) `()` `fac.`sayısal tuş takımı:: truename (true için) ile eşleşmelidir.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından [](#get) `do_get`çağrıldığı Get için örneğe bakın.

## <a name="get"></a>num_get:: Get

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

*adı*\
Sayının okunacağı karakter aralığının başlangıcı.

*soyadına*\
Sayının okunacağı karakter aralığının sonu.

*_Iosbase*\
Bayrakları dönüştürme tarafından kullanılan [ios_base](../standard-library/ios-base-class.md) .

*_Durum*\
Failbit durumu (bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate)) hata üzerine eklenir.

*Acil*\
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra Yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri [do_get](#do_get)döndürür ( `first`, `last` `_Iosbase`,, `val`,). `_State`

İlk sanal korumalı üye işlevi, bir tam, boş olmayan tamsayı giriş alanı tanınıncaya kadar, `first`[ `last`,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı tür **uzunluğu** olarak eşdeğer değerine dönüştürür ve sonucu *Val*olarak depolar. İlk öğeyi sayısal giriş alanından daha fazla tanımlayarak bir yineleyici döndürür. Aksi takdirde, işlev *değer* ve kümeler `ios_base::failbit` içinde _ *durum*olarak hiçbir şey depolar. Geçerli bir tamsayı giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse, işlev `ios_base::eofbit` *_State*olarak ayarlanır.

Tamsayı girişi alanı, tarama işlevleri tarafından bir dosyadaki **karakter** öğelerinin serisini eşleştirmek ve dönüştürmek için kullanılan kurallara göre dönüştürülür. Her bir **char** öğesi, basit, bire bir eşleme ile türünde `CharType` eşdeğer bir öğeyle eşlenecek şekilde varsayılır. Eşdeğer tarama dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer `iosbase`. [bayrak](../standard-library/ios-base-class.md#flags) & [Eki,](../standard-library/ios-functions.md#oct)dönüştürme belirtimi .`lo``ios_base::basefield` == `ios_base::`

- **İosbase. Flags** & **ios_base:: basefield** == `ios_base::`[onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi olur `lx`.

- Eğer **iosbase. Flags** & **ios_base:: basefield** = = 0 ise, dönüştürme belirtimi olur `li`.

- Aksi takdirde, dönüştürme belirtimi olur `ld`.

Bir tamsayı girişi alanının biçimi, Call [use_facet](../standard-library/locale-functions.md#use_facet) < [unct](../standard-library/numpunct-class.md) \< **eled**> ( **iosbase**) tarafından döndürülen [yerel ayar modeli](../standard-library/locale-class.md#facet_class)**fac** tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)). Engelle

- **fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler.

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) , basamak gruplarını herhangi bir ondalık noktanın soluna ayıran Sırayı belirler.

Eğer **fac**örneği yoksa. `thousands_sep`sayısal giriş alanında gerçekleşir, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, **fac**tarafından uygulanan gruplandırma kısıtlamaları. **Gruplandırma** zorlanır ve ayırıcılar, tarama dönüştürme gerçekleşmeden önce kaldırılır.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `lu`aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **işaretsiz Long** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

, tam, boş olmayan bir kayan nokta giriş alanını eşleştirmeyi denediğinden, ilki ile aynı şekilde davranır. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer tarama dönüştürme belirticisi `lf`.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyicisi `Lf`olması dışında, üçüncüsü aynı şekilde davranır.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

, eşdeğer tarama dönüştürme belirleyicisi `p`olması dışında, ilki ile aynı şekilde davranır.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

, tümü, boş olmayan bir Boole giriş alanını eşleştirmeyi denediğinden, ilki ile aynı şekilde davranır. Başarılı olursa, Boole giriş alanını **bool** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Boole girişi alanı iki formdan birini alır. Eğer **iosbase**ise.  & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) bayrakları **false**ise, dönüştürülmüş değerin 0 ( **false**için) veya 1 ( **true**için) olması dışında bir tamsayı girişi alanı ile aynıdır. Aksi takdirde, sıranın **fac**ile eşleşmesi gerekir. [falsename](../standard-library/numpunct-class.md#falsename) ( **false**için) veya **fac**. [truename](../standard-library/numpunct-class.md#truename) ( **true**için).

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

## <a name="iter_type"></a>num_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `InputIterator`için bir eş anlamlı.

## <a name="num_get"></a>num_get::num_get

Dizilerden sayısal değerler ayıklamak için `num_get` kullanılan türündeki nesneler için Oluşturucu.

```cpp
explicit num_get(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: Nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)( `_Refs`) ile başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yerel ayar >](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
