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
ms.openlocfilehash: 2ede0ccd85f116f300939c819ae8209435da72b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223564"
---
# <a name="numput-class"></a>num_put Sınıfı

Denetlemek için sayısal değerler türü için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı `CharType`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*Outputıterator*<br/>
Sayısal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_put](#num_put)|Türündeki nesneler için oluşturucu `num_put`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Dizisine bir sayı dönüştürmek için çağrılan sanal işlev `CharType`sayıyı temsil eden bir belirtilen yerel ayar için biçimlendirilmiş.|
|[yerleştirme](#put)|Dizisine bir sayı dönüştürür `CharType`sayıyı temsil eden bir belirtilen yerel ayar için biçimlendirilmiş.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  num_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `CharType`.

## <a name="do_put"></a>  num_put::do_put

Dizisine bir sayı dönüştürmek için çağrılan sanal işlev `CharType`sayıyı temsil eden bir belirtilen yerel ayar için biçimlendirilmiş.

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

*Sonraki*<br/>
Eklenen dizenin ilk öğeyi adresleyen bir yineleyici.

*_Iosbase*<br/>
Numpunct modelinde çıkış ve çıktıyı biçimlendirmek için bayrakları punctuate kullanılacak yerel ayar içeren akış belirtildi.

*_Fill*<br/>
Aralığı için kullanılan karakter.

*VAL*<br/>
Sayı veya çıkış olarak Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Çıkış yineleyici son öğenin ötesinde konumu bir adresleri üretilen.

### <a name="remarks"></a>Açıklamalar

Konumunda başlayan ardışık öğeleri ilk korumalı sanal üye işlevi oluşturur *sonraki* değeri bir tamsayı çıkış alanından üretmek için *val*. İşlevi, oluşturulmuş bir tamsayı çıktı alanı dışında bir öğe eklemek için sonraki yeri belirleme bir yineleyici döndürür.

Tamsayı çıkış alanı yazdırma işlevleri tarafından bir dizi oluşturmak için kullanılan aynı kuralları tarafından oluşturulan **char** bir dosyaya öğeleri. Her tür char öğe türünde eşdeğer bir öğe için harita varsayılır `CharType` ile basit, bire bir eşleştirerek. Yazdırma işlevi boşluk ya da 0 basamağı olan bir alana ancak sıfır ekleyerek doldurur burada `do_put` bunun yerine kullanır `fill`. Eşdeğer yazdırma dönüştürme belirtimi şu şekilde belirlenir:

- Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[Eki](../standard-library/ios-functions.md#oct), dönüştürme belirtimi `lo`.

- Varsa **iosbase.flags** & **ios_base::basefield** == `ios_base::`[onaltılık](../standard-library/ios-functions.md#hex), dönüştürme belirtimi `lx`.

- Aksi takdirde, dönüştürme belirtimidir `ld`.

Varsa **iosbase**. [Genişlik](../standard-library/ios-base-class.md#width) olan bir alan genişliği bu değerin sıfır eklenir. Ardından işlev çağrıları **iosbase**. **Genişlik**alan genişliği sıfırlamak için (0).

Doldurma oluşursa yalnızca en düşük öğe sayısı *N* çıkış alanı olduğunu belirtmek için gerekli az **iosbase**. [Genişlik](../standard-library/ios-base-class.md#width). Böyle doldurma oluşan bir dizi *N* - **genişliği** , kopyalar **dolgu**. Ardından doldurma aşağıdaki gibidir:

- Varsa **iosbase**. **bayrakları** & `ios_base::adjustfield` == `ios_base::`[sol](../standard-library/ios-functions.md#left), bayrağı **-** eklenir. (Doldurma, oluşturulan metin sonra gerçekleşir.)

- Varsa **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[iç](../standard-library/ios-functions.md#internal), bayrağı **0** eklenir. (Bir sayısal çıkış alanı için doldurma yazdırma işlevleri 0 ile burada paneli gerçekleşir.)

- Aksi takdirde, hiçbir ek bayrak eklenir. (Doldurma, oluşturulan sıralı önce gerçekleşir.)

Son olarak:

- Varsa **iosbase**. **bayrakları** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) sıfır bayrak **+** dönüştürme belirtimi için eklenir.

- Varsa **iosbase**. **bayrakları** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) sıfır bayrak **#** dönüştürme belirtimi için eklenir.

Tamsayı biçimi alanı tarafından belirlenen daha ayrıntılı çıktı [yerel ayar modeli](../standard-library/locale-class.md#facet_class)**fac** çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct ](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). Özellikle:

- **Fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) basamakların herhangi bir ondalık noktasının solunda nasıl gruplandığını belirler

- **Fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran dizeyi belirler

Gruplandırma kısıtlamalar tarafından uygulanan varsa **fac**. **Gruplandırma** (ilk öğesi CHAR_MAX değer varsa), ardından hiçbir örneklerini **fac**. `thousands_sep` Çıkış alanı oluşturulur. Aksi takdirde, yazdırma dönüştürme gerçekleşir sonra ayırıcıları eklenir.

İkinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `lu`.

Üçüncü korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

değerini bir kayan nokta çıkış alanından ürettiği dışında ilk olarak aynı şekilde davranır **val**. **Fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) tamsayı basamak kesirli basamaklardan ayıran dizeyi belirler. Eşdeğer yazdırma dönüştürme belirtimi şu şekilde belirlenir:

- Varsa **iosbase**. **bayrakları** & `ios_base::floatfield` == `ios_base::`[sabit](../standard-library/ios-functions.md#fixed), dönüştürme belirtimi `lf`.

- Varsa **iosbase**. **bayrakları** & **ios_base::floatfield** == `ios_base::`[bilimsel](../standard-library/ios-functions.md#scientific), dönüştürme belirtimi `le`. Varsa **iosbase**. **bayrakları** & `ios_base::`[büyük](../standard-library/ios-functions.md#uppercase) sıfır değilse, `e` ile değiştirilir `E`.

- Aksi takdirde, dönüştürme belirtimidir **lg**. Varsa **iosbase**. **bayrakları** & **ios_base::uppercase** sıfır değilse, `g` ile değiştirilir `G`.

Varsa **iosbase**. **bayrakları** & **ios_base::fixed** sıfır dışında olan veya **iosbase**. [Duyarlık](../standard-library/ios-base-class.md#precision) bir duyarlık değeri sıfırdan büyük **iosbase**. **Duyarlık** dönüştürme belirtimi için eklenir. Hiçbir doldurma tamsayı çıkış alanı olduğu gibi davranır. Doldurma karakteri **dolgu**. Son olarak:

- Varsa **iosbase**. **bayrakları** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) sıfır bayrak **+** dönüştürme belirtimi için eklenir.

- Varsa **iosbase**. **bayrakları** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) sıfır bayrak **#** dönüştürme belirtimi için eklenir.

Dördüncü korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

aynı şekilde davranır hariç üçüncü niteleyici `l` dönüştürme belirtimi ile değiştirilir `L`.

Beşinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

dönüştürme belirtimi olması dışında ilk davranır `p` **,** artı doldurma belirtmek için gereken tüm niteleyicisi.

Altıncı korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

bir Boolean çıkış alanından oluşturur, birincisi ile aynı davranış *val*.

Bir Boolean çıkış alanı iki biçimlerden birini alır. Varsa `iosbase.flags & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) olan **false**, üye işlevinin döndürdüğü `do_put(_Next, _Iosbase, _Fill, (long)val)`, hangi genellikle üretir oluşturulan bir sıralı ya da 0 (için **false**) veya 1 (için **true**). Aksi takdirde, oluşturulan sıralı geçerli *fac*.[ falsename](../standard-library/numpunct-class.md#falsename) (için **false**), veya *fac*.[ truename](../standard-library/numpunct-class.md#truename) (için **true**).

Yedinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `lld`.

Sekizinci korumalı sanal üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

bir dönüştürme belirtimi değiştirir dışında ilk olarak aynı şekilde davranır `ld` ile `llu`.

### <a name="example"></a>Örnek

Örneğin bakın [put](#put), çağıran `do_put`.

## <a name="iter_type"></a>  num_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **Outputıterator.**

## <a name="num_put"></a>  num_put::num_put

Türündeki nesneler için oluşturucu `num_put`.

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*<br/>
Bellek yönetimi için nesne türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: Nesnenin ömrünü, onu içeren yerel ayarlar tarafından yönetilir.

- 1: Nesnenin ömrünü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlı değil.

Yok edici korumalı olduğundan doğrudan örnek mümkündür.

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="put"></a>  num_put::Put

Dizisine bir sayı dönüştürür `CharType`sayıyı temsil eden bir belirtilen yerel ayar için biçimlendirilmiş.

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

*Hedef*<br/>
Eklenen dizenin ilk öğeyi adresleyen bir yineleyici.

*_Iosbase*<br/>
Numpunct modelinde çıkış ve çıktıyı biçimlendirmek için bayrakları punctuate kullanılacak yerel ayar içeren akış belirtildi.

*_Fill*<br/>
Aralığı için kullanılan karakter.

*VAL*<br/>
Sayı veya çıkış olarak Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Çıkış yineleyici son öğenin ötesinde konumu bir adresleri üretilen.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri dönüş [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `val`).

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

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
