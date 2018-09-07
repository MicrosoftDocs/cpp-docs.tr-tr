---
title: basic_streambuf sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bc4fa8da5d9fa2d15febc3c7b016622e614129a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100969"
---
# <a name="basicstreambuf-class"></a>basic_streambuf Sınıfı

Belirli bir gösterimiyse bir akış, gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin türetmek için Özet temel sınıf tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_streambuf;
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
A [char_type](#char_type).

*tr*<br/>
Karakter [traits_type](#traits_type).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, belirli bir gösterimiyse bir akış, gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin türetmek için Özet temel sınıf tanımlar. Sınıfın bir nesnesi `basic_streambuf` yardımcı denetim türünde öğelere sahip bir akış *Tr*olarak da bilinen [char_type](#char_type), olan karakter nitelikleri sınıfı tarafından belirlenen [char_traits](../standard-library/char-traits-struct.md)olarak da bilinen [traits_type](#traits_type).

Her akış arabelleği kavramsal olarak iki bağımsız akışları denetler: ayıklamalar (giriş) için diğeri eklemeler (çıkış) için. Belirli bir gösterimiyse ancak, bu akışlardan ya da erişilemez olmasına neden olabilir. Genellikle, iki akışları arasında bazı ilişki tutar. Çıkış akışına eklediğiniz bir [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`> Örneğin, nesnesidir ne, daha sonra giriş akışından ayıklar. Bir akışı konumlandırma ne zaman bir [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> Nesne, diğer akış dağıtımınızla getirin.

Şablon sınıfı ortak arabiriminin `basic_streambuf` ancak özelleştirilmiş tüm akış arabellekleri için ortak olan işlemler sağlar. Korumalı kullanıcı arabirimi, işlemini gerçekleştirmek için belirli bir gösterimi bir akış için gereken işlemleri sağlar. Korumalı sanal üye işlevleri, bir türetilmiş akış arabelleği için bir akış belirli bir gösterimiyse davranışını uyumlu hale getirmenizi sağlar. Her türetilmiş akış arabelleği bu kitaplıktaki korumalı sanal üye işlevleri davranışını nasıl konusunda uzmanlaşmış açıklar. Genellikle olduğundan, hiçbir şey yapma, temel sınıfı için varsayılan davranış, bu konuda açıklanmıştır.

Kalan üye işlevleri denetimi ve arabellek istemcileriniz için sağlanan herhangi bir depolama alanı ve akışları kopyalamak korumalı. Örneğin, bir giriş arabellek, tarafından belirlenir:

- [eback](#eback), arabelleğin başına bir işaretçi.

- [gptr](#gptr), okunacak sonraki öğeye bir işaretçi.

- [egptr](#egptr), yalnızca arabellek bitişini geçen bir işaretçi.

Benzer şekilde, bir çıkış arabelleği tarafından belirlenir:

- [pbase](#pbase), arabelleğin başına bir işaretçi.

- [pptr](#pptr), yazmak için sonraki öğeye bir işaretçi.

- [epptr](#epptr), yalnızca arabellek bitişini geçen bir işaretçi.

Herhangi bir arabellek için aşağıdaki protokolü kullanılır:

- Sonraki işaretçisi, null ise, hiçbir arabellek bulunmaktadır. Aksi takdirde, tüm üç işaretçi aynı dizi gelin. Sipariş için güvenli bir şekilde karşılaştırılabilir.

- Sonraki işaretçisi son işaretçi sayısından az karşılaştırırsa, bir çıkış arabelleği için sonraki işaretçisi tarafından belirlenen yazma konumunda bir öğe depolayabilirsiniz.

- Sonraki işaretçisi son işaretçi sayısından az karşılaştırırsa, bir giriş arabellek için sonraki işaretçisi tarafından belirlenen okuma konumunda bir öğe okuyabilirsiniz.

- Başlangıç işaretçisi sonraki işaretçisi sayısından az karşılaştırırsa bir giriş arabellek için geri öğenin indirildiği sonraki işaretçisi tarafından belirlenen putback konumunda koyabilirsiniz.

Herhangi bir sanal üye işlev öğesinden türetilmiş bir sınıf için yazma korumalı `basic_streambuf` <  `Elem`, `Tr`> Bu protokolü sürdürmeye işbirliği gerekir.

Sınıfın bir nesnesi `basic_streambuf` <  `Elem`, `Tr`> daha önce açıklanan altı işaretçileri depolar. Ayrıca türünde bir nesne bir yerel ayar nesnesini depolar [yerel ayar](../standard-library/locale-class.md) olası kullanımına türetilmiş akış arabelleği.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_streambuf](#basic_streambuf)|Türünde bir nesne oluşturur `basic_streambuf`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adıyla ilişkilendirir `Elem` şablon parametresi.|
|[int_type](#int_type)|İçinde bir tür adını ilişkilendirir `basic_streambuf` ile kapsam `Elem` şablon parametresi.|
|[off_type](#off_type)|İçinde bir tür adını ilişkilendirir `basic_streambuf` ile kapsam `Elem` şablon parametresi.|
|[pos_type](#pos_type)|İçinde bir tür adını ilişkilendirir `basic_streambuf` ile kapsam `Elem` şablon parametresi.|
|[traits_type](#traits_type)|Bir tür adıyla ilişkilendirir `Tr` şablon parametresi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[eback](#eback)|Bir korumalı işlev giriş arabelleği başlangıcına bir işaretçi döndürür.|
|[egptr](#egptr)|Bir korumalı işlevi yalnızca giriş arabelleği sonunu geçen bir işaretçi döndürür.|
|[epptr](#epptr)|Bir korumalı işlevi yalnızca çıkış arabelleği sonunu geçen bir işaretçi döndürür.|
|[gbump](#gbump)|Ekleyen korumalı işlevi `count` için giriş arabelleği için sonraki işaretçisi.|
|[getloc](#getloc)|Alır `basic_streambuf` nesnenin yerel ayar.|
|[gptr](#gptr)|Bir korumalı işlev giriş arabelleği sonraki öğeye bir işaretçi döndürür.|
|[imbue](#imbue)|Korumalı, çağrılan sanal işlev [pubimbue](#pubimbue).|
|[in_avail](#in_avail)|Arabellekteki okumak hazır olan öğelerin sayısını döndürür.|
|[taşma](#overflow)|Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Bir öğe giriş akışa geri koymak çalışır bir korumalı sanal üye işlevi ardından sunun (sonraki işaretçisi tarafından işaret edilen) geçerli öğe.|
|[pbase](#pbase)|Çıkış arabelleği başlangıcına bir işaretçi döndüren korumalı bir işlev.|
|[pbump](#pbump)|Ekleyen korumalı işlevi `count` çıkış arabelleği için sonraki işaretçisi için.|
|[pptr](#pptr)|Çıkış arabelleği sonraki öğeye bir işaretçi döndüren korumalı bir işlev.|
|[pubimbue](#pubimbue)|Kümeleri `basic_streambuf` nesnenin yerel ayar.|
|[pubseekoff](#pubseekoff)|Çağrıları [seekoff](#seekoff), korumalı türetilen bir sınıfta geçersiz kılınmış sanal işlev.|
|[pubseekpos](#pubseekpos)|Çağrıları [seekpos](#seekpos), korunan sanal işlev türetilen bir sınıfta geçersiz kılınır ve geçerli işaretçisi konumuna sıfırlar.|
|[pubsetbuf](#pubsetbuf)|Çağrıları [setbuf](#setbuf), korumalı türetilen bir sınıfta geçersiz kılınmış sanal işlev.|
|[pubsync](#pubsync)|Çağrıları [eşitleme](#sync), korunan sanal işlev türetilen bir sınıfta geçersiz kılınır ve bu arabellek ile ilişkili dış akış güncelleştirir.|
|[sbumpc](#sbumpc)|Okur ve taşıma akış işaretçisini geçerli öğeye döndürür.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi her türetilmiş akış arabelleği için bir işlemi belirli gerçekleştirir.|
|[setg](#setg)|Depolayan bir korumalı işlevi `_Gbeg` başlangıç işaretçisi olarak `_Gnext` sonraki işaretçisi olarak ve `_Gend` içinde giriş arabelleği sonu işaretçisi.|
|[setp](#setp)|Depolayan bir korumalı işlevi `_Pbeg` başlangıç işaretçisi olarak ve `_Pend` içinde çıkış arabelleği sonu işaretçisi.|
|[sgetc](#sgetc)|Geçerli öğe akışta konumu değiştirmeden döndürür.|
|[sgetn](#sgetn)|Okuma öğelerin sayısını döndürür.|
|[showmanyc](#showmanyc)|Korumalı sanal üye işlevi, giriş akışından ayıklanabileceği ve program belirsiz bir bekleme tabi olmayacağı olun karakter sayısını döndürür.|
|[snextc](#snextc)|Geçerli öğe okur ve aşağıdaki öğeyi döndürür.|
|[sputbackc](#sputbackc)|Koyar bir `char_type` akış.|
|[sputc](#sputc)|Bir karakter akışı halinde yerleştirir.|
|[sputn](#sputn)|Akışa bir karakter dizesi koyar.|
|[stossc](#stossc)|Akıştaki geçerli öğe geçmiş taşıyın.|
|[sungetc](#sungetc)|Bir karakter akıştan alır.|
|[değiştirme](#swap)|Bu nesne için sağlanan değerler değerleri değiştirir `basic_streambuf` parametresi nesne.|
|[Eşitleme](#sync)|Denetlenen akışları ilişkili herhangi bir dış akışlarla eşitlemeye çalışır korumalı bir sanal işlev.|
|[uflow](#uflow)|Geçerli öğe girdi akışından ayıklar korumalı bir sanal işlev.|
|[yetersiz kalması](#underflow)|Geçerli öğe girdi akışından ayıklar korumalı bir sanal işlev.|
|[xsgetn](#xsgetn)|Öğeleri girdi akışından ayıklar korumalı bir sanal işlev.|
|[xsputn](#xsputn)|Öğe çıkış akışına ekler; korumalı bir sanal işlev.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu nesnenin değerlerini birbirinden atar `basic_streambuf` nesne.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<streambuf >

**Namespace:** std

## <a name="basic_streambuf"></a>  basic_streambuf::basic_streambuf

Türünde bir nesne oluşturur `basic_streambuf`.

```cpp
basic_streambuf();

basic_streambuf(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir lvalue başvurusuna `basic_streambuf` bu değerleri ayarlamak için kullanılan nesne `basic_streambuf` nesne.

### <a name="remarks"></a>Açıklamalar

İlk korumalı Oluşturucu tüm işaretçilerin giriş arabelleği ve çıkış arabelleği denetleme null bir işaretçi depolar. Ayrıca depolar `locale::classic` yerel ayar nesnesi içinde. Daha fazla bilgi için [locale::classic](../standard-library/locale-class.md#classic).

İşaretçiler ve yerel ayardan ikinci korumalı Oluşturucu kopyalar *doğru*.

## <a name="char_type"></a>  basic_streambuf::char_type

Bir tür adıyla ilişkilendirir **Elem** şablon parametresi.

```cpp
typedef Elem char_type;
```

## <a name="eback"></a>  basic_streambuf::eback

Bir korumalı işlev giriş arabelleği başlangıcına bir işaretçi döndürür.

```cpp
char_type *eback() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği başlangıcına bir işaretçi.

## <a name="egptr"></a>  basic_streambuf::egptr

Bir korumalı işlevi yalnızca giriş arabelleği sonunu geçen bir işaretçi döndürür.

```cpp
char_type *egptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca giriş arabelleği sonunu geçen bir işaretçi.

## <a name="epptr"></a>  basic_streambuf::epptr

Bir korumalı işlevi yalnızca çıkış arabelleği sonunu geçen bir işaretçi döndürür.

```cpp
char_type *epptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca çıkış arabelleği sonunu geçen bir işaretçi.

## <a name="gbump"></a>  basic_streambuf::gbump

Ekleyen korumalı işlevi *sayısı* için giriş arabelleği için sonraki işaretçisi.

```cpp
void gbump(int count);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Tutarı işaretçi ilerleyin.

## <a name="getloc"></a>  basic_streambuf::getloc

Basic_streambuf nesnenin yerel alır.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için bkz. [ios_base::getloc](../standard-library/ios-base-class.md#getloc).

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

## <a name="gptr"></a>  basic_streambuf::gptr

Bir korumalı işlev giriş arabelleği sonraki öğeye bir işaretçi döndürür.

```cpp
char_type *gptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği sonraki öğeye bir işaretçi.

## <a name="imbue"></a>  basic_streambuf::imbue

Korumalı sanal işlevi çağıran [pubimbue](#pubimbue).

```cpp
virtual void imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*<br/>
Bir yerel ayar için bir başvuru.

### <a name="remarks"></a>Açıklamalar

Hiçbir şey yapmamak için varsayılan davranıştır.

## <a name="in_avail"></a>  basic_streambuf::in_avail

Arabellekteki okumak hazır olan öğelerin sayısını döndürür.

```cpp
streamsize in_avail();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekteki okumak hazır olan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Varsa bir [okuyun konum](../standard-library/basic-streambuf-class.md) üye işlevinin döndürdüğü kullanılabilir [egptr](#egptr) - [gptr](#gptr). Aksi halde [showmanyc](#showmanyc).

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

## <a name="int_type"></a>  basic_streambuf::int_type

Basic_streambuf kapsam içinde bir tür adı, bir şablon parametresi türlerini ilişkilendirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="off_type"></a>  basic_streambuf::off_type

Basic_streambuf kapsam içinde bir tür adı, bir şablon parametresi türlerini ilişkilendirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="op_eq"></a>  basic_streambuf::operator =

Bu nesnenin değerlerini birbirinden atar `basic_streambuf` nesne.

```cpp
basic_streambuf& operator=(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir lvalue başvurusuna `basic_streambuf` değerleri bu nesneye atamak için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işleci alanından kopyalar *doğru* giriş arabelleği ve çıkış arabelleği kontrol işaretçileri. Ayrıca depolar `right.` [getloc()](#getloc) içinde `locale object`. Döndürür `*this`.

## <a name="overflow"></a>  basic_streambuf::Overflow

Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür **traits_type::eof** veya bir özel durum oluşturur. Aksi halde **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*). Döndürülecek varsayılan davranıştır **traits_type::eof**.

### <a name="remarks"></a>Açıklamalar

_ *Meta* eşit karşılaştırmaz **traits_type::eof**, korumalı sanal üye işlevi endeavors öğe eklemek **traits_type::**[ile_ char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) çıkış akışına içine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Varsa bir `write position` olan kullanılabilir, bu öğe yazma konumuna depolayabilir ve çıkış arabelleği için sonraki işaretçisine artırılacak.

- Çıkış arabelleği için yeni veya ek depolama alanı ayırarak bunu yazma konumunu kullanılabilir duruma getirebilirsiniz.

- Bu yazma konumunu kullanılabilir tarafından kullanıma, dış bazı hedef, bazı veya tüm öğeleri arasında başına yazmayı ve sonraki işaretçileri çıkış arabelleği için yapabilirsiniz.

İle birlikte sanal taşma işlevi [eşitleme](#sync) ve [underflow](#underflow) İşlevler, streambuf türetilmiş sınıf özelliklerini tanımlayan. Her bir türetilmiş sınıf taşma farklı uygulayabilir, ancak arabirim çağıran stream sınıfı ile aynıdır.

`overflow` Genel tarafından en sık çağrıldığında `streambuf` gibi işlev `sputc` ve `sputn` zaman put alanı dolu olduğundan, ancak stream sınıfları da dahil olmak üzere, diğer sınıflar çağırabilirsiniz `overflow` zaman.

İşlev karakter arasında bir yerleştirme alanında tüketir `pbase` ve `pptr` işaretçileri ve sonra put alan yeniden başlatır. `overflow` İşlevi gerekir ayrıca tüketen `nCh` (varsa `nCh` değil `EOF`), veya sonraki çağrıda tüketilir şekilde karakter yeni alan yerleştirmek koymak isteyebilirsiniz.

Tüket tanımını türetilmiş sınıflar arasında değişir. Örneğin, `filebuf` sınıfı, karakter bir dosyaya yazar while `strstreambuf` sınıfı bunları kendi arabellekte tutar ve arabellek taşmasına çağrısına (arabellek dinamik olarak belirlendiyse) genişletir. Bu genişleme eski arabellek boşaltma ve yeni, daha büyük bir tane ile değiştirerek elde edilir. İşaretçileri gerektiğinde ayarlanır.

## <a name="pbackfail"></a>  basic_streambuf::pbackfail

Bir öğe giriş akışa geri koymak çalışır bir korumalı sanal üye işlevi ardından sunun (sonraki işaretçisi tarafından işaret edilen) geçerli öğe.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür **traits_type::eof** veya bir özel durum oluşturur. Aksi takdirde, başka bir değer döndürür. Döndürülecek varsayılan davranıştır **traits_type::eof**.

### <a name="remarks"></a>Açıklamalar

_ *Meta* karşılaştırır eşit **traits_type::eof**, geri göndermek için etkili bir şekilde akış önce geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğe tarafından değiştirilir **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*). İşlevi, öğenin çeşitli yollarla geri koyabilirsiniz:

- Putback konumu varsa, bu öğe putback konumda depolamak ve sonraki işaretçisi giriş arabelleği için azaltma.

- Giriş arabelleği için yeni veya ek depolama alanı ayırarak bu putback konum kullanılabilir hale getirebilirsiniz.

- Bir akış arabelleği için ortak bir giriş ve çıkış akışları, putback konum kullanılabilir tarafından kullanıma, dış bazı hedef, bazı veya tüm öğeleri arasında başına yazmayı ve sonraki işaretçileri çıkış arabelleği için zorlaştırabilir.

## <a name="pbase"></a>  basic_streambuf::pbase

Çıkış arabelleği başlangıcına bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pbase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış arabelleği başlangıcına bir işaretçi.

## <a name="pbump"></a>  basic_streambuf::pbump

Ekleyen korumalı işlevi *sayısı* çıkış arabelleği için sonraki işaretçisi için.

```cpp
void pbump(int count);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Yazma konumunu ilerlemek karakter sayısı.

## <a name="pos_type"></a>  basic_streambuf::pos_type

Basic_streambuf kapsam içinde bir tür adı, bir şablon parametresi türlerini ilişkilendirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="pptr"></a>  basic_streambuf::pptr

Çıkış arabelleği sonraki öğeye bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış arabelleği sonraki öğeye bir işaretçi.

## <a name="pubimbue"></a>  basic_streambuf::pubimbue

Basic_streambuf nesnenin yerel ayarlar.

```cpp
locale pubimbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*<br/>
Bir yerel ayar için bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yerel ayar nesnesinde depolanan önceki değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, _ depolar *Loc* çağrıları ve yerel ayar nesnesi [imbue](#imbue).

### <a name="example"></a>Örnek

Bkz: [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue) kullanan bir örnek için `pubimbue`.

## <a name="pubseekoff"></a>  basic_streambuf::pubseekoff

Çağrıları [seekoff](#seekoff), korumalı türetilen bir sınıfta geçersiz kılınmış sanal işlev.

```cpp
pos_type pubseekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Arama için göreli konumunu *_Way*.

*_Way*<br/>
İşlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) için olası değerler.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumunu döndürür ( [seekoff](#seekoff)(_ *kapalı*, `_Way`, `_Which`)).

### <a name="remarks"></a>Açıklamalar

İşaretçi göreli olarak hareket *_Way*.

## <a name="pubseekpos"></a>  basic_streambuf::pubseekpos

Çağrıları [seekpos](#seekpos), korunan sanal işlev türetilen bir sınıfta geçersiz kılınır ve geçerli işaretçisi konumuna sıfırlar.

```cpp
pos_type pubseekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*<br/>
Arama konumu.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumu. Akış konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırmak `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [seekpos](#seekpos)(_ *Sp*, `_Which`).

## <a name="pubsetbuf"></a>  basic_streambuf::pubsetbuf

Çağrıları [setbuf](#setbuf), korumalı türetilen bir sınıfta geçersiz kılınmış sanal işlev.

```cpp
basic_streambuf<Elem, Tr> *pubsetbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*<br/>
Bir işaretçi `char_type` bu örneklemesi için.

*Sayısı*<br/>
Arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Döndürür [setbuf](#setbuf)( `_Buffer`, `count`).

## <a name="pubsync"></a>  basic_streambuf::pubsync

Çağrıları [eşitleme](#sync), korunan sanal işlev türetilen bir sınıfta geçersiz kılınır ve bu arabellek ile ilişkili dış akış güncelleştirir.

```cpp
int pubsync();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür [eşitleme](#sync) veya -1 hata.

## <a name="sbumpc"></a>  basic_streambuf::sbumpc

Okur ve taşıma akış işaretçisini geçerli öğeye döndürür.

```cpp
int_type sbumpc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Okuma konumuna kullanılabilir değilse, üye işlevi döndürür **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( <strong>\*</strong> [gptr](#gptr)) ve giriş arabelleği için sonraki işaretçisi artırır. Aksi halde [uflow](#uflow).

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

```Output

3

```

```Output

      33
51
```

## <a name="seekoff"></a>  basic_streambuf::seekoff

Denetlenen akışlar için geçerli konumları alter dener ve korumalı sanal üye işlevi.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Arama için göreli konumunu *_Way*.

*_Way*<br/>
İşlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) için olası değerler.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumunu döndürür ( `seekoff` (_ *kapalı*, `_Way`, `_Which`)).

### <a name="remarks"></a>Açıklamalar

Yeni konumu şu şekilde belirlenir:

- Varsa `_Way`  ==  `ios_base::beg`, yeni konuma stream yanı sıra _ başlangıcıdır *kapalı*.

- Varsa `_Way`  ==  `ios_base::cur`, yeni geçerli akış konumu artı _ konumdur *kapalı*.

- Varsa `_Way`  ==  `ios_base::end`, akış ve _ sonuna yeni konumudur *kapalı*.

Genellikle, **hangi & ios_base::in** olan sıfır olmayan, Giriş akışı etkilenir ve **hangi & ios_base::out** olan sıfır olmayan, çıkış akışına etkilenir. Bu parametrenin gerçek kullanım ancak türetilmiş akış arabellekleri arasında farklılık gösterir.

Akış konum veya konumlarını değiştirme işlev başarılı olursa, akış konumu veya elde edilen akışı konumları birini döndürür. Aksi takdirde geçersiz akış konumu döndürür. Geçersiz akış konumu döndürmek için varsayılan davranıştır.

## <a name="seekpos"></a>  basic_streambuf::seekpos

Denetlenen akışlar için geçerli konumları alter dener ve korumalı sanal üye işlevi.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*<br/>
Arama konumu.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

Yeni konumunu veya geçersiz akış konumu. Akış konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırmak `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Yeni konumudur _ *Sp*.

Genellikle, **hangi & ios_base::in** olan sıfır olmayan, Giriş akışı etkilenir ve **hangi & ios_base::out** olan sıfır olmayan, çıkış akışına etkilenir. Bu parametrenin gerçek kullanım ancak türetilmiş akış arabellekleri arasında farklılık gösterir.

Akış konum veya konumlarını değiştirme işlev başarılı olursa, akış konumu veya elde edilen akışı konumları birini döndürür. Aksi takdirde, bir geçersiz akış konumu (-1) döndürür. Geçersiz akış konumu döndürmek için varsayılan davranıştır.

## <a name="setbuf"></a>  basic_streambuf::setbuf

Her türetilmiş akış arabelleği için bir işlemi belirli gerçekleştiren bir korumalı sanal üye işlevi.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*<br/>
Arabellek için işaretçi.

*Sayısı*<br/>
Arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Döndürülecek varsayılan davranıştır **bu**.

### <a name="remarks"></a>Açıklamalar

Bkz: [basic_filebuf](../standard-library/basic-filebuf-class.md). `setbuf` bir alan için bellek sunar `streambuf` kullanılacak nesne. Arabellek nasıl kullanıldığına türetilmiş sınıflarda tanımlanır.

## <a name="setg"></a>  basic_streambuf::setg

_ Depolayan bir korumalı işlevi *Gbeg* başlangıç işaretçisi olarak `_Gnext` sonraki işaretçisi olarak ve `_Gend` içinde giriş arabelleği sonu işaretçisi.

```cpp
void setg(char_type* _Gbeg,
    char_type* _Gnext,
    char_type* _Gend);
```

### <a name="parameters"></a>Parametreler

*_Gbeg*<br/>
Arabelleğin başına bir işaretçi.

*_Gnext*<br/>
Yere bir işaretçi arabellek ortasında.

*_Gend*<br/>
Arabelleğin sonuna bir işaretçi.

## <a name="setp"></a>  basic_streambuf::setp

Depolayan bir korumalı işlevi *_Pbeg* başlangıç işaretçisi olarak ve *_Pend* içinde çıkış arabelleği sonu işaretçisi.

```cpp
void setp(char_type* _Pbeg, char_type* _Pend);
```

### <a name="parameters"></a>Parametreler

*_Pbeg*<br/>
Arabelleğin başına bir işaretçi.

*_Pend*<br/>
Arabelleğin sonuna bir işaretçi.

## <a name="sgetc"></a>  basic_streambuf::sgetc

Geçerli öğe akışta konumu değiştirmeden döndürür.

```cpp
int_type sgetc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Okuma konumuna kullanılabilir değilse, üye işlevi döndürür **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `*` [gptr](#gptr)). Aksi halde [underflow](#underflow).

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

## <a name="sgetn"></a>  basic_streambuf::sgetn

En fazla ayıklar *sayısı* karakterler giriş ara bellekten ve sağlanan arabelleğinde depolar *ptr*.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan olmasına olduğundan bu güvensiz olabilecek bir yöntemdir.

```cpp
streamsize sgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Ayıklanan karakterleri içeren arabellek.

*Sayısı*<br/>
Okunacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını okuyun. Bkz: [streamsize](../standard-library/ios-typedefs.md#streamsize) daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [xsgetn](#xsgetn)( `ptr`, `count`).

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

## <a name="showmanyc"></a>  basic_streambuf::showmanyc

Girdi akışından ayıklanabileceği ve program belirsiz bir bekleme tabi olmayacağı olun karakter sayısını döndüren bir korumalı sanal üye işlevi.

```cpp
virtual streamsize showmanyc();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürülecek varsayılan davranışıdır.

## <a name="snextc"></a>  basic_streambuf::snextc

Geçerli öğe okur ve aşağıdaki öğeyi döndürür.

```cpp
int_type snextc();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki sonraki öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [sbumpc](#sbumpc) ve bu işlev döndürürse **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), döndürür **traits_type::eof**. Aksi halde [sgetc](#sgetc).

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

```Output

aa

```

```Output

aa97
```

## <a name="sputbackc"></a>  basic_streambuf::sputbackc

Stream'de bir char_type koyar.

```cpp
int_type sputbackc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*<br/>
Karakter.

### <a name="return-value"></a>Dönüş Değeri

Bir karakter ya da hata verir.

### <a name="remarks"></a>Açıklamalar

Putback konumu varsa ve *_Ch* karşılaştırır sonraki işaretçiyi döndürür ve giriş arabelleği için üye işlevi azaltır, bu konumda depolanan bir karaktere eşit **traits_type::** [ to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `_Ch`). Aksi halde [pbackfail](#pbackfail)( `_Ch`).

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

## <a name="sputc"></a>  basic_streambuf::sputc

Bir karakter akışı halinde yerleştirir.

```cpp
int_type sputc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*<br/>
Karakter.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa karakteri döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa bir `write position` , kullanılabilir üye işlevi depoları *_Ch* çıkış arabelleği için sonraki işaretçisi yazma konumu artırır ve döndürür **traits_type::**[to_int_type ](../standard-library/char-traits-struct.md#to_int_type)( `_Ch`). Aksi halde [taşma](#overflow)( `_Ch`).

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

## <a name="sputn"></a>  basic_streambuf::sputn

Akışa bir karakter dizesi koyar.

```cpp
streamsize sputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Karakter dizesi.

*Sayısı*<br/>
Karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Aslında akışa eklenen karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [xsputn](#xsputn)( `ptr`, `count`). Daha fazla bilgi için bu üyeye ilişkin açıklamalar bölümüne bakın.

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

## <a name="stossc"></a>  basic_streambuf::stossc

Akıştaki geçerli öğe geçmiş taşıyın.

```cpp
void stossc();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [sbumpc](#sbumpc). Bir uygulama olmadığına dikkat edin, bu üye işlevi sağlamak için gereklidir.

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

## <a name="sungetc"></a>  basic_streambuf::sungetc

Bir karakter akıştan alır.

```cpp
int_type sungetc();
```

### <a name="return-value"></a>Dönüş Değeri

Karakter ya da hata döndürür.

### <a name="remarks"></a>Açıklamalar

Üye putback konumu varsa, döndürür ve giriş arabelleği için sonraki işaretçisi azaltır işlev `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `*` [gptr](#gptr)). Ancak, her zaman geçerli arabelleğini durumda yakalanabilir böylece son karakter okuma belirlemek mümkün değildir. Bu durum geçerlidir sonra işlevi döndürür [pbackfail](#pbackfail). Bu durumu önlemek için yeniden yerleştirin ve çağırmak için karakter izlemek `sputbackc(ch)`, sağlanan başarısız olmasına neden olmaz, bu akış, başında çağırmaz ve birden fazla karakter geri koymak çalışmayın.

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

## <a name="swap"></a>  basic_streambuf::Swap

Bu nesne için sağlanan değerler değerleri değiştirir `basic_streambuf` nesne.

```cpp
void swap(basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Bir lvalue başvurusuna `basic_streambuf` değerleri değişimi için kullanılan nesne.|

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi değiştirir ile *doğru* denetleme işaretçileri `input buffer` ve `output buffer`. Ayrıca birbiriyle değiştirir `right.` [getloc()](#getloc) ile `locale` nesne.

## <a name="sync"></a>  basic_streambuf::Sync

Denetlenen akışları ilişkili herhangi bir dış akışlarla eşitlemeye çalışır korumalı bir sanal işlev.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı ise -1 döndürür. Sıfır döndürülecek varsayılan davranışıdır.

### <a name="remarks"></a>Açıklamalar

`sync` çıkış arabelleği için başlangıç ve sonraki işaretçileri arasında herhangi bir öğe kullanıma yazma içerir. Sonraki arasında herhangi bir öğe geri yerleştirme içermeyen ve son giriş arabellek için işaretçi.

## <a name="traits_type"></a>  basic_streambuf::traits_type

Bir tür adıyla ilişkilendirir **Tr** şablon parametresi.

```cpp
typedef Tr traits_type;
```

## <a name="uflow"></a>  basic_streambuf::uflow

Geçerli öğe girdi akışından ayıklar korumalı bir sanal işlev.

```cpp
virtual int_type uflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, geçerli öğe ayıklamak dener **ch** giriş akışından sonra geçerli stream konumuna ilerleyin ve öğenin iade **traits_type::** [ to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **ch**). Bunu çeşitli yöntemlerle yapabilirsiniz:

- Okuma konumuna kullanılabilir haldeyse, sürdüğünü **ch** öğesi salt okunur bir konumda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

- Bir öğeyi doğrudan, bir dış kaynaktan okumak ve değeri olarak teslim **ch**.

- Ortak bir giriş ve çıkış akışları ile bir akış arabelleği için bir okuma konumuna kullanılabilir tarafından kullanıma, dış bazı hedef, bazı veya tüm öğeleri arasında başına yazmayı ve sonraki işaretçileri çıkış arabelleği için zorlaştırabilir. Veya yeni veya ek depolama için giriş arabelleği ayırabilirsiniz. İşlev daha sonra bir dış kaynaktan bir veya daha fazla öğe okur.

İşlev başarılı olursa, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), veya bir özel durum oluşturur. Aksi takdirde, geçerli öğe döndürür `ch` yukarıda açıklandığı gibi giriş akışında dönüştürülür ve giriş arabelleği için sonraki işaretçisi ilerler. Çağırmak için varsayılan davranıştır [underflow](#underflow) ve bu işlev döndürürse **traits_type::eof**döndürülmesini **traits_type::eof**. Aksi halde, işlev geçerli öğeyi döndürür **ch** giriş akışında dönüştürülür daha önce açıklandığı gibi ve giriş arabelleği için sonraki işaretçisi ilerler.

## <a name="underflow"></a>  basic_streambuf::underflow

Korumalı, geçerli öğe girdi akışından ayıklanacak sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi endeavors geçerli öğe ayıklanacak **ch** giriş akışından ilerledikten olmadan geçerli akış konumu ve olarak iade `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type)() **ch**). Bunu çeşitli yöntemlerle yapabilirsiniz:

- Okuma konumuna varsa **ch** salt okunur bir konumda depolanan bir öğe. Bunun hakkında daha fazla bilgi için Açıklamalar bölümüne bakın. [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md).

- Ardından, bir veya daha fazla öğe bir dış kaynaktan okunurken giriş arabelleği için yeni veya ek depolama alanı ayırarak bunu okuyun konum kullanılabilir hale getirebilirsiniz. Bunun hakkında daha fazla bilgi için Açıklamalar bölümüne bakın. [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md).

İşlev başarılı olursa, döndürür `traits_type::` [eof](../standard-library/char-traits-struct.md#eof) `()` veya bir özel durum oluşturur. Aksi takdirde, daha önce açıklandığı gibi geçerli öğe dönüştürülerek giriş akışına döndürür. Döndürülecek varsayılan davranıştır `traits_type::eof()`.

Sanal `underflow` işlevi ile [eşitleme](#sync) ve [taşma](#overflow) İşlevler, özelliklerini tanımlayan `streambuf`-türetilmiş sınıf. Her bir türetilmiş sınıf uygulayabilir `underflow` farklı, ancak arabirim çağıran stream sınıfı ile aynıdır.

`underflow` Genel tarafından en sık çağrıldığında `streambuf` gibi işlev [sgetc](#sgetc) ve [sgetn](#sgetn) zaman get alan boşsa, ancak stream sınıfları da dahil olmak üzere, diğer sınıfların çağırabilir `underflow` zaman.

`underflow` İşlevi, giriş kaynağı karakteri ile get alanı sağlar. Get alan karakterler içeriyorsa `underflow` ilk karakteri döndürür. Get alan boşsa, get alanı doldurur ve (Bu veriler get alanında dışına) sonraki karakteri döndürür. Daha fazla karakter kullanılabilir olduğunda, ardından `underflow` döndürür `EOF` ve get alanın boş bırakır.

İçinde `strstreambuf` sınıfı `underflow` ayarlar [egptr](#egptr) işaretçisi için bir çağrı tarafından dinamik olarak ayrılan erişim depolama `overflow`.

## <a name="xsgetn"></a>  basic_streambuf::xsgetn

Korumalı öğeleri girdi akışından ayıklanacak sanal işlev.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan olmasına olduğundan bu güvensiz olabilecek bir yöntemdir.

```cpp
virtual streamsize xsgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Ayıklanan karakterleri içeren arabellek.

*Sayısı*<br/>
Ayıklanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayıklanan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi kadar ayıklar *sayısı* giriş akışından öğeleri olarak da, yinelenen çağrısına [sbumpc](#sbumpc)ve dizi başında depolar *ptr*. Aslında ayıklanan öğelerin sayısını döndürür.

## <a name="xsputn"></a>  basic_streambuf::xsputn

Korumalı öğeleri çıkış akımına eklenecek sanal işlev.

```cpp
virtual streamsize xsputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Öğeleri eklemeye yönelik işaretçi.

*Sayısı*<br/>
Eklenecek öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Aslında akışa eklenen öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi en fazla ekler *sayısı* yinelenen çağrıları gibi tarafından öğeye çıkış akışı [sputc](#sputc), dizinin başından *ptr*. Karakterleri çıkış akışına içine ekleme kez durdurulur *sayısı* karakter yazılı, veya çağırma `sputc( count)` döndürecekti `traits::eof()`. Aslında eklenen öğelerin sayısını döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
