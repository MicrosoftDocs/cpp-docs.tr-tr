---
title: ios_base Sınıfı
description: Microsoft Visual C++ standart kitaplığı sınıfı için API başvurusu `ios_base`
ms.date: 10/23/2020
f1_keywords:
- xiosbase/std::ios_base
- ios/std::ios_base::event_callback
- xiosbase/std::ios_base::fmtflags
- xiosbase/std::ios_base::iostate
- xiosbase/std::ios_base::openmode
- xiosbase/std::ios_base::seekdir
- xiosbase/std::ios_base::event
- xiosbase/std::ios_base::adjustfield
- xiosbase/std::ios_base::app
- xiosbase/std::ios_base::ate
- xiosbase/std::ios_base::badbit
- xiosbase/std::ios_base::basefield
- xiosbase/std::ios_base::beg
- xiosbase/std::ios_base::binary
- xiosbase/std::ios_base::boolalpha
- xiosbase/std::ios_base::cur
- xiosbase/std::ios_base::dec
- xiosbase/std::ios_base::end
- xiosbase/std::ios_base::eofbit
- xiosbase/std::ios_base::failbit
- xiosbase/std::ios_base::fixed
- xiosbase/std::ios_base::floatfield
- xiosbase/std::ios_base::goodbit
- xiosbase/std::ios_base::hex
- xiosbase/std::ios_base::in
- xiosbase/std::ios_base::internal
- xiosbase/std::ios_base::left
- xiosbase/std::ios_base::oct
- xiosbase/std::ios_base::out
- xiosbase/std::ios_base::right
- xiosbase/std::ios_base::scientific
- xiosbase/std::ios_base::showbase
- xiosbase/std::ios_base::showpoint
- xiosbase/std::ios_base::showpos
- xiosbase/std::ios_base::skipws
- xiosbase/std::ios_base::trunc
- xiosbase/std::ios_base::unitbuf
- xiosbase/std::ios_base::uppercase
- xiosbase/std::ios_base::failure
- xiosbase/std::ios_base::flags
- xiosbase/std::ios_base::getloc
- xiosbase/std::ios_base::imbue
- xiosbase/std::ios_base::Init
- xiosbase/std::ios_base::iword
- xiosbase/std::ios_base::precision
- xiosbase/std::ios_base::pword
- ios/std::ios_base::register_callback
- xiosbase/std::ios_base::setf
- xiosbase/std::ios_base::sync_with_stdio
- xiosbase/std::ios_base::unsetf
- xiosbase/std::ios_base::width
- xiosbase/std::ios_base::xalloc
helpviewer_keywords:
- std::ios_base [C++]
- std::ios_base [C++], event_callback
- std::ios_base [C++], fmtflags
- std::ios_base [C++], iostate
- std::ios_base [C++], openmode
- std::ios_base [C++], seekdir
- std::ios_base [C++], event
- std::ios_base [C++], adjustfield
- std::ios_base [C++], app
- std::ios_base [C++], ate
- std::ios_base [C++], badbit
- std::ios_base [C++], basefield
- std::ios_base [C++], beg
- std::ios_base [C++], binary
- std::ios_base [C++], boolalpha
- std::ios_base [C++], cur
- std::ios_base [C++], dec
- std::ios_base [C++], end
- std::ios_base [C++], eofbit
- std::ios_base [C++], failbit
- std::ios_base [C++], fixed
- std::ios_base [C++], floatfield
- std::ios_base [C++], goodbit
- std::ios_base [C++], hex
- std::ios_base [C++], in
- std::ios_base [C++], internal
- std::ios_base [C++], left
- std::ios_base [C++], oct
- std::ios_base [C++], out
- std::ios_base [C++], right
- std::ios_base [C++], scientific
- std::ios_base [C++], showbase
- std::ios_base [C++], showpoint
- std::ios_base [C++], showpos
- std::ios_base [C++], skipws
- std::ios_base [C++], trunc
- std::ios_base [C++], unitbuf
- std::ios_base [C++], uppercase
- std::ios_base [C++], failure
- std::ios_base [C++], flags
- std::ios_base [C++], getloc
- std::ios_base [C++], imbue
- std::ios_base [C++], Init
- std::ios_base [C++], iword
- std::ios_base [C++], precision
- std::ios_base [C++], pword
- std::ios_base [C++], register_callback
- std::ios_base [C++], setf
- std::ios_base [C++], sync_with_stdio
- std::ios_base [C++], unsetf
- std::ios_base [C++], width
- std::ios_base [C++], xalloc
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
ms.openlocfilehash: b425df2cf8d0c98c3558b377c29d013adf82d014
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907564"
---
# <a name="ios_base-class"></a>ios_base Sınıfı

