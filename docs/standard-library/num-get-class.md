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
ms.openlocfilehash: bf6623bb61e7a217fcc18a268a583a7ecea4931d
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72889986"
---
# <a name="num_get-class"></a>num_get Sınıfı

Sayısal değerlere `CharType` türündeki dizilerin dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType* \
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*InputIterator* \
Sayısal alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_get](#num_get)|Dizilerden sayısal değerler ayıklamak için kullanılan `num_get` türündeki nesneler için Oluşturucu.|

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

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="char_type"></a>num_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType**şablon parametresi için bir eş anlamlı.

## <a name="do_get"></a>num_get::d o_get

Bir karakter dizisinden sayısal veya Boolean değeri ayıklamak için çağrılan sanal işlev.

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

### <a name="parameters"></a>Parametreler

*ilk* \
Sayının okunacağı karakter aralığının başlangıcı.

*son* \
Sayının okunacağı karakter aralığının sonu.

*iosbase* \
Bayrakları dönüştürme tarafından kullanılan [ios_base](../standard-library/ios-base-class.md) .

*durum* \
Failbit durumu (bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate)) hata üzerine eklenir.

*val* \
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra Yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi,

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;
```

bir tam, boş olmayan tamsayı giriş alanı kabul edene kadar, sıradaki *ilk* başlayan sıralı öğeleri eşler `[first, last)`. Başarılı olursa, bu alanı **Long**türünde eşdeğer değerine dönüştürür ve sonucu *Val*içinde depolar. İlk öğeyi sayısal giriş alanından daha fazla tanımlayarak bir yineleyici döndürür. Aksi takdirde, işlev *değer* olarak hiçbir şey depolar ve `state``ios_base::failbit` ayarlar. Geçerli bir tamsayı giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri `last`eşitse, işlev `state``ios_base::eofbit` belirler.

Tamsayı girişi alanı, tarama işlevleri tarafından bir dosyadaki **karakter** öğelerinin serisini eşleştirmek ve dönüştürmek için kullanılan kurallara göre dönüştürülür. (Böyle bir **char** öğesi, basit, bire-tek, eşleme tarafından `Elem` türünde bir eşdeğer öğeyle eşlenecek varsayılır.) Eşdeğer tarama dönüştürme belirtimi aşağıdaki şekilde belirlenir:

`iosbase.`[ios_base:: Flags](../standard-library/ios-base-class.md#flags) [Eki](../standard-library/ios-functions.md#oct)`() & ios_base::basefield == ios_base::`, dönüştürme belirtimi `lo`.

`iosbase.flags() & ios_base::basefield == ios_base::`[onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi `lx`.

`iosbase.flags() & ios_base::basefield == 0`, dönüştürme belirtimi `li`.

Aksi takdirde, dönüştürme belirtimi `ld`.

Bir tamsayı girişi alanının biçimi, Call `<`[use_facet](../standard-library/locale-functions.md#use_facet) tarafından döndürülen [yerel ayar esası](../standard-library/locale-class.md#facet_class)`fac` tarafından [belirlenir`<Elem>(iosbase.`](../standard-library/numpunct-class.md) [ios_base:: getloc](../standard-library/ios-base-class.md#getloc)`())`. Engelle

`fac.`[tuş takımı:: gruplandırma](../standard-library/numpunct-class.md#grouping)`()`, basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler

`fac.`[tuş takımı:: thousands_sep](../standard-library/numpunct-class.md#thousands_sep)`()`, basamak gruplarını herhangi bir ondalık noktanın soluna ayıran Sırayı belirler.

Sayısal giriş alanında `fac.thousands_sep()` örneği yoksa, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, `fac.grouping()` tarafından uygulanan gruplandırma kısıtlamaları zorlanır ve bu, tarama dönüştürme gerçekleşmeden önce ayırıcılar kaldırılır.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

, `ld` dönüştürme belirtimini `lu` ile değiştirmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **işaretsiz Long** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;
```

, `ld` dönüştürme belirtimini `lld` ile değiştirmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **Long Long** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;
```

, `ld` dönüştürme belirtimini `llu` ile değiştirmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **işaretsiz Long** Long türünde bir değere dönüştürür ve bu değeri *Val*içinde depolar.

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;
```

