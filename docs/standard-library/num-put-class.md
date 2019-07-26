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
ms.openlocfilehash: ac034a4b80225bd9674e72ca3255938316c5905a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457695"
---
# <a name="numput-class"></a>num_put Sınıfı

Sayısal değerlerin tür `CharType`dizilerine dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*OutputIterator*\
Sayısal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_put](#num_put)|Türündeki `num_put`nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayıyı, `CharType`belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürmek için çağrılan bir sanal işlev.|
|[konur](#put)|Bir sayıyı, `CharType`belirtilen bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="char_type"></a>num_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`için bir eş anlamlı.

## <a name="do_put"></a>num_put::d o_put

Bir sayıyı, `CharType`belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürmek için çağrılan bir sanal işlev.

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

*ileri*\
Ekli dizenin ilk öğesini adresleyen bir yineleyici.

*_Iosbase*\
Çıktıyı biçimlendirmeye yönelik çıktıyı ve bayrakları bir yere eklemek için kullanılan sayısal tuş takımı ile yerel ayar içeren bir akış belirtildi.

*_Doldur*\
Aralık için kullanılan bir karakter.

*Acil*\
Çıkış yapılacak sayı veya Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi, değer ' den sonra bir tamsayı çıkış alanı üretmede *sonraki* ardışık öğeleri *oluşturur.* İşlevi, oluşturulan tamsayı çıkış alanının ötesinde bir öğe eklemek için sonraki yeri tanımlayarak bir yineleyici döndürür.

Tamsayı çıkış alanı, bir dosyaya bir dizi **char** öğesi oluşturmak için Print işlevleri tarafından kullanılan kurallar tarafından oluşturulur. Her bir Char öğesi, basit, bire bir eşleme ile türünde `CharType` eşdeğer bir öğeyle eşlenecek şekilde varsayılır. Yazdırma işlevinin, `do_put` boşluk veya 0 basamaklı bir alanı, ancak bunun yerine kullanır `fill`. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer **iosbase**ise. [bayrak](../standard-library/ios-base-class.md#flags) & [Eki,](../standard-library/ios-functions.md#oct)dönüştürme belirtimi .`lo``ios_base::basefield` == `ios_base::`

- **İosbase. Flags** & **ios_base:: basefield** == `ios_base::`[onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi olur `lx`.

- Aksi takdirde, dönüştürme belirtimi olur `ld`.

Eğer **iosbase**ise. [Genişlik](../standard-library/ios-base-class.md#width) sıfır dışında, bu değerin alan genişliği, önüne getirilir. İşlev daha sonra **ıosbase**öğesini çağırır. **Genişlik** (0) alanı genişliğini sıfıra sıfırlamak için.

Doldurma yalnızca çıkış alanını belirtmek için gereken en az *sayıda öğe* **ıosbase**değerinden küçükse oluşur. [Genişlik](../standard-library/ios-base-class.md#width). Bu tür doldurma, **dolgunun** *N* - **Genişlik** kopyalarından oluşan bir dizisinden oluşur. Doldurma daha sonra aşağıdaki gibi gerçekleşir:

- Eğer **iosbase**ise. **bayrak kalmadı**[](../standard-library/ios-functions.md#left), **bayrak-** önüne getirilir. & `ios_base::adjustfield` == `ios_base::` (Doldurma, oluşturulan metinden sonra gerçekleşir.)

- **İosbase. Flags** & **ios_base:: adjustfield** == `ios_base::`[iç](../standard-library/ios-functions.md#internal), **0** bayrağı önüne getirilir. (Sayısal bir çıkış alanı için, yazdırma işlevlerinin 0 ile ayarlandığı doldurma oluşur.)

- Aksi takdirde, ek bayrak alınmaz. (Doldurma, oluşturulan dizmeden önce gerçekleşir.)

Son olarak

- Eğer **iosbase**ise.  & [showpos](../standard-library/ios-functions.md#showpos) **+** bayrakları`ios_base::`sıfır dışında, bayrak dönüştürme belirtimine göre sona erer.

- Eğer **iosbase**ise. **Flags**[](../standard-library/ios-functions.md#showbase) **#** ios_base:: showbase sıfırdan farklı, bayrak dönüştürme belirtimine göre sona erer. & 

Bir tamsayı çıkış alanının biçimi, Call [use_facet](../standard-library/locale-functions.md#use_facet) < [unct](../standard-library/numpunct-class.md) \< **eled**> ( **iosbase**) tarafından döndürülen [yerel ayar modeli](../standard-library/locale-class.md#facet_class)**fac** tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)). Engelle

- **fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) , basamak gruplarını herhangi bir ondalık noktanın soluna ayıran Sırayı belirler

**Fac**tarafından gruplandırma kısıtlaması yoksa. **Gruplandırma** (ilk öğesi CHAR_MAX değerine sahiptir), sonra **fac**örneği yoktur. `thousands_sep`çıktı alanında oluşturulur. Aksi takdirde, yazdırma dönüştürme gerçekleştikten sonra ayırıcılar eklenir.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `lu`aynı şekilde davranır.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

**Val**değerinden bir kayan nokta çıkış alanı ürettiğinden, ilki ile aynı şekilde davranır. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer **iosbase**ise. **bayraklar** & [düzeltildi,](../standard-library/ios-functions.md#fixed)dönüştürme belirtimi .`lf``ios_base::floatfield` == `ios_base::`

- Eğer **iosbase**ise. **Flags** == `ios_base::`[](../standard-library/ios-functions.md#scientific) `le`ios_base:: floatfield bilimsel, dönüştürme belirtimi. &  Eğer **iosbase**ise.  & [büyük harfli](../standard-library/ios-functions.md#uppercase) bayraklar`ios_base::`sıfır dışı ,`e` ile`E`değiştirilmiştir.

- Aksi takdirde, dönüştürme belirtimi **LG**' dir. Eğer **iosbase**ise. **Flags** `g` `G`ios_base:: büyük harf sıfır dışı, ile değiştirilmiştir. & 

Eğer **iosbase**ise. Flags & **ios_base:: fixed** , sıfır değil veya **iosbase**. [duyarlık](../standard-library/ios-base-class.md#precision) sıfırdan büyük, **ıosbase**değeri ile bir duyarlık. **duyarlık** , dönüştürme belirtimine göre sona erer. Herhangi bir doldurma, bir tamsayı çıkış alanı ile aynı şekilde davranır. Doldurma karakteri **Fill**. Son olarak

- Eğer **iosbase**ise.  & [showpos](../standard-library/ios-functions.md#showpos) **+** bayrakları`ios_base::`sıfır dışında, bayrak dönüştürme belirtimine göre sona erer.

- Eğer **iosbase**ise.  & [showpoint](../standard-library/ios-functions.md#showpoint) **#** bayrakları`ios_base::`sıfır dışında, bayrak dönüştürme belirtimine göre sona erer.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

dönüştürme belirtiminde niteleyicinin `l` `L`yenisiyle değiştirilmesinin dışında, üçüncüsü aynı şekilde davranır.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

, dönüştürme belirtiminin ve Padding belirtmek için gereken herhangi bir niteleyicinin `p` **olduğu durumlar** dışında, ilki ile aynı şekilde davranır.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

*Val*'Den bir Boole çıktı alanı oluşturması dışında, ilki ile aynı şekilde davranır.

Boole çıkış alanı iki formdan birini alır. `do_put(_Next, _Iosbase, _Fill, (long)val)`   [](../standard-library/ios-functions.md#boolalpha) Boolalpha false ise, üye işlevi genellikle 0 (yanlış için) veya 1 (true için) olarak oluşturulmuş bir dizi üretir. `iosbase.flags & ios_base::` Aksi takdirde, oluşturulan sıra *fac*olur. [falsename](../standard-library/numpunct-class.md#falsename) ( **false**için) veya *fac*. [truename](../standard-library/numpunct-class.md#truename) ( **true**için).

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `lld`aynı şekilde davranır.

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

, bir dönüştürme belirtimini `ld` ile değiştirmesi dışında, ilki ile `llu`aynı şekilde davranır.

### <a name="example"></a>Örnek

Öğesini çağıran `do_put` [PUT](#put)için örneğe bakın.

## <a name="iter_type"></a>num_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **OutputIterator** şablon parametresi için bir eş anlamlı.

## <a name="num_put"></a>num_put::num_put

Türündeki `num_put`nesneler için Oluşturucu.

```cpp
explicit num_put(size_t _Refs = 0);
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

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)(_ *refs*) ile başlatır.

## <a name="put"></a>num_put::p UT

Bir sayıyı, `CharType`belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürür.

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

*HD*\
Ekli dizenin ilk öğesini adresleyen bir yineleyici.

*_Iosbase*\
Çıktıyı biçimlendirmeye yönelik çıktıyı ve bayrakları işaret etmek için kullanılan sayısal tuş takımı ile yerel ayar içeren bir akış belirtildi.

*_Doldur*\
Aralık için kullanılan bir karakter.

*Acil*\
Çıkış yapılacak sayı veya Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri [do_put](#do_put)döndürür ( `next`, `_Iosbase` `_Fill`,,). `val`

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

[\<Yerel ayar >](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