Sınıfı, şablon parametrelerine bağlı olmayan hem giriş hem de çıkış akışları için ortak olan depolama ve üye işlevlerini açıklar. (Sınıf şablonu, [`basic_ios`](../standard-library/basic-ios-class.md) neyin yaygın olduğunu ve şablon parametrelerine bağımlı olduğunu açıklar.)

Sınıfının bir nesnesi, ' den oluşan biçimlendirme bilgilerini depolar ios_base.

- Türü bir nesne içindeki biçim bayrakları [`fmtflags`](#fmtflags) .

- Türünde bir nesnede özel durum maskesi [`iostate`](#iostate) .

- Türündeki bir nesnedeki alan genişliği `int` .

- Türünde bir nesnede bir görüntüleme hassasiyeti `int` .

- Türünde bir nesnede yerel ayar nesnesi `locale` .

- Türü ve işaretçisi öğeleri olan iki Genişletilebilir dizi `long` `void` .

İos_base sınıfının bir nesnesi, akış durum bilgilerini türü bir nesne [`iostate`](#iostate) ve geri çağırma yığını da depolar.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[`ios_base`](#ios_base)|`ios_base`Nesneler oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[`event_callback`](#event_callback)|Öğesine geçirilen bir işlevi açıklar [`register_call`](#register_callback) .|
|[`fmtflags`](#fmtflags)|Çıktının görünümünü belirtmek için sabitler.|
|[`iostate`](#iostate)|Akışın durumunu açıklayan sabitleri tanımlar.|
|[`openmode`](#openmode)|Bir Stream ile nasıl etkileşim kuracağınızı açıklar.|
|[`seekdir`](#seekdir)|Dengeleme işlemleri için başlangıç noktasını belirtir.|

### <a name="enums"></a>Numaralandırmalar

|Ad|Açıklama|
|-|-|
|[`event`](#event)|Olay türlerini belirtir.|

### <a name="constants"></a>Sabitler

|Ad|Açıklama|
|-|-|
|[`adjustfield`](#fmtflags)|Olarak tanımlanan bir bit maskesi `internal` \| `left` \| `right` .|
|[`app`](#openmode)|Her ekleme işleminden önce akışın sonuna kadar aramayı belirtir.|
|[`ate`](#openmode)|Denetim nesnesi ilk oluşturulduğunda akışın sonuna aramayı belirtir.|
|[`badbit`](#iostate)|Akış arabelleğinin bütünlüğünden oluşan bir kayıp kaydeder.|
|[`basefield`](#fmtflags)|Olarak tanımlanan bir bit maskesi `dec` \| `hex` \| `oct` .|
|[`beg`](#seekdir)|Bir dizinin başlangıcına göre aramayı belirtir.|
|[`binary`](#openmode)|Bir dosyanın metin akışı yerine ikili akış olarak okunması gerektiğini belirtir.|
|[`boolalpha`](#fmtflags)|Tür nesnelerinin, `bool` `true` sayısal değerler yerine ad (ve gibi) olarak eklenmesi veya ayıklanmasını belirtir `false` .|
|[`cur`](#seekdir)|Bir dizi içindeki geçerli konuma göre aramayı belirtir.|
|[`dec`](#fmtflags)|Ondalık biçimdeki tamsayı değerlerinin eklenmesini veya ayıklanmasını belirtir.|
|[`end`](#seekdir)|Bir sıranın sonuna göre aramayı belirtir.|
|[`eofbit`](#iostate)|Akıştan ayıklanan dosya sonunu kaydeder.|
|[`failbit`](#iostate)|Akıştan geçerli bir alan ayıklama hatası kaydeder.|
|[`fixed`](#fmtflags)|Kayan nokta değerlerinin sabit noktalı biçimde (üs alanı olmadan) eklenmesini belirtir.|
|[`floatfield`](#fmtflags)|Olarak `fixed` \| tanımlanan bir bit maskesi `scientific`|
|[`goodbit`](#iostate)|Tüm durum bitleri net.|
|[`hex`](#fmtflags)|Tamsayı değerlerinin onaltılık biçimde eklenmesini veya ayıklanmasını belirtir.|
|[`in`](#openmode)|Akıştan ayıklama belirtir.|
|[`internal`](#fmtflags)|Oluşturulan bir sayısal alana yönelik bir noktada Fill karakterleri ekleyerek alan genişliğine göre doldurur.|
|[`left`](#fmtflags)|Sola yaslama belirtir.|
|[`oct`](#fmtflags)|Tamsayı değerlerinin sekizli biçimde eklenmesini veya ayıklanmasını belirtir.|
|[`out`](#openmode)|Bir akışa ekleme belirtir.|
|[`right`](#fmtflags)|Sağ gerekçe belirtir.|
|[`scientific`](#fmtflags)|Kayan nokta değerlerinin bilimsel biçimde (üs alanı ile) eklenmesini belirtir.|
|[`showbase`](#fmtflags)|Oluşturulan bir tamsayı alanının temelini ortaya çıkaran bir ön ek ekleme işlemini belirtir.|
|[`showpoint`](#fmtflags)|Oluşturulan kayan nokta alanında ondalık noktanın koşulsuz eklenmesini belirtir.|
|[`showpos`](#fmtflags)|Negatif olmayan oluşturulan sayısal bir alanda artı işareti ekleme işlemini belirtir.|
|[`skipws`](#fmtflags)|Belirli dışlamaları öncesinde baştaki boşluk atlanmasını belirtir.|
|[`trunc`](#openmode)|Denetim nesnesi oluşturulduğunda varolan bir dosyanın içeriğini silmeyi belirtir.|
|[`unitbuf`](#fmtflags)|Her ekleme işleminden sonra çıktının temizlenmesine neden olur.|
|[`uppercase`](#fmtflags)|Belirli eklemelerde küçük harflerin büyük harfli eşdeğerlerinin eklenmesini belirtir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[`failure`](#failure)|Üye sınıfı, Sınıf şablonunda [basic_ios](../standard-library/basic-ios-class.md) [üye işlevi tarafından](../standard-library/basic-ios-class.md#clear) oluşturulan tüm özel durumlar için temel sınıf işlevi görür.|
|[`flags`](#flags)|Geçerli bayrak ayarlarını ayarlar veya döndürür.|
|[`getloc`](#getloc)|Depolanan yerel ayar nesnesini döndürür.|
|[`imbue`](#imbue)|Yerel ayarı değiştirir.|
|[`Init`](#init)|`iostream`Oluşturulduğunda Standart nesneleri oluşturur.|
|[`iword`](#iword)|Olarak depolanacak bir değer atar `iword` .|
|[`precision`](#precision)|Kayan noktalı bir sayı içinde görüntülenecek basamakların sayısını belirtir.|
|[`pword`](#pword)|Olarak depolanacak bir değer atar `pword` .|
|[`register_callback`](#register_callback)|Bir geri çağırma işlevi belirtir.|
|[`setf`](#setf)|Belirtilen bayrakları ayarlar.|
|[`sync_with_stdio`](#sync_with_stdio)|`iostream`Ve C çalışma zamanı kitaplığı işlemlerinin, kaynak kodda göründükleri sırada gerçekleşmesini sağlar.|
|[`unsetf`](#unsetf)|Belirtilen bayrakların kapalı olmasına neden olur.|
|[`width`](#width)|Çıkış akışının uzunluğunu ayarlar.|
|[`xalloc`](#xalloc)|Bir değişkenin akışın parçası olmayacağını belirtir.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[`operator=`](#op_eq)|Nesneler için atama işleci `ios_base` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<ios>

**Ad alanı:** std

## <a name="event"></a><a name="event"></a> `event`

Olay türlerini belirtir.

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>Açıklamalar

Türü, ile kaydedilen bir işleve bağımsız değişken olarak kullanılan geri çağırma olayını depolayabilen bir nesneyi açıklayan, numaralandırılmış bir türdür [`register_callback`](#register_callback) . Ayrı olay değerleri şunlardır:

- `copyfmt_event`, bir çağrısının sonuna yakın bir şekilde bir geri çağırma işlemini belirlemek için [`copyfmt`](../standard-library/basic-ios-class.md#copyfmt) , [özel durum maskesi](../standard-library/ios-base-class.md) kopyalanmadan hemen önce.

- `erase_event`, bir çağrısının başlangıcında [`copyfmt`](../standard-library/basic-ios-class.md#copyfmt) veya bir yıkıcının çağrısının başlangıcında oluşan bir geri çağırma işlemini belirlemek için `*this` .

- `imbue_event`, bir çağrısının sonunda gerçekleşen bir geri çağırma işlemini belirlemek için [`imbue`](#imbue) , işlevin dönüşmesinden hemen önce.

### <a name="example"></a>Örnek

[`register_callback`](#register_callback)Bir örnek için bkz..

## <a name="event_callback"></a><a name="event_callback"></a> `event_callback`

Öğesine geçirilen bir işlevi açıklar [`register_call`](#register_callback) .

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Parametreler

*`_E`*\
[`event`](#event).

*`_Base`*\
Olayın çağrıldığı akış.

*`_I`*\
Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Türü, ile kaydedileyeşabilebir işlev için bir işaretçi tanımlar [`register_callback`](#register_callback) . Bu tür bir işlevin özel durum oluşturması gerekir.

### <a name="example"></a>Örnek

Tarafından [`register_call`](#register_callback) kullanılan bir örnek için bkz `event_callback` ..

## <a name="failure"></a><a name="failure"></a> `failure`

Sınıfı, `failure` `iostreams` akış arabelleği işlemleri sırasında algılanan hataları raporlamak için, kitaplıktaki işlevlere göre özel durum olarak oluşturulan tüm nesnelerin türleri için temel sınıfı tanımlar.

```cpp
namespace std {
    class failure : public system_error {
    public:
        explicit failure(
            const string& _Message,
            const error_code& _Code = io_errc::stream);

        explicit failure(
            const char* str,
            const error_code& _Code = io_errc::stream);
    };
}
```

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what()` `_Message` , büyük olasılıkla bir test ile birlikte genişletilmiş bir kopyasıdır `_Code` . `_Code`Belirtilmemişse, varsayılan değer `make_error_code(io_errc::stream)` .

### <a name="example"></a>Örnek

```cpp
// ios_base_failure.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.exceptions(ios::failbit);
    try
    {
        file.open( "rm.txt", ios_base::in );
        // Opens nonexistent file for reading
    }
    catch( ios_base::failure f )
    {
        cout << "Caught an exception: " << f.what() << endl;
    }
}
```

```Output
Caught an exception: ios_base::failbit set
```

## <a name="flags"></a><a name="flags"></a> `flags`

Geçerli bayrak ayarlarını ayarlar veya döndürür.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Parametreler

*`fmtfl`*\
Yeni `fmtflags` ayar.

### <a name="return-value"></a>Dönüş Değeri

Önceki veya geçerli `fmtflags` ayar.

### <a name="remarks"></a>Açıklamalar

[`ios_base::fmtflags`](#fmtflags)Bayrakların listesi için bkz..

İlk üye işlevi depolanan biçim bayraklarını döndürür. İkinci üye işlevi *`fmtfl`* Biçim bayraklarını depolar ve önceki depolanmış değerini döndürür.

### <a name="example"></a>Örnek

```cpp
// ios_base_flags.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    cout << cout.flags( ) << endl;
    cout.flags( ios::dec | ios::boolalpha );
    cout << cout.flags( );
}
```

```Output
513
16896
```

## <a name="fmtflags"></a><a name="fmtflags"></a> `fmtflags`

Çıktının görünümünü belirtmek için sabitler.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type fmtflags;
   static const fmtflags boolalpha;
   static const fmtflags dec;
   static const fmtflags fixed;
   static const fmtflags hex;
   static const fmtflags internal;
   static const fmtflags left;
   static const fmtflags oct;
   static const fmtflags right;
   static const fmtflags scientific;
   static const fmtflags showbase;
   static const fmtflags showpoint;
   static const fmtflags showpos;
   static const fmtflags skipws;
   static const fmtflags unitbuf;
   static const fmtflags uppercase;
   static const fmtflags adjustfield;
   static const fmtflags basefield;
   static const fmtflags floatfield;
   // ...
};
```

### <a name="remarks"></a>Açıklamalar

, İçindeki işleicileri destekler [`ios`](../standard-library/ios.md) .

Tür, biçim bayraklarını depolayabilen bir nesneyi açıklayan bir bit maskesi türüdür. DISTINCT bayrak değerleri (öğeler) şunlardır:

- `dec`tamsayı değerlerini ondalık biçimde eklemek veya ayıklamak için.

- `hex`, tamsayı değerlerini onaltılık biçimde eklemek veya ayıklamak için.

- `oct`, tamsayı değerlerini sekizlik biçimde eklemek veya ayıklamak için.

- `showbase`, oluşturulan bir tamsayı alanının temelini ortaya çıkaran bir ön ek eklemek için.

- `internal`, üretilen bir sayısal alana işaret eden bir noktaya doldurma karakterleri ekleyerek gerektiği şekilde bir alan genişliğine doldurma. (Alan genişliğini ayarlama hakkında daha fazla bilgi için bkz [`setw`](../standard-library/iomanip-functions.md#setw) .).

- `left`, oluşturulan bir alanın sonuna doldurma karakterleri ekleyerek gerektiği şekilde bir alan genişliğine doldurma (sol gerekçe).

- `right`, oluşturulan alanın başına doldurma karakterleri ekleyerek gerektiği şekilde bir alan genişliğine doldurma (sağ gerekçe).

- `boolalpha`, tür nesnelerini `bool` `true` sayısal değerler yerine ad (ve gibi) olarak eklemek veya ayıklamak için `false` .

- `fixed`, kayan nokta değerlerini sabit noktalı biçimde (üs alanı olmadan) eklemek için.

- `scientific`, kayan nokta değerlerini bilimsel biçimde (üs alanı ile) eklemek için.

- `showpoint`, üretilen kayan nokta alanına koşulsuz olarak ondalık bir nokta eklemek için.

- `showpos`, negatif olmayan oluşturulan sayısal bir alanda artı işareti eklemek için.

- `skipws`, belirli dışlamaları öncesinde baştaki boşluğu atlamak için.

- `unitbuf`Her ekleme işleminden sonra çıktıyı temizlemek için.

- `uppercase`, belirli eklemelerde küçük harflerin büyük harfli eşdeğerleri eklemek için.

Ayrıca, birkaç yararlı değer şunlardır:

- `adjustfield`, `internal` \| `left` olarak \| tanımlanan bir bit maskesi `right`

- `basefield`, `dec` \| `hex` şöyle \| tanımlanır `oct`

- `floatfield`, şöyle `fixed` \| tanımlanır `scientific`

Bu biçim bayraklarını değiştiren işlevlerin örnekleri için bkz [`<iomanip>`](../standard-library/iomanip.md) ..

## <a name="getloc"></a><a name="getloc"></a> `getloc`

Depolanan yerel ayar nesnesini döndürür.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan yerel ayar nesnesi.

### <a name="example"></a>Örnek

```cpp
// ios_base_getlock.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << cout.getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="imbue"></a><a name="imbue"></a> `imbue`

Yerel ayarı değiştirir.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*`_Loc`*\
Yeni yerel ayar ayarı.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *`_Loc`* yerel ayar nesnesini depolar ve sonra geri çağırma olayını ve bildirir `imbue_event` . Önceki depolanmış değeri döndürür.

### <a name="example"></a>Örnek

[`basic_ios::imbue`](../standard-library/basic-ios-class.md#imbue)Bir örnek için bkz..

## <a name="init"></a><a name="init"></a> `Init`

`iostream`Oluşturulduğunda Standart nesneleri oluşturur.

```cpp
class Init { };
```

### <a name="remarks"></a>Açıklamalar

İç içe yerleştirilmiş sınıf, bir `iostream` oluşturucunun rastgele bir statik nesne için yürütülmesinden önce bile standart nesnelerin düzgün şekilde oluşturulmasını sağlayan bir nesneyi açıklar.

## <a name="ios_base"></a><a name="ios_base"></a> `ios_base`

İos_base nesneleri oluşturur.

```cpp
ios_base();
```

### <a name="remarks"></a>Açıklamalar

(Korumalı) Oluşturucu hiçbir şey yapmaz. Daha sonraki bir `basic_ios::` [Init](../standard-library/basic-ios-class.md#init) çağrısı, güvenli bir şekilde yok edilebilmesi için nesneyi başlatmalıdır. Bu nedenle, ios_base sınıfı için tek güvenli kullanım sınıfı şablon [basic_ios](../standard-library/basic-ios-class.md)temel bir sınıf olarak bulunur.

## <a name="iostate"></a><a name="iostate"></a> `iostate`

Akışın durumunu tanımlayan sabitlerin türü.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Açıklamalar

Türü, Stream durum bilgilerini depolayabilen bir nesneyi açıklayan bir bit maskesi türüdür. DISTINCT bayrak değerleri (öğeler) şunlardır:

- `badbit`, akış arabelleğinin bütünlüğü kaybını kaydetmek için.
- `eofbit`, bir akıştan ayıklama sırasında dosya sonunu kaydetmek için.
- `failbit`bir akıştan geçerli bir alan ayıklama hatası kaydetmek için.

Buna ek olarak, `goodbit` daha önce bahsedilen bitlerin hiçbirinin ayarlandığı, yararlı bir değer ( `goodbit` sıfır olduğu garanti edilir).

## <a name="iword"></a><a name="iword"></a> `iword`

Olarak depolanacak bir değer atar `iword` .

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Parametreler

*`idx`*\
Depolanacak değerin dizini `iword` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Genişletilebilir dizinin öğe *IDX* öğesine, türündeki öğeleri içeren bir başvuru döndürür `long` . Tüm öğeler etkili bir şekilde bulunur ve başlangıçta sıfır değerini depolar. Döndürülen başvuru, nesne için bir sonraki çağrıdan sonra, nesne `iword` öğesine yapılan bir çağrı tarafından değiştirildikten sonra `basic_ios::` [`copyfmt`](../standard-library/basic-ios-class.md#copyfmt) veya nesne yok edildiğinde geçersizdir.

*`idx`* Negatifse veya öğe için benzersiz depolama alanı kullanılamıyorsa, işlev, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` benzersiz olmayan bir başvuru çağırır ve döndürür.

Tüm nesneler genelinde kullanılmak üzere benzersiz bir dizin almak için, `ios_base` çağrısı yapın [`xalloc`](#xalloc) .

### <a name="example"></a>Örnek

[`xalloc`](#xalloc)Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz `iword` ..

## <a name="openmode"></a><a name="openmode"></a> `openmode`

Bir Stream ile nasıl etkileşim kuracağınızı açıklar.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type openmode;
   static const openmode  in;
   static const openmode  out;
   static const openmode  ate;
   static const openmode  app;
   static const openmode  trunc;
   static const openmode  binary;
   // ...
};
```

### <a name="remarks"></a>Açıklamalar

Birçok nesne için açma modu `iostream` . Bayrak değerleri şunlardır:

| Sabit | Etki  |
|---------|---------|
| `app` | Her yazmadan önce akışın sonuna kadar ara |
| `ate`  | Açık olduktan hemen sonra akışın sonuna kadar ara |
| `binary`| İkili modda açın. ( [`fopen`](../c-runtime-library/reference/fopen-wfopen.md) İkili modun açıklaması için bkz.)|
| `in` |   Okuma için aç |
| `out` | Yazma için aç |
| `trunc` | Açık olduktan sonra dosyanın içeriğini Sil |

### <a name="example"></a>Örnek

```cpp
// ios_base_openmode.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
}
```

## <a name="operator"></a><a name="op_eq"></a> `operator=`

İos_base nesneler için atama işleci.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Parametreler

*`right`*\
`ios_base` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Atanmakta olan nesne.

### <a name="remarks"></a>Açıklamalar

İşleci, Genişletilebilir dizilerin yeni bir kopyasını oluşturan, depolanan biçimlendirme bilgilerini kopyalar. Ardından döndürür `*this` . Geri çağırma yığınının kopyalanmadığını unutmayın.

Bu işleç yalnızca öğesinden türetilmiş sınıflar tarafından kullanılır `ios_base` .

## <a name="precision"></a><a name="precision"></a> `precision`

Kayan noktalı bir sayı içinde görüntülenecek basamakların sayısını belirtir.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Parametreler

*`_Prec`*\
Sabit gösterimdeki ondalık ayırıcıdan sonraki basamak sayısı veya görüntülenecek önemli basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi depolanan [görüntüleme duyarlığını](../standard-library/ios-base-class.md)döndürür. İkinci üye işlevi, görüntüleme duyarlığını *_Prec* depolar ve önceki depolanmış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Kayan noktalı sayılar sabit gösterimde [düzeltildi](../standard-library/ios-functions.md#fixed)olarak görüntülenir.

### <a name="example"></a>Örnek

```cpp
// ios_base_precision.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    float i = 31.31234F;

    cout.precision( 3 );
    cout << i << endl;          // display three significant digits
    cout << fixed << i << endl; // display three digits after decimal
                                // point
}
```

```Output
31.3
31.312
```

## <a name="pword"></a><a name="pword"></a> `pword`

Olarak depolanacak bir değer atar `pword` .

```cpp
void *& pword(int index);
```

### <a name="parameters"></a>Parametreler

*`index`*\
Depolanacak değerin dizini `pword` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, işaretçi türündeki öğeleri içeren Genişletilebilir dizinin öğe *dizinine* bir başvuru döndürür `void` . Tüm öğeler etkili bir şekilde bulunur ve başlangıçta null işaretçiyi depolar. Döndürülen başvuru, nesne için bir sonraki çağrıdan sonra, nesne `pword` öğesine yapılan bir çağrı tarafından değiştirildikten sonra `basic_ios::` [`copyfmt`](../standard-library/basic-ios-class.md#copyfmt) veya nesne yok edildiğinde geçersizdir.

*Dizin* negatifse veya öğe için benzersiz depolama alanı kullanılamıyorsa işlev, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` benzersiz olmayan bir başvuru çağırır ve döndürür.

Tüm nesneler genelinde kullanılmak üzere benzersiz bir dizin almak için, `ios_base` çağrısı yapın [`xalloc`](#xalloc) .

### <a name="example"></a>Örnek

[`xalloc`](#xalloc)Hakkında bir örnek için bkz `pword` ..

## <a name="register_callback"></a><a name="register_callback"></a> `register_callback`

Bir geri çağırma işlevi belirtir.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Parametreler

*`pfn`*\
Geri çağırma işlevine yönelik işaretçi.

*`idx`*\
Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, çiftin `{pfn, idx}` depolanan geri çağırma yığını [geri çağırma yığınına](../standard-library/ios-base-class.md)iter. Bir geri **çağırma olayı oluşturulduğunda** , işlevler, ifadeye göre ters kayıt sırasında çağrılır `(*pfn)(ev, *this, idx)` .

### <a name="example"></a>Örnek

```cpp
// ios_base_register_callback.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void callback1( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback1" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

void callback2( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback2" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

int main( )
{
    // Make sure the imbue will not throw an exception
    // assert( setlocale( LC_ALL, "german" )!=NULL );

    cout.register_callback( callback1, 0 );
    cin.register_callback( callback2, 0 );

    try
    {
        // If no exception because the locale's not found,
        // generate an imbue_event on callback1
        cout.imbue(locale("german"));
    }
    catch(...)
    {
        cout << "exception" << endl;
    }

    // This will
    // (1) erase_event on callback1
    // (2) copyfmt_event on callback2
    cout.copyfmt(cin);

    // We get two erase events from callback2 at the end because
    // both cin and cout have callback2 registered when cin and cout
    // are destroyed at the end of program.
}
```

```Output
in callback1
an imbue event
in callback1
an erase event
in callback2
an copyfmt event
in callback2
an erase event
in callback2
an erase event
```

## <a name="seekdir"></a><a name="seekdir"></a> `seekdir`

Dengeleme işlemleri için başlangıç noktasını belirtir.

```cpp
namespace std {
    class ios_base {
    public:
        typedef implementation-defined-enumerated-type seekdir;
        static const seekdir beg;
        static const seekdir cur;
        static const seekdir end;
        // ...
    };
}
```

### <a name="remarks"></a>Açıklamalar

Türü, birkaç sınıfın üye işlevlerine bağımsız değişken olarak kullanılan arama modunu depolayabilen bir nesneyi açıklayan bir numaralandırılmış türdür `iostream` . DISTINCT bayrak değerleri şunlardır:

- `beg`, bir sıranın (dizi, akış veya dosya) başına göreli olarak (geçerli okuma veya yazma konumunu değiştirme) arama yapmak.

- `cur`, bir dizi içindeki geçerli konuma göre arama yapmak için.

- `end`, bir sıranın sonuna göre arama yapmak için.

### <a name="example"></a>Örnek

```cpp
// ios_base_seekdir.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
    file.seekp( 0, ios_base::beg );
    file << "a";
    file.seekp( 0, ios_base::end );
    file << "a";
}
```

## <a name="setf"></a><a name="setf"></a> `setf`

Belirtilen bayrakları ayarlar.

```cpp
fmtflags setf(
    fmtflags _Mask
);
fmtflags setf(
    fmtflags _Mask,
    fmtflags _Unset
);
```

### <a name="parameters"></a>Parametreler

*`_Mask`*\
Açmak için bayraklar.

*`_Unset`*\
Kapatılacak bayraklar.

### <a name="return-value"></a>Dönüş Değeri

Önceki biçim bayrakları

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi etkin bir şekilde çağırır [`flags(_Mask | _Flags)`](#flags) (seçili bitleri ayarlar) ve ardından önceki biçim bayraklarını döndürür. İkinci üye işlevi etkin bir şekilde çağırır `flags(_Mask & fmtfl, flags & ~_Mask)` (seçili bitleri bir maske altında değiştirir) ve ardından önceki biçim bayraklarını döndürür.

### <a name="example"></a>Örnek

```cpp
// ios_base_setf.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    int i = 10;
    cout << i << endl;

    cout.unsetf( ios_base::dec );
    cout.setf( ios_base::hex );
    cout << i << endl;

    cout.setf( ios_base::dec );
    cout << i << endl;
    cout.setf( ios_base::hex, ios_base::dec );
    cout << i << endl;
}
```

## <a name="sync_with_stdio"></a><a name="sync_with_stdio"></a> `sync_with_stdio`

`iostream`Ve C çalışma zamanı kitaplığı işlemlerinin, kaynak kodda göründükleri sırada gerçekleşmesini sağlar.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Parametreler

*`_Sync`*\
Tüm akışların ile eşitlenmiş olup olmadığı `stdio` .

### <a name="return-value"></a>Dönüş Değeri

Bu işlev için önceki ayar.

### <a name="remarks"></a>Açıklamalar

Statik üye işlevi `stdio` , başlangıçta olan bir eşitleme bayrağını depolar `true` . Ne zaman `true` Bu bayrak, [`iostreams`](../standard-library/iostreams-conventions.md) C++ standart kitaplığı 'nda tanımlanmış işlevler ile aynı dosyadaki işlemlerin düzgün şekilde eşitlenmesini sağlar. Aksi takdirde, eşitleme garanti edilebilir veya olmayabilir, ancak performans artırılabilir. İşlevi, *_Sync* `stdio` eşitleme bayrağında _Sync depolar ve önceki depolanmış değerini döndürür. Standart akışlarda herhangi bir işlem gerçekleştirmeden önce güvenilir bir şekilde çağrı yapabilirsiniz.

## <a name="unsetf"></a><a name="unsetf"></a> `unsetf`

Belirtilen bayrakları kapatır.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Parametreler

*`_Mask`*\
Kapatmak istediğiniz bayraklar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin bir şekilde çağırır [`flags(~_Mask & flags)`](#flags) (seçili bitleri temizle).

### <a name="example"></a>Örnek

[`ios_base::setf`](#setf)Bir örneği için bkz `unsetf` ..

## <a name="width"></a><a name="width"></a> `width`

Çıkış akışının uzunluğunu ayarlar.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Parametreler

*`_Wide`*\
Çıkış akışının istenen boyutu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli genişlik ayarı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan alan genişliğini döndürür. İkinci üye işlevi *`_Wide`* alan genişliğine göre saklanır ve önceki depolanmış değerini döndürür.

### <a name="example"></a>Örnek

```cpp
// ios_base_width.cpp
// compile with: /EHsc
#include <iostream>

int main( ) {
    using namespace std;

    cout.width( 20 );
    cout << cout.width( ) << endl;
    cout << cout.width( ) << endl;
}
```

```Output
20
0
```

## <a name="xalloc"></a><a name="xalloc"></a> `xalloc`

Bir değişkenin akışın bir parçası olduğunu belirtir.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Dönüş Değeri

Statik üye işlevi, her çağrıda artan bir depolanmış statik değer döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerini veya çağırmak için dönüş değerini benzersiz bir dizin bağımsız değişkeni olarak kullanabilirsiniz [`iword`](#iword) [`pword`](#pword) .

### <a name="example"></a>Örnek

```cpp
// ios_base_xalloc.cpp
// compile with: /EHsc
// Lets you store user-defined information.
// iword, jword, xalloc
#include <iostream>

int main( )
{
    using namespace std;

    static const int i = ios_base::xalloc();
    static const int j = ios_base::xalloc();
    cout.iword( i ) = 11;
    cin.iword( i ) = 13;
    cin.pword( j ) = "testing";
    cout << cout.iword( i ) << endl;
    cout << cin.iword( i ) << endl;
    cout << ( char * )cin.pword( j ) << endl;
}
```

```Output
11
13
testing
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
