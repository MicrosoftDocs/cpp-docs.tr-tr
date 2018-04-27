---
title: basic_streambuf sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af21182cbea0299fe28be5621d8b35752e123352
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="basicstreambuf-class"></a>basic_streambuf Sınıfı

Öğeleri bir akış belirli bir gösterimini gelen ve giden iletimini denetleyen bir Akış Arabellek türetme için Özet temel sınıf tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_streambuf;
```

### <a name="parameters"></a>Parametreler

`Elem` A [char_type](#char_type).

`Tr` Karakter [traits_type](#traits_type).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı öğelerini bir akış belirli bir gösterimini gelen ve giden iletimini denetleyen bir Akış Arabellek türetme için Özet temel sınıf tanımlar. Sınıfın bir nesnesi `basic_streambuf` yardımcı türdeki öğeleri olan bir akış denetim `Tr`, olarak da bilinen [char_type](#char_type), olan karakter nitelikler sınıfı tarafından belirlenir [char_traits](../standard-library/char-traits-struct.md), ayrıca bilinen olarak [traits_type](#traits_type).

Her akış arabellek kavramsal olarak iki bağımsız akışları denetler: biri ayıklamaları (giriş) için ve biri eklemeleri (çıktı) için. Belirli bir gösterimi ancak ya da bu akışlardan erişilemez hale getirebilir. Genellikle, iki akışları arasındaki bazı ilişki tutar. Çıkış akışına INSERT bir [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`>, örneğin, nesnesidir ne, daha sonra kendi giriş akışından ayıklayın. Bir akışı getirin ne zaman bir [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> Nesne art arda diğer akış getirin.

Şablon sınıfı için ortak arabirimi `basic_streambuf` ancak özelleştirilmiş tüm akış arabellekleri için ortak olan işlemler sağlar. Korumalı kullanıcı arabirimi işini yapmak için belirli bir gösterimini bir akış için gereken işlem sağlar. Korumalı sanal üye işlevleri, belirli bir gösterimi olan bir akış için türetilen Akış Arabellek davranışını uyarlamak olanak tanır. Bu kitaplıktaki her türetilmiş Akış Arabellek nasıl korumalı sanal üye işlevleri davranışını uzmanlaşmış açıklar. Varsayılan davranış olduğu çoğunlukla hiçbir şey yapmak için temel sınıfı için bu konudaki açıklanmıştır.

Kalan ve arabellek aktarımları için sağlanan herhangi bir depolama alanı ve akışlar kopyalama üye işlevleri denetimi korumalı. Bir giriş arabelleği, örneğin, tarafından belirlenir:

- [eback](#eback), arabellek başlangıcını gösteren bir işaretçi.

- [gptr](#gptr), okumak için sonraki öğe için bir işaretçi.

- [egptr](#egptr), yalnızca geçmiş arabelleğin sonuna bir işaretçi.

Benzer şekilde, bir çıkış arabelleği tarafından belirlenir:

- [pbase](#pbase), arabellek başlangıcını gösteren bir işaretçi.

- [pptr](#pptr), sonraki öğeye yazmak için bir işaretçi.

- [epptr](#epptr), yalnızca geçmiş arabelleğin sonuna bir işaretçi.

Herhangi bir arabellek için aşağıdaki protokolü kullanılır:

- Sonraki işaretçisi null ise, hiçbir arabellek bulunmaktadır. Aksi takdirde, tüm üç işaretçileri aynı dizisi gelin. Sipariş için güvenli bir şekilde karşılaştırılabilir.

- Bir çıkış arabelleği için sonraki işaretçisi tarafından belirlenen yazma konumunda bir öğe sonraki işaretçisi son işaretçi sayısından az karşılaştırır saklayabilir.

- Bir giriş arabellek için sonraki işaretçisi tarafından belirlenen okuma konumunda bir öğe sonraki işaretçisi son işaretçi sayısından az karşılaştırır okuyabilir.

- Başlangıç işaretçisi sonraki işaretçisi sayısından az karşılaştırır, bir giriş arabellek için geri öğenin indirildiği sonraki işaretçisi tarafından belirlenen putback konumunda koyabilirsiniz.

Herhangi bir sınıfın türetildiği için yazdığınız sanal üye işlevleri korumalı `basic_streambuf` <  `Elem`, `Tr`> Bu protokolü bakımıyla işbirliği gerekir.

Sınıfın bir nesnesi `basic_streambuf` <  `Elem`, `Tr`> daha önce açıklanan altı işaretçileri depolar. Ayrıca bir nesne türü bir yerel ayar nesnesi depolar [yerel](../standard-library/locale-class.md) türetilmiş Akış Arabellek olası kullanmak için.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_streambuf](#basic_streambuf)|Türünde bir nesne oluşturur `basic_streambuf`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adıyla ilişkilendirir `Elem` şablon parametresi.|
|[int_type](#int_type)|İçinde bir tür adı ilişkilendirir `basic_streambuf` ile kapsam `Elem` şablon parametresi.|
|[off_type](#off_type)|İçinde bir tür adı ilişkilendirir `basic_streambuf` ile kapsam `Elem` şablon parametresi.|
|[pos_type](#pos_type)|İçinde bir tür adı ilişkilendirir `basic_streambuf` ile kapsam `Elem` şablon parametresi.|
|[traits_type](#traits_type)|Bir tür adıyla ilişkilendirir `Tr` şablon parametresi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[eback](#eback)|Giriş arabelleği başlangıcına işaretçi döndüren korumalı bir işlev.|
|[egptr](#egptr)|Yalnızca giriş arabelleği sonunu aşan bir işaretçi döndürür korumalı bir işlev.|
|[epptr](#epptr)|Çıkış arabelleğinin sonundan sonraya yalnızca işaretçi döndüren korumalı bir işlev.|
|[gbump](#gbump)|Ekler korumalı bir işlev `count` giriş arabelleği için sonraki işaretçisi için.|
|[getloc](#getloc)|Alır `basic_streambuf` nesnenin yerel ayar.|
|[gptr](#gptr)|Bir işaretçi giriş arabelleği sonraki öğeye döndürür korumalı bir işlev.|
|[imbue](#imbue)|Bir korumalı, sanal işlev tarafından çağrılır [pubimbue](#pubimbue).|
|[in_avail](#in_avail)|Arabellekteki okumaya hazırsınız öğe sayısını döndürür.|
|[Taşma](#overflow)|Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Bir öğeyi geri Giriş akışı yerleştirilecek çalışır bir korumalı sanal üye işlevi sonra onu yapın (tarafından sonraki işaretçisi işaret) geçerli öğe.|
|[pbase](#pbase)|Çıkış arabelleği başlangıcına işaretçi döndüren korumalı bir işlev.|
|[pbump](#pbump)|Ekler korumalı bir işlev `count` çıkış arabelleği için sonraki işaretçisi için.|
|[pptr](#pptr)|Bir işaretçi çıkış arabelleği sonraki öğeye döndürür korumalı bir işlev.|
|[pubimbue](#pubimbue)|Ayarlar `basic_streambuf` nesnenin yerel ayar.|
|[pubseekoff](#pubseekoff)|Çağrıları [seekoff](#seekoff), türetilen bir sınıfta geçersiz sanal işlev korumalı.|
|[pubseekpos](#pubseekpos)|Çağrıları [seekpos](#seekpos), türetilen bir sınıfta geçersiz kılınır ve geçerli işaretçi konumu sıfırlar sanal işlev korumalı.|
|[pubsetbuf](#pubsetbuf)|Çağrıları [setbuf](#setbuf), türetilen bir sınıfta geçersiz sanal işlev korumalı.|
|[pubsync](#pubsync)|Çağrıları [eşitleme](#sync), türetilen bir sınıfta geçersiz kılınır ve bu arabellek ile ilişkili dış akış güncelleştiren sanal işlev korumalı.|
|[sbumpc](#sbumpc)|Okur ve akış işaretçiyi taşıma geçerli öğeyi döndürür.|
|[seekoff](#seekoff)|Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.|
|[seekpos](#seekpos)|Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.|
|[setbuf](#setbuf)|Korumalı sanal üye fonksiyonu her türetilmiş Akış Arabellek bir işlemi belirli gerçekleştirir.|
|[setg](#setg)|Depolar korumalı bir işlev `_Gbeg` başlangıç işaretçisi olarak `_Gnext` sonraki işaretçisi olarak ve `_Gend` giriş arabelleği son işaretçisi olarak.|
|[setp](#setp)|Depolar korumalı bir işlev `_Pbeg` başlangıç işaretçisi olarak ve `_Pend` çıkış arabelleği son işaretçisi olarak.|
|[sgetc](#sgetc)|Geçerli öğe akış konumda değiştirmeden döndürür.|
|[sgetn](#sgetn)|Okuma öğe sayısını döndürür.|
|[showmanyc](#showmanyc)|Giriş akışından ayıklanabilir ve programı bir belirsiz bekleme süresi tabi olmaz olun karakter sayısını verir korumalı sanal üye işlevi.|
|[snextc](#snextc)|Geçerli öğe okur ve aşağıdaki öğeyi döndürür.|
|[sputbackc](#sputbackc)|Koyan bir `char_type` akış.|
|[sputc](#sputc)|Bir karakter akışa koyar.|
|[sputn](#sputn)|Bir karakter dizesi akışa koyar.|
|[stossc](#stossc)|Akış geçerli öğe geçmiş taşıyın.|
|[sungetc](#sungetc)|Bir karakteri akıştan alır.|
|[Değiştirme](#swap)|Bu nesne için sağlanan değerler değerlerde alış verişleri `basic_streambuf` parametre nesnesi.|
|[Eşitleme](#sync)|Denetimli akışları ile ilişkili tüm dış akışları eşitlemeye çalışır korumalı bir sanal işlev.|
|[uflow](#uflow)|Giriş akışından geçerli öğe ayıklar korumalı bir sanal işlev.|
|[underflow](#underflow)|Giriş akışından geçerli öğe ayıklar korumalı bir sanal işlev.|
|[xsgetn](#xsgetn)|Giriş akışından öğeleri ayıklar korumalı bir sanal işlev.|
|[xsputn](#xsputn)|Çıkış akışı öğeleri ekler korumalı bir sanal işlev.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu nesnenin değerleri diğerinden atar `basic_streambuf` nesnesi.|

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

`right` Lvalue başvuru `basic_streambuf` bu değerleri ayarlamak için kullanılan nesne `basic_streambuf` nesne.

### <a name="remarks"></a>Açıklamalar

İlk korumalı Oluşturucu null işaretçi giriş arabelleği ve çıkış arabelleği denetleme tüm işaretçiler içinde depolar. Ayrıca depolar `locale::classic` yerel ayar nesnesindeki. Daha fazla bilgi için bkz: [locale::classic](../standard-library/locale-class.md#classic).

İkinci korumalı Oluşturucu işaretçiler ve yerel ayarını kopyalar `right`.

## <a name="char_type"></a>  basic_streambuf::char_type

Bir tür adıyla ilişkilendirir **Elem** şablon parametresi.

```cpp
typedef Elem char_type;
```

## <a name="eback"></a>  basic_streambuf::eback

Giriş arabelleği başlangıcına işaretçi döndüren korumalı bir işlev.

```cpp
char_type *eback() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği başlangıcını gösteren bir işaretçi.

## <a name="egptr"></a>  basic_streambuf::egptr

Yalnızca giriş arabelleği sonunu aşan bir işaretçi döndürür korumalı bir işlev.

```cpp
char_type *egptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi yalnızca giriş arabelleği sonunu geçti.

## <a name="epptr"></a>  basic_streambuf::epptr

Çıkış arabelleğinin sonundan sonraya yalnızca işaretçi döndüren korumalı bir işlev.

```cpp
char_type *epptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi yalnızca çıkış arabelleği sonunu geçti.

## <a name="gbump"></a>  basic_streambuf::gbump

Ekler korumalı bir işlev `count` giriş arabelleği için sonraki işaretçisi için.

```cpp
void gbump(int count);
```

### <a name="parameters"></a>Parametreler

`count` İşaretçinin ilerletmek, tutar.

## <a name="getloc"></a>  basic_streambuf::getloc

Basic_streambuf nesnenin yerel alır.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgi için bkz: [ios_base::getloc](../standard-library/ios-base-class.md#getloc).

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

Bir işaretçi giriş arabelleği sonraki öğeye döndürür korumalı bir işlev.

```cpp
char_type *gptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleği sonraki öğeye yönelik işaretçi.

## <a name="imbue"></a>  basic_streambuf::imbue

Bir korumalı sanal işlev tarafından çağrılır [pubimbue](#pubimbue).

```cpp
virtual void imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

`_Loc` Bir yerel bir başvuru.

### <a name="remarks"></a>Açıklamalar

Hiçbir şey yapmak için varsayılan davranıştır.

## <a name="in_avail"></a>  basic_streambuf::in_avail

Arabellekteki okumaya hazırsınız öğe sayısını döndürür.

```cpp
streamsize in_avail();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekteki okumaya hazırsınız öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Varsa bir [konumunu okuma](../standard-library/basic-streambuf-class.md) üye fonksiyonu döndürür, kullanılabilir [egptr](#egptr) - [gptr](#gptr). Aksi takdirde, döndürür [showmanyc](#showmanyc).

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

Bu nesnenin değerleri diğerinden atar `basic_streambuf` nesnesi.

```cpp
basic_streambuf& operator=(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

`right` Lvalue başvuru `basic_streambuf` değerleri bu nesneye atamak için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işleci kopyalar `right` giriş arabelleği ve çıkış arabelleği kontrol işaretçileri. Ayrıca depolar `right.` [getloc()](#getloc) içinde `locale object`. Döndürdüğü `*this`.

## <a name="overflow"></a>  basic_streambuf::Overflow

Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::eof** veya bir özel durum oluşturur. Aksi takdirde, döndürür **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*). Döndürülecek varsayılan davranıştır **traits_type::eof**.

### <a name="remarks"></a>Açıklamalar

Varsa _ *Meta* eşit karşılaştırmak değil **traits_type::eof**, korumalı sanal üye fonksiyonu endeavors öğesi eklemek **traits_type::**[to_ char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) çıkış akışına içine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Varsa bir `write position` olan kullanılabilir, bu öğenin yazma konumunu depolayabilir ve çıkış arabelleği için sonraki işaretçisi Artır.

- Çıkış arabelleği için yeni veya ek depolama alanı ayırarak, yazma konumunu kullanılabilir hale getirebilirsiniz.

- Bu yazma konumunu çıkışı, bazı dış hedef, bazı veya tüm öğeleri başına arasında yazmayı ve sonraki işaretçiler tarafından için çıkış arabelleği sunabilirsiniz.

İle birlikte sanal taşma işlevi [eşitleme](#sync) ve [underflow](#underflow) İşlevler, streambuf türetilmiş sınıf özelliklerini tanımlar. Her türetilmiş bir sınıf taşma desteklememesinden, ancak arabirim arama stream sınıfı ile aynıdır.

`overflow` Ortak tarafından en sık çağrıldığında `streambuf` gibi işlev `sputc` ve `sputn` kullandığınızda put alanı dolu ancak stream sınıfları dahil olmak üzere diğer sınıflar çağırabilirsiniz `overflow` zaman.

İşlev arasında put alanındaki karakterlerin tüketir `pbase` ve `pptr` işaretçiler ve put alan yeniden başlatır. `overflow` Gerekir işlevi de kullanmak `nCh` (varsa `nCh` değil `EOF`), ya da sonraki çağrıda tüketilebilir şekilde karakter yeni alan yerleştirmek koymak isteyebilirsiniz.

Tüket tanımını türetilen sınıflar arasında değişir. Örneğin, `filebuf` sınıf kendi karakterleri bir dosyaya yazar while `strstreambuf` sınıf kendi arabellekte tutar ve (arabellek dinamik olarak belirlendiyse) taşmasına çağrısına arabellekte genişletir. Bu genişleme eski arabellek boşaltma ve yeni, büyük bir değiştirme tarafından sağlanır. İşaretçileri gerektiği şekilde ayarlanır.

## <a name="pbackfail"></a>  basic_streambuf::pbackfail

Bir öğeyi geri Giriş akışı yerleştirilecek çalışır bir korumalı sanal üye işlevi sonra onu yapın (tarafından sonraki işaretçisi işaret) geçerli öğe.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::eof** veya bir özel durum oluşturur. Aksi takdirde, başka bir değer döndürür. Döndürülecek varsayılan davranıştır **traits_type::eof**.

### <a name="remarks"></a>Açıklamalar

Varsa _ *Meta* karşılaştırır eşit **traits_type::eof**, geri göndermek için etkili bir şekilde akış geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğenin değiştirilmiştir **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*). İşlev, çeşitli yollarla bir öğe geri koyabilirsiniz:

- Putback konumu varsa, bu öğeyi putback konumda depolamak ve giriş arabelleği için sonraki işaretçisi azaltma.

- Giriş arabelleği için yeni veya ek depolama alanı ayırarak, putback konum kullanılabilir hale getirebilirsiniz.

- Ortak giriş ve çıkış akışları ile bir akış arabellek için bunu putback konumu çıkışı, bazı dış hedef, bazı veya tüm öğeleri başına arasında yazmayı ve sonraki işaretçiler tarafından için çıkış arabelleği sunabilirsiniz.

## <a name="pbase"></a>  basic_streambuf::pbase

Çıkış arabelleği başlangıcına işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pbase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış arabelleği başlangıcını gösteren bir işaretçi.

## <a name="pbump"></a>  basic_streambuf::pbump

Ekler korumalı bir işlev `count` çıkış arabelleği için sonraki işaretçisi için.

```cpp
void pbump(int count);
```

### <a name="parameters"></a>Parametreler

`count` Yazma konumunu ilerlemek için karakter sayısı.

## <a name="pos_type"></a>  basic_streambuf::pos_type

Basic_streambuf kapsam içinde bir tür adı, bir şablon parametresi türlerini ilişkilendirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="pptr"></a>  basic_streambuf::pptr

Bir işaretçi çıkış arabelleği sonraki öğeye döndürür korumalı bir işlev.

```cpp
char_type *pptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış arabelleği sonraki öğeye yönelik işaretçi.

## <a name="pubimbue"></a>  basic_streambuf::pubimbue

Basic_streambuf nesnenin yerel ayarlar.

```cpp
locale pubimbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

`_Loc` Bir yerel bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yerel ayar nesnesinde depolanan önceki değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevini depolar _ *Loc* yerel nesne ve çağrıları [imbue](#imbue).

### <a name="example"></a>Örnek

Bkz: [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue) kullanan bir örnek `pubimbue`.

## <a name="pubseekoff"></a>  basic_streambuf::pubseekoff

Çağrıları [seekoff](#seekoff), türetilen bir sınıfta geçersiz sanal işlev korumalı.

```cpp
pos_type pubseekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Off` Göreli olarak için arama konumunu `_Way`.

`_Way` Uzaklık işlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) olası değerler için.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumunu döndürür ( [seekoff](#seekoff)(_ *kapalı*, `_Way`, `_Which`)).

### <a name="remarks"></a>Açıklamalar

İşaretçi göreli `_Way`.

## <a name="pubseekpos"></a>  basic_streambuf::pubseekpos

Çağrıları [seekpos](#seekpos), türetilen bir sınıfta geçersiz kılınır ve geçerli işaretçi konumu sıfırlar sanal işlev korumalı.

```cpp
pos_type pubseekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Sp` Arama konumu.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya bir geçersiz akış konumu. Akışı konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırın `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [seekpos](#seekpos)(_ *Sp*, `_Which`).

## <a name="pubsetbuf"></a>  basic_streambuf::pubsetbuf

Çağrıları [setbuf](#setbuf), türetilen bir sınıfta geçersiz sanal işlev korumalı.

```cpp
basic_streambuf<Elem, Tr> *pubsetbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

`_Buffer` Bir işaretçi `char_type` Bu örnek oluşturma için.

`count` Arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Döndürür [setbuf](#setbuf)( `_Buffer`, `count`).

## <a name="pubsync"></a>  basic_streambuf::pubsync

Çağrıları [eşitleme](#sync), türetilen bir sınıfta geçersiz kılınır ve bu arabellek ile ilişkili dış akış güncelleştiren sanal işlev korumalı.

```cpp
int pubsync();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür [eşitleme](#sync) veya -1 hata.

## <a name="sbumpc"></a>  basic_streambuf::sbumpc

Okur ve akış işaretçiyi taşıma geçerli öğeyi döndürür.

```cpp
int_type sbumpc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Okuma konumu bulunup bulunmadığını üye işlevinin döndürdüğü **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **\*** [gptr](#gptr)) ve giriş arabelleği için sonraki işaretçisi artırır. Aksi takdirde, döndürür [uflow](#uflow).

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

Geçerli konumlar denetimli akışlar için alter dener korumalı sanal üye işlevi.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Off` Göreli olarak için arama konumunu `_Way`.

`_Way` Uzaklık işlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) olası değerler için.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumunu döndürür ( `seekoff` (_ *kapalı*, `_Way`, `_Which`)).

### <a name="remarks"></a>Açıklamalar

Yeni bir konuma şu şekilde belirlenir:

- Varsa `_Way`  ==  `ios_base::beg`, yeni bir konuma akış artı _ başlangıcıdır *devre dışı*.

- Varsa `_Way`  ==  `ios_base::cur`, yeni konumu geçerli akışı konumu hem _ olan *devre dışı*.

- Varsa `_Way`  ==  `ios_base::end`, yeni bir konuma akış artı _ sonudur *devre dışı*.

Genellikle, varsa **hangi & ios_base::in** olan sıfır olmayan, Giriş akışı etkilenir ve **hangi & ios_base::out** olan sıfır olmayan, çıkış akışı etkilenir. Bu parametrenin gerçek kullanımı ancak türetilmiş akış arabellekleri arasında değişir.

Akış konum veya konumlarını değiştirmeden içinde işlevi başarılı olursa, sonuçta elde edilen akış konum veya elde edilen akış konumlar birini döndürür. Aksi halde, bir geçersiz akış konumunu döndürür. Varsayılan davranışı geçersiz akış konumu getirmektir.

## <a name="seekpos"></a>  basic_streambuf::seekpos

Geçerli konumlar denetimli akışlar için alter dener korumalı sanal üye işlevi.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Sp` Arama konumu.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya bir geçersiz akış konumu. Akışı konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırın `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Yeni konumdur _ *Sp*.

Genellikle, varsa **hangi & ios_base::in** olan sıfır olmayan, Giriş akışı etkilenir ve **hangi & ios_base::out** olan sıfır olmayan, çıkış akışı etkilenir. Bu parametrenin gerçek kullanımı ancak türetilmiş akış arabellekleri arasında değişir.

Akış konum veya konumlarını değiştirmeden içinde işlevi başarılı olursa, sonuçta elde edilen akış konum veya elde edilen akış konumlar birini döndürür. Aksi takdirde, geçersiz akış konumu (-1) döndürür. Varsayılan davranışı geçersiz akış konumu getirmektir.

## <a name="setbuf"></a>  basic_streambuf::setbuf

Her türetilmiş Akış Arabellek bir işlemi belirli gerçekleştiren bir korumalı sanal üye işlevi.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

`_Buffer` Arabellek için işaretçi.

`count` Arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Döndürülecek varsayılan davranıştır **bu**.

### <a name="remarks"></a>Açıklamalar

Bkz: [basic_filebuf](../standard-library/basic-filebuf-class.md). `setbuf` bellek için bir alan sağlar `streambuf` nesnesi. Arabellek nasıl kullanıldığını türetilmiş sınıflarda tanımlanır.

## <a name="setg"></a>  basic_streambuf::setg

Depolar _ korumalı bir işlev *Gbeg* başlangıç işaretçisi olarak `_Gnext` sonraki işaretçisi olarak ve `_Gend` giriş arabelleği son işaretçisi olarak.

```cpp
void setg(char_type* _Gbeg,
    char_type* _Gnext,
    char_type* _Gend);
```

### <a name="parameters"></a>Parametreler

*_Gbeg* arabellek başlangıcını gösteren bir işaretçi.

`_Gnext` Bir işaretçi bir yere arabellek gerçekleştiriyor.

`_Gend` Arabelleğin sonuna bir işaretçi.

## <a name="setp"></a>  basic_streambuf::setp

Depolar korumalı bir işlev `_Pbeg` başlangıç işaretçisi olarak ve `_Pend` çıkış arabelleği son işaretçisi olarak.

```cpp
void setp(char_type* _Pbeg, char_type* _Pend);
```

### <a name="parameters"></a>Parametreler

`_Pbeg` Arabellek başlangıcını gösteren bir işaretçi.

`_Pend` Arabelleğin sonuna bir işaretçi.

## <a name="sgetc"></a>  basic_streambuf::sgetc

Geçerli öğe akış konumda değiştirmeden döndürür.

```cpp
int_type sgetc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Okuma konumu bulunup bulunmadığını üye işlevinin döndürdüğü **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `*` [gptr](#gptr)). Aksi takdirde, döndürür [underflow](#underflow).

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

En fazla ayıklar `count` sağlanan arabelleğinde depolar ve karakter giriş arabelleğinden `ptr`.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir.

```cpp
streamsize sgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

`ptr` Ayıklanan karakterden arabelleği.

`count` Okunacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Okunan öğelerin sayısı. Bkz: [streamsize](../standard-library/ios-typedefs.md#streamsize) daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [xsgetn](#xsgetn)( `ptr`, `count`).

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

Giriş akışından ayıklanabilir ve programı bir belirsiz bekleme süresi tabi olmaz olun karakter sayısını döndüren bir korumalı sanal üye işlev.

```cpp
virtual streamsize showmanyc();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürülecek varsayılan davranıştır.

## <a name="snextc"></a>  basic_streambuf::snextc

Geçerli öğe okur ve aşağıdaki öğeyi döndürür.

```cpp
int_type snextc();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki sonraki öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrılarını [sbumpc](#sbumpc) ve bu işlev döndürürse **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), döndürür **traits_type::eof**. Aksi takdirde, döndürür [sgetc](#sgetc).

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

Bir char_type akışta koyar.

```cpp
int_type sputbackc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

`_Ch` Karakter.

### <a name="return-value"></a>Dönüş Değeri

Karakter ya da hata döndürür.

### <a name="remarks"></a>Açıklamalar

Putback konumu varsa ve `_Ch` karşılaştırır üye fonksiyonu azaltır, bu konumda depolanan karakteri döndürür ve giriş arabelleği için sonraki işaretçisi eşit **traits_type::**[to_int_ tür](../standard-library/char-traits-struct.md#to_int_type)( `_Ch`). Aksi takdirde, döndürür [pbackfail](#pbackfail)( `_Ch`).

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

Bir karakter akışa koyar.

```cpp
int_type sputc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

`_Ch` Karakter.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa karakteri döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa bir `write position` kullanılabilir üye fonksiyonu depoları `_Ch` çıkış arabelleği için sonraki işaretçisi yazma konumda artırır ve döndürür **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)() `_Ch`). Aksi takdirde, döndürür [taşma](#overflow)( `_Ch`).

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

Bir karakter dizesi akışa koyar.

```cpp
streamsize sputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

`ptr` Karakter dizesi.

`count` Karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte akışa eklenen karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [xsputn](#xsputn)( `ptr`, `count`). Daha fazla bilgi için bu üye Açıklamalar bölümüne bakın.

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

Akış geçerli öğe geçmiş taşıyın.

```cpp
void stossc();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrılarını [sbumpc](#sbumpc). Bir uygulama olmadığına dikkat edin, bu üye işlevi sağlamak için gereklidir.

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

Bir karakteri akıştan alır.

```cpp
int_type sungetc();
```

### <a name="return-value"></a>Dönüş Değeri

Karakter ya da hata verir.

### <a name="remarks"></a>Açıklamalar

Üye putback konumu olup olmadığını döndürür ve giriş arabelleği için sonraki işaretçisi azaltır işlev `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `*` [gptr](#gptr)). Bununla birlikte, her zaman geçerli arabellek durumda yakalanabilir böylece son karakter okuma belirlemek mümkün değildir. Bu durum geçerlidir sonra işlevi döndürür [pbackfail](#pbackfail). Bu durumu önlemek için geri koymak ve çağırmak için karakter izlemek `sputbackc(ch)`, hangi sağlanan başarısız olmaz, akış başında çağrısından yoktur ve birden fazla karakter geri almaya denemeyin.

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

Bu nesne için sağlanan değerler değerlerde alış verişleri `basic_streambuf` nesnesi.

```cpp
void swap(basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`right`|Lvalue başvuru `basic_streambuf` değerleri değişimi için kullanılan nesne.|

### <a name="remarks"></a>Açıklamalar

Korumalı üye fonksiyonu alış verişleri ile `right` denetleme tüm işaretçiler `input buffer` ve `output buffer`. Ayrıca alış verişleri `right.` [getloc()](#getloc) ile `locale` nesnesi.

## <a name="sync"></a>  basic_streambuf::Sync

Denetimli akışları ile ilişkili tüm dış akışları eşitlemeye çalışır korumalı bir sanal işlev.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı yoksa -1 döndürür. Sıfır döndürülecek varsayılan davranıştır.

### <a name="remarks"></a>Açıklamalar

`sync` çıkış arabelleği için başlangıç ve sonraki işaretçiler arasında herhangi bir öğe çıkışı yazma içerir. Tekrar sonraki arasında herhangi bir öğe için gerektirmez ve giriş arabelleği işaretçileri bitmelidir.

## <a name="traits_type"></a>  basic_streambuf::traits_type

Bir tür adıyla ilişkilendirir **Tr** şablon parametresi.

```cpp
typedef Tr traits_type;
```

## <a name="uflow"></a>  basic_streambuf::uflow

Giriş akışından geçerli öğe ayıklar korumalı bir sanal işlev.

```cpp
virtual int_type uflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Geçerli öğe ayıklamak korumalı sanal üye fonksiyonu çalışır **ch** giriş akışından sonra geçerli akışı konumu ilerleyin ve öğesi olarak dönmek **traits_type::** [ to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **ch**). Bunu çeşitli yöntemlerle yapabilirsiniz:

- Okuma konumu varsa, sürdüğünü **ch** öğe okuma konumunda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

- Bir öğe, doğrudan bir dış kaynaktan okumak ve değeri olarak teslim **ch**.

- Ortak giriş ve çıkış akışları ile bir akış arabellek için onu okuma konumu çıkışı, bazı dış hedef, bazı veya tüm öğeleri başına arasında yazmayı ve sonraki işaretçiler tarafından için çıkış arabelleği sunabilirsiniz. Veya yeni veya ek depolama alanı için giriş arabelleği ayırabilirsiniz. İşlev daha sonra bir dış kaynaktan bir veya daha fazla öğe okur.

İşlev başarısız olması durumunda, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), veya bir özel durum oluşturur. Aksi takdirde, geçerli öğe döndürür `ch` Giriş akışı, yukarıda açıklandığı gibi dönüştürülür ve giriş arabelleği için sonraki işaretçisi ilerler. Varsayılan davranış çağırmaktır [underflow](#underflow) ve bu işlev döndürürse **traits_type::eof**, döndürülecek **traits_type::eof**. Aksi takdirde, geçerli öğe işlevi döndürür **ch** giriş akışında dönüştürülen daha önce açıklandığı gibi ve giriş arabelleği için sonraki işaretçisi ilerletir.

## <a name="underflow"></a>  basic_streambuf::underflow

Korumalı, geçerli öğe giriş akışından ayıklamak için sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu endeavors geçerli öğe ayıklamak **ch** giriş akışından ilerledikten olmadan geçerli akışı konumu ve olarak geri dönüp `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type)() **ch**). Bunu çeşitli yöntemlerle yapabilirsiniz:

- Okuma konumu olup olmadığını **ch** okuma konumunda depolanan öğedir. Bunun hakkında daha fazla bilgi için Açıklamalar bölümüne bakın [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md).

- Ardından, bir veya daha fazla öğe bir dış kaynaktan okunuyor giriş arabelleği için yeni veya ek depolama alanı ayırarak, okuma konum kullanılabilir hale getirebilirsiniz. Bunun hakkında daha fazla bilgi için Açıklamalar bölümüne bakın [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md).

İşlev başarısız olması durumunda, döndürür `traits_type::` [eof](../standard-library/char-traits-struct.md#eof) `()` veya bir özel durum oluşturur. Aksi takdirde, daha önce açıklandığı gibi dönüştürülen geçerli öğe Giriş akışı döndürür. Döndürülecek varsayılan davranıştır `traits_type::eof()`.

Sanal `underflow` işlevi ile [eşitleme](#sync) ve [taşma](#overflow) İşlevler, özelliklerini tanımlayan `streambuf`-türetilmiş sınıf. Her türetilmiş bir sınıf uygulayabilir `underflow` farklı şekilde, ancak arabirim arama stream sınıfı ile aynıdır.

`underflow` Ortak tarafından en sık çağrıldığında `streambuf` gibi işlev [sgetc](#sgetc) ve [sgetn](#sgetn) zaman get alanın boş olduğu, ancak stream sınıfları dahil olmak üzere diğer sınıflar çağırabilirsiniz `underflow` zaman.

`underflow` İşlevi, giriş kaynağı karakterlerinden get alanıyla sağlar. Get alanı karakterler içeriyorsa `underflow` ilk karakteri döndürür. Get alanı boş ise, get alanını doldurur ve sonraki (get alanında bırakır) karakteri döndürür. Daha fazla karakter kullanılabilir varsa, ardından `underflow` döndürür `EOF` ve get alanı boş bırakır.

İçinde `strstreambuf` sınıfı, `underflow` ayarlar [egptr](#egptr) için yapılan bir çağrı tarafından dinamik olarak ayrılan erişimli depolama işaretçi `overflow`.

## <a name="xsgetn"></a>  basic_streambuf::xsgetn

Korumalı öğeleri giriş akışından ayıklamak için sanal işlev.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir.

```cpp
virtual streamsize xsgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

`ptr` Ayıklanan karakterden arabelleği.

`count` Ayıklanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayıklanan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu kadar ayıklar `count` Giriş akışı öğelerinden olarak yinelenen çağrıları durumunda da [sbumpc](#sbumpc)ve dizi başında depolar `ptr`. Gerçekte ayıklanan öğe sayısını döndürür.

## <a name="xsputn"></a>  basic_streambuf::xsputn

Korumalı, çıktı akışa öğe eklemek için sanal işlev.

```cpp
virtual streamsize xsputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

`ptr` İşaretçi eklemek için öğeleri.

`count` Eklenecek öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte akışa eklenen öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu kadar ekler `count` yinelenen yapılan çağrılar tarafından gibi çıkış elemanlara akış [sputc](#sputc), dizi başında gelen `ptr`. Çıkış akışı karakterler ekleme kez tüm durdurur `count` karakter yazılı, veya çağırma `sputc( count)` döndürecekti `traits::eof()`. Gerçekte eklenen öğelerin sayısını döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
