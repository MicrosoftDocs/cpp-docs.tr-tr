---
description: 'Hakkında daha fazla bilgi edinin: num_get sınıfı'
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
ms.openlocfilehash: 0236aac2e7c7859f966430bd276b4dffc42820b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338089"
---
# <a name="num_get-class"></a>num_get Sınıfı

Tür dizilerinin dize dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu `CharType` .

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
|[num_get](#num_get)|`num_get`Dizilerden sayısal değerler ayıklamak için kullanılan türündeki nesneler için Oluşturucu.|

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

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="num_getchar_type"></a><a name="char_type"></a> num_get:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType** şablon parametresi için bir eş anlamlı.

## <a name="num_getdo_get"></a><a name="do_get"></a> num_get::d o_get

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

*adı*\
Sayının okunacağı karakter aralığının başlangıcı.

*soyadına*\
Sayının okunacağı karakter aralığının sonu.

*iosbase*\
Bayrakları dönüştürme tarafından kullanılan [ios_base](../standard-library/ios-base-class.md) .

*durumunda*\
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
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;
```

 `[first, last)` bir tam, boş olmayan tamsayı giriş alanı tanınana kadar dizideki ilk başlayan sıralı öğeleri eşleştirir. Başarılı olursa, bu alanı türü olarak eşdeğer değerine dönüştürür **`long`** ve sonucu *Val* içinde depolar. İlk öğeyi sayısal giriş alanından daha fazla tanımlayarak bir yineleyici döndürür. Aksi takdirde, işlevi içinde *değer* ve Ayarlar ' da hiçbir şey depolar `ios_base::failbit` `state` . Geçerli bir tamsayı giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri eşitse `last` , işlevi ' de ayarlanır `ios_base::eofbit` `state` .

Tamsayı girişi alanı, tarama işlevleri tarafından bir dosyadaki bir dizi öğeyi eşleştirmek ve dönüştürmek için kullanılan kurallara göre dönüştürülür **`char`** . (Bu tür her **`char`** öğe, `Elem` basit, bire-tek, eşleme ile türünde eşdeğer bir öğeyle eşlenecek varsayılır.) Eşdeğer tarama dönüştürme belirtimi aşağıdaki şekilde belirlenir:

`iosbase.` [İos_base:: Flags](../standard-library/ios-base-class.md#flags) `() & ios_base::basefield == ios_base::` [Oct](../standard-library/ios-functions.md#oct)ise, dönüştürme belirtimi olur `lo` .

`iosbase.flags() & ios_base::basefield == ios_base::` [Onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi olur `lx` .

İse `iosbase.flags() & ios_base::basefield == 0` , dönüştürme belirtimi olur `li` .

Aksi takdirde, dönüştürme belirtimi olur `ld` .

Bir tamsayı girişi alanının biçimi, çağrı tarafından döndürülen [yerel ayar modeli](../standard-library/locale-class.md#facet_class) tarafından daha fazla belirlenir `fac` [use_facet](../standard-library/locale-functions.md#use_facet) `<` [](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [ios_base:: getloc](../standard-library/ios-base-class.md#getloc) `())` . Özellikle:

`fac.`[tuş takımı unct:: Grouping](../standard-library/numpunct-class.md#grouping) `()` basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler

`fac.`[sayısal tuş takımı:: thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran Sırayı belirler.

`fac.thousands_sep()`Sayısal giriş alanında hiçbir örnek gerçekleşmiyor ise, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, tarafından uygulanan gruplandırma kısıtlamaları `fac.grouping()` zorlanır ve ayırıcılar, tarama dönüştürme gerçekleşmeden önce kaldırılır.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `lu` . Başarılı olursa, sayısal giriş alanını türünde bir değere dönüştürür **`unsigned long`** ve bu değeri *Val*' de depolar.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `lld` . Başarılı olursa, sayısal giriş alanını türünde bir değere dönüştürür **`long long`** ve bu değeri *Val*' de depolar.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `llu` . Başarılı olursa, sayısal giriş alanını türünde bir değere dönüştürür **`unsigned long long`** ve bu değeri *Val*' de depolar.

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;
```

