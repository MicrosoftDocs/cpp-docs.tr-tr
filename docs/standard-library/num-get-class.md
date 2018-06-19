---
title: num_get sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocnum/std::num_get
- locale/std::num_get::char_type
- locale/std::num_get::iter_type
- locale/std::num_get::do_get
- locale/std::num_get::get
dev_langs:
- C++
helpviewer_keywords:
- std::num_get [C++]
- std::num_get [C++], char_type
- std::num_get [C++], iter_type
- std::num_get [C++], do_get
- std::num_get [C++], get
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d6e1df322ba6959431913097111e4af1a179cd9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862754"
---
# <a name="numget-class"></a>num_get Sınıfı

Denetim dönüşümleri sıralarının türü için bir yerel ayar model olarak hizmet verebilir bir nesneyi tanımlayan bir şablon sınıfı `CharType` sayısal değerler için.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

`CharType` Yerel karakter kodlamak için bir program içinde kullanılan türü.

`InputIterator` Sayısal işlevler alma yineleyici türü kendi giriş okuyun.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_get](#num_get)|Nesne türü Oluşturucusu `num_get` serilerinden sayısal değerleri ayıklamak için kullanılır.|

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

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

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

`first` Sayı okunacak karakter aralığı başlangıcı.

`last` Sayı okunacak karakter aralığı sonu.

`_Iosbase` [İos_base](../standard-library/ios-base-class.md) , bayrakları dönüştürme işlemi tarafından kullanılır.

`_State` Hangi failbit durumuna (bkz [ios_base::iostate](../standard-library/ios-base-class.md#iostate)) hata yapması üzerine eklenir.

`val` Okundu değeri.

### <a name="return-value"></a>Dönüş Değeri

Değer okuduktan sonra yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;
```

Başlangıç sıralı öğeleri eşleşen `first` sırada `[first, last)` tamamı tanıdığını kadar alan boş olmayan tamsayı girin. Başarılı, bu alan türü olarak eşdeğer değerine dönüştürür, `long`ve sonuçta depolar `val`. Sayısal giriş alanı ötesinde ilk öğe belirleme yineleyici döndürür. Aksi takdirde, işlev içinde hiçbir şey depolar `val` ve ayarlar `ios_base::failbit` içinde `state`. Herhangi bir geçerli bir tamsayı giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde `state`.

Tamsayı giriş alanını eşleşen ve bir dizi dönüştürme için tarama işlevler tarafından kullanılan aynı kurallar tarafından dönüştürülür `char` bir dosyadan öğeleri. (Her gibi `char` öğe türü eşdeğer bir öğeye eşlemek için varsayılır `Elem` basit bir tarafından birebir, eşleme.) Eşdeğer tarama dönüştürme belirtimi şu şekilde belirlenir:

Varsa `iosbase.` [ios_base::flags](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`[Eki](../standard-library/ios-functions.md#oct), dönüştürme belirtimi `lo`.

Varsa `iosbase.flags() & ios_base::basefield == ios_base::` [onaltılık](../standard-library/ios-functions.md#hex), dönüştürme belirtimi `lx`.

Varsa `iosbase.flags() & ios_base::basefield == 0`, dönüştürme belirtimi `li`.

Aksi takdirde, dönüştürme belirtimidir `ld`.

Tamsayı giriş alanını biçimi daha fazla tarafından belirlenen [yerel model](../standard-library/locale-class.md#facet_class) `fac` çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet) `<` [numpunct](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [ios_base::getloc](../standard-library/ios-base-class.md#getloc)`())`. Özellikle:

`fac.` [numpunct::Grouping](../standard-library/numpunct-class.md#grouping) `()` basamak herhangi Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirler

`fac.` [numpunct::thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` herhangi Ondalık ayırıcının sol tarafındaki basamak grupları ayıran sırası belirler.

Hiçbir örneği varsa `fac.thousands_sep()` ortaya sayısal giriş alanı hiçbir gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, gruplandırma kısıtlamalar uygulanan tarafından `fac.grouping()` uygulanır ve ayırıcılar tarama dönüştürme oluşmadan önce kaldırılır.

Dördüncü sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır `ld` ile `lu`. Başarılı sayısal giriş alanı türü değerine dönüştürür, `unsigned long` ve bu değeri depolar `val`.

Beşinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır `ld` ile `lld`. Başarılı sayısal giriş alanı türü değerine dönüştürür, `long long` ve bu değeri depolar `val`.

Altıncı sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır `ld` ile `llu`. Başarılı sayısal giriş alanı türü değerine dönüştürür, `unsigned long long` ve bu değeri depolar `val`.

Yedinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;
```

bir tam, boş olmayan kayan nokta giriş alanını eşleşecek şekilde endeavors dışında birinci ile aynı şekilde davranır. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point) `()` tamsayı basamak kesir rakamları ayıran sırası belirler. Eşdeğer tarama dönüştürme belirleyici olduğu `lf`.

Sekizinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

bir tam, boş olmayan kayan nokta giriş alanını eşleşecek şekilde endeavors dışında birinci ile aynı şekilde davranır. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point) `()` tamsayı basamak kesir rakamları ayıran sırası belirler. Eşdeğer tarama dönüştürme belirleyici olduğu `lf`.

Dokuzuncu sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyici olması dışında sekizinci ile aynı şekilde davranır `Lf`.

Onuncu sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

eşdeğer tarama dönüştürme belirleyici olması dışında aynı ilk davranır `p`.

Son (eleventh) sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

bir tam, boş olmayan Boole giriş alanı eşleşecek şekilde endeavors dışında birinci ile aynı şekilde davranır. Başarılı Boole giriş alanı türü değerine dönüştürür, `bool` ve bu değeri depolar `val`.

Bir Boole giriş alanı iki biçimlerden birini alır. Varsa `iosbase.flags() & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) , olduğunu bir tamsayı giriş alanı ile aynı dönüştürülmüş değeri 0 (false) veya 1 (true) olmalıdır dışında false olur. Sıra ya da aksi takdirde eşleşmelidir `fac.` [numpunct::falsename](../standard-library/numpunct-class.md#falsename) `()` (için false), veya `fac.` [numpunct::truename](../standard-library/numpunct-class.md#truename) `()` (için true).

### <a name="example"></a>Örnek

Örneğin bkz [almak](#get), sanal üye fonksiyonu tarafından çağrılır burada `do_get`.

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

`first` Sayı okunacak karakter aralığı başlangıcı.

`last` Sayı okunacak karakter aralığı sonu.

`_Iosbase` [İos_base](../standard-library/ios-base-class.md) , bayrakları dönüştürme işlemi tarafından kullanılır.

`_State` Hangi failbit durumuna (bkz [ios_base::iostate](../standard-library/ios-base-class.md#iostate)) hata yapması üzerine eklenir.

`val` Okundu değeri.

### <a name="return-value"></a>Dönüş Değeri

Değer okuduktan sonra yineleyici.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri dönmek [do_get](#do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`).

İlk sanal korumalı üye fonksiyonu ilk sırada başlayarak sıralı öğeleri eşleştirmeyi dener [ `first`, `last`) bir tam tanıdığını kadar alan boş olmayan tamsayı girin. Başarılı, bu alan türü olarak eşdeğer değerine dönüştürür, **uzun** ve sonuçta depolar `val`. Sayısal giriş alanı ötesinde ilk öğe belirleme yineleyici döndürür. Aksi takdirde, işlev içinde hiçbir şey depolar `val` ve ayarlar `ios_base::failbit` _ içinde *durumu*. Herhangi bir geçerli bir tamsayı giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da **son**, işlev kümeleri `ios_base::eofbit` içinde `_State`.

Tamsayı giriş alanını eşleşen ve bir dizi dönüştürme için tarama işlevler tarafından kullanılan aynı kurallar tarafından dönüştürülür `char` bir dosyadan öğeleri. Her gibi `char` öğe türü eşdeğer bir öğeye eşlemek için varsayılır **CharType** basit, bire bir eşleme tarafından. Eşdeğer tarama dönüştürme belirtimi şu şekilde belirlenir:

- Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[Eki](../standard-library/ios-functions.md#oct), dönüştürme belirtimi **aet.aet**.

- Varsa **iosbase.flags** & **ios_base::basefield** == `ios_base::`[onaltılık](../standard-library/ios-functions.md#hex), dönüştürme belirtimi **lx** .

- Varsa **iosbase.flags** & **ios_base::basefield** == 0 ise, dönüştürme belirtimi `li`.

- Aksi takdirde, dönüştürme belirtimidir **ld**.

Tamsayı giriş alanını biçimi daha fazla tarafından belirlenen [yerel model](../standard-library/locale-class.md#facet_class)**fac** çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct ](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). Özellikle:

- **Fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) basamak herhangi Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirler.

- **Fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) herhangi Ondalık ayırıcının sol tarafındaki basamak grupları ayıran sırası belirler.

Hiçbir örneği varsa **fac**. `thousands_sep` sayısal giriş alanı ortaya, hiçbir gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, gruplandırma kısıtlamalar uygulanan tarafından **fac**. **Gruplandırma** zorlanır ve ayırıcılar tarama dönüştürme oluşmadan önce kaldırılır.

İkinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır **ld** ile **lu**. Başarılı, sayısal giriş alanı türü değerine dönüştürür, `unsigned long` ve bu değeri depolar `val`.

Üçüncü sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

bir tam, boş olmayan kayan nokta giriş alanını eşleştirmeye çalışır dışında birinci ile aynı şekilde davranır. **Fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) tamsayı basamak kesir rakamları ayıran sırası belirler. Eşdeğer tarama dönüştürme belirleyici olduğu **lf**.

Dördüncü sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

eşdeğer tarama dönüştürme belirleyici olması dışında aynı şekilde davranır üçüncü **Lf**.

Beşinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

eşdeğer tarama dönüştürme belirleyici olması dışında aynı ilk davranır **p**.

Altıncı sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

bir tam, boş olmayan Boole giriş alanı eşleştirmeye çalışır dışında birinci ile aynı şekilde davranır. Başarılı Boole giriş alanı türü değerine dönüştürür, `bool` ve bu değeri depolar `val`.

Bir Boole giriş alanı iki biçimlerden birini alır. Varsa **iosbase**. **bayrakları** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) olan **false**, dönüştürülen değer ya da 0 olmalı, dışında bir tamsayı giriş alanı ile aynı olduğundan (için **false** ) veya 1 (için **true**). Sıra ya da aksi takdirde eşleşmelidir **fac**. [falsename](../standard-library/numpunct-class.md#falsename) (için **false**), veya **fac**. [truename](../standard-library/numpunct-class.md#truename) (için **true**).

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

Şablon parametresi için bir eş anlamlı türüdür **InputIterator**.

## <a name="num_get"></a>  num_get::num_get

Nesne türü Oluşturucusu `num_get` serilerinden sayısal değerleri ayıklamak için kullanılır.

```cpp
explicit num_get(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

`_Refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `_Refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.

Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
