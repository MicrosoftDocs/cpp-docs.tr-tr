---
title: ios_base Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 17fb83cdbf882467f0ec330e05a6506b13051cab
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72890121"
---
# <a name="ios_base-class"></a>ios_base Sınıfı

Sınıfı, şablon parametrelerine bağlı olmayan hem giriş hem de çıkış akışları için ortak olan depolama ve üye işlevlerini açıklar. ( [Basic_ios](../standard-library/basic-ios-class.md) sınıf şablonu, ortak olduğunu ve şablon parametrelerine bağlı olanları açıklar.)

İos_base sınıfının bir nesnesi, şunları içeren biçimlendirme bilgilerini depolar:

- [`fmtflags`](#fmtflags)türünde bir nesnedeki biçim bayrakları.

- [`iostate`](#iostate)türünde bir nesnedeki özel durum maskesi.

- **İnt**türünde bir nesne içindeki alan genişliği.

- **İnt**türünde bir nesnede bir görüntüleme hassasiyeti.

- `locale`türünde bir nesnedeki yerel ayar nesnesi.

- **Long** ve **void** işaretçisi türünde öğeleri olan iki Genişletilebilir dizi.

İos_base sınıfının bir nesnesi akış durum bilgilerini [`iostate`](#iostate)türünde bir nesne ve bir geri çağırma yığını da depolar.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[ios_base](#ios_base)|`ios_base` nesneleri oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[event_callback](#event_callback)|[Register_call](#register_callback)'e geçirilen bir işlevi açıklar.|
|[`fmtflags`](#fmtflags)|Çıktının görünümünü belirtmek için sabitler.|
|[`iostate`](#iostate)|Akışın durumunu açıklayan sabitleri tanımlar.|
|[OpenMode](#openmode)|Bir Stream ile nasıl etkileşim kuracağınızı açıklar.|
|[seekdir](#seekdir)|Dengeleme işlemleri için başlangıç noktasını belirtir.|

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[event](#event)|Olay türlerini belirtir.|

### <a name="constants"></a>Sabitler

|||
|-|-|
|[adjustfield](#fmtflags)|`internal` &#124;`left`&#124;`right`olarak tanımlanan bir bit maskesi.|
|[uygulamanızda](#openmode)|Her ekleme işleminden önce akışın sonuna kadar aramayı belirtir.|
|[önemi](#openmode)|Denetim nesnesi ilk oluşturulduğunda akışın sonuna aramayı belirtir.|
|[rozbit](#iostate)|Akış arabelleğinin bütünlüğünden oluşan bir kayıp kaydeder.|
|[basefield](#fmtflags)|`dec` &#124;`hex`&#124;`oct`olarak tanımlanan bir bit maskesi.|
|[BEG](#seekdir)|Bir dizinin başlangıcına göre aramayı belirtir.|
|[ý](#openmode)|Bir dosyanın metin akışı yerine ikili akış olarak okunması gerektiğini belirtir.|
|[boolalpha](#fmtflags)|**Bool** türündeki nesnelerin, sayısal değerler yerine ad ( **true** ve **false**gibi) eklenmesini veya ayıklanmasını belirtir.|
|[geçerli](#seekdir)|Bir dizi içindeki geçerli konuma göre aramayı belirtir.|
|[Dec](#fmtflags)|Ondalık biçimdeki tamsayı değerlerinin eklenmesini veya ayıklanmasını belirtir.|
|[erer](#seekdir)|Bir sıranın sonuna göre aramayı belirtir.|
|[eofbit](#iostate)|Akıştan ayıklanan dosya sonunu kaydeder.|
|[failbit](#iostate)|Akıştan geçerli bir alan ayıklama hatası kaydeder.|
|[Düzenle](#fmtflags)|Kayan nokta değerlerinin sabit noktalı biçimde (üs alanı olmadan) eklenmesini belirtir.|
|[floatfield](#fmtflags)|`fixed` &#124; olarak tanımlanan bir bit maskesi`scientific`|
|[goodbit](#iostate)|Tüm durum bitleri net.|
|[eşlenecek](#fmtflags)|Tamsayı değerlerinin onaltılık biçimde eklenmesini veya ayıklanmasını belirtir.|
|[in](#openmode)|Akıştan ayıklama belirtir.|
|[internal](#fmtflags)|Oluşturulan bir sayısal alana yönelik bir noktada Fill karakterleri ekleyerek alan genişliğine göre doldurur.|
|[tarafta](#fmtflags)|Sola yaslama belirtir.|
|[Oct](#fmtflags)|Tamsayı değerlerinin sekizli biçimde eklenmesini veya ayıklanmasını belirtir.|
|[out](#openmode)|Bir akışa ekleme belirtir.|
|[Right](#fmtflags)|Sağ gerekçe belirtir.|
|[bilimsel](#fmtflags)|Kayan nokta değerlerinin bilimsel biçimde (üs alanı ile) eklenmesini belirtir.|
|[showbase](#fmtflags)|Oluşturulan bir tamsayı alanının temelini ortaya çıkaran bir ön ek ekleme işlemini belirtir.|
|[showpoint](#fmtflags)|Oluşturulan kayan nokta alanında ondalık noktanın koşulsuz eklenmesini belirtir.|
|[showpos](#fmtflags)|Negatif olmayan oluşturulan sayısal bir alanda artı işareti ekleme işlemini belirtir.|
|[skipws](#fmtflags)|Belirli dışlamaları öncesinde baştaki boşluk atlanmasını belirtir.|
|[TRUNC](#openmode)|Denetim nesnesi oluşturulduğunda varolan bir dosyanın içeriğini silmeyi belirtir.|
|[unitbuf](#fmtflags)|Her ekleme işleminden sonra çıktının temizlenmesine neden olur.|
|[İngiliz](#fmtflags)|Belirli eklemelerde küçük harflerin büyük harfli eşdeğerlerinin eklenmesini belirtir.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[hataları](#failure)|Üye sınıfı, sınıf şablonu [basic_ios](../standard-library/basic-ios-class.md)içinde [clear](../standard-library/basic-ios-class.md#clear) üye işlevi tarafından oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|
|[larına](#flags)|Geçerli bayrak ayarlarını ayarlar veya döndürür.|
|[getloc](#getloc)|Depolanan yerel ayar nesnesini döndürür.|
|[imbue](#imbue)|Yerel ayarı değiştirir.|
|[Init](#init)|Oluşturulduğunda standart `iostream` nesnelerini oluşturur.|
|[iword](#iword)|`iword`olarak depolanacak bir değer atar.|
|[duyarlılık](#precision)|Kayan noktalı bir sayı içinde görüntülenecek basamakların sayısını belirtir.|
|[pword](#pword)|`pword`olarak depolanacak bir değer atar.|
|[register_callback](#register_callback)|Bir geri çağırma işlevi belirtir.|
|[setf](#setf)|Belirtilen bayrakları ayarlar.|
|[sync_with_stdio](#sync_with_stdio)|`iostream` ve C çalışma zamanı kitaplığı işlemlerinin, kaynak kodda göründükleri sırada gerçekleşmesini sağlar.|
|[unsetf](#unsetf)|Belirtilen bayrakların kapalı olmasına neden olur.|
|[Genişlik](#width)|Çıkış akışının uzunluğunu ayarlar.|
|[xalloc](#xalloc)|Bir değişkenin akışın parçası olmayacağını belirtir.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_eq)|`ios_base` nesneler için atama işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ios >

**Ad alanı:** std

## <a name="event"></a>olay

Olay türlerini belirtir.

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>Açıklamalar

Tür, [register_callback](#register_callback)ile kaydedilmiş bir işleve bağımsız değişken olarak kullanılan geri çağırma olayını depolayabilen bir nesneyi açıklayan, numaralandırılmış bir türdür. Ayrı olay değerleri şunlardır:

- `copyfmt_event`, [copyfmt](../standard-library/basic-ios-class.md#copyfmt)çağrısının sonuna yakın bir şekilde bir geri çağırma işlemini belirlemek için, [özel durum maskesi](../standard-library/ios-base-class.md) kopyalanamadı.

- `erase_event`, [copyfmt](../standard-library/basic-ios-class.md#copyfmt)çağrısının başlangıcında veya **Bu\*** için yok edicinin çağrısının başlangıcında gerçekleşen bir geri çağırma işlemini tanımlamak için.

- `imbue_event`, yalnızca işlevin dönüşmesinden önce [Imbue](#imbue)çağrısının sonunda gerçekleşen geri çağırma işlemini tanımlamak için.

### <a name="example"></a>Örnek

Bir örnek için bkz. [register_callback](#register_callback) .

## <a name="event_callback"></a>event_callback

[Register_call](#register_callback)'e geçirilen bir işlevi açıklar.

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Parametreler

*_E*\
[Olay](#event).

*_Temel*\
Olayın çağrıldığı akış.

*_I*\
Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Türü, [register_callback](#register_callback)ile kaydedilenebilir bir işleve yönelik bir işaretçi tanımlar. Bu tür bir işlevin özel durum oluşturması gerekir.

### <a name="example"></a>Örnek

`event_callback`kullanan bir örnek için bkz. [register_call](#register_callback) .

## <a name="failure"></a>hataları

Sınıf `failure`, akış arabelleği işlemleri sırasında algılanan hataları raporlamak için `iostreams` kitaplığındaki işlevlere göre özel durum olarak oluşturulan tüm nesnelerin türleri için temel sınıfı tanımlar.

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

`what()` tarafından döndürülen değer, bir `_Message`kopyasıdır, muhtemelen `_Code`dayalı bir test ile genişletilebilir. `_Code` belirtilmemişse, varsayılan değer `make_error_code(io_errc::stream)`.

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

## <a name="flags"></a>larına

Geçerli bayrak ayarlarını ayarlar veya döndürür.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Parametreler

*fmtfl* \
Yeni `fmtflags` ayarı.

### <a name="return-value"></a>Dönüş Değeri

Önceki veya geçerli `fmtflags` ayarı.

### <a name="remarks"></a>Açıklamalar

Bayrakların listesi için bkz. [ios_base:: fmtflags](#fmtflags) .

İlk üye işlevi depolanan biçim bayraklarını döndürür. İkinci üye işlevi *fmtfl* 'yi biçim bayraklarıyla depolar ve önceki depolanmış değerini döndürür.

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

## <a name="fmtflags"></a>fmıtflags

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

[İOS](../standard-library/ios.md)'daki işleicileri destekler.

Tür, biçim bayraklarını depolayabilen bir nesneyi açıklayan bir bit maskesi türüdür. DISTINCT bayrak değerleri (öğeler) şunlardır:

- tamsayı değerlerini ondalık biçimde eklemek veya ayıklamak için `dec`.

- tamsayı değerlerini onaltılık biçimde eklemek veya ayıklamak için `hex`.

- tamsayı değerlerini sekizlik biçimde eklemek veya ayıklamak için `oct`.

- oluşturulan bir tamsayı alanının temelini ortaya çıkaran bir ön ek eklemek için `showbase`.

- `internal`, üretilen bir sayısal alana işaret eden bir noktaya doldurma karakterleri ekleyerek gerektiği şekilde bir alan genişliğine doldurma. (Alan genişliğini ayarlama hakkında daha fazla bilgi için bkz. [`setw`](../standard-library/iomanip-functions.md#setw)).

- `left`, oluşturulan alanın sonuna doldurma karakterleri ekleyerek gerektiği şekilde bir alan genişliğine doldurma (sol gerekçe).

- `right`, oluşturulan alanın başına doldurma karakterleri ekleyerek gerektiği şekilde bir alan genişliğine doldurma (sağ gerekçe).

- `boolalpha`, **bool** türündeki nesneleri sayısal değerler yerine ad ( **true** ve **false**gibi) eklemek veya ayıklamak için.

- `fixed`, kayan nokta değerlerini sabit noktalı biçimde (üs alanı olmadan) eklemek için.

- `scientific`, kayan nokta değerlerini bilimsel biçimde (üs alanı ile) eklemek için.

- `showpoint`, üretilen kayan nokta alanına koşulsuz olarak ondalık bir nokta eklemek için.

- `showpos`, negatif olmayan oluşturulan sayısal bir alanda artı işareti eklemek için.

- belirli dışlamaları öncesinde baştaki boşluğu atlamak için `skipws`.

- Her ekleme işleminden sonra çıktıyı temizlemek için `unitbuf`.

- `uppercase`, belirli eklemelerdeki küçük harflerin büyük harfli eşdeğerlerini eklemek için.

Ayrıca, birkaç yararlı değer şunlardır:

- `adjustfield`, `internal` &#124; `left` &#124; olarak tanımlanan bir bit maskesi `right`

- `basefield`, `dec` &#124; `hex` &#124; olarak tanımlanır `oct`

- `floatfield`, `fixed` &#124; olarak tanımlanmış `scientific`

Bu biçim bayraklarını değiştiren işlevlerin örnekleri için bkz. [\<iomanip >](../standard-library/iomanip.md).

## <a name="getloc"></a>getloc

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

## <a name="imbue"></a>imbue

Yerel ayarı değiştirir.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*\
Yeni yerel ayar ayarı.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi *_Loc* ' i yerel ayar nesnesinde depolar ve sonra geri çağırma olayını ve `imbue_event`bildirir. Önceki depolanmış değeri döndürür.

### <a name="example"></a>Örnek

Örnek için bkz. [basic_ios:: imbue](../standard-library/basic-ios-class.md#imbue) .

## <a name="init"></a>Dengeleyici

Oluşturulduğunda standart `iostream` nesnelerini oluşturur.

```cpp
class Init { };
```

### <a name="remarks"></a>Açıklamalar

İç içe yerleştirilmiş sınıf, bir oluşturucunun rastgele bir statik nesne için yürütmeden önce bile standart `iostream` nesnelerinin düzgün şekilde oluşturulmasını sağlayan bir nesneyi tanımlar.

## <a name="ios_base"></a>ios_base

İos_base nesneleri oluşturur.

```cpp
ios_base();
```

### <a name="remarks"></a>Açıklamalar

(Korumalı) Oluşturucu hiçbir şey yapmaz. `basic_ios::`[Init](../standard-library/basic-ios-class.md#init) 'in daha sonraki bir çağrısı, güvenli bir şekilde yok edilebilmesi için nesneyi başlatmalıdır. Bu nedenle, ios_base sınıfı için tek güvenli kullanım, [basic_ios](../standard-library/basic-ios-class.md)sınıf şablonu için bir temel sınıf olarak bulunur.

## <a name="iostate"></a>iostate

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

- akış arabelleğinin bütünlüğü kaybını kaydetmek için `badbit`.

- `eofbit`, bir akıştan ayıklanan dosya sonunu kaydetmek için.

- `failbit`, akıştan geçerli bir alan ayıklama hatası kaydetmek için.

Buna ek olarak, daha önce bahsedilen bitlerin hiçbirinin ayarlandığı `goodbit` yararlı bir değer (`goodbit` sıfır olduğu garanti edilir).

## <a name="iword"></a>iword

`iword`olarak depolanacak bir değer atar.

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Parametreler

*idx* \
`iword`olarak depolanacak değerin dizini.

### <a name="remarks"></a>Açıklamalar

Member işlevi, Genişletilebilir dizinin öğe *IDX* öğesine, **Long**türünde öğeler içeren bir başvuru döndürür. Tüm öğeler etkili bir şekilde bulunur ve başlangıçta sıfır değerini depolar. Döndürülen başvuru, nesne için `iword` bir sonraki çağrıdan sonra geçersiz, nesne bir `basic_ios::`[copyfmt](../standard-library/basic-ios-class.md#copyfmt)çağrısı tarafından değiştirildikten sonra veya nesne yok edildiğinde.

*İdx* negatifse veya öğe için benzersiz depolama alanı kullanılamıyorsa, işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(badbit)` çağırır ve benzersiz olmayan bir başvuru döndürür.

`ios_base`türünde tüm nesnelerde kullanılmak üzere benzersiz bir dizin almak için, [`xalloc`](#xalloc)çağırın.

### <a name="example"></a>Örnek

`iword`nasıl kullanılacağına ilişkin bir örnek için bkz. [`xalloc`](#xalloc) .

## <a name="openmode"></a>OpenMode

Bir Stream ile nasıl etkileşim kuracağınızı açıklar.

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

Tür, çeşitli `iostream` nesneleri için açma modunu depolayabilen bir nesneyi tanımlayan bir `bitmask type`. DISTINCT bayrak değerleri (öğeler) şunlardır:

- Her ekleme işleminden önce akışın sonuna kadar aramak için `app`.

- Denetim nesnesi ilk oluşturulduğunda akışın sonuna kadar aramak için `ate`.

- bir dosyayı metin akışı yerine ikili akış olarak okumak için `binary`.

- akıştan ayıklanmasına izin vermek için `in`.

- `out` bir akışa eklenmesine izin vermek için.

- Denetim nesnesi oluşturulduğunda mevcut bir dosyanın içeriğini silmek için `trunc`.

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

## <a name="op_eq"></a>işleç =

İos_base nesnelerine yönelik atama işleci.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
`ios_base`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Atanmakta olan nesne.

### <a name="remarks"></a>Açıklamalar

İşleci, Genişletilebilir dizilerin yeni bir kopyasını oluşturan, depolanan biçimlendirme bilgilerini kopyalar. Ardından **\*this**döndürür. Geri çağırma yığınının kopyalanmadığını unutmayın.

Bu işleç yalnızca `ios_base`türetilen sınıflar tarafından kullanılır.

## <a name="precision"></a>duyarlılık

Kayan noktalı bir sayı içinde görüntülenecek basamakların sayısını belirtir.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Parametreler

*_Prec*\
Sabit gösterimdeki ondalık ayırıcıdan sonraki basamak sayısı veya görüntülenecek önemli basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi depolanan [görüntüleme duyarlığını](../standard-library/ios-base-class.md)döndürür. İkinci üye işlevi, *_Prec* 'i görüntüleme duyarlığına depolar ve önceki depolanmış değerini döndürür.

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

## <a name="pword"></a>pword

`pword`olarak depolanacak bir değer atar.

```cpp
void *& pword(int index);
```

### <a name="parameters"></a>Parametreler

*dizin*\
`pword`olarak depolanacak değerin dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Genişletilebilir dizinin öğe *dizinine* , **void** işaretçisinin türü öğeleriyle bir başvuru döndürür. Tüm öğeler etkili bir şekilde bulunur ve başlangıçta null işaretçiyi depolar. Döndürülen başvuru, nesne için `pword` bir sonraki çağrıdan sonra geçersiz, nesne bir `basic_ios::`[copyfmt](../standard-library/basic-ios-class.md#copyfmt)çağrısı tarafından değiştirildikten sonra veya nesne yok edildiğinde.

*Dizin* negatifse veya öğe için benzersiz depolama alanı kullanılamıyorsa, işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(badbit)` çağırır ve benzersiz olmayan bir başvuru döndürür.

`ios_base`türünde tüm nesnelerde kullanılmak üzere benzersiz bir dizin almak için, [`xalloc`](#xalloc)çağırın.

### <a name="example"></a>Örnek

`pword`kullanma örneği için bkz. [`xalloc`](#xalloc) .

## <a name="register_callback"></a>register_callback

Bir geri çağırma işlevi belirtir.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Parametreler

*PFN* \
Geri çağırma işlevine yönelik işaretçi.

*idx* \
Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Çift `{pfn, idx}` depolanan geri çağırma yığını [geri çağırma yığınına](../standard-library/ios-base-class.md)iter. Bir geri **çağırma olayı oluşturulduğunda** , işlevler, `(*pfn)(ev, *this, idx)` ifade tarafından tersine kayıt sırasında çağrılır.

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

## <a name="seekdir"></a>seekdir

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

Türü, birkaç `iostream` sınıfının üye işlevlerine bağımsız değişken olarak kullanılan arama modunu depolayabilen bir nesneyi açıklayan, numaralandırılmış bir türdür. DISTINCT bayrak değerleri şunlardır:

- `beg`, bir dizinin başlangıcına (dizi, akış veya dosya) göre arama yapmak için (geçerli okuma veya yazma konumunu değiştirme).

- `cur`, bir dizi içindeki geçerli konuma göre arama yapmak için.

- `end`, sıranın sonuna göre arama yapmak için.

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

## <a name="setf"></a>setf

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

*_Maske*\
Açmak için bayraklar.

*_Unset*\
Kapatılacak bayraklar.

### <a name="return-value"></a>Dönüş Değeri

Önceki biçim bayrakları

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, [bayrakları](#flags)`(_Mask | _Flags)` (seçili bitleri ayarla) etkin bir şekilde çağırır ve ardından önceki biçim bayraklarını döndürür. İkinci üye işlevi `flags(_Mask & fmtfl, flags & ~_Mask)` etkin bir şekilde çağırır (seçili bitleri bir maske altında değiştirir) ve ardından önceki biçim bayraklarını döndürür.

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

## <a name="sync_with_stdio"></a>sync_with_stdio

`iostream` ve C çalışma zamanı kitaplığı işlemlerinin, kaynak kodda göründükleri sırada gerçekleşmesini sağlar.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Parametreler

*_Eşitleme*\
Tüm akışların `stdio` eşitlenmiş olup olmadığı.

### <a name="return-value"></a>Dönüş Değeri

Bu işlev için önceki ayar.

### <a name="remarks"></a>Açıklamalar

Statik üye işlevi, başlangıçta **doğru**olan bir `stdio` Sync bayrağını depolar. **True**olduğunda, bu bayrak aynı dosyadaki işlemlerin, [`iostreams`](../standard-library/iostreams-conventions.md) işlevleri ve C++ standart kitaplıkta tanımlananlar arasında düzgün şekilde eşitlenmesini sağlar. Aksi takdirde, eşitleme garanti edilebilir veya olmayabilir, ancak performans artırılabilir. İşlevi, *_sync* `stdio` eşitleme bayrağıyla depolar ve önceki depolanmış değerini döndürür. Standart akışlarda herhangi bir işlem gerçekleştirmeden önce güvenilir bir şekilde çağrı yapabilirsiniz.

## <a name="unsetf"></a>unsetf

Belirtilen bayrakların kapalı olmasına neden olur.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Parametreler

*_Maske*\
İstediğiniz bayraklar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [bayrakları](#flags)etkin bir şekilde çağırır (`~` *_Mask* **& bayrakları**) (seçili bitleri temizle).

### <a name="example"></a>Örnek

`unsetf`kullanımı örneği için bkz. [ios_base:: setf](#setf) .

## <a name="width"></a>Genişlik

Çıkış akışının uzunluğunu ayarlar.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Parametreler

*_Geniş*\
Çıkış akışının istenen boyutu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli genişlik ayarı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan alan genişliğini döndürür. İkinci üye işlevi alan genişliğine göre *_geniş* depolar ve önceki depolanmış değerini döndürür.

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

## <a name="xalloc"></a>xalloc

Bir değişkenin akışın bir parçası olduğunu belirtir.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Dönüş Değeri

Statik üye işlevi, her çağrıda artan bir depolanmış statik değer döndürür.

### <a name="remarks"></a>Açıklamalar

[`iword`](#iword) veya [`pword`](#pword)üye işlevleri çağrılırken, dönüş değerini benzersiz bir dizin bağımsız değişkeni olarak kullanabilirsiniz.

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

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
