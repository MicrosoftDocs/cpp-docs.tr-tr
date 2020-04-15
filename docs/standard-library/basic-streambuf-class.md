---
title: basic_streambuf Sınıfı
ms.date: 11/04/2016
f1_keywords:
- streambuf/std::basic_streambuf
- streambuf/std::basic_streambuf::char_type
- streambuf/std::basic_streambuf::int_type
- streambuf/std::basic_streambuf::off_type
- streambuf/std::basic_streambuf::pos_type
- streambuf/std::basic_streambuf::traits_type
- streambuf/std::basic_streambuf::eback
- streambuf/std::basic_streambuf::egptr
- streambuf/std::basic_streambuf::epptr
- streambuf/std::basic_streambuf::gbump
- streambuf/std::basic_streambuf::getloc
- streambuf/std::basic_streambuf::gptr
- streambuf/std::basic_streambuf::imbue
- streambuf/std::basic_streambuf::in_avail
- streambuf/std::basic_streambuf::overflow
- streambuf/std::basic_streambuf::pbackfail
- streambuf/std::basic_streambuf::pbase
- streambuf/std::basic_streambuf::pbump
- streambuf/std::basic_streambuf::pptr
- streambuf/std::basic_streambuf::pubimbue
- streambuf/std::basic_streambuf::pubseekoff
- streambuf/std::basic_streambuf::pubseekpos
- streambuf/std::basic_streambuf::pubsetbuf
- streambuf/std::basic_streambuf::pubsync
- streambuf/std::basic_streambuf::sbumpc
- streambuf/std::basic_streambuf::seekoff
- streambuf/std::basic_streambuf::seekpos
- streambuf/std::basic_streambuf::setbuf
- streambuf/std::basic_streambuf::setg
- streambuf/std::basic_streambuf::setp
- streambuf/std::basic_streambuf::sgetc
- streambuf/std::basic_streambuf::sgetn
- streambuf/std::basic_streambuf::showmanyc
- streambuf/std::basic_streambuf::snextc
- streambuf/std::basic_streambuf::sputbackc
- streambuf/std::basic_streambuf::sputc
- streambuf/std::basic_streambuf::sputn
- streambuf/std::basic_streambuf::stossc
- streambuf/std::basic_streambuf::sungetc
- streambuf/std::basic_streambuf::swap
- streambuf/std::basic_streambuf::sync
- streambuf/std::basic_streambuf::uflow
- streambuf/std::basic_streambuf::underflow
- streambuf/std::basic_streambuf::xsgetn
- streambuf/std::basic_streambuf::xsputn
helpviewer_keywords:
- std::basic_streambuf [C++]
- std::basic_streambuf [C++], char_type
- std::basic_streambuf [C++], int_type
- std::basic_streambuf [C++], off_type
- std::basic_streambuf [C++], pos_type
- std::basic_streambuf [C++], traits_type
- std::basic_streambuf [C++], eback
- std::basic_streambuf [C++], egptr
- std::basic_streambuf [C++], epptr
- std::basic_streambuf [C++], gbump
- std::basic_streambuf [C++], getloc
- std::basic_streambuf [C++], gptr
- std::basic_streambuf [C++], imbue
- std::basic_streambuf [C++], in_avail
- std::basic_streambuf [C++], overflow
- std::basic_streambuf [C++], pbackfail
- std::basic_streambuf [C++], pbase
- std::basic_streambuf [C++], pbump
- std::basic_streambuf [C++], pptr
- std::basic_streambuf [C++], pubimbue
- std::basic_streambuf [C++], pubseekoff
- std::basic_streambuf [C++], pubseekpos
- std::basic_streambuf [C++], pubsetbuf
- std::basic_streambuf [C++], pubsync
- std::basic_streambuf [C++], sbumpc
- std::basic_streambuf [C++], seekoff
- std::basic_streambuf [C++], seekpos
- std::basic_streambuf [C++], setbuf
- std::basic_streambuf [C++], setg
- std::basic_streambuf [C++], setp
- std::basic_streambuf [C++], sgetc
- std::basic_streambuf [C++], sgetn
- std::basic_streambuf [C++], showmanyc
- std::basic_streambuf [C++], snextc
- std::basic_streambuf [C++], sputbackc
- std::basic_streambuf [C++], sputc
- std::basic_streambuf [C++], sputn
- std::basic_streambuf [C++], stossc
- std::basic_streambuf [C++], sungetc
- std::basic_streambuf [C++], swap
- std::basic_streambuf [C++], sync
- std::basic_streambuf [C++], uflow
- std::basic_streambuf [C++], underflow
- std::basic_streambuf [C++], xsgetn
- std::basic_streambuf [C++], xsputn
ms.assetid: 136af6c3-13bf-4501-9288-b93da26efac7
ms.openlocfilehash: 0cf7b61bde86a4643836346dafd36680fb8cf302
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376739"
---
# <a name="basic_streambuf-class"></a>basic_streambuf Sınıfı

Bir akışın belirli bir temsiline ve öğelerinin iletimini kontrol eden bir akış arabelleği türetmek için soyut bir taban sınıf açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_streambuf;
```

### <a name="parameters"></a>Parametreler

*Elem*\
Bir [char_type.](#char_type)

*Tr*\
Karakter [traits_type.](#traits_type)

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, öğelerin bir akışın belirli bir temsiline ve iletimini kontrol eden bir akış arabelleği türetmek için soyut bir taban sınıf açıklar. Sınıf `basic_streambuf` bir nesne türü *Tr*öğeleri ile bir akışı kontrol yardımcı olur , ayrıca [char_type](#char_type)olarak bilinen , olan karakter özellikleri sınıf tarafından belirlenir [char_traits](../standard-library/char-traits-struct.md), ayrıca [traits_type](#traits_type)olarak bilinen .

Her akış arabelleği kavramsal olarak iki bağımsız akışı kontrol eder: biri çıkarma (giriş) ve diğeri eklemeler (çıktı) için. Ancak, belirli bir gösterim bu akışlardan birini veya her ikisini erişilemez hale getirebilir. Genellikle iki akış arasında bazı ilişki korur. Örneğin, [bir basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`,> `Tr` nesnenin çıktı akışına eklediğiniz şey, daha sonra giriş akışından çıkardığınız şeydir. Bir [basic_filebuf,](../standard-library/basic-filebuf-class.md)< `Elem` `Tr` nesne> bir akışı konumlandırdığınızda, diğer akışı birlikte konumlandırın.

