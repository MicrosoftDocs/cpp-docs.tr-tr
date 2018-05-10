---
title: num_put sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a860f7c266685e7e10f9b4cbe46c280c356f2681
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="numput-class"></a>num_put Sınıfı

Sayısal değerler Denetim dönüşümleri dizilerini türü için bir yerel ayar model olarak hizmet verebilir bir nesneyi tanımlayan bir şablon sınıfı `CharType`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

`CharType` Yerel karakter kodlamak için bir program içinde kullanılan türü.

`OutputIterator` Sayısal işlevleri çıktılarını yazma yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[num_put](#num_put)|Nesne türü Oluşturucusu `num_put`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir dizi sayıya dönüştürme için çağrılan bir sanal işlev `CharType`sayıyı temsil eden s biçimlendirilmiş belirtilen yerel ayar.|
|[PUT](#put)|Bir sayıyı bir dizi dönüştürür `CharType`sayısını temsil eden s biçimlendirilmiş belirtilen yerel ayar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  num_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

## <a name="do_put"></a>  num_put::do_put

Bir dizi sayıya dönüştürme için çağrılan bir sanal işlev **CharType**sayıyı temsil eden s biçimlendirilmiş belirtilen yerel ayar.

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

`next` Eklenen dizenin ilk öğe adresleme yineleyici.

`_Iosbase` Çıktı biçimlendirmesi bayrakları ve çıktı punctuate için kullanılan numpunct modeli ile yerel ayar içeren akış belirtilmiş.

`_Fill` Aralığı için kullanılan karakter.

`val` Sayı veya çıkış olacak Boolean türü.

### <a name="return-value"></a>Dönüş Değeri

Çıktı yineleyici adresleri son öğenin ötesinde konumu bir üretilen.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye fonksiyonu başlangıç sıralı öğeleri oluşturur `next` değeri bir tamsayı çıktı alanından üretmek için `val`. Oluşturulan tamsayı çıktı alanı dışında bir öğe eklemek için sonraki yer belirleme yineleyici işlevi döndürür.

Tamsayı çıktı alanı bir dizi oluşturmak için yazdırma işlevleri tarafından kullanılan aynı kurallar tarafından oluşturulan `char` öğeleri dosyaya. Her tür char öğe türü eşdeğer bir öğeye eşlemek için varsayılır **CharType** basit, bire bir eşleme tarafından. Ancak, boşluk veya 0 ise, basamaklı alanıyla yazdırma işlevi pads burada `do_put` yerine kullanır **dolgu**. Eşdeğer yazdırma dönüştürme belirtimi şu şekilde belirlenir:

- Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[Eki](../standard-library/ios-functions.md#oct), dönüştürme belirtimi **aet.aet**.

- Varsa **iosbase.flags** & **ios_base::basefield** == `ios_base::`[onaltılık](../standard-library/ios-functions.md#hex), dönüştürme belirtimi **lx** .

- Aksi takdirde, dönüştürme belirtimidir **ld**.

Varsa **iosbase**. [Genişlik](../standard-library/ios-base-class.md#width) olan bir alan genişliği bu değerin sıfır olmayan, eklenir. Daha sonra işlevi çağırır **iosbase**. **Genişlik**alan genişliği sıfırlamak için (0).

Doldurma oluşursa yalnızca en az öğe sayısını *N* çıktı alanı belirtmek için gerekli az **iosbase**. [Genişlik](../standard-library/ios-base-class.md#width). Bu tür doldurma bir dizi oluşan oluşur *N* - **genişliği** birini kopyalar **dolgu**. Ardından doldurma aşağıdaki gibidir:

- Varsa **iosbase**. **bayrakları** & `ios_base::adjustfield` == `ios_base::`[sol](../standard-library/ios-functions.md#left), bayrağı **-** eklenir. (Doldurma oluşturulan metinden sonra gerçekleşir.)

- Varsa **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[iç](../standard-library/ios-functions.md#internal), bayrağı **0** eklenir. (Sayısal çıkış alanı için dolgu burada 0 ile yazdırma işlevleri paneli oluşur.)

- Aksi takdirde, hiçbir ek bayrağı eklenir. (Doldurma önce oluşturulan dizisi gerçekleşir.)

Son olarak:

- Varsa **iosbase**. **bayrakları** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) sıfır olmayan, olan bayrağı **+** dönüştürme belirtimi eklenir.

- Varsa **iosbase**. **bayrakları** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) sıfır olmayan, olan bayrağı **#** dönüştürme belirtimi eklenir.

Tamsayı biçimi alan tarafından belirlenen daha ayrıntılı çıktı [yerel model](../standard-library/locale-class.md#facet_class)**fac** çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct ](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). Özellikle:

- **Fac**. [Gruplandırma](../standard-library/numpunct-class.md#grouping) basamak herhangi Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirler

- **Fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) herhangi Ondalık ayırıcının sol tarafındaki basamak grupları ayıran sırası belirler

Hiçbir gruplandırma kısıtlamaları tarafından uygulanan varsa **fac**. **Gruplandırma** (ilk öğe CHAR_MAX değeri varsa), ardından hiçbir örneği **fac**. `thousands_sep` Çıktı alanında oluşturulur. Aksi takdirde, yazdırma dönüştürme gerçekleştikten sonra ayırıcıları eklenir.

İkinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır **ld** ile **lu**.

Üçüncü sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

değeri kayan nokta çıktı alanından üreten dışında birinci ile aynı şekilde davranır **val**. **Fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) tamsayı basamak kesir rakamları ayıran sırası belirler. Eşdeğer yazdırma dönüştürme belirtimi şu şekilde belirlenir:

- Varsa **iosbase**. **bayrakları** & `ios_base::floatfield` == `ios_base::`[sabit](../standard-library/ios-functions.md#fixed), dönüştürme belirtimi **lf**.

- Varsa **iosbase**. **bayrakları** & **ios_base::floatfield** == `ios_base::`[bilimsel](../standard-library/ios-functions.md#scientific), dönüştürme belirtimi `le`. Varsa **iosbase**. **bayrakları** & `ios_base::`[büyük](../standard-library/ios-functions.md#uppercase) sıfır olmayan, olan **e** ile değiştirilir **E**.

- Aksi takdirde, dönüştürme belirtimidir **lg**. Varsa **iosbase**. **bayrakları** & **ios_base::uppercase** sıfır olmayan, olan **g** ile değiştirilir **G**.

Varsa **iosbase**. **bayrakları** & **ios_base::fixed** sıfır dışında olan veya **iosbase**. [Duyarlık](../standard-library/ios-base-class.md#precision) sıfır, değer kesinliği değerinden daha büyük **iosbase**. **Duyarlık** dönüştürme belirtimi eklenir. Herhangi bir doldurmaya tamsayı çıktı alan aynı şekilde davranır. Doldurma karakteri **dolgu**. Son olarak:

- Varsa **iosbase**. **bayrakları** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) sıfır olmayan, olan bayrağı **+** dönüştürme belirtimi eklenir.

- Varsa **iosbase**. **bayrakları** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) sıfır olmayan, olan bayrağı **#** dönüştürme belirtimi eklenir.

Dördüncü sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

aynı hariç üçüncü davrandığını niteleyici **l** dönüştürme belirtimi ile değiştirilir **L**.

Beşinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

dönüştürme belirtimi olması dışında aynı ilk davranır `p` **,** doldurma belirtmek için gereken niteleyicisi artı.

Altıncı sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

Boole çıkış alandan oluşturur dışında birinci ile aynı şekilde davranır `val`.

Boole çıktı alanı iki biçimlerden birini alır. Varsa **iosbase**. **bayrakları** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) olan **false**, üye işlevinin döndürdüğü `do_put`(_ *sonraki*, \_ *Iosbase*, \_ *doldurun*, ( **uzun**) `val`), hangi genellikle oluşturur ya da 0 oluşturulmuş bir dizi ( için**yanlış**) veya 1 (için **true**). Aksi takdirde, oluşturulan sıralı ya da değer **fac**. [falsename](../standard-library/numpunct-class.md#falsename) `)` (için **false**), veya **fac**. [truename](../standard-library/numpunct-class.md#truename) (için **true**).

Yedinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır **ld** ile **lld**.

Sekizinci sanal korumalı üye fonksiyonu:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

bir dönüştürme belirtimi yerini dışında birinci ile aynı şekilde davranır `ld` ile `llu`.

### <a name="example"></a>Örnek

Örneğin bkz [put](#put), çağıran `do_put`.

## <a name="iter_type"></a>  num_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **OutputIterator.**

## <a name="num_put"></a>  num_put::num_put

Nesne türü Oluşturucusu `num_put`.

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

`_Refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `_Refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.

Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="put"></a>  num_put::Put

Bir sayıyı bir dizi dönüştürür **CharType**sayıyı temsil eden s biçimlendirilmiş belirtilen yerel ayar.

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

`dest` Eklenen dizenin ilk öğe adresleme yineleyici.

`_Iosbase` Çıktı biçimlendirmesi bayrakları ve çıktı punctuate için kullanılan numpunct modeli ile yerel ayar içeren akışı belirtilmiş.

`_Fill` Aralığı için kullanılan karakter.

`val` Sayı veya çıkış olacak Boolean türü.

### <a name="return-value"></a>Dönüş Değeri

Çıktı yineleyici adresleri son öğenin ötesinde konumu bir üretilen.

### <a name="remarks"></a>Açıklamalar

Tüm üye işlevleri dönmek [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `val`).

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
