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
ms.openlocfilehash: 76d2832141c65ca67c42f1994a3c8f5b532f0092
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373653"
---
# <a name="num_get-class"></a>num_get Sınıfı

Tür `CharType` dizilerinin sayısal değerlere dönüşümlerini denetlemek için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*GirişIterator*\
Sayısal alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_get](#num_get)|Dizilerden sayısal değerleri ayıklamak için kullanılan tür `num_get` nesnelerinin oluşturucusu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[do_get](#do_get)|Bir karakter dizisinden sayısal veya Boolean değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Bir karakter dizisinden sayısal veya Boolean değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="num_getchar_type"></a><a name="char_type"></a>num_get:char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **CharType**ile eş anlamlıdır.

## <a name="num_getdo_get"></a><a name="do_get"></a>num_get::do_get

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

*Ilk*\
Sayıyı okumak için karakter aralığının başlangıcı.

*Son*\
Sayıyı okumak için karakter aralığının sonu.

*iosbase*\
Bayrakları dönüşüm tarafından kullanılan [ios_base.](../standard-library/ios-base-class.md)

*Durum*\
Failbit 'in (bkz. [ios_base::iostate)](../standard-library/ios-base-class.md#iostate)hata üzerine eklendiği durum.

*Val*\
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra yineleyici.

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

tam, boş *first* olmayan bir `[first, last)` tamsayı giriş alanını tanıyana kadar sırayla ilk başta başlayan sıralı elemanlar ile eşleşir. Başarılı olursa, bu alanı **uzun**tür olarak eşdeğer değerine dönüştürür ve sonucu *val*olarak depolar. Sayısal giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, işlev *val* hiçbir `ios_base::failbit` `state`şey depolar ve ayarlar. Geçerli bir tamsayı giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade `last`değeri eşitse, işlev . `ios_base::eofbit` `state`

Tamsayı giriş alanı, bir dosyadan bir dizi **char** öğesini eşleştirmek ve dönüştürmek için scan işlevleri tarafından kullanılan aynı kurallarla dönüştürülür. (Her tür **char** öğesi basit, bire `Elem` bir, haritalama tarafından tür eşdeğer bir öğeiçin eşleme varsayılır.) Eşdeğer tazyik dönüştürme belirtimi aşağıdaki gibi belirlenir:

`iosbase.` [ios_base::flags](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`[oct](../standard-library/ios-functions.md#oct)ise, dönüşüm `lo`belirtimi .

`iosbase.flags() & ios_base::basefield == ios_base::` [Hex](../standard-library/ios-functions.md#hex)ise, dönüşüm `lx`belirtimi .

Eğer `iosbase.flags() & ios_base::basefield == 0`, dönüşüm `li`belirtimi .

Aksi takdirde, dönüştürme `ld`belirtimi .

Bir tamsayı giriş alanının biçimi, [numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.`[ios_base::getloc](../standard-library/ios-base-class.md#getloc)`())`arama [use_facet](../standard-library/locale-functions.md#use_facet) `<`döndürülen yerel [fason](../standard-library/locale-class.md#facet_class) `fac` tarafından daha da belirlenir. Daha ayrıntılı şekilde belirtmek gerekirse:

`fac.`[numpunct::gruplandırma,](../standard-library/numpunct-class.md#grouping) `()` basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırış edildiğini belirler

`fac.`[numpunct::thousands_sep,](../standard-library/numpunct-class.md#thousands_sep) `()` herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran sırayı belirler.

Sayısal giriş alanında `fac.thousands_sep()` hiçbir örnek oluşmazsa, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, tarafından `fac.grouping()` dayatılan gruplandırma kısıtlamaları zorlanır ve seperatörler tcan dönüştürme gerçekleşmeden önce kaldırılır.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `lu`çalışır. Başarılı olursa, sayısal giriş alanını **imzasız uzun** tür bir değere dönüştürür ve bu değeri *val'de*depolar.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `lld`çalışır. Başarılı olursa, sayısal giriş alanını **uzun** bir tür değerine dönüştürür ve bu değeri *val'de*depolar.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `llu`çalışır. Başarılı olursa, sayısal giriş alanını **imzasız uzun** bir tür değerine dönüştürür ve bu değeri *val'de*depolar.

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;
```

tam, boş olmayan kayan nokta giriş alanı eşleştirmeye çalışması dışında, ilki yle aynı şekilde olur. `fac.`[numpunct::decimal_point,](../standard-library/numpunct-class.md#decimal_point) `()` tamsayı basamaklarını kesir basamaklarından ayıran sırayı belirler. Eşdeğer tarayın dönüştürme belirtimi. `lf`

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

tam, boş olmayan kayan nokta giriş alanı eşleştirmeye çalışması dışında, ilki yle aynı şekilde olur. `fac.`[numpunct::decimal_point,](../standard-library/numpunct-class.md#decimal_point) `()` tamsayı basamaklarını kesir basamaklarından ayıran sırayı belirler. Eşdeğer tarayın dönüştürme belirtimi. `lf`

Dokuzuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

eşdeğer tarayın dönüştürme belirticisinin `Lf`.

Onuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

eşdeğer tarayın dönüştürme belirtimi nin `p`.

Son (onbirinci) sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

tam, boş olmayan boolean giriş alanı maç için çaba dışında, ilk aynı şekilde kalır. Başarılı olursa Boolean giriş alanını **bool** türüne dönüştürür ve bu değeri *val'de*depolar.

Boolean giriş alanı iki formdan birini alır. `iosbase.flags() & ios_base::` [Boolalpha](../standard-library/ios-functions.md#boolalpha) yanlışsa, dönüştürülen değerin 0 (false için) veya 1 (gerçek için) olması dışında, tamsayı giriş alanıyla aynıdır. Aksi takdirde, sıra `fac.` [numpunct eşleşmelidir::falsename](../standard-library/numpunct-class.md#falsename) `()` `fac.`(falsename için), veya [numpunct::truename](../standard-library/numpunct-class.md#truename) `()` (truename için).

### <a name="example"></a>Örnek

Almak [için](#get)örneğe bakın , sanal üye `do_get`işlevi tarafından çağrılır.

## <a name="num_getget"></a><a name="get"></a>num_get::get

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

*Ilk*\
Sayıyı okumak için karakter aralığının başlangıcı.

*Son*\
Sayıyı okumak için karakter aralığının sonu.

*iosbase*\
Bayrakları dönüşüm tarafından kullanılan [ios_base.](../standard-library/ios-base-class.md)

*Durum*\
Failbit 'in (bkz. [ios_base::iostate)](../standard-library/ios-base-class.md#iostate)hata üzerine eklendiği durum.

*Val*\
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevler [do_get](#do_get)`( first, last, iosbase, state, val)`döndürün.

İlk sanal korumalı üye işlevi, tam, boş olmayan `first` `last`bir tamsayı giriş alanını tanıyana kadar sıralı öğeleri ilk sırada [, ) olarak eşleştirmeye çalışır. Başarılı olursa, bu alanı **uzun** yazı olarak eşdeğer değerine dönüştürür ve sonucu *val*olarak depolar. Sayısal giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, işlev *val* hiçbir `ios_base::failbit` şey depolar ve *durum*ayarlar. Geçerli bir tamsayı giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade değeri *son* `ios_base::eofbit` eşitse, işlev *durum*olarak ayarlar.

Tamsayı giriş alanı, bir dosyadan bir dizi **char** öğesini eşleştirmek ve dönüştürmek için scan işlevleri tarafından kullanılan aynı kurallarla dönüştürülür. Bu tür **char** öğesi basit, bire `CharType` bir eşleme ile eşdeğer bir tür öğesi için eşleme varsayılır. Eşdeğer tazyik dönüştürme belirtimi aşağıdaki gibi belirlenir:

- `iosbase.` [Bayraklar](../standard-library/ios-base-class.md#flags)`& ios_base::basefield == ios_base::`[ekim](../standard-library/ios-functions.md#oct)ise, `lo`dönüşüm belirtimi .

- `iosbase.flags & ios_base::basefield == ios_base::` [Hex](../standard-library/ios-functions.md#hex)ise, dönüşüm `lx`belirtimi .

- Eğer `iosbase.flags & ios_base::basefield == 0`, dönüşüm `li`belirtimi .

- Aksi takdirde, dönüştürme `ld`belirtimi .

Bir tamsayı giriş alanının biçimi,[getloc](../standard-library/ios-base-class.md#getloc)`())` [use_facet](../standard-library/locale-functions.md#use_facet)`<`[`numpunct`](../standard-library/numpunct-class.md)`<Elem>(iosbase.`çağrı tarafından döndürülen [yerel fason](../standard-library/locale-class.md#facet_class) `fac` tarafından daha da belirlenir. Daha ayrıntılı şekilde belirtmek gerekirse:

- `fac.`[gruplandırma,](../standard-library/numpunct-class.md#grouping) basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırılmalarını belirler.

- `fac.`[thousands_sep,](../standard-library/numpunct-class.md#thousands_sep) basamak gruplarını herhangi bir ondalık noktanın solunda ayıran sırayı belirler.

Sayısal giriş alanında `fac.thousands_sep` hiçbir örnek oluşmazsa, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, tarafından `fac.grouping` dayatılan gruplandırma kısıtlamaları zorlanır ve skan dönüştürme gerçekleşmeden önce ayırıcılar kaldırılır.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `lu`çalışır. Başarılı olursa, sayısal giriş alanını **imzasız uzun** tür bir değere dönüştürür ve bu değeri *val'de*depolar.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

tam, boş olmayan kayan nokta giriş alanı eşleştirmeye çalışır dışında, ilk olarak aynı şekilde çalışır. `fac.`[decimal_point,](../standard-library/numpunct-class.md#decimal_point) tamsayı basamaklarını kesir basamaklarından ayıran sırayı belirler. Eşdeğer tarayın dönüştürme belirtimi. `lf`

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

eşdeğer tarayın dönüştürme belirtimi nin `Lf`.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

eşdeğer tarayın dönüştürme belirtimi nin `p`.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

tam, boş olmayan boolean giriş alanı eşleştirmeye çalışır dışında, ilk aynı şekilde çalışır. Başarılı olursa Boolean giriş alanını **bool** türüne dönüştürür ve bu değeri *val'de*depolar.

Bir boolean giriş alanı iki formdan birini alır. `iosbase.flags & ios_base::` [Boolalpha](../standard-library/ios-functions.md#boolalpha) **yanlışsa,** dönüştürülen değerin 0 **(false**için) veya 1 **(gerçek**için) olması dışında, tamsayı giriş alanıyla aynıdır. Aksi takdirde, sıra `fac.` [falsename](../standard-library/numpunct-class.md#falsename) **(false**name) veya `fac.` [truename](../standard-library/numpunct-class.md#truename) **(true**for true) eşleşmelidir.

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

## <a name="num_getiter_type"></a><a name="iter_type"></a>num_get:iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `InputIterator`ile eş anlamlıdır.

## <a name="num_getnum_get"></a><a name="num_get"></a>num_get:num_get

Dizilerden sayısal değerleri ayıklamak için kullanılan tür `num_get` nesnelerinin oluşturucusu.

```cpp
explicit num_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refler*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Yıkıcı korunduğundan, doğrudan örnek yoktur.

Oluşturucu, temel nesnesini `locale::` [fason](../standard-library/locale-class.md#facet_class)`(refs)`la başharfe doğrulaştırır.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[fateks Sınıf](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
