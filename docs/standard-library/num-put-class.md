---
title: num_put Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
ms.openlocfilehash: 3f65d7140bb5c691fa58ec9d74ceda5573280ddb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373641"
---
# <a name="num_put-class"></a>num_put Sınıfı

Sayısal değerlerin tür `CharType`dizilerine dönüşümlerini denetlemek için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*OutputIterator*\
Sayısal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_put](#num_put)|Tür `num_put`nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayıyı, belirli bir yerel bölge `CharType`için biçimlendirilmiş sayıyı temsil eden bir s dizisine dönüştürmek için çağrılan sanal işlev.|
|[Koymak](#put)|Bir sayıyı, belirli `CharType`bir yerel bölge için biçimlendirilmiş sayıyı temsil eden bir s dizisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="num_putchar_type"></a><a name="char_type"></a>num_put:char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

## <a name="num_putdo_put"></a><a name="do_put"></a>num_put::do_put

Bir sayıyı, belirli bir yerel bölge `CharType`için biçimlendirilmiş sayıyı temsil eden bir s dizisine dönüştürmek için çağrılan sanal işlev.

```cpp
virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const unsigned long long val) const;
```

### <a name="parameters"></a>Parametreler

*Sonraki*\
Eklenen dizenin ilk öğesini ele alan bir yineleyici.

*_Iosbase*\
Çıktıyı ve çıktıyı biçimlendirmek için bayrakları noktalamak için kullanılan numpunct facet ile yerel akışı içeren akışı belirtin.

*_Fill*\
Boşluk için kullanılan bir karakter.

*Val*\
Çıktı edilecek sayı veya Boolean türü.

### <a name="return-value"></a>Dönüş Değeri

Çıktı yineleyici, üretilen son öğenin ötesindeki konumu ele alır.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi *val*değerinden bir tamsayı çıkış alanı üretmek için *yanında* başlayan sıralı elemanlar oluşturur. İşlev, oluşturulan isterosi çıkış alanının ötesine bir öğe eklemek için bir sonraki yeri atayan bir yineleyici döndürür.

Tamsayı çıktı alanı, bir dosyaya bir dizi **char** öğesi oluşturmak için yazdırma işlevleri tarafından kullanılan aynı kurallar tarafından oluşturulur. Bu tür char öğesi basit, bire `CharType` bir eşleme ile eşdeğer bir tür öğesi için eşleme varsayılır. Yazdırma işlevi, bir alanı boşluklarveya 0 rakamı olan `do_put` bir `fill`alanı pads, ancak, bunun yerine kullanır. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki gibi belirlenir:

- Eğer **iosbase**. [bayraklar](../standard-library/ios-base-class.md#flags) & `ios_base::`[oct](../standard-library/ios-functions.md#oct) `lo`ekim , dönüşüm belirtimi .`ios_base::basefield` == 

- **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex)ise, `lx`dönüşüm belirtimi .

- Aksi takdirde, dönüştürme `ld`belirtimi .

Eğer **iosbase**. [genişlik](../standard-library/ios-base-class.md#width) sıfır değildir, bu değerin alan genişliği hazırlanır. Fonksiyon daha sonra **iosbase**çağırır. **alan genişliğini**sıfırlamak için genişlik (0)

Dolgu, yalnızca çıkış alanını belirtmek için gereken minimum eleman sayısı *n* **iosbase'den**daha az sayılsa oluşur. [genişliği](../standard-library/ios-base-class.md#width). Bu tür dolgu **dolgu** *N* - **genişliği** kopyaları bir dizi oluşur. Dolgu sonra aşağıdaki gibi oluşur:

- Eğer **iosbase**. **bayraklar** & `ios_base::`[left](../standard-library/ios-functions.md#left) **-** bırakılır, bayrak hazırlanır.`ios_base::adjustfield` ==  (Dolgu, oluşturulan metinden sonra oluşur.)

- **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[iç,](../standard-library/ios-functions.md#internal)bayrak **0** prepended olduğunu. (Sayısal bir çıkış alanı için, dolgu, yazdırma işlevleri0 ile pad oluşur.)

- Aksi takdirde, ek bayrak hazırlanır. (Dolgu, oluşturulan diziden önce oluşur.)

Sonunda:

- Eğer **iosbase**. **bayraklar** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) sıfır değil, bayrak **+** dönüşüm belirtimine hazır.

- Eğer **iosbase**. **bayraklar** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) sıfır **#** değil, bayrak dönüşüm belirtimine hazır.

Bir tamsayı çıkış alanının biçimi, **iosbase(iosbase)** use_facet[numpunct](../standard-library/numpunct-class.md) \< **>** [arama](../standard-library/locale-functions.md#use_facet) < ile**döndürülen** [yerel fac](../standard-library/locale-class.md#facet_class)tarafından daha da belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)). Daha ayrıntılı şekilde belirtmek gerekirse:

- **fac**. [gruplandırma,](../standard-library/numpunct-class.md#grouping) basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırıldığını belirler

- **fac**. [thousands_sep,](../standard-library/numpunct-class.md#thousands_sep) basamak gruplarını herhangi bir ondalık noktanın solunda ayıran sırayı belirler

Fac tarafından gruplandırma kısıtlamaları **fac**uygulanmazsa. **gruplandırma** (ilk öğesi CHAR_MAX değeri vardır), sonra **fac**örnekleri . `thousands_sep`çıkış alanında oluşturulur. Aksi takdirde, yazdırma dönüştürme oluştuktan sonra ayırıcılar eklenir.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `lu`çalışır.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

**val**değerinden kayan nokta çıkış alanı üretmesi dışında, ilki ile aynı şekilde kalır. **fac**. [decimal_point,](../standard-library/numpunct-class.md#decimal_point) tamsayı basamaklarını kesir basamaklarından ayıran sırayı belirler. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki gibi belirlenir:

- Eğer **iosbase**. **bayraklar** & `ios_base::`[fixed](../standard-library/ios-functions.md#fixed) `lf`sabit , dönüşüm belirtimi .`ios_base::floatfield` == 

- Eğer **iosbase**. **bayraklar** & **ios_base::floatfield** == `ios_base::`[bilimsel](../standard-library/ios-functions.md#scientific), `le`dönüşüm belirtimi . Eğer **iosbase**. **bayraklar** & `ios_base::`[büyük harf](../standard-library/ios-functions.md#uppercase) `e` sıfır değildir, `E`değiştirilir.

- Aksi takdirde, dönüşüm özellikleri **lg**. Eğer **iosbase**. **bayraklar** & **ios_base::büyük harf** `g` sıfır değil, `G`değiştirilir.

Eğer **iosbase**. **bayraklar** & **ios_base::sabit** sıfır değil veya **iosbase**ise . [hassas](../standard-library/ios-base-class.md#precision) sıfırdan büyük, değeri **iosbase**ile bir hassasiyet . **hassasiyet,** dönüştürme belirtimine göre hazırlanır. Herhangi bir dolgu bir tamsayı çıkış alanı için aynı şekilde olur. Dolgu karakteri **doldurulur.** Sonunda:

- Eğer **iosbase**. **bayraklar** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) sıfır değil, bayrak **+** dönüşüm belirtimine hazır.

- Eğer **iosbase**. **bayraklar** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) sıfır değil, bayrak **#** dönüşüm belirtimine hazır.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

dönüştürme belirtimindeki niteleyicinin `l` `L`".

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

dönüşüm belirtimi `p`dışında, dolgu belirtmek için gerekli herhangi bir niteleyici, **ilk** aynı şekilde çalışır.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

*val*bir Boolean çıkış alanı oluşturur dışında, ilk aynı şekilde olur.

Boolean çıkış alanı iki formdan birini alır. `iosbase.flags & ios_base::` [Boolalpha](../standard-library/ios-functions.md#boolalpha) **yanlışsa,** üye `do_put(_Next, _Iosbase, _Fill, (long)val)`işlev döndürür , genellikle oluşturulan bir dizi üretir 0 **(false**için) veya 1 **(true**için). Aksi takdirde, oluşturulan sıra ya *fac'* dir. [falsename](../standard-library/numpunct-class.md#falsename) **(yanlış**için ), veya *fac*. [truename](../standard-library/numpunct-class.md#truename) **(gerçek**için).

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `lld`çalışır.

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

ile bir dönüşüm belirtimi `ld` yerine dışında, ilk aynı şekilde `llu`çalışır.

### <a name="example"></a>Örnek

[Koymak](#put)için örneğe bakın `do_put`, hangi çağırır .

## <a name="num_putiter_type"></a><a name="iter_type"></a>num_put:iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **OutputIterator** ile eş anlamlıdır.

## <a name="num_putnum_put"></a><a name="num_put"></a>num_put:num_put

Tür `num_put`nesneleri için oluşturucu.

```cpp
explicit num_put(size_t _Refs = 0);
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

Oluşturucu, temel nesnesini yerel olarak başlatleştirir:: **locale::**[fason](../standard-library/locale-class.md#facet_class)(_ *Refs).*

## <a name="num_putput"></a><a name="put"></a>num_put::put

Bir sayıyı, belirli `CharType`bir yerel bölge için biçimlendirilmiş sayıyı temsil eden bir s dizisine dönüştürür.

```cpp
iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Long long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Unsigned long long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;
```

### <a name="parameters"></a>Parametreler

*Dest*\
Eklenen dizenin ilk öğesini ele alan bir yineleyici.

*_Iosbase*\
Çıktıyı ve çıktıyı biçimlendirmek için bayrakları noktalamak için kullanılan numpunct facet ile yerel akışı belirten.

*_Fill*\
Boşluk için kullanılan bir karakter.

*Val*\
Çıktı edilecek sayı veya Boolean türü.

### <a name="return-value"></a>Dönüş Değeri

Çıktı yineleyici, üretilen son öğenin ötesindeki konumu ele alır.

### <a name="remarks"></a>Açıklamalar

Tüm üye [do_put](#do_put)işlevler `next` `_Iosbase`do_put `_Fill` `val`( , , , , ) döndürüler.

### <a name="example"></a>Örnek

```cpp
// num_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );
   basic_stringstream<char> psz2;
   ios_base::iostate st = 0;
   long double fVal;
   cout << "The thousands separator is: "
        << use_facet < numpunct <char> >(loc).thousands_sep( )
        << endl;

   psz2.imbue( loc );
   use_facet < num_put < char > >
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),
                    psz2, ' ', fVal=1000.67);

   if ( st & ios_base::failbit )
      cout << "num_put( ) FAILED" << endl;
   else
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;
}
```

```Output
The thousands separator is: .
num_put( ) = 1.000,67
```

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[fateks Sınıf](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
