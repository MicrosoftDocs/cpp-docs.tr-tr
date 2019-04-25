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
ms.openlocfilehash: 8911c3763e6a0c861c162611e1b2617ec26f0cf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158597"
---
# <a name="iosbase-class"></a>ios_base Sınıfı

Depolama sınıfı açıklar ve üye işlevleri, şablon parametrelerine bağlı olmayan giriş ve çıkış yaygın olarak kullanılan akış. (Şablon sınıfı [basic_ios](../standard-library/basic-ios-class.md) ne için ortaktır ve şablon parametrelerine bağlı olduğu açıklanmaktadır.)

İos_base sınıfı bir nesnenin oluşan biçimlendirme bilgileri depolar:

- Biçim bayrakları türünde bir nesne [fmtflags](#fmtflags).

- Bir özel durum maskesi türünde bir nesne [iostate](#iostate).

- Türünde bir nesne bir alan genişliği **int**.

- Türünde bir nesne içinde görünen kesinliği **int**.

- Bir yerel ayar nesnesi türünde bir nesne içinde `locale`.

- Türünde öğelere sahip iki Genişletilebilir diziler **uzun** ve **void** işaretçi.

İos_base sınıfı bir nesne türünde bir nesne akışa durum bilgilerini de depolar. [iostate](#iostate)ve bir geri çağırma yığını.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ios_base](#ios_base)|Yapıları `ios_base` nesneleri.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[event_callback](#event_callback)|Geçirilen bir işlev açıklar [register_call](#register_callback).|
|[fmtflags](#fmtflags)|Çıkış görünümünü belirtmek için sabitler.|
|[iostate](#iostate)|Bir akış durumunu açıklayan sabit değerleri tanımlar.|
|[AçmaModu](#openmode)|Bir akış ile etkileşim kurmak açıklar.|
|[seekdir](#seekdir)|İşlemleri için başlangıç noktası belirtir.|

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[event](#event)|Olay türlerini belirtir.|

### <a name="constants"></a>Sabitler

|||
|-|-|
|[adjustfield](#fmtflags)|Tanımlanan bir bit maskesi `internal` &#124; `left` &#124; `right`.|
|[Uygulama](#openmode)|Her ekleme önce bir akışın sonuna isteyen belirtir.|
|[Oluştur](#openmode)|Denetleme, nesne ilk oluşturulduğunda bir akış sonuna arayan belirtir.|
|[badbit](#iostate)|Akış arabelleğinin bütünlüğünü kaybı kaydeder.|
|[basefield](#fmtflags)|Tanımlanan bir bit maskesi `dec` &#124; `hex` &#124; `oct`.|
|[beg](#seekdir)|Bir dizi başlangıcına göre arama belirtir.|
|[İkili](#openmode)|Metin akışına olarak değil, ikili akış olarak bir dosya okunmalıdır belirtir.|
|[boolalpha](#fmtflags)|Ekleme veya çıkarma nesne türü belirtir **bool** adları olarak (gibi **true** ve **false**) olarak sayısal değerlerin değil.|
|[Yinele](#seekdir)|Bir dizi içinde geçerli konumuna göre arama belirtir.|
|[Ara](#fmtflags)|Ekleme veya çıkarma tamsayı değerleri ondalık biçiminde belirtir.|
|[Son](#seekdir)|Bir dizinin sonuna göreli arayan belirtir.|
|[eofbit](#iostate)|Kayıt-bir akıştan ayıklanıyor sırasında dosya sonu.|
|[failbit](#iostate)|Geçerli bir alan bir akışından ayıklanacak bir hata kaydeder.|
|[düzeltildi](#fmtflags)|Kayan nokta değerlerinin ekleme (ile üs alan yok) sabit noktalı biçim belirtir.|
|[floatfield](#fmtflags)|A bitmask defined as `fixed` &#124; `scientific`|
|[goodbit](#iostate)|Tüm durum bitleri temizleyin.|
|[onaltılık](#fmtflags)|Onaltılık biçimde ekleme veya çıkarma tamsayı değerleri belirtir.|
|[in](#openmode)|Bir akıştan ayıklama belirtir.|
|[internal](#fmtflags)|Bölmeleri ekleyerek bir alan genişliği için oluşturulan bir sayısal alan iç bir noktada karakter girin.|
|[Sol](#fmtflags)|Sol gerekçe belirtir.|
|[Eki](#fmtflags)|Ekleme veya çıkarma tamsayı değerleri sekizlik biçiminde belirtir.|
|[out](#openmode)|Bir akışa ekleme belirtir.|
|[sağ](#fmtflags)|Doğru gerekçe belirtir.|
|[Bilimsel](#fmtflags)|Kayan nokta değerlerinin ekleme biçiminde bilimsel (üstel bir alan) belirtir.|
|[showbase](#fmtflags)|Gösteren temel bir oluşturulmuş bir tamsayı alan bir ön ek ekleme belirtir.|
|[showpoint](#fmtflags)|Bir ondalık noktasının koşulsuz ekleme oluşturulan bir kayan nokta alanını belirtir.|
|[showpos](#fmtflags)|Artı işareti ekleme, negatif olmayan bir oluşturulmuş sayısal alan belirtir.|
|[skipws](#fmtflags)|Baştaki boşluk önce belirli ayıklamalar atlanıyor belirtir.|
|[trunc](#openmode)|Kendi kontrol eden bir nesne oluşturulduğunda silme Varolan bir dosyanın içeriğini belirtir.|
|[unitbuf](#fmtflags)|Çıkış sonra her bir ekleme kopyalanması için neden olur.|
|[büyük harf](#fmtflags)|Küçük harfler, büyük harf eşdeğeri ekleme bazı eklemeler belirtir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[hata](#failure)|Üye sınıfı üye işlevi tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet veren [Temizle](../standard-library/basic-ios-class.md#clear) şablon sınıfında [basic_ios](../standard-library/basic-ios-class.md).|
|[bayrakları](#flags)|Geçerli bayrak ayarlarını döndürür veya ayarlar.|
|[getloc](#getloc)|Depolanan yerel ayar nesnesi döndürür.|
|[imbue](#imbue)|Yerel ayar değiştirir.|
|[Init](#init)|Oluşturulan standart iostream nesneleri oluşturur.|
|[iword](#iword)|Olarak depolanacak değer atayan bir `iword`.|
|[Duyarlık](#precision)|Bir kayan noktalı sayı görüntülenecek basamak sayısını belirtir.|
|[pword](#pword)|Olarak depolanacak değer atayan bir `pword`.|
|[register_callback](#register_callback)|Bir geri çağırma işlevi belirtir.|
|[setf](#setf)|Belirtilen bayraklar ayarlar.|
|[sync_with_stdio](#sync_with_stdio)|İostream ve C çalışma zamanı kitaplığı işlemleri kaynak kodunda göründükleri sırayla gerçekleşmemesini sağlar.|
|[unsetf](#unsetf)|Belirtilen bayraklar kapalı olması neden olur.|
|[Genişlik](#width)|Çıkış akışına uzunluğunu ayarlar.|
|[xalloc](#xalloc)|Bir değişken akışın bir parçası olacaktır belirtir.|

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

Kayıtlı bir işleve bağımsız değişken olarak kullanılan geri çağırma olay depolayan bir nesne tanımlayan bir listeden seçimli türü türüdür [register_callback](#register_callback). Farklı olay değerler şunlardır:

- `copyfmt_event`, bir çağrı sonuna yakın oluşan bir geri çağırma tanımlamak için [copyfmt](../standard-library/basic-ios-class.md#copyfmt), hemen önce [özel durum maskesini](../standard-library/ios-base-class.md) kopyalanır.

- `erase_event`, çağrı başına oluşan bir geri çağırma tanımlamak için [copyfmt](../standard-library/basic-ios-class.md#copyfmt), ya da yok edici için yapılan bir çağrının başında  **\*bu**.

- `imbue_event`, bir çağrı, sonunda oluşan bir geri çağırma tanımlamak için [imbue](#imbue)önce yalnızca işlev döndürür.

### <a name="example"></a>Örnek

Bkz: [register_callback](#register_callback) örneği.

## <a name="event_callback"></a>  ios_base::event_callback

Geçirilen bir işlev açıklar [register_call](#register_callback).

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Parametreler

*_E*<br/>
[Olay](#event).

*_Base*<br/>
Akış olayı çağrıldı.

*_I*<br/>
Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Türü ile kayıtlı bir işleve işaretçi tanımlayan [register_callback](#register_callback). Bu tür bir işlev bir özel durum oluşturmamalıdır.

### <a name="example"></a>Örnek

Bkz: [register_call](#register_callback) kullanan bir örnek için `event_callback`.

## <a name="failure"></a>  ios_base::failure

Sınıf `failure` işlevleri tarafından özel durumlar, tüm nesne türleri için temel sınıf tanımlar `iostreams` kitaplığına Akış Arabellek işlemleri sırasında algılanan hataları bildir.

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

Tarafından döndürülen değer `what()` bir kopyasıdır `_Message`, temel bir test ile büyük olasılıkla Genişletilmiş `_Code`. Varsa `_Code` belirtilmezse, varsayılan değer `make_error_code(io_errc::stream)`.

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

Geçerli bayrak ayarlarını döndürür veya ayarlar.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Parametreler

*fmtfl*<br/>
Yeni `fmtflags` ayarı.

### <a name="return-value"></a>Dönüş Değeri

Önceki veya geçerli `fmtflags` ayarı.

### <a name="remarks"></a>Açıklamalar

Bkz: [ios_base::fmtflags](#fmtflags) bayrakların listesi için.

İlk üye işlevi, depolanan biçim bayrakları döndürür. İkinci üye işlevi depoları *fmtfl* biçim bayrakları döndürür, önceki değeri depolanır.

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

Çıkış görünümünü belirtmek için sabitler.

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

İçinde manipülatörleri destekler [ios](../standard-library/ios.md).

Biçim bayrakları depolayan bir nesneyi tanımlayan bir bit maskesi türü türüdür. (Öğeleri) ayrı bayrağı değerler şunlardır:

- `dec`, eklemek veya ondalık biçiminde tamsayı değerlerini ayıklamak için.

- `hex`, eklemek veya onaltılık biçiminde tamsayı değerlerini ayıklamak için.

- `oct`, eklemek veya tamsayı değerleri, sekizli biçimdedir ve ayıklamak için.

- `showbase`, temel bir oluşturulmuş bir tamsayı alan gösteren bir önek eklenecek.

- `internal`, bir alan genişliği için oluşturulan bir sayısal alan iç bir noktada doldurma karakterleri ekleyerek gerektiğinde doldurulacak. (Alan genişliği ayarlama hakkında daha fazla bilgi için bkz. [setw](../standard-library/iomanip-functions.md#setw)).

- `left`, bir alan genişliği için oluşturulan alana (sol gerekçe) sonunda doldurma karakterleri ekleyerek gerektiğinde doldurulacak.

- `right`, bir alan genişliği için oluşturulan alana (doğru gerekçe) başında doldurma karakterleri ekleyerek gerektiğinde doldurulacak.

- `boolalpha`, ekleme veya türünden nesnelerin ayıklama **bool** adları olarak (gibi **true** ve **false**) olarak sayısal değerlerin değil.

- `fixed`, kayan nokta değerini sabit noktalı biçim (ile üs alan yok) eklemek için.

- `scientific`, kayan nokta değerleri biçiminde bilimsel (üstel bir alan) eklemek için.

- `showpoint`, bir ondalık noktası koşulsuz olarak oluşturulan bir kayan nokta alanına eklemek için.

- `showpos`, negatif olmayan bir oluşturulmuş sayısal alana bir artı işareti eklemek için.

- `skipws`, baştaki boşluk belirli ayıklamalar önce atlanacak.

- `unitbuf`, her eklemeden sonra çıktı temizleyemedi.

- `uppercase`, bazı eklemeler küçük harfler, büyük harf eşdeğeri eklenecek.

Ayrıca, birçok yararlı değerler şunlardır:

- `adjustfield`, olarak tanımlanan bir bit maskesi `internal` &#124; `left`&#124; `right`

- `basefield`, tanımlanan `dec` &#124; `hex`&#124; `oct`

- `floatfield`, tanımlanan `fixed`&#124; `scientific`

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

Yerel ayar değiştirir.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*<br/>
Yeni yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi depoları *_Loc* yerel ayar nesnesi içinde ve daha sonra geri çağırma olay raporlar ve `imbue_event`. Önceki depolanan değeri döndürür.

### <a name="example"></a>Örnek

Bkz: [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue) örneği.

## <a name="init"></a>  ios_base::Init

Oluşturulan standart iostream nesneleri oluşturur.

```cpp
class Init { };
```

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş sınıf, standart iostreams nesnelerin düzgün, rastgele bir statik nesne için bir oluşturucu yürütülmesini önce oluşturulan emin olan yapı sağlar. bir nesneyi tanımlar.

## <a name="ios_base"></a>  ios_base::ios_base

İos_base nesneleri oluşturur.

```cpp
ios_base();
```

### <a name="remarks"></a>Açıklamalar

(Korumalı) Oluşturucu hiçbir şey yapmaz. Bir sonraki çağrı **basic_ios::**[init](../standard-library/basic-ios-class.md#init) güvenli bir şekilde edilebilir önce nesneyi başlatmak gerekir. Bu nedenle, yalnızca güvenli ios_base sınıfı için Şablon sınıfı için temel sınıf olarak kullanımda [basic_ios](../standard-library/basic-ios-class.md).

## <a name="iostate"></a>  ios_base::iostate

Bir akış durumunu açıklayan sabit türü.

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

Akışa durum bilgilerini depolayan bir nesne tanımlayan bir bit maskesi türünde türüdür. (Öğeleri) ayrı bayrağı değerler şunlardır:

- `badbit`, bir akış arabelleğinin bütünlüğünü kaybı kaydetmek için.

- `eofbit`, kayıt-bir akıştan ayıklanıyor sırasında dosya sonu için.

- `failbit`, geçerli bir alan bir akıştan ayıklamak için hata kaydetmek için.

Ayrıca, kullanışlı bir değerdir `goodbit`, ayarladığınız yerdir yukarıda açıklanan BITS hiçbiri (`goodbit` sıfır olması sağlanır).

## <a name="iword"></a>  ios_base::iword

Olarak depolanacak değer atayan bir `iword`.

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Parametreler

*IDX*<br/>
Dizin değeri olarak depolamak için bir `iword`.

### <a name="remarks"></a>Açıklamalar

Üye işlevi öğeye bir başvuru döndürür *IDX* Genişletilebilir dizinin öğelerini türle **uzun**. Tüm öğeleri etkili bir şekilde varsa ve ilk başta sıfır değeri depolar. Sonraki çağrısından sonra döndürülen başvuru geçersiz `iword` nesne için bir çağrı tarafından değiştirilen sonra nesne **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt), veya nesnesi yok edildikten sonra.

Varsa *IDX* negatif veya öğesi için benzersiz bir depolama alanı kullanılamıyorsa, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** ve benzersiz olmayabilir bir başvuru döndürür.

Türdeki tüm nesneler üzerinde kullanım için benzersiz bir dizinini elde etmek için `ios_base`, çağrı [xalloc](#xalloc).

### <a name="example"></a>Örnek

Bkz: [xalloc](#xalloc) nasıl kullanılacağını gösteren bir örnek `iword`.

## <a name="openmode"></a>  ios_base::Openmode

Bir akış ile etkileşim kurmak açıklar.

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

Türü bir `bitmask type` birkaç iostreams nesneler için açılış modu depolayan nesneyi tanımlar. (Öğeleri) ayrı bayrağı değerler şunlardır:

- `app`, her ekleme önce bir akışın sonuna aranacak.

- `ate`, denetleme, nesne ilk oluşturulduğunda bir akış sonuna aranacak.

- `binary`, bir dosyayı bir metin akışına olarak değil, ikili akış olarak okumak için.

- `in`, ayıklama akıştan izin vermek için.

- `out`, bir akışa ekleme izin vermek için.

- `trunc`, kendi kontrol eden bir nesne oluşturulduğunda, varolan bir dosyanın içeriğini silmek için.

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

İos_base nesneler için atama işleci.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir nesne türü `ios_base`.

### <a name="return-value"></a>Dönüş Değeri

Atanan nesne.

### <a name="remarks"></a>Açıklamalar

İşleci, Genişletilebilir bir dizi yeni kopyalayarak saklı biçimlendirme bilgileri kopyalar. Ardından döndürür  **\*bu**. Geri çağırma yığınını kopyalanmaz unutmayın.

Bu işleç yalnızca türetilmiş sınıfları tarafından kullanılan `ios_base`.

## <a name="precision"></a>  ios_base::Precision

Bir kayan noktalı sayı görüntülenecek basamak sayısını belirtir.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Parametreler

*_Prec*<br/>
Görüntülenecek anlamlı basamak sayısı veya sabit gösterimde ondalık basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi saklı döndürür [görüntü duyarlılığı](../standard-library/ios-base-class.md). İkinci üye işlevi depoları *_Prec* görüntüleme duyarlılığına döndürür, önceki değeri depolanır.

### <a name="remarks"></a>Açıklamalar

Kayan nokta sayıları ile sabit gösterimi görüntülenir [sabit](../standard-library/ios-functions.md#fixed).

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

Olarak depolanacak değer atayan bir `pword`.

```cpp
void *& pword(int _Idx);
```

### <a name="parameters"></a>Parametreler

*_Idx*<br/>
Dizin değeri olarak depolamak için bir `pword`.

### <a name="remarks"></a>Açıklamalar

Üye işlevi öğesi _ bir başvuru döndürür *IDX* Genişletilebilir dizinin öğelerini türle **void** işaretçi. Tüm öğeleri etkili bir şekilde varsa ve başlangıçta boş işaretçi depolar. Sonraki çağrısından sonra döndürülen başvuru geçersiz `pword` nesne için bir çağrı tarafından değiştirilen sonra nesne **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt), veya nesnesi yok edildikten sonra.

_ *IDX* negatif veya öğe için benzersiz bir depolama alanı kullanılamıyorsa, işlev çağıran [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** ve benzersiz olmayabilir bir başvuru döndürür.

Türdeki tüm nesneler üzerinde kullanım için benzersiz bir dizinini elde etmek için `ios_base`, çağrı [xalloc](#xalloc).

### <a name="example"></a>Örnek

Bkz: [xalloc](#xalloc) kullanma örneği için `pword`.

## <a name="register_callback"></a>  ios_base::register_callback

Bir geri çağırma işlevi belirtir.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Parametreler

*pfn*<br/>
Geri çağırma işlevi işaretçisi.

*IDX*<br/>
Kullanıcı tanımlı bir sayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi çifti gönderim `{pfn, idx}` saklı geri çağırma yığına [geri çağırma yığınını](../standard-library/ios-base-class.md). Bir geri çağırma olay **ev** bildirilir işlevleri çağrılır, kayıt, ters sırada ifadeyle `(*pfn)(ev, *this, idx)`.

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

İşlemleri için başlangıç noktası belirtir.

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

Birkaç iostream sınıflarının üye işlevleri bağımsız değişken olarak kullanılan arama modunda depolayan bir nesne tanımlayan bir listeden seçimli türü türüdür. Farklı bayrak değerleri şunlardır:

- `beg`, aranacak (alter geçerli okuma veya yazma konumunu) bir sıra (array, akış veya dosya) başlangıcına göre.

- `cur`, bir dizi içinde geçerli konumuna göre arama.

- `end`, bir dizinin sonuna göreli aranacak.

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

Belirtilen bayraklar ayarlar.

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

*_Mask*<br/>
Açmak için bayrakları.

*_Unset*<br/>
Devre dışı bırakmak için bayrak.

### <a name="return-value"></a>Dönüş Değeri

Önceki biçim bayrakları

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi etkili bir şekilde çağıran [bayrakları](#flags)(  *\_maskesi* &#124;  *\_bayrakları*) (Seçili bit ayarlanır) ve ardından döndürür Önceki biçim bayrakları. İkinci üye işlevi etkili bir şekilde çağıran `flags(_Mask & fmtfl, flags & ~_Mask)` (Seçili bit maskesi altında değiştirin) ve ardından önceki biçim bayrakları döndürür.

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

İostream ve C çalışma zamanı kitaplığı işlemleri kaynak kodunda göründükleri sırayla gerçekleşmemesini sağlar.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Parametreler

*_Sync*<br/>
Tüm akışları ile eşitleme halindeki `stdio`.

### <a name="return-value"></a>Dönüş Değeri

Bu işlev için önceki ayar.

### <a name="remarks"></a>Açıklamalar

Statik üye işlevi depoları bir `stdio` eşitleme başlangıçta bayrak **true**. Zaman **true**, aynı dosya üzerindeki işlemler arasında düzgün bir şekilde eşitlendiğini bu bayrağı sağlar [iostreams](../standard-library/iostreams-conventions.md) işlevler ve C++ Standart Kitaplığı'nda tanımlanan. Aksi takdirde, eşitleme olabilir veya garanti edilmez, ancak performans artırılabilir. İşlev depoları *_Sync* içinde `stdio` eşitleme bayrağı ve önceki depolanan değerine döndürür. Yalnızca standart akışlar üzerinde herhangi bir işlem gerçekleştirmeden önce güvenle çağırabilirsiniz.

## <a name="unsetf"></a> ios_base::unsetf

Belirtilen bayraklar kapalı olması neden olur.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Parametreler

*_Mask*<br/>
Kapatmak istediğiniz bayrakları.

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkili bir şekilde çağıran [bayrakları](#flags)(`~`*_maskesi* **& bayrakları**) (Seçili bit Temizle).

### <a name="example"></a>Örnek

Bkz: [ios_base::setf](#setf) kullanımının bir örneği için `unsetf`.

## <a name="width"></a> ios_base::width

Çıkış akışına uzunluğunu ayarlar.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Parametreler

*_Wide*<br/>
Çıkış akışı istenen boyutu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli genişliği ayarı.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan alan genişliği döndürür. İkinci üye işlevi depoları *_Wide* alan genişliğini ve döndürür, önceki değer depolanır.

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

Bir değişken akışın bir parçası olduğunu belirtir.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Dönüş Değeri

Statik üye işlevi her çağrıda artırır depolanan bir statik değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri üye işlevlerini çağırırken bir benzersiz dizin bağımsız değişken olarak kullanabilirsiniz [iword](#iword) veya [pword](#pword).

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