, tam, boş olmayan kayan nokta giriş alanı ile eşleşmesi endeavors hariç, ilki ile aynı şekilde davranır. `fac.`[tuş takımı unct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()` kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer tarama dönüştürme belirticisi `lf` .

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

, tam, boş olmayan kayan nokta giriş alanı ile eşleşmesi endeavors hariç, ilki ile aynı şekilde davranır. `fac.`[tuş takımı unct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()` kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer tarama dönüştürme belirticisi `lf` .

Dokuzuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyicisi olması dışında, sekizinci ile aynı şekilde davranır `Lf` .

Onuncu sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

, eşdeğer tarama dönüştürme belirleyicisi olması dışında, ilki ile aynı şekilde davranır `p` .

Son (Eleventh) sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

, tüm endeavors, boş olmayan bir Boole girişi alanıyla eşleşmesi dışında, ilki ile aynı şekilde davranır. Başarılı olursa, Boole giriş alanını türünde bir değere dönüştürür **`bool`** ve bu değeri *Val*' de depolar.

Boole girişi alanı iki formdan birini alır. `iosbase.flags() & ios_base::` [Boolalpha](../standard-library/ios-functions.md#boolalpha) false ise, dönüştürülmüş değerin 0 (false için) veya 1 (true için) olması dışında bir tamsayı girişi alanı ile aynıdır. Aksi takdirde, dizi, bir `fac.` Inor [unct:: falsename](../standard-library/numpunct-class.md#falsename) `()` (false için) veya `fac.` [sayısal tuş takımı:: truename](../standard-library/numpunct-class.md#truename) `()` (true için) ile eşleşmelidir.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [Get](#get)için örneğe bakın `do_get` .

## <a name="num_getget"></a><a name="get"></a> num_get:: Get

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

*adı*\
Sayının okunacağı karakter aralığının başlangıcı.

*soyadına*\
Sayının okunacağı karakter aralığının sonu.

*iosbase*\
Bayrakları dönüştürme tarafından kullanılan [ios_base](../standard-library/ios-base-class.md) .

*durumunda*\
Failbit durumu (bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate)) hata üzerine eklenir.

*Acil*\
Okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Değer okunduktan sonra Yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri [do_get](#do_get)döndürür `( first, last, iosbase, state, val)` .

İlk sanal korumalı üye işlevi, `first` `last` bir tam, boş olmayan tamsayı giriş alanı tanınıncaya kadar, [,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı türe eşit değerine dönüştürür **`long`** ve sonucu *Val* olarak depolar. İlk öğeyi sayısal giriş alanından daha fazla tanımlayarak bir yineleyici döndürür. Aksi takdirde, işlev *değer 'de değer* olarak hiçbir şey depolar ve `ios_base::failbit` *durum* olarak ayarlar. Geçerli bir tamsayı giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son* eşitse işlev `ios_base::eofbit` *durum* olarak ayarlanır.

Tamsayı girişi alanı, tarama işlevleri tarafından bir dosyadaki bir dizi öğeyi eşleştirmek ve dönüştürmek için kullanılan kurallara göre dönüştürülür **`char`** . Bu tür her **`char`** öğe `CharType` , basit, bire bir eşleme ile türünde eşdeğer bir öğeyle eşlenecek varsayılır. Eşdeğer tarama dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- `iosbase.` [Bayrak](../standard-library/ios-base-class.md#flags) `& ios_base::basefield == ios_base::` [Eki](../standard-library/ios-functions.md#oct)ise, dönüştürme belirtimi olur `lo` .

- `iosbase.flags & ios_base::basefield == ios_base::` [Onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi olur `lx` .

- İse `iosbase.flags & ios_base::basefield == 0` , dönüştürme belirtimi olur `li` .

- Aksi takdirde, dönüştürme belirtimi olur `ld` .

Bir tamsayı girişi alanının biçimi, [](../standard-library/locale-class.md#facet_class) `fac` [](../standard-library/locale-functions.md#use_facet) `<` [`numpunct`](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [getloc](../standard-library/ios-base-class.md#getloc) `())` use_facet çağrısı tarafından döndürülen yerel ayar modeli tarafından daha fazla belirlenir. Özellikle:

- `fac.`[Gruplandırma](../standard-library/numpunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler.

- `fac.`[thousands_sep](../standard-library/numpunct-class.md#thousands_sep) , herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran Sırayı belirler.

`fac.thousands_sep`Sayısal giriş alanında hiçbir örnek gerçekleşmiyor ise, gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, tarafından uygulanan gruplandırma kısıtlamaları, `fac.grouping` tarama dönüştürmesi gerçekleşmeden önce zorlanır ve ayırıcılar kaldırılır.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `lu` . Başarılı olursa, sayısal giriş alanını türünde bir değere dönüştürür **`unsigned long`** ve bu değeri *Val*' de depolar.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

, tam, boş olmayan bir kayan nokta giriş alanını eşleştirmeyi denediğinden, ilki ile aynı şekilde davranır. `fac.`[decimal_point](../standard-library/numpunct-class.md#decimal_point) , kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer tarama dönüştürme belirticisi `lf` .

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyicisi olması dışında, üçüncüsü aynı şekilde davranır `Lf` .

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

, eşdeğer tarama dönüştürme belirleyicisi olması dışında, ilki ile aynı şekilde davranır `p` .

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

, tümü, boş olmayan bir Boole giriş alanını eşleştirmeyi denediğinden, ilki ile aynı şekilde davranır. Başarılı olursa, Boole giriş alanını türünde bir değere dönüştürür **`bool`** ve bu değeri *Val*' de depolar.

Boole girişi alanı iki formdan birini alır. `iosbase.flags & ios_base::` [Boolalpha](../standard-library/ios-functions.md#boolalpha) ise, **`false`** Dönüştürülmüş değerin 0 (for **`false`** ) ya da 1 (için) olması dışında bir tamsayı girişi alanı ile aynıdır **`true`** . Aksi takdirde, sıranın `fac.` [falsename](../standard-library/numpunct-class.md#falsename) (for **`false`** ) veya `fac.` [truename](../standard-library/numpunct-class.md#truename) (için) ile eşleşmesi gerekir **`true`** .

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

## <a name="num_getiter_type"></a><a name="iter_type"></a> num_get:: iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `InputIterator` .

## <a name="num_getnum_get"></a><a name="num_get"></a> num_get:: num_get

`num_get`Dizilerden sayısal değerler ayıklamak için kullanılan türündeki nesneler için Oluşturucu.

```cpp
explicit num_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini model ile başlatır `locale::` [](../standard-library/locale-class.md#facet_class) `(refs)` .

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