Sınıf şablonuna `basic_streambuf` ortak arabirim, ancak özelleştirilmiş, tüm akış arabellekleri için ortak olan işlemleri sağlar. Korumalı arabirim, bir akışın işini yapması için belirli bir gösterim için gereken işlemleri sağlar. Korumalı sanal üye işlevleri, türetilmiş bir akış arabelleği davranışını bir akışın belirli bir gösterimi için uyarlamanıza izin verebiliyor. Bu kitaplıktaki türetilen her akış arabelleği, korumalı sanal üye işlevlerinin davranışını nasıl uzmanlaştırdığını açıklar. Genellikle hiçbir şey yapmamak için taban sınıf için varsayılan davranış, bu konuda açıklanmıştır.

Kalan korumalı üye işlevler, akışlara arabellek iletimleri için sağlanan herhangi bir depolama alanına ve bu depodan kopyalamayı denetler. Örneğin, bir giriş arabelleği aşağıdakiler ile karakterize edilir:

- [eback](#eback), arabellek başına bir işaretçi.

- [gptr](#gptr), okumak için bir sonraki öğeiçin bir işaretçi.

- [egptr](#egptr), arabelleğenin sonuna kadar bir işaretçi.

Benzer şekilde, bir çıktı arabelleği ile karakterizedir:

- [pbase](#pbase), arabellek başına bir işaretçi.

- [pptr](#pptr), yazmak için bir sonraki öğeye bir işaretçi.

- [epptr](#epptr), arabelleğenin sonuna kadar bir işaretçi.

Herhangi bir arabellek için aşağıdaki protokol kullanılır:

- Bir sonraki işaretçi null ise arabellek yok. Aksi takdirde, üç işaretçi de aynı sırayı işaret eder. Onlar güvenli bir şekilde sipariş için karşılaştırılabilir.

- Bir çıktı arabelleği için, bir sonraki işaretçi son işaretçiden daha az karşılaştırırsa, bir sonraki işaretçi tarafından belirlenen yazma konumunda bir öğe depolayabilirsiniz.

- Bir giriş arabelleği için, bir sonraki işaretçi son işaretçiden daha az karşılaştırırsa, bir sonraki işaretçi tarafından belirlenen okuma konumundabir öğeyi okuyabilirsiniz.

- Bir giriş arabelleği için, başlangıç işaretçisi bir sonraki işaretçiden daha az karşılaştırırsa, bir sonraki işaretçi tarafından belirlenen geri alma konumuna bir öğe koyabilirsiniz.

`basic_streambuf` <  `Elem`Türetilen bir sınıf için yazdığınız korumalı sanal üye işlevleri, `Tr`> bu protokolün korunmasında işbirliği yapılmalıdır.

`basic_streambuf` < Sınıfın `Elem`bir nesnesi , `Tr`> daha önce açıklanan altı işaretçiyi depolar. Ayrıca, türemiş bir akış arabelleği tarafından olası kullanım için bir tür [yerel nesnesi](../standard-library/locale-class.md) bir yerel nesne depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_streambuf](#basic_streambuf)|Türünde `basic_streambuf`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir tür adını `Elem` şablon parametresi ile ilişkilendirer.|
|[Int_type](#int_type)|Kapsam içindeki `basic_streambuf` bir tür `Elem` adını şablon parametresi ile ilişkilendirer.|
|[off_type](#off_type)|Kapsam içindeki `basic_streambuf` bir tür `Elem` adını şablon parametresi ile ilişkilendirer.|
|[pos_type](#pos_type)|Kapsam içindeki `basic_streambuf` bir tür `Elem` adını şablon parametresi ile ilişkilendirer.|
|[traits_type](#traits_type)|Bir tür adını `Tr` şablon parametresi ile ilişkilendirer.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[eback](#eback)|Bir işaretçiyi giriş arabelleği başına döndüren korumalı bir işlev.|
|[egptr](#egptr)|Giriş arabelleği sonundan hemen geçmiş bir işaretçi döndüren korumalı bir işlev.|
|[epptr](#epptr)|Çıktı arabelleği sonundan hemen geçmiş bir işaretçi döndüren korumalı bir işlev.|
|[gbump](#gbump)|Giriş arabelleği `count` için bir sonraki işaretçiye ekleyen korumalı bir işlev.|
|[getloc](#getloc)|Nesnenin `basic_streambuf` yerel liğini alır.|
|[gptr](#gptr)|Bir işaretçiyi giriş arabellesinin bir sonraki öğesine döndüren korumalı bir işlev.|
|[imbue](#imbue)|[Pubimbue](#pubimbue)tarafından çağrılan korumalı, sanal bir işlev.|
|[in_avail](#in_avail)|Arabellekten okunmaya hazır öğelerin sayısını verir.|
|[Taşma](#overflow)|Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Giriş akışına bir öğeyi geri koymaya çalışan, ardından geçerli öğeyi (bir sonraki işaretçitarafından işaret edilen) yapmaya çalışan korumalı bir sanal üye işlev.|
|[Pbase](#pbase)|Çıkış arabelleği başına bir işaretçi döndüren korumalı bir işlev.|
|[pbump](#pbump)|Çıktı arabelleği `count` için bir sonraki işaretçiye ekleyen korumalı bir işlev.|
|[pptr](#pptr)|Çıkış arabelleği sonraki öğesine bir işaretçi döndüren korumalı bir işlev.|
|[pubimbue](#pubimbue)|Nesnenin `basic_streambuf` yerel ayarını ayarlar.|
|[Pubseekoff](#pubseekoff)|Aramalar [seekoff](#seekoff), türetilmiş bir sınıfta geçersiz kılınmış bir korumalı sanal işlev.|
|[pubseekpos](#pubseekpos)|Çağrıları [seekpos](#seekpos), türetilmiş bir sınıfta geçersiz kılınmış ve geçerli işaretçi konumunu sıfırlayan korumalı bir sanal işlev.|
|[pubsetbuf](#pubsetbuf)|[Çağrılar setbuf](#setbuf), türemiş bir sınıfta geçersiz kılınmış bir korumalı sanal işlev.|
|[pubsync](#pubsync)|Türemiş bir sınıfta geçersiz kılınan ve bu arabellekle ilişkili dış akışı güncelleyen korumalı bir sanal işlev olan [eşitleme](#sync)çağırır.|
|[sbumpc](#sbumpc)|Akış işaretçisini hareket ettiren geçerli öğeyi okur ve döndürür.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi, türetilen her akış arabelleği için özel bir işlem gerçekleştirir.|
|[setg](#setg)|Başlangıç işaretçisinde, `_Gbeg` `_Gnext` sonraki işaretçide ve `_Gend` giriş arabelleği için son işaretçide depolayan korumalı işlev.|
|[setp](#setp)|Çıkış arabelleği `_Pbeg` için başlangıç `_Pend` işaretçisinde ve son işaretçide depolayan korumalı bir işlev.|
|[sgetc](#sgetc)|Akıştaki konumu değiştirmeden geçerli öğeyi döndürür.|
|[sgetn](#sgetn)|Okunan öğe sayısını döndürür.|
|[showmanyc](#showmanyc)|Giriş akışından çıkarılabilen karakter sayısının sayısını döndüren ve programın süresiz beklemeye tabi tutulmamasını sağlayan korumalı sanal üye işlevi.|
|[snextc](#snextc)|Geçerli öğeyi okur ve aşağıdaki öğeyi döndürür.|
|[sputbackc](#sputbackc)|Dereye `char_type` bir yer.|
|[sputc](#sputc)|Bir karakteri akışına koyar.|
|[sputn](#sputn)|Akışa bir karakter dizesi koyar.|
|[stossc](#stossc)|Akıştaki geçerli öğeyi geride taşıyın.|
|[sungetc](#sungetc)|Akıştan bir karakter alır.|
|[Takas](#swap)|Sağlanan `basic_streambuf` nesne parametresindeki değerler için bu nesnedeki değerleri değiştirir.|
|[Eşitleme](#sync)|Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışan korumalı bir sanal işlev.|
|[uflow](#uflow)|Giriş akışından geçerli öğeyi ayıklayan korumalı bir sanal işlev.|
|[akış altı](#underflow)|Giriş akışından geçerli öğeyi ayıklayan korumalı bir sanal işlev.|
|[xsgetn](#xsgetn)|Giriş akışından öğeleri ayıklayan korumalı bir sanal işlev.|
|[xsputn](#xsputn)|Öğeleri çıktı akışına yerleştiren korumalı bir sanal işlev.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bu nesnenin değerlerini başka `basic_streambuf` bir nesneden atar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<streambuf>

**Ad alanı:** std

## <a name="basic_streambufbasic_streambuf"></a><a name="basic_streambuf"></a>basic_streambuf:basic_streambuf

Türünde `basic_streambuf`bir nesne oluşturuyor.

```cpp
basic_streambuf();

basic_streambuf(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bu `basic_streambuf` `basic_streambuf` nesnenin değerlerini ayarlamak için kullanılan nesneye bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk korumalı oluşturucu, giriş arabelleği ve çıktı arabelleği denetleyen tüm işaretçilerde bir null işaretçisi depolar. Ayrıca yerel `locale::classic` nesnede depolar. Daha fazla bilgi için [bkz: yerel::klasik](../standard-library/locale-class.md#classic).

İkinci korumalı oluşturucu işaretçileri ve yerelliği *sağdan*kopyalar.

## <a name="basic_streambufchar_type"></a><a name="char_type"></a>basic_streambuf:char_type

Bir tür adını **Elem** şablon parametresi ile ilişkilendirer.

```cpp
typedef Elem char_type;
```

## <a name="basic_streambufeback"></a><a name="eback"></a>basic_streambuf::eback

Bir işaretçiyi giriş arabelleği başına döndüren korumalı bir işlev.

```cpp
char_type *eback() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği başına bir işaretçi.

## <a name="basic_streambufegptr"></a><a name="egptr"></a>basic_streambuf::egptr

Giriş arabelleği sonundan hemen geçmiş bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *egptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği sonuna sadece geçmiş bir işaretçi.

## <a name="basic_streambufepptr"></a><a name="epptr"></a>basic_streambuf::epptr

Çıktı arabelleği sonundan hemen geçmiş bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *epptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktı arabelleği sonuna sadece geçmiş bir işaretçi.

## <a name="basic_streambufgbump"></a><a name="gbump"></a>basic_streambuf::gbump

Giriş arabelleği için bir sonraki işaretçiye *sayı* ekleyen korumalı bir işlev.

```cpp
void gbump(int count);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
İşaretçiyi ilerletmek için gereken miktar.

## <a name="basic_streambufgetloc"></a><a name="getloc"></a>basic_streambuf::getloc

nesnenin basic_streambuf'nın yerel liğini alır.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan yerel nesne.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için [ios_base::getloc](../standard-library/ios-base-class.md#getloc)' a bakın.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_getloc.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << cout.rdbuf( )->getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="basic_streambufgptr"></a><a name="gptr"></a>basic_streambuf::gptr

Bir işaretçiyi giriş arabellesinin bir sonraki öğesine döndüren korumalı bir işlev.

```cpp
char_type *gptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği sonraki öğesi için bir işaretçi.

## <a name="basic_streambufimbue"></a><a name="imbue"></a>basic_streambuf::imbue

[Pubimbue](#pubimbue)tarafından çağrılan korumalı bir sanal işlev.

```cpp
virtual void imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*\
Bir yerel örne başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış hiçbir şey yapmamaktır.

## <a name="basic_streambufin_avail"></a><a name="in_avail"></a>basic_streambuf::in_avail

Arabellekten okunmaya hazır öğelerin sayısını verir.

```cpp
streamsize in_avail();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekten okunmaya hazır öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Okuma [pozisyonu](../standard-library/basic-streambuf-class.md) varsa, üye işlev [egptr](#egptr) - [gptr](#gptr)döndürür. Aksi takdirde, [showmanyc](#showmanyc)döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_in_avail.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   char c;
   // cin's buffer is empty, in_avail will return 0
   cout << cin.rdbuf( )->in_avail( ) << endl;
   cin >> c;
   cout << cin.rdbuf( )->in_avail( ) << endl;
}
```

## <a name="basic_streambufint_type"></a><a name="int_type"></a>basic_streambuf:int_type

Basic_streambuf kapsamdaki bir tür adını şablon parametresindeki türlerden biriyle ilişkilendirin.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_streambufoff_type"></a><a name="off_type"></a>basic_streambuf:off_type

Basic_streambuf kapsamdaki bir tür adını şablon parametresindeki türlerden biriyle ilişkilendirin.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_streambufoperator"></a><a name="op_eq"></a>basic_streambuf::operator=

Bu nesnenin değerlerini başka `basic_streambuf` bir nesneden atar.

```cpp
basic_streambuf& operator=(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bu `basic_streambuf` nesneye değer atamak için kullanılan nesneye bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işleç, giriş arabelleği ve çıktı arabelleği denetimi *işaretçileri sağdan* kopyalar. Ayrıca mağazalar `right.` [getloc()](#getloc) `locale object`içinde . Geri `*this`dönüyor.

## <a name="basic_streambufoverflow"></a><a name="overflow"></a>basic_streambuf::taşma

Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı **olamazsa, traits_type** döndürür veya bir özel durum atar. Aksi takdirde, traits_type döndürür:: **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta).* Varsayılan davranış traits_type **dönmektir::eof**.

### <a name="remarks"></a>Açıklamalar

*\_* **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type) **traits_type::eof** *Meta traits_type eşit karşılaştırmak değilse::eof , korumalı sanal üye işlevi traits_type öğeeklemek için çaba: to_char_type ( Meta \_* ) çıkış akışına. Bunu çeşitli şekillerde yapabilirsiniz:

- A `write position` varsa, öğeyi yazma konumuna depolayabilir ve çıktı arabelleği için bir sonraki işaretçiyi öne çıkarabilirsiniz.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak yazma konumunu kullanılabilir hale getirebilir.

- Bir yazma konumunu, bazı dış hedefe, çıktı arabelleği için başlangıç ve sonraki işaretçiler arasındaki öğelerin bazılarına veya tümüne yazarak kullanılabilir hale getirebilir.

Sanal taşma işlevi, [eşitleme](#sync) ve [akış altı](#underflow) işlevleriyle birlikte, akış buf türetilmiş sınıfın özelliklerini tanımlar. Türetilen her sınıf taşması farklı şekilde uygulayabilir, ancak arama akışı sınıfıyla arabirim aynıdır.

`overflow` İşlev en sık, `streambuf` `sputc` put alanının `sputn` dolu olduğu gibi genel işlevler tarafından çağrılır, `overflow` ancak akış sınıfları da dahil olmak üzere diğer sınıflar her zaman arayabilir.

İşlev, put alanındaki karakterleri işaretçiler `pbase` le `pptr` işaretçiler arasında tüketir ve ardından put alanını yeniden başolarak yeniden başlarlar. İşlev `overflow` de `nCh` tüketmelidir `nCh` `EOF`(değilse), ya da bir sonraki çağrıda tüketilen olacak şekilde yeni put alanına bu karakteri koymak seçebilirsiniz.

Tüketim tanımı türemiş sınıflar arasında değişir. Örneğin, `filebuf` sınıf karakterlerini bir dosyaya yazarken, `strstreambuf` sınıf bunları arabelleğinde tutar ve (arabellek dinamik olarak belirlenmişse) taşması çağrısına yanıt olarak arabelleği genişletir. Bu genişletme, eski arabelleği serbest bırakıp yeni, daha büyük bir arabellekle değiştirerek elde edilir. İşaretçiler gerektiği gibi ayarlanır.

## <a name="basic_streambufpbackfail"></a><a name="pbackfail"></a>basic_streambuf::pbackfail

Giriş akışına bir öğeyi geri koymaya çalışan, ardından geçerli öğeyi (bir sonraki işaretçitarafından işaret edilen) yapmaya çalışan korumalı bir sanal üye işlev.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı **olamazsa, traits_type** döndürür veya bir özel durum atar. Aksi takdirde, başka bir değer döndürür. Varsayılan davranış traits_type **dönmektir::eof**.

### <a name="remarks"></a>Açıklamalar

Meta traits_type eşit **karşılaştırırsa::eof**, geri itmek için öğe etkili bir geçerli öğeönce akışı zaten biridir. * \_* Aksi takdirde, bu öğe traits_type ile **değiştirilir::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(*\_Meta*). İşlev çeşitli şekillerde bir öğegeri koyabilirsiniz:

- Bir geri alma konumu varsa, öğeyi geri koyma konumuna depolayabilir ve giriş arabelleği için bir sonraki işaretçiyi atabilir.

- Giriş arabelleği için yeni veya ek depolama alanı ayırarak geri alma konumunu kullanılabilir hale getirebilir.

- Ortak giriş ve çıktı akışlarına sahip bir akış arabelleği için, çıktı arabelleği için başlangıç ve sonraki işaretçiler arasındaki öğelerin bazılarını veya tümlerini bazı dış hedefe, bazı dış hedefe yazarak bir geri alma konumunu kullanılabilir hale getirebilir.

## <a name="basic_streambufpbase"></a><a name="pbase"></a>basic_streambuf::pbase

Çıkış arabelleği başına bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pbase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktı arabelleği başına bir işaretçi.

## <a name="basic_streambufpbump"></a><a name="pbump"></a>basic_streambuf::ptümsek

Çıktı arabelleği için bir sonraki işaretçiye *sayı* ekleyen korumalı bir işlev.

```cpp
void pbump(int count);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Yazma konumunu ileriye taşımak için karakter sayısı.

## <a name="basic_streambufpos_type"></a><a name="pos_type"></a>basic_streambuf::pos_type

Basic_streambuf kapsamdaki bir tür adını şablon parametresindeki türlerden biriyle ilişkilendirin.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_streambufpptr"></a><a name="pptr"></a>basic_streambuf::pptr

Çıkış arabelleği sonraki öğesine bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktı arabelleği sonraki öğesi için bir işaretçi.

## <a name="basic_streambufpubimbue"></a><a name="pubimbue"></a>basic_streambuf::pubimbue

basic_streambuf nesnenin yerel ayarını ayarlar.

```cpp
locale pubimbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*\
Bir yerel örne başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yerel nesnede depolanan önceki değer.

### <a name="remarks"></a>Açıklamalar

Üye işlev , _ *Loc'u* yerel nesnede saklar ve [imbue](#imbue)çağırır.

### <a name="example"></a>Örnek

[Bkz. basic_ios::kullanan](../standard-library/basic-ios-class.md#imbue) `pubimbue`bir örnek için imbue .

## <a name="basic_streambufpubseekoff"></a><a name="pubseekoff"></a>basic_streambuf::pubseekoff

Aramalar [seekoff](#seekoff), türetilmiş bir sınıfta geçersiz kılınmış bir korumalı sanal işlev.

```cpp
pos_type pubseekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_off*\
*_Way*göreli aramak için pozisyon .

*_way*\
Ofset işlemleri için başlangıç noktası. Bkz. olası değerler için [seekdir.](../standard-library/ios-base-class.md#seekdir)

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu veya geçersiz akış konumunu döndürür ( `_Way` `_Which` [arama](#seekoff)(_ *Kapalı*, , ) ).

### <a name="remarks"></a>Açıklamalar

İşaretçiyi göreli olarak *_Way*taşır.

## <a name="basic_streambufpubseekpos"></a><a name="pubseekpos"></a>basic_streambuf::pubseekpos

Çağrıları [seekpos](#seekpos), türetilmiş bir sınıfta geçersiz kılınmış bir korumalı sanal işlev ve geçerli işaretçi konumunu sıfırlar.

```cpp
pos_type pubseekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Aranacak pozisyon.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konum veya geçersiz akış konumu. Akış konumunun geçersiz olup olmadığını belirlemek için, `pos_type(off_type(-1))`iade değerini .

### <a name="remarks"></a>Açıklamalar

Üye işlev [seekpos](#seekpos)döndürür `_Which`(_ *Sp*, ).

## <a name="basic_streambufpubsetbuf"></a><a name="pubsetbuf"></a>basic_streambuf::pubsetbuf

[Çağrılar setbuf](#setbuf), türemiş bir sınıfta geçersiz kılınmış bir korumalı sanal işlev.

```cpp
basic_streambuf<Elem, Tr> *pubsetbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
Bu anlık `char_type` için bir işaretçi.

*Sayısı*\
Arabelleğe in boyutu.

### <a name="return-value"></a>Dönüş Değeri

[Setbuf (,](#setbuf) `_Buffer` `count`) döndürür.

## <a name="basic_streambufpubsync"></a><a name="pubsync"></a>basic_streambuf::pubsync

Türemiş bir sınıfta geçersiz kılınan korumalı sanal işlev [eşitleme](#sync)çağırır ve bu arabellekle ilişkili dış akışı güncelleştirir.

```cpp
int pubsync();
```

### <a name="return-value"></a>Dönüş Değeri

[Eşitleme](#sync) veya -1 verir eğer hata.

## <a name="basic_streambufsbumpc"></a><a name="sbumpc"></a>basic_streambuf::sbumpc

Akış işaretçisini hareket ettiren geçerli öğeyi okur ve döndürür.

```cpp
int_type sbumpc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Okuma konumu varsa, üye işlev **traits_type**döndürür:[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( <strong>\*</strong> [gptr](#gptr)) ve giriş arabelleği için bir sonraki işaretçiyi öne çıkar. Aksi takdirde, [uflow](#uflow)döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sbumpc.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 0;
   i = cin.rdbuf( )->sbumpc( );
   cout << i << endl;
}
```

```Input
3
```

```Output
33
51
```

## <a name="basic_streambufseekoff"></a><a name="seekoff"></a>basic_streambuf::seekoff

Denetitilen akışlar için geçerli konumları değiştirmeye çalışan korumalı sanal üye işlevi.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_off*\
*_Way*göreli aramak için pozisyon .

*_way*\
Ofset işlemleri için başlangıç noktası. Bkz. olası değerler için [seekdir.](../standard-library/ios-base-class.md#seekdir)

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu veya geçersiz akış konumunu `seekoff` döndürür `_Way` `_Which`( (_ *Kapalı*, , ) ).

### <a name="remarks"></a>Açıklamalar

Yeni pozisyon aşağıdaki gibi belirlenir:

- `_Way`  == Eğer `ios_base::beg`, yeni pozisyon akışı artı _ *Off*başlangıcıdır.

- `_Way`  == Eğer `ios_base::cur`, yeni konum geçerli akış konumu artı _ *Off.*

- `_Way`  == Eğer `ios_base::end`, yeni pozisyon akışı artı _ *Off*sonudur.

Genellikle, **ios_base &::in** sıfır değilse, giriş akışı etkilenir ve **ios_base &::çıkış** sıfır değilse, çıkış akışı etkilenir. Ancak, bu parametrenin gerçek kullanımı türetilmiş akış arabellekleri arasında değişir.

İşlev akış konumunu veya pozisyonlarını değiştirmeyi başarırsa, ortaya çıkan akış konumunu veya çıkan akış konumlarından birini döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür. Varsayılan davranış geçersiz bir akış konumunu döndürmektir.

## <a name="basic_streambufseekpos"></a><a name="seekpos"></a>basic_streambuf::seekpos

Denetitilen akışlar için geçerli konumları değiştirmeye çalışan korumalı sanal üye işlevi.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Aranacak pozisyon.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konum veya geçersiz akış konumu. Akış konumunun geçersiz olup olmadığını belirlemek için, `pos_type(off_type(-1))`iade değerini .

### <a name="remarks"></a>Açıklamalar

Yeni pozisyon _ *Sp*.

Genellikle, **ios_base &::in** sıfır değilse, giriş akışı etkilenir ve **ios_base &::çıkış** sıfır değilse, çıkış akışı etkilenir. Ancak, bu parametrenin gerçek kullanımı türetilmiş akış arabellekleri arasında değişir.

İşlev akış konumunu veya pozisyonlarını değiştirmeyi başarırsa, ortaya çıkan akış konumunu veya çıkan akış konumlarından birini döndürür. Aksi takdirde, geçersiz bir akış konumu (-1) döndürür. Varsayılan davranış geçersiz bir akış konumunu döndürmektir.

## <a name="basic_streambufsetbuf"></a><a name="setbuf"></a>basic_streambuf::setbuf

Türetilen her akış arabelleği için özel bir işlem gerçekleştiren korumalı sanal üye işlevi.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
Arabellek için işaretçi.

*Sayısı*\
Arabelleğe boyutu.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan davranış **bu**döndürecek.

### <a name="remarks"></a>Açıklamalar

[Bkz. basic_filebuf.](../standard-library/basic-filebuf-class.md) `setbuf`nesnenin `streambuf` kullanması için bir bellek alanı sağlar. Arabellek türemiş sınıflarda tanımlanan nasıl kullanılır.

## <a name="basic_streambufsetg"></a><a name="setg"></a>basic_streambuf::setg

_ *Gbeg'i* başlangıç işaretçisinde, `_Gnext` sonraki işaretçide `_Gend` ve giriş arabelleği için son işaretçide depolayan korumalı işlev.

```cpp
void setg(char_type* _Gbeg,
    char_type* _Gnext,
    char_type* _Gend);
```

### <a name="parameters"></a>Parametreler

*_Gbeg*\
Arabellek başına bir işaretçi.

*_Gnext*\
Arabelleğe inin ortasında bir yere işaretçi.

*_Gend*\
Arabelleğenin sonuna giden bir işaretçi.

## <a name="basic_streambufsetp"></a><a name="setp"></a>basic_streambuf::setp

_Pbeg başlangıç *işaretçisinde* depolayan ve çıktı arabelleği için son işaretçide *_Pend* korumalı bir işlev.

```cpp
void setp(char_type* _Pbeg, char_type* _Pend);
```

### <a name="parameters"></a>Parametreler

*_Pbeg*\
Arabellek başına bir işaretçi.

*_Pend*\
Arabelleğenin sonuna giden bir işaretçi.

## <a name="basic_streambufsgetc"></a><a name="sgetc"></a>basic_streambuf::sgetc

Akıştaki konumu değiştirmeden geçerli öğeyi döndürür.

```cpp
int_type sgetc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Okuma konumu varsa, üye işlev **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)to_int_type `*`( [gptr)](#gptr)döndürür. Aksi takdirde, [akış altında](#underflow)döner.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sgetc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   ifstream myfile( "basic_streambuf_sgetc.txt", ios::in );

   char i = myfile.rdbuf( )->sgetc( );
   cout << i << endl;
   i = myfile.rdbuf( )->sgetc( );
   cout << i << endl;
}
```

## <a name="basic_streambufsgetn"></a><a name="sgetn"></a>basic_streambuf::sgetn

Giriş arabelleği karakterleri *saymak* için ayıklar ve sağlanan arabellek *ptr*onları depolar.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir.

```cpp
streamsize sgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Çıkarılan karakterleri içerecek arabellek.

*Sayısı*\
Okunacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Okunan öğelerin sayısı. Daha fazla bilgi için [akış boyutuna](../standard-library/ios-typedefs.md#streamsize) bakın.

### <a name="remarks"></a>Açıklamalar

Üye işlev [xsgetn](#xsgetn) `ptr`döndürür ( , `count`).

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sgetn.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;

    ifstream myfile("basic_streambuf_sgetn.txt", ios::in);
    char a[10];

    // Extract 3 characters from myfile and store them in a.
    streamsize i = myfile.rdbuf()->sgetn(&a[0], 3);  // C4996
    a[i] = myfile.widen('\0');

    // Display the size and contents of the buffer passed to sgetn.
    cout << i << " " << a << endl;

    // Display the contents of the original input buffer.
    cout << myfile.rdbuf() << endl;
}
```

## <a name="basic_streambufshowmanyc"></a><a name="showmanyc"></a>basic_streambuf::showmanyc

Giriş akışından çıkarılabilen karakter sayısının sayısını döndüren ve programın süresiz beklemeye tabi tutulmamasını sağlayan korumalı sanal üye işlevi.

```cpp
virtual streamsize showmanyc();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan davranış sıfır dönmektir.

## <a name="basic_streambufsnextc"></a><a name="snextc"></a>basic_streambuf::snextc

Geçerli öğeyi okur ve aşağıdaki öğeyi döndürür.

```cpp
int_type snextc();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki bir sonraki öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev [sbumpc](#sbumpc) çağırır ve, bu işlev **traits_type dönerse::**[eof](../standard-library/char-traits-struct.md#eof), traits_type döndürür::eof . **traits_type::eof** Aksi takdirde, [sgetc](#sgetc)döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_snextc.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   int i = 0;
   i = cin.rdbuf( )->snextc( );
   // cout << ( int )char_traits<char>::eof << endl;
   cout << i << endl;
}
```

```Input
aa
```

```Output
aa97
```

## <a name="basic_streambufsputbackc"></a><a name="sputbackc"></a>basic_streambuf::sputbackc

Dereye bir char_type koyar.

```cpp
int_type sputbackc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Karakter.

### <a name="return-value"></a>Dönüş Değeri

Karakteri veya başarısızlığı döndürür.

### <a name="remarks"></a>Açıklamalar

Bir geri alma konumu varsa ve *_Ch* bu konumda depolanan karaktere eşit karşılaştırırsa, üye işlev giriş arabelleği için `_Ch`bir sonraki işaretçiyi verir ve traits_type döndürür: **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( ). Aksi takdirde, [pbackfail](#pbackfail)() `_Ch`döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sputbackc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;

    ifstream myfile("basic_streambuf_sputbackc.txt",
        ios::in);

    int i = myfile.rdbuf()->sbumpc();
    cout << (char)i << endl;
    int j = myfile.rdbuf()->sputbackc('z');
    if (j == 'z')
    {
        cout << "it worked" << endl;
    }
    i = myfile.rdbuf()->sgetc();
    cout << (char)i << endl;
}
```

## <a name="basic_streambufsputc"></a><a name="sputc"></a>basic_streambuf::sputc

Bir karakteri akışına koyar.

```cpp
int_type sputc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Karakter.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa karakteri döndürür.

### <a name="remarks"></a>Açıklamalar

`write position` A varsa, üye işlev *yazma* konumunda _Ch depolar, çıktı arabelleği için bir sonraki işaretçiyi `_Ch`artırdı ve traits_type döndürür: **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( ). Aksi takdirde, [taşma](#overflow)() `_Ch`döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sputc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   int i = cout.rdbuf( )->sputc( 'a' );
   cout << endl << ( char )i << endl;
}
```

```Output
a
a
```

## <a name="basic_streambufsputn"></a><a name="sputn"></a>basic_streambuf::sputn

Akışa bir karakter dizesi koyar.

```cpp
streamsize sputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Karakter dizesi.

*Sayısı*\
Karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Akışa eklenen karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev [xsputn](#xsputn) `ptr`(, ) `count`döndürür. Daha fazla bilgi için bu üyenin Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sputn.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;

    streamsize i = cout.rdbuf()->sputn("test", 4);
    cout << endl << i << endl;
}
```

```Output
test
4
```

## <a name="basic_streambufstossc"></a><a name="stossc"></a>basic_streambuf::stossc

Akıştaki geçerli öğeyi geride taşıyın.

```cpp
void stossc();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev [sbumpc](#sbumpc)çağırır. Bu üye işlevi sağlamak için bir uygulama nın gerekli olmadığını unutmayın.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_stossc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   ifstream myfile( "basic_streambuf_stossc.txt", ios::in );

   myfile.rdbuf( )->stossc( );
   char i = myfile.rdbuf( )->sgetc( );
   cout << i << endl;
}
```

## <a name="basic_streambufsungetc"></a><a name="sungetc"></a>basic_streambuf::sungetc

Akıştan bir karakter alır.

```cpp
int_type sungetc();
```

### <a name="return-value"></a>Dönüş Değeri

Karakteri veya başarısızlığı döndürür.

### <a name="remarks"></a>Açıklamalar

Bir geri alma konumu varsa, üye işlev giriş arabelleği için bir sonraki `traits_type::`işaretçiyi verir ve [to_int_type](../standard-library/char-traits-struct.md#to_int_type) `*` [(gptr)](#gptr)döndürür. Ancak, geçerli arabellek durumunda yakalanan böylece okunan son karakteri belirlemek her zaman mümkün değildir. Bu doğruysa, işlev [pbackfail](#pbackfail)döndürür. Bu durumu önlemek için, geri koymak ve `sputbackc(ch)`aramak için karakter takip edin , hangi akışı başında aramazsanız başarısız olmaz ve birden fazla karakter geri koymak için çalışmayın.

### <a name="example"></a>Örnek

```cpp
// basic_streambuf_sungetc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ifstream myfile( "basic_streambuf_sungetc.txt", ios::in );

   // Read and increment
   int i = myfile.rdbuf( )->sbumpc( );
   cout << ( char )i << endl;

   // Read and increment
   i = myfile.rdbuf( )->sbumpc( );
   cout << ( char )i << endl;

   // Decrement, read, and do not increment
   i = myfile.rdbuf( )->sungetc( );
   cout << ( char )i << endl;

   i = myfile.rdbuf( )->sungetc( );
   cout << ( char )i << endl;

   i = myfile.rdbuf( )->sbumpc( );
   cout << ( char )i << endl;
}
```

## <a name="basic_streambufswap"></a><a name="swap"></a>basic_streambuf::takas

Sağlanan `basic_streambuf` nesnedeki değerler için bu nesnedeki değerleri değiştirir.

```cpp
void swap(basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Doğru*|Değer alışverişi `basic_streambuf` için kullanılan nesneye bir lvalue başvurusu.|

### <a name="remarks"></a>Açıklamalar

Korunan üye işlev, *doğru* tüm işaretçileri `input buffer` ve `output buffer`. Ayrıca `right.` [getloc()](#getloc) nesne ile `locale` alışverişi.

## <a name="basic_streambufsync"></a><a name="sync"></a>basic_streambuf::senkronize

Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışan korumalı bir sanal işlev.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, -1 döndürür. Varsayılan davranış sıfır dönmektir.

### <a name="remarks"></a>Açıklamalar

`sync`çıktı arabelleği için başlangıç ve sonraki işaretçiler arasında herhangi bir öğe yazma içerir. Bu giriş arabellek için sonraki ve bitiş işaretçileri arasında herhangi bir öğe geri koyarak içermez.

## <a name="basic_streambuftraits_type"></a><a name="traits_type"></a>basic_streambuf::traits_type

Bir tür adını **Tr** şablon parametresi ile ilişkilendirer.

```cpp
typedef Tr traits_type;
```

## <a name="basic_streambufuflow"></a><a name="uflow"></a>basic_streambuf::uflow

Giriş akışından geçerli öğeyi ayıklayan korumalı bir sanal işlev.

```cpp
virtual int_type uflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş akışından geçerli öğe **ch** ayıklamak için çalışır, sonra geçerli akış konumunu ilerletmek ve traits_type olarak öğeyi döndürün:: **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **ch).** Bunu çeşitli şekillerde yapabilirsiniz:

- Okuma konumu varsa, okuma konumunda depolanan öğe olarak **ch** alır ve giriş arabelleği için bir sonraki işaretçiyi ilerler.

- Bir öğeyi doğrudan, bazı dış kaynaktan okuyabilir ve değeri **ch**olarak teslim edebilir.

- Ortak giriş ve çıktı akışlarına sahip bir akış arabelleği için, çıktı arabelleği için başlangıç ve sonraki işaretçiler arasındaki öğelerin bazılarını veya tümlerini bazı dış hedefe, bazı dış hedefe yazarak okuma konumunu kullanılabilir hale getirebilir. Veya giriş arabelleği için yeni veya ek depolama alanı tahsis edebilir. İşlev daha sonra, bazı dış kaynaktan, bir veya daha fazla öğe okur.

İşlev başarılı olamazsa, **traits_type**döndürür:[eof](../standard-library/char-traits-struct.md#eof), ya da bir özel durum atar. Aksi takdirde, yukarıda `ch` açıklandığı gibi dönüştürülen giriş akışındaki geçerli öğeyi döndürür ve giriş arabelleği için bir sonraki işaretçiyi ilerler. Varsayılan [davranış, akış azlığı](#underflow) aramak ve bu işlev traits_type dönerse::eof , **traits_type::eof** **traits_type::eof**. Aksi takdirde, işlev giriş akışındaki geçerli öğe **ch'yi** daha önce açıklandığı gibi dönüştürülür ve giriş arabelleği için bir sonraki işaretçiyi ilerler.

## <a name="basic_streambufunderflow"></a><a name="underflow"></a>basic_streambuf::underflow

Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi, geçerli akış konumunu ilerletmeden geçerli öğe **yi** giriş akışından ayıklamak ve `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type) **(ch)** olarak döndürmek için çaba göstermektedir. Bunu çeşitli şekillerde yapabilirsiniz:

- Okuma konumu varsa, **ch** okuma konumunda depolanan öğedir. Bu konuda daha fazla bilgi için [basic_streambuf Sınıfı'nın](../standard-library/basic-streambuf-class.md)Açıklamalar bölümüne bakın.

- Giriş arabelleği için yeni veya ek depolama alanı ayırarak, daha sonra bazı dış kaynaktan, bir veya daha fazla öğeden okuma yaparak okuma konumunu kullanılabilir hale getirebilir. Bu konuda daha fazla bilgi için [basic_streambuf Sınıfı'nın](../standard-library/basic-streambuf-class.md)Açıklamalar bölümüne bakın.

İşlev başarılı `traits_type::` [olamazsa, eof](../standard-library/char-traits-struct.md#eof) `()` döndürür veya bir özel durum atar. Aksi takdirde, giriş akışındaki geçerli öğeyi, daha önce açıklandığı gibi dönüştürülür. Varsayılan davranış döndürmektir. `traits_type::eof()`

Eşitleme `underflow` ve [taşma](#overflow) işlevleriyle sanal işlev, `streambuf`türetilmiş sınıfın özelliklerini tanımlar. [sync](#sync) Türetilen her `underflow` sınıf farklı şekilde uygulanabilir, ancak arama akışı sınıfıyla arabirim aynıdır.

`underflow` İşlev en sık alma `streambuf` alanı boşolduğunda [sgetc](#sgetc) ve [sgetn](#sgetn) gibi ortak işlevler tarafından çağrılır, `underflow` ancak akış sınıfları da dahil olmak üzere diğer sınıflar her zaman arayabilir.

İşlev, `underflow` giriş kaynağından gelen karakterlerle alma alanını sağlar. Alma alanı karakterler içeriyorsa, `underflow` ilk karakteri döndürür. Alma alanı boşsa, alma alanını doldurur ve bir sonraki karakteri döndürür (alma alanında bırakır). Başka karakter yoksa, `underflow` döndürür `EOF` ve alma alanını boş bırakır.

`strstreambuf` Sınıfta, `underflow` [egptr](#egptr) işaretçisini dinamik olarak bir çağrı ile ayrılan depolamaya erişmek için `overflow`ayarlar.

## <a name="basic_streambufxsgetn"></a><a name="xsgetn"></a>basic_streambuf::xsgetn

Giriş akışından öğeleri ayıklamak için korumalı, sanal işlev.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir.

```cpp
virtual streamsize xsgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Çıkarılan karakterleri içerecek arabellek.

*Sayısı*\
Ayıklamak için öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Çıkarılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, [sbumpc](#sbumpc)için tekrarlanan çağrılar gibi, giriş akışından öğeleri *saymak* için kadar ayıklar ve *ptr*başlayan dizi depolar. Ayıklanan öğelerin sayısını döndürür.

## <a name="basic_streambufxsputn"></a><a name="xsputn"></a>basic_streambuf::xsputn

Öğeleri çıkış akışına eklemek için korumalı, sanal işlev.

```cpp
virtual streamsize xsputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Eklenecek öğeleriçin işaretçi.

*Sayısı*\
Eklenecek öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Akışa eklenen öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi, *ptr'den*başlayan diziden, [sputc'a](#sputc)tekrarlanan çağrılar gibi öğeleri çıkış akışına *saymak* için ekler. Tüm *sayım* karakterleri yazıldıktan veya çağrı `sputc( count)` döndürülecekse, `traits::eof()`karakterlerin çıkış akışına eklenmesi durur. Aslında eklenen öğelerin sayısını döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