, tam, boş olmayan kayan nokta giriş alanı ile eşleşmesi endeavors hariç, ilki ile aynı şekilde davranır. `fac.`[tuş takımı::d ecimal_point](../standard-library/numpunct-class.md#decimal_point)`()`, tamsayı basamaklarını kesir basamaklarından ayıran Sırayı belirler. Eşdeğer tarama dönüştürme belirticisi `lf`.

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

, tam, boş olmayan kayan nokta giriş alanı ile eşleşmesi endeavors hariç, ilki ile aynı şekilde davranır. `fac.`[tuş takımı::d ecimal_point](../standard-library/numpunct-class.md#decimal_point)`()`, tamsayı basamaklarını kesir basamaklarından ayıran Sırayı belirler. Eşdeğer tarama dönüştürme belirticisi `lf`.

Dokuzuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

, eşdeğer tarama dönüştürme tanımlayıcısının `Lf` olması dışında, sekizinci ile aynı şekilde davranır.

Onuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

, eşdeğer tarama dönüştürme belirticisi `p` dışında, ilki aynı şekilde davranır.

Son (Eleventh) sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

, tüm endeavors, boş olmayan bir Boole girişi alanıyla eşleşmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, Boole giriş alanını **bool** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Boole girişi alanı iki formdan birini alır. `iosbase.flags() & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) false ise, dönüştürülmüş değerin 0 (false için) veya 1 (true için) olması dışında bir tamsayı girişi alanı ile aynıdır. Aksi takdirde, dizi `fac.` bir[sayısal tuş takımı:: falsename](../standard-library/numpunct-class.md#falsename) `()` (false için) veya `fac.`[sayısal tuş takımı:: truename](../standard-library/numpunct-class.md#truename) `()` (true için) ile aynı olmalıdır.

### <a name="example"></a>Örnek

Sanal üye işlevinin `do_get`tarafından çağrıldığı [Get](#get)için örneğe bakın.

## <a name="get"></a>num_get:: Get

Bir karakter dizisinden sayısal veya Boolean değeri ayıklar.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

### <a name="parameters"></a>Parametreler

*ilk* \
Sayının okunacağı karakter aralığının başlangıcı.

*son* \
Sayının okunacağı karakter aralığının sonu.

*iosbase* \
Bayrakları dönüştürme tarafından kullanılan [ios_base](../standard-library/ios-base-class.md) .

*durum* \
Failbit durumu (bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate)) hata üzerine eklenir.

*val* \
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra Yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri [do_get](#do_get)`( first, last, iosbase, state, val)`döndürür.

İlk sanal korumalı üye işlevi, bir tam, boş olmayan tamsayı giriş alanı tanınıncaya kadar [`first`, `last`) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı tür **uzunluğu** olarak eşdeğer değerine dönüştürür ve sonucu *Val*olarak depolar. İlk öğeyi sayısal giriş alanından daha fazla tanımlayarak bir yineleyici döndürür. Aksi takdirde, işlev *değer* olarak hiçbir şey depolar ve *durumu*`ios_base::failbit` ayarlar. Geçerli bir tamsayı giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse, işlev `ios_base::eofbit` *durumu*olarak ayarlanır.

Tamsayı girişi alanı, tarama işlevleri tarafından bir dosyadaki **karakter** öğelerinin serisini eşleştirmek ve dönüştürmek için kullanılan kurallara göre dönüştürülür. Her bir **char** öğesi, basit, bire bir eşleme tarafından `CharType` türünde eşdeğer bir öğeyle eşlenecek varsayılır. Eşdeğer tarama dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- ` & ios_base::basefield == ios_base::``iosbase.`[bayrak](../standard-library/ios-base-class.md#flags) , [dönüştürme](../standard-library/ios-functions.md#oct)belirtimi `lo`olur.

- `iosbase.flags & ios_base::basefield == ios_base::`[onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi `lx`.

- `iosbase.flags & ios_base::basefield == 0`, dönüştürme belirtimi `li`.

- Aksi takdirde, dönüştürme belirtimi `ld`.

Bir tamsayı girişi alanının biçimi,`<Elem>(iosbase.`[getloc](../standard-library/ios-base-class.md#getloc)`())`çağrısı [use_facet](../standard-library/locale-functions.md#use_facet) [`numpunct`](../standard-library/numpunct-class.md)`<`tarafından döndürülen [yerel ayar modeli](../standard-library/locale-class.md#facet_class) `fac` tarafından belirlenir. Engelle

- `fac.`[Gruplandırma](../standard-library/numpunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler.

- `fac.`[thousands_sep](../standard-library/numpunct-class.md#thousands_sep) , herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran Sırayı belirler.

Sayısal giriş alanında `fac.thousands_sep` örneği yoksa, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, `fac.grouping` tarafından uygulanan gruplandırma kısıtlamaları zorlanır ve bu, tarama dönüştürme gerçekleşmeden önce ayırıcılar kaldırılır.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

, `ld` dönüştürme belirtimini `lu` ile değiştirmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, sayısal giriş alanını **işaretsiz Long** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

, tam, boş olmayan bir kayan nokta giriş alanını eşleştirmeyi denediğinden, ilki ile aynı şekilde davranır. `fac.`[decimal_point](../standard-library/numpunct-class.md#decimal_point) , tamsayı basamaklarını kesir basamaklarından ayıran Sırayı belirler. Eşdeğer tarama dönüştürme belirticisi `lf`.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirticisi `Lf` dışında, üçüncüsü aynı şekilde davranır.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

, eşdeğer tarama dönüştürme belirticisi `p` dışında, ilki aynı şekilde davranır.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

, tümü, boş olmayan bir Boole giriş alanını eşleştirmeyi denediğinden, ilki ile aynı şekilde davranır. Başarılı olursa, Boole giriş alanını **bool** türünde bir değere dönüştürür ve bu değeri *Val*' de depolar.

Boole girişi alanı iki formdan birini alır. `iosbase.flags & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) **false**ise, dönüştürülmüş değerin 0 ( **false**için) veya 1 ( **true**için) olması dışında bir tamsayı girişi alanı ile aynıdır. Aksi takdirde, sıranın `fac.`[falsename](../standard-library/numpunct-class.md#falsename) ( **false**için) veya `fac.`[truename](../standard-library/numpunct-class.md#truename) ( **true**) ile eşleşmesi gerekir.

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

Tür, `InputIterator` şablon parametresi için bir eş anlamlı.

## <a name="num_get"></a>num_get::num_get

Dizilerden sayısal değerler ayıklamak için kullanılan `num_get` türündeki nesneler için Oluşturucu.

```cpp
explicit num_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refs* \
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu, temel nesnesini `locale::`[modeli](../standard-library/locale-class.md#facet_class)`(refs)`ile başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale >](../standard-library/locale.md) \
[model sınıfı](../standard-library/locale-class.md#facet_class) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
