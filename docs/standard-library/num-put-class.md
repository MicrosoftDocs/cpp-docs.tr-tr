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
ms.openlocfilehash: 49d76c5d553054934907cd2ddc0b7fd1f8b1e998
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687637"
---
# <a name="num_put-class"></a>num_put Sınıfı

Sayısal değerlerin `CharType` türündeki sıralara dönüştürülmesine yönelik bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType* \
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*OutputIterator* \
Sayısal koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_put](#num_put)|@No__t_0 türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayıyı, belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir `CharType`s dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[konur](#put)|Bir sayıyı, belirtilen bir yerel ayar için biçimlendirilen sayıyı temsil eden `CharType`s dizisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="char_type"></a>num_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `CharType` şablon parametresi için bir eş anlamlı.

## <a name="do_put"></a>num_put::d o_put

Bir sayıyı, belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir `CharType`s dizisine dönüştürmek için çağrılan bir sanal işlev.

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

*sonraki* \
Ekli dizenin ilk öğesini adresleyen bir yineleyici.

*_Iosbase* \
Çıktıyı biçimlendirmeye yönelik çıktıyı ve bayrakları bir yere eklemek için kullanılan sayısal tuş takımı ile yerel ayar içeren bir akış belirtildi.

*_Fill* \
Aralık için kullanılan bir karakter.

*val* \
Çıkış yapılacak sayı veya Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi *, değer '* den sonra bir tamsayı çıkış alanı üretmede *sonraki* ardışık öğeleri oluşturur. İşlevi, oluşturulan tamsayı çıkış alanının ötesinde bir öğe eklemek için sonraki yeri tanımlayarak bir yineleyici döndürür.

Tamsayı çıkış alanı, bir dosyaya bir dizi **char** öğesi oluşturmak için Print işlevleri tarafından kullanılan kurallar tarafından oluşturulur. Her bir Char öğesi, basit, bire bir eşleme tarafından `CharType` türünde eşdeğer bir öğeyle eşlenecek varsayılır. Bir Print işlevinin, boşluk veya 0 basamaklı bir alanı, ancak bunun yerine `do_put` `fill` kullanması gerekir. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer **iosbase**ise. [bayraklar](../standard-library/ios-base-class.md#flags)  &  `ios_base::basefield`  ==  `ios_base::`[Ekim](../standard-library/ios-functions.md#oct), dönüştürme belirtimi `lo`.

- **İosbase. flags**  & **ios_base:: basefield**  == [onaltılı](../standard-library/ios-functions.md#hex)`ios_base::`, dönüştürme belirtimi `lx`.

- Aksi takdirde, dönüştürme belirtimi `ld`.

Eğer **iosbase**ise. [Genişlik](../standard-library/ios-base-class.md#width) sıfır dışında, bu değerin alan genişliği, önüne getirilir. İşlev daha sonra **ıosbase**öğesini çağırır. alan genişliğini sıfıra sıfırlamak için **Genişlik**(0).

Doldurma yalnızca çıkış alanını belirtmek için gereken en az *sayıda öğe* **ıosbase**değerinden küçükse oluşur. [Genişlik](../standard-library/ios-base-class.md#width). Bu tür bir doldurma, **dolgunun**bir dizi *N*  - **genişliğiyle** oluşur. Doldurma daha sonra aşağıdaki gibi gerçekleşir:

- Eğer **iosbase**ise. **bayraklar**  &  `ios_base::adjustfield`  ==  `ios_base::`[sol](../standard-library/ios-functions.md#left), bayrak **-** önüne getirilir. (Doldurma, oluşturulan metinden sonra gerçekleşir.)

- **İosbase. flags**  & **ios_base:: adjustfield**  == [Internal](../standard-library/ios-functions.md#internal)`ios_base::`, **0** bayrağı önüne getirilir. (Sayısal bir çıkış alanı için, yazdırma işlevlerinin 0 ile ayarlandığı doldurma oluşur.)

- Aksi takdirde, ek bayrak alınmaz. (Doldurma, oluşturulan dizmeden önce gerçekleşir.)

Son olarak

- Eğer **iosbase**ise. `ios_base::`[showpos](../standard-library/ios-functions.md#showpos)  &  **bayrakları** sıfır dışında, **+** bayrağı dönüştürme belirtimine geri getirilir.

- Eğer **iosbase**ise. **flags**  & **ios_base::** [showbase](../standard-library/ios-functions.md#showbase) sıfırdan farklı, **#** bayrak, dönüştürme belirtimine eklenecek.

Bir tamsayı çıkış alanının biçimi, Call [use_facet](../standard-library/locale-functions.md#use_facet)  < [tuş takımı](../standard-library/numpunct-class.md) \< **elem>** ( **iosbase**)**tarafından döndürülen** [yerel ayar modeli](../standard-library/locale-class.md#facet_class)tarafından daha fazla belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)). Engelle

- **fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) , basamak gruplarını herhangi bir ondalık noktanın soluna ayıran Sırayı belirler

**Fac**tarafından gruplandırma kısıtlaması yoksa. **Gruplandırma** (Ilk öğesi CHAR_MAX değerine sahiptir), sonra **fac**örneği yoktur. `thousands_sep` çıktı alanında oluşturulur. Aksi takdirde, yazdırma dönüştürme gerçekleştikten sonra ayırıcılar eklenir.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

, `ld` dönüştürme belirtimini `lu` ile değiştirmesi dışında, ilki ile aynı şekilde davranır.

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

**Val**değerinden bir kayan nokta çıkış alanı ürettiğinden, ilki ile aynı şekilde davranır. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer **iosbase**ise. **bayraklar**  &  `ios_base::floatfield`  ==  `ios_base::`[düzeltildi](../standard-library/ios-functions.md#fixed), dönüştürme belirtimi `lf`.

- Eğer **iosbase**ise. **flags**  & **ios_base:: floatfield**  == [bilimsel](../standard-library/ios-functions.md#scientific)`ios_base::`, dönüştürme belirtimi `le`. Eğer **iosbase**ise. [büyük harfli](../standard-library/ios-functions.md#uppercase) `ios_base::`  &  **bayrakları** sıfır dışında `e` `E` ile değiştirilmiştir.

- Aksi takdirde, dönüştürme belirtimi **LG**' dir. Eğer **iosbase**ise. **bayraklar**  & **ios_base:: büyük harf** sıfır değil, `g` `G` ile değiştirilmiştir.

Eğer **iosbase**ise. **flags**  & **ios_base:: fixed** sıfır veya **iosbase**. [duyarlık](../standard-library/ios-base-class.md#precision) sıfırdan büyük, **ıosbase**değeri ile bir duyarlık. **duyarlık** , dönüştürme belirtimine göre sona erer. Herhangi bir doldurma, bir tamsayı çıkış alanı ile aynı şekilde davranır. Doldurma karakteri **Fill**. Son olarak

- Eğer **iosbase**ise. `ios_base::`[showpos](../standard-library/ios-functions.md#showpos)  &  **bayrakları** sıfır dışında, **+** bayrağı dönüştürme belirtimine geri getirilir.

- Eğer **iosbase**ise. `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint)  &  **bayrakları** sıfır dışında, **#** bayrağı dönüştürme belirtimine geri getirilir.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

dönüştürme belirtiminde `l` niteleyicinin `L` ile değiştirilmesinin dışında, üçüncüsü aynı şekilde davranır.

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

dönüştürme**belirtiminin `p` olması, ayrıca** doldurma belirtmek için gereken herhangi bir niteleyicinin olması dışında, ilki aynı şekilde davranır.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

*Val*'Den bir Boole çıktı alanı oluşturması dışında, ilki ile aynı şekilde davranır.

Boole çıkış alanı iki formdan birini alır. @No__t_0[boolalpha](../standard-library/ios-functions.md#boolalpha) **false**ise, üye işlevi genellikle 0 ( **yanlış**için) veya 1 ( **true**için) olarak üretilen bir dizi üreten `do_put(_Next, _Iosbase, _Fill, (long)val)` döndürür. Aksi takdirde, oluşturulan sıra *fac*olur. [falsename](../standard-library/numpunct-class.md#falsename) ( **false**için) veya *fac*. [truename](../standard-library/numpunct-class.md#truename) ( **true**için).

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

, `ld` dönüştürme belirtimini `lld` ile değiştirmesi dışında, ilki ile aynı şekilde davranır.

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

, `ld` dönüştürme belirtimini `llu` ile değiştirmesi dışında, ilki ile aynı şekilde davranır.

### <a name="example"></a>Örnek

@No__t_1 çağıran [PUT](#put)örneğine bakın.

## <a name="iter_type"></a>num_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **OutputIterator** şablon parametresi için bir eş anlamlı.

## <a name="num_put"></a>num_put::num_put

@No__t_0 türündeki nesneler için Oluşturucu.

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs* \
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)(_ *refs*) ile başlatır.

## <a name="put"></a>num_put::p UT

Bir sayıyı, belirtilen bir yerel ayar için biçimlendirilen sayıyı temsil eden `CharType`s dizisine dönüştürür.

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

*hedef* \
Ekli dizenin ilk öğesini adresleyen bir yineleyici.

*_Iosbase* \
Çıktıyı biçimlendirmeye yönelik çıktıyı ve bayrakları işaret etmek için kullanılan sayısal tuş takımı ile yerel ayar içeren bir akış belirtildi.

*_Fill* \
Aralık için kullanılan bir karakter.

*val* \
Çıkış yapılacak sayı veya Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri [do_put](#do_put)döndürür (`next`, `_Iosbase`, `_Fill`, `val`).

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

[\<locale >](../standard-library/locale.md) \
[model sınıfı](../standard-library/locale-class.md#facet_class) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
