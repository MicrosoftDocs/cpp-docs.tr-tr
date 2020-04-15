---
title: codecvt Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 3dba971b112c23325e0529e53746cbee827df5e9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371959"
---
# <a name="codecvt-class"></a>codecvt Sınıfı

Yerel bir yönü olarak hizmet verebilir bir nesne açıklayan bir sınıf şablonu. Programın içindeki karakterleri ve program dışındaki karakterleri kodlamak için kullanılan değerler dizisi arasındaki dönüştürmeleri denetleyebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*Bayt*\
Bir program dışındaki karakterleri kodlamak için kullanılan bir tür.

*StateType*\
Karakter temsillerinin iç ve dış türleri arasındaki bir dönüştürmenin ara durumlarını temsil etmek için kullanılan bir tür.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, *CharType* türündeki değerler dizisi ile Byte türündeki değerler dizisi arasındaki dönüşümleri denetlemek için [yerel bir fason](../standard-library/locale-class.md#facet_class)olarak hizmet verebilen bir *nesneyi*açıklar. Class *StateType* dönüşümü karakterize eder -- ve *statetype* sınıfının bir nesnesi dönüşüm sırasında gerekli durum bilgilerini depolar.

Dahili kodlama, karakter başına sabit sayıda bayt içeren bir gösterim kullanır, genellikle **char** veya tip **wchar_t**türü.

Herhangi bir yerel fasonda olduğu `id` gibi, statik nesnenin de ilk depolanmış değeri sıfırdır. Depolanan değerine erişmek için ilk girişim benzersiz `id`bir pozitif değer depolar.

[do_in](#do_in) ve [do_out](#do_out) şablon sürümleri `codecvt_base::noconv`her zaman geri döner.

C++ Standart Kitaplığı birkaç açık uzmanlık tanımlar:

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**wchar_t** ve **char** dizileri arasında dönüştürür.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

UTF-16 olarak kodlanmış diziler ile UTF-8 olarak kodlanmış `char16_t` **char** dizileri arasında dönüştürür.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

UTF-32 (UCS-4) olarak kodlanmış diziler ile UTF-8 olarak kodlanmış `char32_t` **char** dizileri arasında dönüşüm ler.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[codecvt](#codecvt)|Dönüşümleri işlemek için yerel `codecvt` bir yönü olarak hizmet veren sınıf nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[extern_type](#extern_type)|Dış temsiller için kullanılan karakter türü.|
|[intern_type](#intern_type)|İç temsiller için kullanılan karakter türü.|
|[state_type](#state_type)|İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[always_noconv](#always_noconv)|Bir dönüştürme yapılıp yapılmayacağını sınar.|
|[do_always_noconv](#do_always_noconv)|Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.|
|[do_encoding](#do_encoding)|`Byte` Akışın kodlanmasının duruma bağlı olup olmadığını, kullanılan `Byte` değerler le üretilen `CharType` değerler arasındaki oranın sabit olup olmadığını ve varsa bu oranın değerini belirleyen sanal bir işlevdir.|
|[do_in](#do_in)|İç `Byte` değer dizisini dış `CharType` değerler dizisine dönüştürmek için çağrılan sanal işlev.|
|[do_length](#do_length)|`Byte` Belirli bir dış `Byte` değer dizisinden kaç değerin belirli bir sayıdan fazla `CharType` iç değer ürettiğini `Byte` belirleyen ve bu değer sayısını döndüren sanal bir işlev.|
|[do_max_length](#do_max_length)|Bir iç `CharType`üretmek için gerekli dış Bayt maksimum sayısını döndüren bir sanal işlev.|
|[do_out](#do_out)|İç `CharType` sel değerler dizisini harici Bayt dizisine dönüştürmek için çağrılan sanal bir işlev.|
|[do_unshift](#do_unshift)|Son karakteri `Byte` `Byte` bir dizi değer dizisinde tamamlamak için duruma bağımlı dönüştürmede gereken değerleri sağlamak için çağrılan sanal işlev.|
|[Kodlama](#encoding)|Akışın `Byte` kodlamasının duruma bağlı olup olmadığını, kullanılan `Byte` değerler le `CharType` üretilen değerler arasındaki oranın sabit olup olmadığını ve varsa bu oranın değerini belirleyip belirlemediğini sınar.|
|[in](#in)|Bir değer dizisinin `Byte` dış gösterimini, bir değer `CharType` dizisinin iç gösterimine dönüştürür.|
|[Uzun -luğu](#length)|Belirli bir `Byte` dış `Byte` değer dizisinden kaç değerin belirli bir iç `CharType` değer sayısından `Byte` fazla üretileceğini belirler ve bu değer sayısını döndürür.|
|[max_length](#max_length)|Bir iç `CharType`oluşturmak `Byte` için gereken en fazla dış değer sayısını verir.|
|[çıkış](#out)|İç `CharType` değer sırasını dış `Byte` değerler dizisine dönüştürür.|
|[Unshift](#unshift)|Değerler dizisindeki son karakteri tamamlamak için duruma bağımlı dönüştürmede gereken dış `Byte` değerleri sağlar. `Byte`|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a>codecvt::always_noconv

Dönüştürme yapılması gerekip gerekmediğini test eder.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüşüm yapılması gerekiyorsa **doğru** olan bir Boolean değeri; en az bir yapılması gerekiyorsa **yanlış.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_always_noconv](#do_always_noconv)döndürür.

### <a name="example"></a>Örnek

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a>codecvt::codecvt

Dönüşümleri işlemek için yerel bir fason olarak hizmet veren sınıf codecvt nesnelerinin oluşturucusu.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refler*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- 2: Bu değerler tanımlı değildir.

Oluşturucu, temel nesnesini `locale::facet` yerel olarak başlaşır::facet [locale::facet](../standard-library/locale-class.md#facet_class)`(refs)`.

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a>codecvt::do_always_noconv

Dönüştürme yapılmayacağını sınamak için çağrılan sanal bir işlev.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korunan sanal üye işlevi yalnızca [do_in](#do_in) veya [do_out](#do_out) `noconv`için yapılan her çağrı geri döndüğünde **doğru** döndürür.

Şablon sürümü her zaman **doğru**döndürür.

### <a name="example"></a>Örnek

[always_noconv](#always_noconv)için örneğe bakın `do_always_noconv`, hangi çağırır .

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a>codecvt::do_encoding

`Byte` Akışın kodlanmasının duruma bağlı olup olmadığını, kullanılan `Byte` değerler le üretilen `CharType` değerler arasındaki oranın sabit olup olmadığını ve varsa bu oranın değerini belirleyen sanal bir işlevdir.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi döndürür:

- -1, tür `extern_type` dizilerinin kodlanması devlete bağlı ise.

- 0, kodlama değişen uzunluklarda dizileri içeriyorsa.

- *N*, kodlama sadece *uzunluk* n dizilerini içeriyorsa

### <a name="example"></a>Örnek

[Kodlama](#encoding)için örneğe bakın `do_encoding`, hangi çağırır .

## <a name="codecvtdo_in"></a><a name="do_in"></a>codecvt::do_in

Dış `Byte` değer dizisini iç `CharType` değerler dizisine dönüştürmek için çağrılan sanal işlev.

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk1*\
Dönüştürülecek dizinin başına işaretçi.

*son1*\
Dönüştürülecek dizinin sonuna işaretçi.

*sonraki1*\
Dönüştürülen dizinin sonundan, dönüştürülmemiş ilk karaktere işaretçi.

*ilk2*\
Dönüştürülen dizinin başına işaretçi.

*son2*\
Dönüştürülen dizinin sonuna işaretçi.

*sonraki2*\
`CharType` Son dönüştürülmeden `CharType`sonra gelen işaretçi, hedef sırada ilk değiştirilmemiş karaktere.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmi başarısını veya başarısızlığını gösteren bir iade. İşlev döner:

- `codecvt_base::error`kaynak sırası kötü oluşursa.

- `codecvt_base::noconv`işlev dönüşüm gerçekleştirmezse.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`kaynak yetersizse veya hedef yeterince büyük değilse, dönüşümün başarılı olması için.

### <a name="remarks"></a>Açıklamalar

*durum,* yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlev, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için depolanan değerini gerektiği gibi değiştirir. Depolanan değeri aksi belirtilmemiştir.

### <a name="example"></a>Örnek

[Bkz.](#in)için örnek , `do_in`çağırır .

## <a name="codecvtdo_length"></a><a name="do_length"></a>codecvt::do_length

`Byte` Belirli bir dış `Byte` değer dizisinden kaç değerin belirli bir sayıdan fazla `CharType` iç değer ürettiğini `Byte` belirleyen ve bu değer sayısını döndüren sanal bir işlev.

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk1*\
Dış dizinin başına işaretçi.

*son1*\
Dış dizinin sonuna işaretçi.

*len2*\
Üye işlev `Byte` tarafından döndürülebilecek en fazla değer sayısı.

### <a name="return-value"></a>Dönüş Değeri

[, `first1`] `last1`dış kaynak dizisi tarafından tanımlanan *len2'den*büyük olmayan, en fazla dönüşüm sayısının sayısını temsil eden bir tamsayı .

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi `do_in( state, first1, last1, next1, buf, buf + len2, next2)` etkili *devlet* (durum bir kopyası), `buf`bazı arabellek ve işaretçiler `next1` ve `next2`çağırır .

Daha sonra `next2`  -  `buf`döner. Böylece, kaynak sırası tarafından tanımlanan *len2'den*büyük olmayan, en fazla `first1` `last1`dönüşüm sayısını sayar [ , ).

Şablon sürümü her zaman *last1* - *first1* ve *len2*daha az döndürür.

### <a name="example"></a>Örnek

[Uzunluk](#length)için örneğe bakın `do_length`, hangi çağırır .

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a>codecvt::do_max_length

Bir iç `CharType`oluşturmak için gereken `Byte` en fazla dış değer sayısını döndüren sanal bir işlev.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tane `CharType` `Byte` üretmek için gereken en fazla değer sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye *işlevi, ilk1* ve *son1'in*rasgele geçerli değerleri için [do_length](#do_length) `( first1, last1, 1)` tarafından döndürülebilen en büyük izin verilen değeri döndürür.

### <a name="example"></a>Örnek

[max_length](#max_length)için örnek bakın `do_max_length`, hangi çağırır .

## <a name="codecvtdo_out"></a><a name="do_out"></a>codecvt::do_out

İç `CharType` değer dizisini dış `Byte` değerler dizisine dönüştürmek için çağrılan sanal işlev.

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk1*\
Dönüştürülecek dizinin başına işaretçi.

*son1*\
Dönüştürülecek dizinin sonuna işaretçi.

*sonraki1*\
Son `CharType` dönüştürülmeden sonra, ilk `CharType`dönüştürülmemiş bir işaretçiye başvuru.

*ilk2*\
Dönüştürülen dizinin başına işaretçi.

*son2*\
Dönüştürülen dizinin sonuna işaretçi.

*sonraki2*\
Son `Byte` dönüştürülmeden sonra, ilk `Byte`dönüştürülmemiş bir işaretçiye başvuru.

### <a name="return-value"></a>Dönüş Değeri

İşlev döner:

- `codecvt_base::error`kaynak sırası kötü oluşursa.

- `codecvt_base::noconv`işlev dönüşüm gerçekleştirmezse.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`kaynak yetersizse veya hedef dönüşümün başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

*durum,* yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlev, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için depolanan değerini gerektiği gibi değiştirir. Depolanan değeri aksi belirtilmemiştir.

### <a name="example"></a>Örnek

[Aramalar](#out)için örneğe bakın `do_out`.

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a>codecvt::do_unshift

Son karakteri `Byte` `Byte` bir dizi değer dizisinde tamamlamak için duruma bağımlı dönüştürmede gereken değerleri sağlamak için çağrılan sanal işlev.

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk2*\
Hedef aralığındaki ilk konumu işaretçi.

*son2*\
Hedef aralığındaki son konumu işaretçi.

*sonraki2*\
Hedef sırada değiştirilmemiş ilk öğeyi işaretle.

### <a name="return-value"></a>Dönüş Değeri

İşlev döner:

- `codecvt_base::error`*durum* geçersiz bir durumu temsil ederse

- `codecvt_base::noconv`işlev dönüşüm gerçekleştirmezse

- `codecvt_base::ok`dönüştürme başarılı olursa

- `codecvt_base::partial`hedef, dönüşümün başarılı olması için yeterince büyük değilse

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi , `CharType`sonlandırıcı öğe `Byte`(0) dışında kaynak `first2` `last2`öğeyi (0) içinde depoladığını bir hedef sırasına dönüştürmeye çalışır. Her zaman *sonraki2* hedef sırada ilk değiştirilmemiş öğeiçin bir işaretçi depolar.

_ *Durum,* yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlev, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için depolanan değerini gerektiği gibi değiştirir. Genellikle, kaynak öğeyi `CharType`dönüştürme (0) ilk dönüşüm durumunda geçerli durumu bırakır.

### <a name="example"></a>Örnek

[Shift için](#unshift)örnek bakınız `do_unshift`, hangi çağırır .

## <a name="codecvtencoding"></a><a name="encoding"></a>codecvt::kodlama

Akışın `Byte` kodlamasının duruma bağlı olup olmadığını, kullanılan `Byte` değerler le `CharType` üretilen değerler arasındaki oranın sabit olup olmadığını ve varsa bu oranın değerini belirleyip belirlemediğini sınar.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İade değeri pozitifse, `Byte` `CharType` bu değer karakteri üretmek için gereken sabit karakter sayısıdır.

Korumalı sanal üye işlevi döndürür:

- -1, tür `extern_type` dizilerinin kodlanması devlete bağlı ise.

- 0, kodlama değişen uzunluklarda dizileri içeriyorsa.

- *N,* kodlama sadece *n* uzunluğunda diziler içeriyorsa.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_encoding](#do_encoding)döndürür.

### <a name="example"></a>Örnek

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a>codecvt::extern_type

Dış temsiller için kullanılan karakter türü.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Byte`ile eş anlamlıdır.

## <a name="codecvtin"></a><a name="in"></a>codecvt::içinde

Bir değer dizisinin `Byte` dış gösterimini, bir değer `CharType` dizisinin iç gösterimine dönüştürür.

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk1*\
Dönüştürülecek dizinin başına işaretçi.

*son1*\
Dönüştürülecek dizinin sonuna işaretçi.

*sonraki1*\
Dönüştürülen dizinin sonunun ötesindeki işaretçi, dönüştürülmemiş ilk karaktere dönüştürülür.

*ilk2*\
Dönüştürülen dizinin başına işaretçi.

*son2*\
Dönüştürülen dizinin sonuna işaretçi.

*sonraki2*\
`CharType` Hedef sıradaki ilk değiştirilmemiş `Chartype` karaktere dönüştürülen son karakterden sonra gelen işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmi başarısını veya başarısızlığını gösteren bir iade. İşlev döner:

- `codecvt_base::error`kaynak sırası kötü oluşursa.

- `codecvt_base::noconv`işlev dönüşüm gerçekleştirmezse.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`kaynak yetersizse veya hedef dönüşümün başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

*durum,* yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlev, gerektiğinde, başarılı bir dönüştürmenin geçerli durumunu yansıtacak şekilde depolanan değerini değiştirir. Kısmi bir dönüşümden sonra, yeni karakterler geldiğinde dönüştürmenin devam etmesine izin verecek şekilde *durum* ayarlanmalıdır.

Üye işlev [do_in](#do_in)`( state, first1,  last1,  next1, first2, last2,  next2)`döndürür.

### <a name="example"></a>Örnek

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a>codecvt::intern_type

İç temsiller için kullanılan karakter türü.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

## <a name="codecvtlength"></a><a name="length"></a>codecvt::uzunluk

Belirli bir `Byte` dış `Byte` değer dizisinden kaç değerin belirli bir iç `CharType` değer sayısından `Byte` fazla üretileceğini belirler ve bu değer sayısını döndürür.

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk1*\
Dış dizinin başına işaretçi.

*son1*\
Dış dizinin sonuna işaretçi.

*len2*\
Üye işlev tarafından döndürülebilen maksimum Bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

[, `first1`] `last1`dış kaynak dizisi tarafından tanımlanan *len2'den*büyük olmayan, en fazla dönüşüm sayısının sayısını temsil eden bir tamsayı .

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_length](#do_length)`( state, first1, last1, len2)`döndürür.

### <a name="example"></a>Örnek

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a>codecvt::max_length

Bir iç `CharType`oluşturmak `Byte` için gereken en fazla dış değer sayısını verir.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tane `CharType` `Byte` üretmek için gereken en fazla değer sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_max_length](#do_max_length)döndürür.

### <a name="example"></a>Örnek

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a>codecvt::çıkış

İç `CharType` değer sırasını dış `Byte` değerler dizisine dönüştürür.

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk1*\
Dönüştürülecek dizinin başına işaretçi.

*son1*\
Dönüştürülecek dizinin sonuna işaretçi.

*sonraki1*\
Son `CharType` `CharType` dönüştürülmeden sonra dönüştürülmemiş ilk işaretçiye başvuru.

*ilk2*\
Dönüştürülen dizinin başına işaretçi.

*son2*\
Dönüştürülen dizinin sonuna işaretçi.

*sonraki2*\
Son dönüştürülmeden `Byte` sonra dönüştürülmemiş ilk işaretçiye `Byte`başvuru.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev [do_out](#do_out)`( state, first1, last1, next1, first2, last2, next2)`döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [codecvt::do_out adresine](#do_out)bakın.

### <a name="example"></a>Örnek

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a>codecvt::state_type

İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `StateType`ile eş anlamlıdır.

## <a name="codecvtunshift"></a><a name="unshift"></a>codecvt::unshift

Son `Byte` karakteri `Byte` bir dizi değer dizisinde tamamlamak için duruma bağımlı dönüştürmede gereken değerleri sağlar.

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*Durum*\
Üye işlevine yapılan çağrılar arasında tutulan dönüşüm durumu.

*ilk2*\
Hedef aralığındaki ilk konumu işaretçi.

*son2*\
Hedef aralığındaki son konumu işaretçi.

*sonraki2*\
Hedef sırada değiştirilmemiş ilk öğeyi işaretle.

### <a name="return-value"></a>Dönüş Değeri

İşlev döner:

- `codecvt_base::error`durum geçersiz bir durumu temsil ederse.

- `codecvt_base::noconv`işlev dönüşüm gerçekleştirmezse.

- `codecvt_base::ok`dönüştürme başarılı olursa.

- `codecvt_base::partial`hedef, dönüşümün başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi , `CharType`sonlandırıcı öğe `Byte`(0) dışında kaynak `first2` `last2`öğeyi (0) içinde depoladığını bir hedef sırasına dönüştürmeye çalışır. Her zaman *sonraki2* hedef sırada ilk değiştirilmemiş öğeiçin bir işaretçi depolar.

*durum,* yeni bir kaynak dizisinin başındaki ilk dönüştürme durumunu temsil etmelidir. İşlev, gerektiğinde, başarılı bir dönüştürmenin geçerli durumunu yansıtacak şekilde depolanan değerini değiştirir. Genellikle, kaynak öğeyi `CharType`dönüştürme (0) ilk dönüşüm durumunda geçerli durumu bırakır.

Üye işlev [do_unshift](#do_unshift)`( state, first2, last2, next2 )`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[Kod Sayfaları](../c-runtime-library/code-pages.md)\
[Yerel Adlar, Diller ve Ülke/Bölge Dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
