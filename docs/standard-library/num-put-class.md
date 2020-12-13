---
description: 'Hakkında daha fazla bilgi edinin: num_put sınıfı'
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
ms.openlocfilehash: 44f7d5248914969b360454bbec80e767a21be55f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338072"
---
# <a name="num_put-class"></a>num_put Sınıfı

Sayısal değerlerin tür dizilerine dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu `CharType` .

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
|[num_put](#num_put)|Türündeki nesneler için Oluşturucu `num_put` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir sayıyı, `CharType` belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürmek için çağrılan bir sanal işlev.|
|[konur](#put)|Bir sayıyı, `CharType` belirtilen bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="num_putchar_type"></a><a name="char_type"></a> num_put:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `CharType` .

## <a name="num_putdo_put"></a><a name="do_put"></a> num_put::d o_put

Bir sayıyı, `CharType` belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürmek için çağrılan bir sanal işlev.

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

*_Fill*\
Aralık için kullanılan bir karakter.

*Acil*\
Çıkış yapılacak sayı veya Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi *, değer '* den sonra bir tamsayı çıkış alanı üretmede *sonraki* ardışık öğeleri oluşturur. İşlevi, oluşturulan tamsayı çıkış alanının ötesinde bir öğe eklemek için sonraki yeri tanımlayarak bir yineleyici döndürür.

Tamsayı çıkış alanı, bir dosya için bir dizi öğe oluşturmak için Print işlevleri tarafından kullanılan kurallar tarafından oluşturulur **`char`** . Her bir Char öğesi `CharType` , basit, bire bir eşleme ile türünde eşdeğer bir öğeyle eşlenecek şekilde varsayılır. Yazdırma işlevinin, boşluk veya 0 basamaklı bir alanı, ancak `do_put` bunun yerine kullanır `fill` . Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer **iosbase** ise. [](../standard-library/ios-base-class.md#flags)  &  `ios_base::basefield` bayraklar  ==  `ios_base::` [Ekim](../standard-library/ios-functions.md#oct), dönüştürme belirtimi `lo` .

- **İosbase. Flags**  &  **ios_base: basefield**  ==  `ios_base::` [onaltılı](../standard-library/ios-functions.md#hex)ise, dönüştürme belirtimi olur `lx` .

- Aksi takdirde, dönüştürme belirtimi olur `ld` .

Eğer **iosbase** ise. [Genişlik](../standard-library/ios-base-class.md#width) sıfır dışında, bu değerin alan genişliği, önüne getirilir. İşlev daha sonra **ıosbase** öğesini çağırır. alan genişliğini sıfıra sıfırlamak için **Genişlik**(0).

Doldurma yalnızca çıkış alanını belirtmek için gereken en az *sayıda öğe* **ıosbase** değerinden küçükse oluşur. [Genişlik](../standard-library/ios-base-class.md#width). Bu tür doldurma, dolgunun *N*  -  **Genişlik** kopyalarından oluşan bir dizisinden oluşur.  Doldurma daha sonra aşağıdaki gibi gerçekleşir:

- Eğer **iosbase** ise.   &  `ios_base::adjustfield` bayraklar  ==  `ios_base::` [sol](../standard-library/ios-functions.md#left), bayrak **-** önüne getirilir. (Doldurma, oluşturulan metinden sonra gerçekleşir.)

- **İosbase. Flags**  &  **ios_base:: adjustfield**  ==  `ios_base::` [iç](../standard-library/ios-functions.md#internal), **0** bayrağı önüne getirilir. (Sayısal bir çıkış alanı için, yazdırma işlevlerinin 0 ile ayarlandığı doldurma oluşur.)

- Aksi takdirde, ek bayrak alınmaz. (Doldurma, oluşturulan dizmeden önce gerçekleşir.)

Son olarak

- Eğer **iosbase** ise.   &  bayraklar `ios_base::` [showpos](../standard-library/ios-functions.md#showpos) sıfır dışında, bayrak **+** dönüştürme belirtimine göre sona erer.

- Eğer **iosbase** ise. **bayraklar**  &  **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) sıfırdan farklı, bayrak **#** dönüştürme belirtimine göre sona erer.

Bir tamsayı çıkış alanının biçimi, çağrı [use_facet](../standard-library/locale-functions.md#use_facet) [](../standard-library/locale-class.md#facet_class)  <  [tuş takımı](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**) tarafından döndürülen yerel ayar modeli fac tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)). Özellikle:

- **fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) , herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran Sırayı belirler

**Fac** tarafından gruplandırma kısıtlaması yoksa. **Gruplandırma** (ilk öğesinin değeri CHAR_MAX), sonra **fac** örneği yoktur. `thousands_sep` çıktı alanında oluşturulur. Aksi takdirde, yazdırma dönüştürme gerçekleştikten sonra ayırıcılar eklenir.

İkinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `lu` .

Üçüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

**Val** değerinden bir kayan nokta çıkış alanı ürettiğinden, ilki ile aynı şekilde davranır. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) , kesir basamaklarından tamsayı basamaklarını ayıran diziyi belirler. Eşdeğer yazdırma dönüştürme belirtimi aşağıdaki şekilde belirlenir:

- Eğer **iosbase** ise.   &  `ios_base::floatfield` bayraklar  ==  `ios_base::` [düzeltildi](../standard-library/ios-functions.md#fixed), dönüştürme belirtimi `lf` .

- Eğer **iosbase** ise. **bayraklar**  &  **ios_base:: floatfield**  ==  `ios_base::` [bilimsel](../standard-library/ios-functions.md#scientific), dönüştürme belirtimi `le` . Eğer **iosbase** ise.   &  bayraklar `ios_base::` [büyük harf](../standard-library/ios-functions.md#uppercase) sıfır dışında, `e` ile değiştirilmiştir `E` .

- Aksi takdirde, dönüştürme belirtimi **LG**' dir. Eğer **iosbase** ise. **bayraklar**  &  **ios_base:: büyük harf** sıfır dışı, `g` ile değiştirilmiştir `G` .

Eğer **iosbase** ise. **bayraklar**  &  **ios_base:: fixed** , sıfır veya **iosbase**. [duyarlık](../standard-library/ios-base-class.md#precision) sıfırdan büyük, **ıosbase** değeri ile bir duyarlık. **duyarlık** , dönüştürme belirtimine göre sona erer. Herhangi bir doldurma, bir tamsayı çıkış alanı ile aynı şekilde davranır. Doldurma karakteri **Fill**. Son olarak

- Eğer **iosbase** ise.   &  bayraklar `ios_base::` [showpos](../standard-library/ios-functions.md#showpos) sıfır dışında, bayrak **+** dönüştürme belirtimine göre sona erer.

- Eğer **iosbase** ise.   &  bayraklar `ios_base::` [showpoint](../standard-library/ios-functions.md#showpoint) sıfırdan farklı, bayrak **#** dönüştürme belirtimine göre sona erer.

Dördüncü sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

dönüştürme belirtiminde niteleyicinin yenisiyle değiştirilmesinin dışında, üçüncüsü aynı şekilde davranır `l` `L` .

Beşinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

, dönüştürme belirtiminin ve `p` Padding belirtmek için gereken herhangi bir niteleyicinin olduğu durumlar dışında, **ilki ile aynı** şekilde davranır.

Altıncı sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

*Val*'Den bir Boole çıktı alanı oluşturması dışında, ilki ile aynı şekilde davranır.

Boole çıkış alanı iki formdan birini alır. `iosbase.flags & ios_base::` [Boolalpha](../standard-library/ios-functions.md#boolalpha) ise, **`false`** üye işlevi, `do_put(_Next, _Iosbase, _Fill, (long)val)` genellikle 0 (için **`false`** ) veya 1 (için) olarak oluşturulan bir dizi üretir **`true`** . Aksi takdirde, oluşturulan sıra *fac* olur. [falsename](../standard-library/numpunct-class.md#falsename) (için **`false`** ) veya *fac*.[ truename](../standard-library/numpunct-class.md#truename) (için **`true`** ).

Yedinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `lld` .

Sekizinci sanal korumalı üye işlevi:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

, bir dönüştürme belirtimini ile değiştirmesi dışında, ilki ile aynı şekilde davranır `ld` `llu` .

### <a name="example"></a>Örnek

Öğesini çağıran [PUT](#put)için örneğe bakın `do_put` .

## <a name="num_putiter_type"></a><a name="iter_type"></a> num_put:: iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **OutputIterator** şablon parametresi için bir eş anlamlı.

## <a name="num_putnum_put"></a><a name="num_put"></a> num_put:: num_put

Türündeki nesneler için Oluşturucu `num_put` .

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::**[model](../standard-library/locale-class.md#facet_class)(_ *refs*) ile başlatır.

## <a name="num_putput"></a><a name="put"></a> num_put::p UT

Bir sayıyı, `CharType` belirli bir yerel ayar için biçimlendirilen sayıyı temsil eden bir dizi öğesine dönüştürür.

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

*_Fill*\
Aralık için kullanılan bir karakter.

*Acil*\
Çıkış yapılacak sayı veya Boole türü.

### <a name="return-value"></a>Dönüş Değeri

Bir çıkış yineleyicisi, üretilen son öğeden sonraki konumdan bir konum adresindedir.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri [do_put](#do_put)döndürür (,,, `next` `_Iosbase` `_Fill` `val` ).

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

[\<locale>](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
