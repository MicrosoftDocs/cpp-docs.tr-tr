---
title: ios_base sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 818d6fad62ec4d506215a82f2faa1e3aa58d1654
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="iosbase-class"></a>ios_base Sınıfı

Şablon parametreleri dayanmayan ortak giriş ve çıkış akışları üye işlevleri ve depolama sınıfı açıklanmaktadır. (Şablon sınıfı [basic_ios](../standard-library/basic-ios-class.md) ne yaygındır ve şablonun parametrelere bağlı olduğu açıklanmaktadır.)

Bir nesne sınıfı ios_base oluşan biçimlendirme bilgileri depolar:

- Biçimlendirme türünde bir nesne bayrakları [fmtflags](#fmtflags).

- Türünde bir nesne bir özel durum maskesinde [iostate](#iostate).

- Türünde bir nesne bir alan genişliği `int`.

- Türünde bir nesne bir görüntü kesinlik `int`.

- Bir yerel ayar nesnesi türünde bir nesne içinde **yerel ayar**.

- Türündeki öğeler ile iki Genişletilebilir dizisi **uzun** ve `void` işaretçi.

Bir nesne sınıfı ios_base akış durum bilgilerini türünde bir nesne de depolar. [iostate](#iostate)ve bir geri çağırma yığını.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ios_base](#ios_base)|Yapıları `ios_base` nesneleri.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[event_callback](#event_callback)|Geçirilen bir işlev açıklar [register_call](#register_callback).|
|[fmtflags](#fmtflags)|Çıktı görünümünü belirtmek için sabitleri.|
|[iostate](#iostate)|Bir akış durumunu açıklayan sabitleri tanımlar.|
|[AçmaModu](#openmode)|Bir akış ile etkileşim açıklar.|
|[seekdir](#seekdir)|Uzaklık işlemleri için başlangıç noktası belirtir.|

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[event](#event)|Olay türlerini belirtir.|

### <a name="constants"></a>Sabitler

|||
|-|-|
|[adjustfield](#fmtflags)|Tanımlanan bir bit maskesi `internal` &#124; `left` &#124; `right`.|
|[Uygulama](#openmode)|Her ekleme önce akışın sonuna isteyen belirtir.|
|[Tarih](#openmode)|Denetleme nesnesi ilk oluşturulduğunda bir akışın sonuna aramayı belirtir.|
|[badbit](#iostate)|Akışı arabelleğe bütünlüğünü kaybı kaydeder.|
|[basefield](#fmtflags)|Tanımlanan bir bit maskesi `dec` &#124; `hex` &#124; `oct`.|
|[beg](#seekdir)|Bir dizi başına göreli aramayı belirtir.|
|[İkili](#openmode)|Bir dosyayı bir metin akışı olarak değil, ikili akış olarak okunmalıdır belirtir.|
|[boolalpha](#fmtflags)|Ekleme veya çıkarma nesne türü belirtir `bool` adları olarak (gibi `true` ve `false`) yerine sayısal değer olarak.|
|[Geçerli](#seekdir)|Bir dizi içindeki geçerli konumu göre aramayı belirtir.|
|[Ara](#fmtflags)|Ekleme veya çıkarma tamsayı değerleri ondalık biçiminde belirtir.|
|[Bitiş](#seekdir)|Bir dizinin sonuna göre aramayı belirtir.|
|[eofbit](#iostate)|Kayıtları son bir akıştan ayıklanıyor sırasında dosya.|
|[failbit](#iostate)|Geçerli bir alan bir akıştan ayıklamak için bir hata kaydeder.|
|[Sabit](#fmtflags)|Kayan nokta değerlerinin ekleme sabit noktalı biçimiyle (üstel alan yok) belirtir.|
|[floatfield](#fmtflags)|Tanımlanan bir bit maskesi `fixed`&#124; `scientific`|
|[goodbit](#iostate)|Tüm durum bitleri temizleyin.|
|[Onaltılık](#fmtflags)|Ekleme veya çıkarma tamsayı değerleri onaltılık biçimde belirtir.|
|[in](#openmode)|Akıştan ayıklama belirtir.|
|[internal](#fmtflags)|Klavye takımı ekleyerek bir alan genişliği için oluşturulan bir sayısal alana iç bir noktada karakterler doldurur.|
|[Sol](#fmtflags)|Sola yaslamayı belirtir.|
|[Eki](#fmtflags)|Ekleme veya çıkarma tamsayı değerleri sekizli biçiminde belirtir.|
|[out](#openmode)|Akış ekleme belirtir.|
|[Sağ](#fmtflags)|Sağa yaslamayı belirtir.|
|[Bilimsel](#fmtflags)|Kayan nokta değerlerinin ekleme bilimsel biçimiyle (üstel alanı) belirtir.|
|[showbase](#fmtflags)|Oluşturulan tamsayı alan tabanı ortaya çıkarır bir önek ekleme belirtir.|
|[showpoint](#fmtflags)|Ondalık noktasının koşulsuz ekleme oluşturulan bir kayan nokta alanını belirtir.|
|[showpos](#fmtflags)|Artı işareti ekleme negatif olmayan bir oluşturulmuş sayısal alana belirtir.|
|[skipws](#fmtflags)|Belirli ayıklamaları önce başında boşluk atlanıyor belirtir.|
|[trunc](#openmode)|Denetleme nesnesi oluşturulduğunda silme Varolan bir dosyanın içeriğini belirtir.|
|[unitbuf](#fmtflags)|Çıkış sonra her ekleme kopyalanması için neden olur.|
|[büyük harf](#fmtflags)|Küçük harfler, büyük harf eşdeğerleri ekleme belirli eklemeleri belirtir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Hata](#failure)|Üye işlevi tarafından oluşturulan tüm özel durumlar için temel sınıf üye sınıfı gören [temizleyin](../standard-library/basic-ios-class.md#clear) şablonu sınıfında [basic_ios](../standard-library/basic-ios-class.md).|
|[Bayrakları](#flags)|Geçerli bayrağı ayarları döndürür veya ayarlar.|
|[getloc](#getloc)|Depolanan yerel ayar nesnesi döndürür.|
|[imbue](#imbue)|Yerel olarak değiştirir.|
|[Init](#init)|Oluşturulan standart iostream nesneleri oluşturur.|
|[iword](#iword)|Olarak depolanması için bir değer atayan bir `iword`.|
|[Duyarlılık](#precision)|Bir kayan noktalı sayı görüntülenecek basamak sayısını belirtir.|
|[pword](#pword)|Olarak depolanması için bir değer atayan bir `pword`.|
|[register_callback](#register_callback)|Bir geri çağırma işlevini belirtir.|
|[setf](#setf)|Belirtilen bayrakları ayarlar.|
|[sync_with_stdio](#sync_with_stdio)|İostream ve C çalışma zamanı kitaplığı operations kaynak kodunda göründükleri sırada gerçekleşmesini sağlar.|
|[unsetf](#unsetf)|Belirtilen bayrakları kapalı olması neden olur.|
|[Genişlik](#width)|Çıkış akışı uzunluğunu belirler.|
|[xalloc](#xalloc)|Bir değişken akış parçası tutulamaz belirtir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Atama işleci için `ios_base` nesneleri.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ios >

**Namespace:** std

## <a name="event"></a>  ios_base::Event

Olay türlerini belirtir.

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>Açıklamalar

Kayıtlı bir işleve bağımsız değişken olarak kullanılan geri çağırma olay depolayan bir nesneyi tanımlayan bir enum türü türüdür [register_callback](#register_callback). Farklı olay değerler şunlardır:

- **copyfmt_event**çağrısı sonunu yakın oluşan bir geri çağırma tanımlamak için [copyfmt](../standard-library/basic-ios-class.md#copyfmt), hemen önce [özel durum maskesi](../standard-library/ios-base-class.md) kopyalanır.

- **erase_event**, çağrı başına oluşan bir geri çağırma tanımlamak için [copyfmt](../standard-library/basic-ios-class.md#copyfmt), veya yıkıcı için yapılan bir çağrı başına  **\*bu**.

- **imbue_event**çağrısı sonunu oluşursa bir geri çağırma tanımlamak için [imbue](#imbue)önce yalnızca işlevi döndürür.

### <a name="example"></a>Örnek

Bkz: [register_callback](#register_callback) bir örnek.

## <a name="event_callback"></a>  ios_base::event_callback

Geçirilen bir işlev açıklar [register_call](#register_callback).

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Parametreler

*Sp_cycle_errorlog* [olay](#event).

`_Base` Olay çağrıldı akış.

*_Lisans* kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

İle kayıtlı bir işlev işaretçisi türü tanımlayan [register_callback](#register_callback). İşlevi bu tür bir özel durum değil.

### <a name="example"></a>Örnek

Bkz: [register_call](#register_callback) kullanan bir örnek `event_callback`.

## <a name="failure"></a>  ios_base::failure

Sınıf `failure` özel durumlar olarak işlevler tarafından oluşturulan tüm nesne türleri için temel sınıf tanımlar `iostreams` kitaplığa rapor hata akışı arabellek işlemleri sırasında algılandı.

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

Tarafından döndürülen değer `what()` bir kopyası `_Message`, büyük olasılıkla genişletilmiş dayalı bir test ile `_Code`. Varsa `_Code` belirtilmezse, varsayılan değer `make_error_code(io_errc::stream)`.

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

## <a name="flags"></a>  ios_base::Flags

Geçerli bayrağı ayarları döndürür veya ayarlar.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Parametreler

`fmtfl` Yeni `fmtflags` ayarı.

### <a name="return-value"></a>Dönüş Değeri

Önceki veya geçerli `fmtflags` ayarı.

### <a name="remarks"></a>Açıklamalar

Bkz: [ios_base::fmtflags](#fmtflags) bayrakları listesi.

İlk üye işlevi saklı biçimi bayrakları döndürür. İkinci üye fonksiyonu depoları `fmtfl` biçimi bayrakları döndürür, önceki değeri depolanır.

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

## <a name="fmtflags"></a>  ios_base::fmtflags

Çıktı görünümünü belirtmek için sabitleri.

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

Manipülatörleri destekleyen [ios](../standard-library/ios.md).

Biçim bayrakları depolayan bir nesneyi tanımlayan bir bit maskesi türü türüdür. (Öğeleri) ayrı bayrak değerleri şunlardır:

- `dec`, veya ondalık biçiminde tamsayı değerlerini ayıklayın.

- `hex`, eklemek veya tamsayı değerleri onaltılık biçimde ayıklamak için.

- `oct`, veya sekizli biçiminde tamsayı değerlerini ayıklayın.

- `showbase`, oluşturulmuş bir tamsayı alan tabanı ortaya çıkarır bir önek eklemek için.

- `internal`, bir alan genişliği oluşturulan bir sayısal alana iç bir noktada dolgu karakterleri ekleyerek gerektiğinde doldurulacak. (Alan genişliği ayarlama hakkında daha fazla bilgi için bkz: [setw](../standard-library/iomanip-functions.md#setw)).

- `left`, bir alan genişliği için oluşturulan alana (sola yaslamayı) sonunda dolgu karakterleri ekleyerek gerektiğinde doldurulacak.

- `right`, bir alan genişliği oluşturulan alanın (sağa yaslamayı) başında dolgu karakterleri ekleyerek gerektiğinde doldurulacak.

- `boolalpha`, eklemek veya türündeki nesneleri ayıklamak için `bool` adları olarak (gibi `true` ve `false`) yerine sayısal değer olarak.

- `fixed`, kayan nokta değerlerine sabit noktalı biçimiyle (üstel alan yok) eklemek için.

- `scientific`, kayan nokta değerlerine bilimsel biçimiyle (üstel alanı) eklemek için.

- `showpoint`, ondalık ayırıcıdan koşulsuz olarak oluşturulan bir kayan nokta alanına eklemek için.

- `showpos`, negatif olmayan bir oluşturulmuş sayısal alana bir artı işareti eklemek için.

- `skipws`, başında boşluk belirli ayıklamaları önce atlanacak.

- `unitbuf`, sonra her ekleme çıkış temizlemek için.

- `uppercase`, küçük harfler, büyük harf eşdeğerleri belirli eklemeleri eklemek için.

Ayrıca, çeşitli yararlı değerler şunlardır:

- `adjustfield`, olarak tanımlanan bir bit maskesi `internal` &#124; `left`&#124; `right`

- `basefield`, olarak tanımlanan `dec` &#124; `hex`&#124; `oct`

- `floatfield`, olarak tanımlanan `fixed`&#124; `scientific`

Bu değişiklik işlevleri örnekleri bayrakları biçimlendirmek için bkz: [ \<iomanip >](../standard-library/iomanip.md).

## <a name="getloc"></a>  ios_base::getloc

Depolanan yerel ayar nesnesi döndürür.

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

## <a name="imbue"></a>  ios_base::imbue

Yerel olarak değiştirir.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

`_Loc` Yeni yerel ayarı.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi depoları `_Loc` yerel ayar nesnesindeki ve daha sonra geri çağırma olay raporlar ve `imbue_event`. Önceki depolanan değeri döndürür.

### <a name="example"></a>Örnek

Bkz: [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue) bir örnek için.

## <a name="init"></a>  ios_base::Init

Oluşturulan standart iostream nesneleri oluşturur.

```cpp
class Init { };
```

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş sınıf standart iostreams nesneleri düzgün, rasgele bir statik nesne için bir oluşturucu yürütülmesi daha önce oluşturulan emin olan yapım sağlar nesneyi açıklar.

## <a name="ios_base"></a>  ios_base::ios_base

İos_base nesneleri oluşturur.

```cpp
ios_base();
```

### <a name="remarks"></a>Açıklamalar

(Korumalı) Oluşturucu hiçbir şey yapmaz. Sonraki çağrı **basic_ios::**[init](../standard-library/basic-ios-class.md#init) güvenle yok önce nesne başlatması gerekir. Bu nedenle, yalnızca güvenli sınıfı ios_base Şablon sınıfı için temel sınıf olarak amaçlıdır [basic_ios](../standard-library/basic-ios-class.md).

## <a name="iostate"></a>  ios_base::iostate

Bir akış durumunu açıklayan sabitleri türü.

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

Akış durum bilgilerini depolayan bir nesneyi tanımlayan bir bit maskesi türü türüdür. (Öğeleri) ayrı bayrak değerleri şunlardır:

- `badbit`, Akış Arabellek bütünlüğünü kaybı kaydetmek için.

- `eofbit`, kayıt son bir akıştan ayıklanıyor sırasında dosya için.

- `failbit`, geçerli bir alan bir akıştan ayıklamak için bir hata kaydetmek için.

Ayrıca, yararlı bir değer olan `goodbit`, yukarıda açıklanan BITS hiçbiri nerede ayarlanır ( `goodbit` sıfır olması garanti).

## <a name="iword"></a>  ios_base::iword

Olarak depolanması için bir değer atayan bir `iword`.

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Parametreler

`idx` Dizini olarak depolamak için bir `iword`.

### <a name="remarks"></a>Açıklamalar

Üye işlevini öğesine bir başvuru döndürür `idx` türündeki öğeler ile Genişletilebilir dizinin **uzun**. Tüm öğeleri etkili bir şekilde varsa ve başlangıçta sıfır değerini depolar. Sonraki çağrısından sonra döndürülen başvuru geçersiz `iword` nesne için bir çağrı tarafından değiştirilmiş sonra nesnesi için **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt), veya nesne yok.

Varsa `idx` negatif veya öğesi için benzersiz depolama kullanılamıyorsa, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** ve benzersiz olmayabilir bir başvuru döndürür.

Türündeki tüm nesneler üzerinde kullanım için benzersiz bir dizin almak için `ios_base`, çağrı [xalloc](#xalloc).

### <a name="example"></a>Örnek

Bkz: [xalloc](#xalloc) nasıl kullanılacağına ilişkin bir örnek için `iword`.

## <a name="openmode"></a>  ios_base::Openmode

Bir akış ile etkileşim açıklar.

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

Tür bir `bitmask type` birkaç iostreams nesneleri için açılış modu depolayabilir nesneyi açıklar. (Öğeleri) ayrı bayrak değerleri şunlardır:

- **Uygulama**, her ekleme önce akışın sonuna aranacağını.

- **Tarih**, kendi denetleme nesnesi ilk oluşturulduğunda bir akışın sonuna arama.

- **ikili**, bir dosyayı bir metin akışı olarak değil, ikili akış olarak okunamıyor.

- **içinde**, ayıklama akıştan izin vermek için.

- **out**, bir akışa ekleme izin vermek için.

- **trunc**, kendi kontrol eden bir nesne oluşturulduğunda, varolan bir dosyanın içeriğini silmek için.

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

## <a name="op_eq"></a>  ios_base::operator =

İos_base nesneleri atama işleci.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Parametreler

`right` Türünde bir nesne `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Atanmasına nesnesi.

### <a name="remarks"></a>Açıklamalar

İşleci, Genişletilebilir bir dizi yeni bir kopyasını oluşturma saklı biçimlendirme bilgileri kopyalar. Daha sonra döndürür  **\*bu**. Geri Çağırma yığını kopyalanmaz unutmayın.

Bu işleç yalnızca türetilmiş sınıfları tarafından kullanılan `ios_base`.

## <a name="precision"></a>  ios_base::Precision

Bir kayan noktalı sayı görüntülenecek basamak sayısını belirtir.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Parametreler

`_Prec` Görüntülenecek basamak sayısı veya sabit gösteriminde ondalık basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi saklı döndürür [görüntü duyarlılığı](../standard-library/ios-base-class.md). İkinci üye fonksiyonu depoları `_Prec` görüntü duyarlık döndürür, önceki değeri depolanır.

### <a name="remarks"></a>Açıklamalar

Kayan nokta sayıları ile sabit gösteriminde görüntülenir [sabit](../standard-library/ios-functions.md#fixed).

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

## <a name="pword"></a>  ios_base::pword

Olarak depolanması için bir değer atayan bir `pword`.

```cpp
void *& pword(int _Idx);
```

### <a name="parameters"></a>Parametreler

`_Idx` Dizini olarak depolamak için bir `pword`.

### <a name="remarks"></a>Açıklamalar

Üye işlevini öğesi _ bir başvuru döndürür *IDX* türündeki öğeler ile Genişletilebilir dizinin `void` işaretçi. Tüm öğeleri etkili bir şekilde yok ve null işaretçinin başlangıçta saklayın. Sonraki çağrısından sonra döndürülen başvuru geçersiz `pword` nesne için bir çağrı tarafından değiştirilmiş sonra nesnesi için **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt), veya nesne yok.

Varsa _ *IDX* negatif veya öğesi için benzersiz depolama kullanılamıyorsa, işlevi çağıran [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** ve benzersiz olmayabilir bir başvuru döndürür.

Türündeki tüm nesneler üzerinde kullanım için benzersiz bir dizin almak için `ios_base`, çağrı [xalloc](#xalloc).

### <a name="example"></a>Örnek

Bkz: [xalloc](#xalloc) kullanma örneği için `pword`.

## <a name="register_callback"></a>  ios_base::register_callback

Bir geri çağırma işlevini belirtir.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Parametreler

`pfn` Geri çağırma işlevi işaretçisi.

`idx` Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevini çifti iter `{pfn, idx}` saklı geri çağırma yığına [geri çağırma yığını](../standard-library/ios-base-class.md). Bir geri çağırma olay **ev** bildirilir işlevleri çağrılır, kayıt, ters sırada ifadeyle `(*pfn)(ev, *this, idx)`.

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

## <a name="seekdir"></a> ios_base::seekdir

Uzaklık işlemleri için başlangıç noktası belirtir.

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

Üye işlevlerini birkaç iostream sınıfları için bağımsız değişken olarak kullanılan arama modu depolayabilir bir nesneyi tanımlayan bir numaralandırılmış türü türüdür. Ayrı bayrak değerleri şunlardır:

- **beg**, arama (geçerli okuma alter veya konumu yazma) bir dizi (array, akış veya dosya) başına göre.

- **Geçerli**, bir dizi içindeki geçerli konumu göre arama.

- **Son**, bir dizinin sonuna göre arama.

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

## <a name="setf"></a> ios_base::setf

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

`_Mask` Açmak için işaretler.

*_Unset* devre dışı bırakmak için bayrak.

### <a name="return-value"></a>Dönüş Değeri

    The previous format flags

### <a name="remarks"></a>Açıklamalar

    The first member function effectively calls [flags](#flags)(_ *Mask* &#124; \_ *Flags*) (set selected bits) and then returns the previous format flags. The second member function effectively calls **flags**(\_ *Mask* **& fmtfl, flags& ~**`_Mask`) (replace selected bits under a mask) and then returns the previous format flags.

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

## <a name="sync_with_stdio"></a> ios_base::sync_with_stdio

İostream ve C çalışma zamanı kitaplığı operations kaynak kodunda göründükleri sırada gerçekleşmesini sağlar.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Parametreler

`_Sync` Tüm akışları ile eşitlenmiş olup **stdio**.

### <a name="return-value"></a>Dönüş Değeri

    Previous setting for this function.

### <a name="remarks"></a>Açıklamalar

    The static member function stores a **stdio** sync flag, which is initially **true**. When **true**, this flag ensures that operations on the same file are properly synchronized between the [iostreams](../standard-library/iostreams-conventions.md) functions and those defined in the C++ Standard Library. Otherwise, synchronization may or may not be guaranteed, but performance may be improved. The function stores `_Sync` in the **stdio** sync flag and returns its previous stored value. You can call it reliably only before performing any operations on the standard streams.

## <a name="unsetf"></a> ios_base::unsetf

Belirtilen bayrakları kapalı olması neden olur.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Parametreler

`_Mask` Kapatmak istediğiniz bayraklar.

### <a name="remarks"></a>Açıklamalar

    The member function effectively calls [flags](#flags)(`~`*_Mask* **& flags**) (clear selected bits).

### <a name="example"></a>Örnek

    See [ios_base::setf](#setf) for a sample of using `unsetf`.

## <a name="width"></a> ios_base::width

Çıkış akışı uzunluğunu belirler.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Parametreler

`_Wide` Çıkış akışı istenen boyutu.

### <a name="return-value"></a>Dönüş Değeri

    The current width setting.

### <a name="remarks"></a>Açıklamalar

    The first member function returns the stored field width. The second member function stores `_Wide` in the field width and returns its previous stored value.

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

## <a name="xalloc"></a> ios_base::xalloc

    Specifies that a variable is part of the stream.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Dönüş Değeri

    The static member function returns a stored static value, which it increments on each call.

### <a name="remarks"></a>Açıklamalar

    You can use the return value as a unique index argument when calling the member functions [iword](#iword) or [pword](#pword).

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
