---
description: 'Hakkında daha fazla bilgi edinin: basic_streambuf sınıfı'
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
ms.openlocfilehash: 7600c60c501c1922deeabca11d41c89bc37548a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325619"
---
# <a name="basic_streambuf-class"></a>basic_streambuf Sınıfı

Bir akışın belirli bir gösterimine ve öğesinden öğelerin aktarılmasını denetleyen bir akış arabelleği türetmek için soyut bir temel sınıf tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_streambuf;
```

### <a name="parameters"></a>Parametreler

*Elem*\
Bir [char_type](#char_type).

*Tr*\
Karakter [traits_type](#traits_type).

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, akış arabelleği türetmede bir soyut temel sınıf tanımlar. Bu, bir akışın belirli bir gösteriminden ve öğesinden öğelerin aktarılmasını denetler. Sınıfının bir nesnesi, `basic_streambuf` karakter nitelikleri [traits_type](#traits_type)olarak da bilinen sınıf [char_traits](../standard-library/char-traits-struct.md)tarafından belirlendiği şekilde, [char_type](#char_type)olarak da bilinen, *tr* türünde öğeleri olan bir akışı denetlemeye yardımcı olur.

Her akış arabelleği kavramsal olarak iki bağımsız akışı denetler: biri ayıklamaları (input) ve biri Eklenenler (output) için. Ancak belirli bir gösterim, bu akışların her birini veya her ikisini de erişilemez hale getirebilir. Genellikle iki akış arasında bir ilişki sağlar. [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)çıkış akışına ne eklediğiniz, <  `Elem` `Tr` Örneğin> nesnesinin, daha sonra giriş akışından ayıkladıklarınız. Bir [basic_filebuf](../standard-library/basic-filebuf-class.md)> nesnenin bir akışını konumlandırdığınızda <  `Elem` `Tr` , diğer akışı art arda yerleştirebilirsiniz.

Sınıf şablonuna genel arabirim, `basic_streambuf` ancak özelleşmiş tüm akış arabelleklerinde ortak olan işlemleri sağlar. Korumalı arabirim, işini yapmak için bir akışın belirli bir temsili için gereken işlemleri sağlar. Korunan sanal üye işlevleri, bir akışın belirli bir temsili için türetilmiş bir akış arabelleğinin davranışını uyarlamanızı sağlar. Bu kitaplıktaki her türetilmiş akış arabelleği, korunan sanal üye işlevlerinin davranışını nasıl uzmanlık sağladığını açıklar. Temel sınıf için genellikle hiçbir şey yapmak için varsayılan davranış, bu konuda açıklanmaktadır.

Kalan korumalı üye işlevleri, akış ve akışlara yönelik arabellek iletimlerinin sağladığı herhangi bir depolama alanına ve bunlardan kopyalanmasını denetler. Örneğin, bir giriş arabelleğinin şu şekilde belirlenir:

- arabelleğin başlangıcına yönelik bir işaretçi olan [eback](#eback).

- [gptr](#gptr), okunacak bir sonraki öğeye yönelik bir işaretçi.

- [egptr](#egptr), bir işaretçi yalnızca arabelleğin sonunu geçti.

Benzer şekilde, bir çıkış arabelleği tarafından belirlenir:

- [pbase](#pbase), arabelleğin başlangıcına yönelik bir işaretçi.

- [pptr](#pptr), yazılacak bir sonraki öğeye yönelik bir işaretçi.

- [epptr](#epptr), bir işaretçi yalnızca arabelleğin sonunu geçti.

Herhangi bir arabellek için aşağıdaki protokol kullanılır:

- Sonraki işaretçi null ise, arabellek yok demektir. Aksi halde, üç işaretçinin hepsi aynı sırada yer noktasıdır. Bunlar, sipariş için güvenli şekilde karşılaştırılabilir.

- Bir çıkış arabelleği için, sonraki işaretçi bitiş işaretçisinden daha az karşılaştırıyorsa, bir öğeyi sonraki işaretçi tarafından belirlenen yazma konumunda saklayabilirsiniz.

- Bir giriş arabelleği için, bir sonraki işaretçi bitiş işaretçisinden daha küçük bir şekilde karşılaştırıyorsa, sonraki işaretçi tarafından belirlenen okuma konumunda bir öğeyi okuyabilirsiniz.

- Bir giriş arabelleği için, Başlangıç işaretçisi bir sonraki işaretçiden daha küçük bir şekilde karşılaştırıyorsa, bir öğeyi, daha az bir sonraki işaretçiye göre belirlenen putback konumuna geri koyabilirsiniz.

' Den türetilen bir sınıf için yazdığınız tüm korumalı sanal üye işlevleri `basic_streambuf` <  `Elem` , `Tr`> bu protokolü sürdürmek için birlikte çalışmalıdır.

> sınıfının bir nesnesi `basic_streambuf` <  `Elem` , `Tr` daha önce açıklanan altı işaretçiyi depolar. Ayrıca, bir yerel ayar nesnesini, türetilmiş bir akış arabelleği tarafından olası kullanım için [Yerel](../standard-library/locale-class.md) türdeki bir nesnede depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_streambuf](#basic_streambuf)|Türünde bir nesne oluşturur `basic_streambuf` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adını `Elem` şablon parametresiyle ilişkilendirir.|
|[int_type](#int_type)|Kapsam içindeki bir tür adını `basic_streambuf` `Elem` şablon parametresiyle ilişkilendirir.|
|[off_type](#off_type)|Kapsam içindeki bir tür adını `basic_streambuf` `Elem` şablon parametresiyle ilişkilendirir.|
|[pos_type](#pos_type)|Kapsam içindeki bir tür adını `basic_streambuf` `Elem` şablon parametresiyle ilişkilendirir.|
|[traits_type](#traits_type)|Bir tür adını `Tr` şablon parametresiyle ilişkilendirir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[eback](#eback)|Giriş arabelleğinin başlangıcına bir işaretçi döndüren korumalı bir işlev.|
|[egptr](#egptr)|Giriş arabelleğinin sonunu geçen bir işaretçi döndüren korumalı bir işlev.|
|[epptr](#epptr)|Yalnızca çıkış arabelleğinin sonunu geçen bir işaretçi döndüren korumalı bir işlev.|
|[gbump](#gbump)|`count`Giriş arabelleğinin sonraki işaretçisine ekleyen korumalı bir işlev.|
|[getloc](#getloc)|`basic_streambuf`Nesnenin yerel ayarını alır.|
|[gptr](#gptr)|Giriş arabelleğinin bir sonraki öğesine bir işaretçi döndüren korumalı bir işlev.|
|[imbue](#imbue)|[Pubimbue](#pubimbue)tarafından çağrılan korumalı, sanal bir işlev.|
|[in_avail](#in_avail)|Arabellekten okunmaya izin veren öğe sayısını döndürür.|
|[taşma](#overflow)|Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.|
|[pbackfail](#pbackfail)|Giriş akışına bir öğe geri döndürmeye çalışan korumalı bir sanal üye işlevi, ardından bunu geçerli öğe yapın (sonraki işaretçi tarafından işaret edilen).|
|[pbase](#pbase)|Çıkış arabelleğinin başlangıcına bir işaretçi döndüren korumalı bir işlev.|
|[pbump](#pbump)|`count`Çıkış arabelleğinin sonraki işaretçisine ekleyen korumalı bir işlev.|
|[pptr](#pptr)|Çıkış arabelleğinin bir sonraki öğesine bir işaretçi döndüren korumalı bir işlev.|
|[pubimbue](#pubimbue)|`basic_streambuf`Nesnenin yerel ayarını ayarlar.|
|[pubseekoff](#pubseekoff)|Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [seekoff](#seekoff)öğesini çağırır.|
|[pubseekpos](#pubseekpos)|Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [seekpos](#seekpos)'u çağırır ve geçerli işaretçi konumunu sıfırlar.|
|[pubsetbuf](#pubsetbuf)|Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [setarabelleğe](#setbuf)çağırır.|
|[pubsync](#pubsync)|Türetilmiş bir sınıfta geçersiz kılınan ve bu arabellekle ilişkili dış akışı güncelleştiren korunan bir sanal işlev olan [eşitleme](#sync)çağırır.|
|[sbumpc](#sbumpc)|Akış işaretçisini taşıyarak geçerli öğeyi okur ve döndürür.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi, her türetilmiş akış arabelleği için bir işlem gerçekleştirir.|
|[setg](#setg)|`_Gbeg`Başlangıç işaretçisine, `_Gnext` sonraki işaretçiye ve `_Gend` giriş arabelleğinin bitiş işaretçisine depolayan korumalı bir işlev.|
|[setp](#setp)|`_Pbeg`Başlangıç işaretçisine ve `_Pend` çıkış arabelleğinin bitiş işaretçisine depolayan korumalı bir işlev.|
|[sgetc](#sgetc)|Akışta konum değişikliği yapmadan geçerli öğeyi döndürür.|
|[sgetn](#sgetn)|Okunan öğe sayısını döndürür.|
|[showmanyc](#showmanyc)|Giriş akışından ayıklanabilen karakter sayısının sayısını döndüren ve programın sonsuz bir beklemeye tabi olmamasını sağlamak için korunan sanal üye işlevi.|
|[snextc](#snextc)|Geçerli öğeyi okur ve aşağıdaki öğeyi döndürür.|
|[sputbackc](#sputbackc)|Akışa bir ekler `char_type` .|
|[sputc](#sputc)|Akışa bir karakter koyar.|
|[sputn](#sputn)|Akışa bir karakter dizesi koyar.|
|[stossc](#stossc)|Akıştaki geçerli öğeyi geçmiş olarak taşıyın.|
|[sungetc](#sungetc)|Akıştan bir karakter alır.|
|[Kur](#swap)|Bu nesnedeki değerleri, belirtilen nesne parametresindeki değerler için değiştirir `basic_streambuf` .|
|[Eşitleme](#sync)|Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışan korumalı bir sanal işlev.|
|[uflow](#uflow)|Giriş akışından geçerli öğeyi çıkaran korumalı bir sanal işlev.|
|[öğe](#underflow)|Giriş akışından geçerli öğeyi çıkaran korumalı bir sanal işlev.|
|[xsgetn](#xsgetn)|Giriş akışından öğeleri çıkaran korumalı bir sanal işlev.|
|[xsputn](#xsputn)|Çıkış akışına öğeler ekleyen korumalı bir sanal işlev.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bu nesnenin değerlerini başka bir `basic_streambuf` nesneden atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<streambuf>

**Ad alanı:** std

## <a name="basic_streambufbasic_streambuf"></a><a name="basic_streambuf"></a> basic_streambuf:: basic_streambuf

Türünde bir nesne oluşturur `basic_streambuf` .

```cpp
basic_streambuf();

basic_streambuf(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`basic_streambuf`Bu nesnenin değerlerini ayarlamak için kullanılan nesneye bir lvalue başvurusu `basic_streambuf` .

### <a name="remarks"></a>Açıklamalar

İlk korumalı Oluşturucu, giriş arabelleğini ve çıkış arabelleğini denetleyen tüm işaretçilerde boş bir işaretçi depolar. Ayrıca `locale::classic` yerel ayar nesnesinde depolar. Daha fazla bilgi için bkz. [locale:: klasik](../standard-library/locale-class.md#classic).

İkinci korumalı Oluşturucu işaretçileri ve yerel ayarı *sağdan* kopyalar.

## <a name="basic_streambufchar_type"></a><a name="char_type"></a> basic_streambuf:: char_type

Bir tür adını **elemtemplate** parametresiyle ilişkilendirir.

```cpp
typedef Elem char_type;
```

## <a name="basic_streambufeback"></a><a name="eback"></a> basic_streambuf:: eback

Giriş arabelleğinin başlangıcına bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *eback() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleğinin başlangıcına yönelik bir işaretçi.

## <a name="basic_streambufegptr"></a><a name="egptr"></a> basic_streambuf:: egptr

Giriş arabelleğinin sonunu geçen bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *egptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi yalnızca giriş arabelleğinin sonunu geçti.

## <a name="basic_streambufepptr"></a><a name="epptr"></a> basic_streambuf:: epptr

Yalnızca çıkış arabelleğinin sonunu geçen bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *epptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi yalnızca çıkış arabelleğinin sonunu geçti.

## <a name="basic_streambufgbump"></a><a name="gbump"></a> basic_streambuf:: gbump

Giriş arabelleğinin sonraki işaretçisine *sayı* ekleyen korumalı bir işlev.

```cpp
void gbump(int count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
İşaretçinin ilerleme miktarı.

## <a name="basic_streambufgetloc"></a><a name="getloc"></a> basic_streambuf:: getloc

Basic_streambuf nesnenin yerel ayarını alır.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan yerel ayar nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, bkz. [ios_base:: getloc](../standard-library/ios-base-class.md#getloc).

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

## <a name="basic_streambufgptr"></a><a name="gptr"></a> basic_streambuf:: gptr

Giriş arabelleğinin bir sonraki öğesine bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *gptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş arabelleğinin bir sonraki öğesine yönelik bir işaretçi.

## <a name="basic_streambufimbue"></a><a name="imbue"></a> basic_streambuf:: imbue

[Pubimbue](#pubimbue)tarafından çağrılan korumalı bir sanal işlev.

```cpp
virtual void imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*\
Bir yerel ayara başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış hiçbir şey yapmaz.

## <a name="basic_streambufin_avail"></a><a name="in_avail"></a> basic_streambuf:: in_avail

Arabellekten okunmaya izin veren öğe sayısını döndürür.

```cpp
streamsize in_avail();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekten okunmaya izin veren öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bir [okuma konumu](../standard-library/basic-streambuf-class.md) varsa, üye işlevi [egptr](#egptr)  -  [gptr](#gptr)döndürür. Aksi takdirde, [showmanyc](#showmanyc)döndürür.

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

## <a name="basic_streambufint_type"></a><a name="int_type"></a> basic_streambuf:: int_type

Basic_streambuf kapsam içindeki bir tür adını bir şablon parametresindeki türlerden biriyle ilişkilendirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_streambufoff_type"></a><a name="off_type"></a> basic_streambuf:: off_type

Basic_streambuf kapsam içindeki bir tür adını bir şablon parametresindeki türlerden biriyle ilişkilendirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_streambufoperator"></a><a name="op_eq"></a> basic_streambuf:: operator =

Bu nesnenin değerlerini başka bir `basic_streambuf` nesneden atar.

```cpp
basic_streambuf& operator=(const basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`basic_streambuf`Bu nesneye değer atamak için kullanılan nesneye bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işleci, giriş arabelleğini ve çıkış arabelleğini denetleyen işaretçilerin *sağına* kopyalar. Ayrıca `right.` , içinde [getloc ()](#getloc) depolar `locale object` . Döndürür **`*this`** .

## <a name="basic_streambufoverflow"></a><a name="overflow"></a> basic_streambuf:: overflow

Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya **traits_type::**[EOF](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, **traits_type:: EOF** döndürür veya bir özel durum oluşturur. Aksi takdirde, **traits_type::**[Not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *meta*) döndürür. Varsayılan davranış **traits_type:: EOF** döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Eğer *\_ meta* şuna eşit **traits_type:: EOF**, korumalı sanal üye işlevi endeavors **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(*\_ meta*) öğesini çıkış akışına eklemek için. Bunu çeşitli yollarla yapabilirsiniz:

- Bir varsa `write position` , öğeyi yazma konumuna saklayabilir ve çıkış arabelleği için bir sonraki işaretçiyi artırabilirsiniz.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak bir yazma konumu kullanılabilir hale getirir.

- Bir yazma konumunu, bazı dış hedeflere, bazı veya tüm öğeleri, çıkış arabelleğinin başlangıç ve sonraki işaretçileri arasında yazarak kullanılabilir hale getirebilirsiniz.

[Eşitleme](#sync) ve [yetersiz](#underflow) yer işlevleriyle birlikte sanal taşma işlevi, streamarabelleğe türetilmiş sınıfın özelliklerini tanımlar. Türetilmiş her sınıf farklı taşma uygulayabilir, ancak çağıran Stream sınıfına sahip arabirim aynıdır.

`overflow`İşlevi, `streambuf` PUT alanı dolduğunda ve gibi genel işlevler tarafından en sık çağrılır `sputc` `sputn` , ancak akış sınıfları dahil diğer sınıflar `overflow` her zaman çağırabilir.

İşlevi, ve işaretçileri arasındaki put alanındaki karakterleri kullanır `pbase` `pptr` ve ardından put alanını yeniden başlatır. `overflow`İşlevin Ayrıca kullanması gerekir `nCh` (değilse `nCh` `EOF` ) veya bir sonraki çağrıda tüketilebilmesi için bu karakteri yeni put alanına koymak tercih edebilir.

Tüketme tanımı türetilmiş sınıflar arasında farklılık gösterir. Örneğin, `filebuf` sınıfı dosyalarını bir dosyaya yazar, ancak `strstreambuf` sınıf bu dosyaları arabellekte tutar ve (arabellek dinamik olarak belirlendiyse), taşmaya bir çağrıya yanıt olarak arabelleği genişletir. Bu genişleme, eski arabelleği serbest bırakarak ve yeni, daha büyük bir ile değiştirilerek elde edilir. İşaretçiler gerektiği şekilde ayarlanır.

## <a name="basic_streambufpbackfail"></a><a name="pbackfail"></a> basic_streambuf::p geri başarısız

Giriş akışına bir öğe geri döndürmeye çalışan korumalı bir sanal üye işlevi, ardından bunu geçerli öğe yapın (sonraki işaretçi tarafından işaret edilen).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya **traits_type::**[EOF](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, **traits_type:: EOF** döndürür veya bir özel durum oluşturur. Aksi takdirde, başka bir değer döndürür. Varsayılan davranış **traits_type:: EOF** döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Eğer *\_ Meta* , **traits_type:: EOF** değerine eşitse, geri gönderme öğesi geçerli öğeden önceki akışta etkin bir şekilde zaten var. Aksi takdirde, bu öğe **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(*\_ meta*) ile değiştirilmiştir. İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- Bir Putback konumu varsa, öğesini putback konumuna saklayabilir ve giriş arabelleği için bir sonraki işaretçiyi azalsaklayabilir.

- Giriş arabelleği için yeni veya ek depolama alanı ayırarak bir Putback konumu kullanılabilir hale getirir.

- Ortak giriş ve Çıkış akışlarına sahip bir akış arabelleği için, bir geri alma konumunu, bazı dış hedeflere, bazı veya tüm öğeleri, çıkış arabelleğinin başlangıç ve sonraki işaretçileri arasında yazarak kullanılabilir hale getirebilirsiniz.

## <a name="basic_streambufpbase"></a><a name="pbase"></a> basic_streambuf::p tabanı

Çıkış arabelleğinin başlangıcına bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pbase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış arabelleğinin başlangıcına yönelik bir işaretçi.

## <a name="basic_streambufpbump"></a><a name="pbump"></a> basic_streambuf::p çarpın

Çıkış arabelleğinin sonraki işaretçisine *sayı* ekleyen korumalı bir işlev.

```cpp
void pbump(int count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Yazma konumunun ileri doğru taşınacağı karakter sayısı.

## <a name="basic_streambufpos_type"></a><a name="pos_type"></a> basic_streambuf::p os_type

Basic_streambuf kapsam içindeki bir tür adını bir şablon parametresindeki türlerden biriyle ilişkilendirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_streambufpptr"></a><a name="pptr"></a> basic_streambuf::p PTR

Çıkış arabelleğinin bir sonraki öğesine bir işaretçi döndüren korumalı bir işlev.

```cpp
char_type *pptr() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış arabelleğinin bir sonraki öğesine yönelik bir işaretçi.

## <a name="basic_streambufpubimbue"></a><a name="pubimbue"></a> basic_streambuf::p ubimbue

Basic_streambuf nesnenin yerel ayarını ayarlar.

```cpp
locale pubimbue(const locale& _Loc);
```

### <a name="parameters"></a>Parametreler

*_Loc*\
Bir yerel ayara başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yerel ayar nesnesinde depolanan önceki değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi _ *loc* ' i yerel ayar nesnesinde depolar ve [Imbue](#imbue)çağırır.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [basic_ios:: imbue](../standard-library/basic-ios-class.md#imbue) `pubimbue` .

## <a name="basic_streambufpubseekoff"></a><a name="pubseekoff"></a> basic_streambuf::p ubseekoff

Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [seekoff](#seekoff)öğesini çağırır.

```cpp
pos_type pubseekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*\
*_Way* göreli olarak arama konumu.

*_Way*\
Dengeleme işlemleri için başlangıç noktası. Olası değerler için bkz. [seekdir](../standard-library/ios-base-class.md#seekdir) .

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu veya geçersiz bir akış konumunu döndürür ( [seekoff](#seekoff)(_ *kapalı*, `_Way` , `_Which` )).

### <a name="remarks"></a>Açıklamalar

İşaretçiyi *_Way* göre kaydırır.

## <a name="basic_streambufpubseekpos"></a><a name="pubseekpos"></a> basic_streambuf::p ubseekpos

Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [seekpos](#seekpos)'u çağırır ve geçerli işaretçi konumunu sıfırlar.

```cpp
pos_type pubseekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konum veya geçersiz akış konumu. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile karşılaştırın `pos_type(off_type(-1))` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [seekpos](#seekpos)(_ *SP*,) döndürür `_Which` .

## <a name="basic_streambufpubsetbuf"></a><a name="pubsetbuf"></a> basic_streambuf::p ubsetarabelleğe

Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [setarabelleğe](#setbuf)çağırır.

```cpp
basic_streambuf<Elem, Tr> *pubsetbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
`char_type`Bu örnek oluşturma için bir işaretçi.

*biriktirme*\
Arabelleğin boyutu.

### <a name="return-value"></a>Dönüş Değeri

[Setarabelleğe](#setbuf)( `_Buffer` , `count` ) döndürür.

## <a name="basic_streambufpubsync"></a><a name="pubsync"></a> basic_streambuf::p ubsync

Türetilmiş bir sınıfta geçersiz kılınan korumalı bir sanal işlev olan [eşitleme](#sync)çağırır ve bu arabellekle ilişkili dış akışı güncelleştirir.

```cpp
int pubsync();
```

### <a name="return-value"></a>Dönüş Değeri

[Eşitleme](#sync) veya hata durumunda-1 döndürür.

## <a name="basic_streambufsbumpc"></a><a name="sbumpc"></a> basic_streambuf:: ssekmeli c

Akış işaretçisini taşıyarak geçerli öğeyi okur ve döndürür.

```cpp
int_type sbumpc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Bir okuma konumu varsa, üye işlevi **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( <strong>\*</strong> [gptr](#gptr)) döndürür ve giriş arabelleği için sonraki işaretçiyi arttırır. Aksi takdirde, [uflow](#uflow)döndürür.

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

## <a name="basic_streambufseekoff"></a><a name="seekoff"></a> basic_streambuf:: seekoff

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*\
*_Way* göreli olarak arama konumu.

*_Way*\
Dengeleme işlemleri için başlangıç noktası. Olası değerler için bkz. [seekdir](../standard-library/ios-base-class.md#seekdir) .

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu ya da geçersiz bir akış konumunu döndürür ( `seekoff` (_ *off*, `_Way` , `_Which` )).

### <a name="remarks"></a>Açıklamalar

Yeni konum aşağıdaki gibi belirlenir:

- İse `_Way`  ==  `ios_base::beg` , yeni konum akışın başlangıcının ve _ *kapalı* olur.

- İse `_Way`  ==  `ios_base::cur` , yeni konum geçerli akış konumu artı _ *kapalı*' dır.

- İse `_Way`  ==  `ios_base::end` , yeni konum akışın sonu artı _ *off* olur.

Genellikle, **& ios_base:: ın** sıfır değilse, giriş akışı etkilenir ve **hangi & ios_base:: Out** sıfır değilse, çıkış akışı etkilenir. Bu parametrenin gerçek kullanımı, türetilmiş akış arabellekleri arasında farklılık gösterir.

İşlev, akış konumunu veya konumlarını değiştirmek için başarılı olursa, sonuçta elde edilen akış konumunu veya sonuç akış konumlarından birini döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür. Varsayılan davranış, geçersiz bir akış konumu döndürmaktır.

## <a name="basic_streambufseekpos"></a><a name="seekpos"></a> basic_streambuf:: seekpos

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konum veya geçersiz akış konumu. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile karşılaştırın `pos_type(off_type(-1))` .

### <a name="remarks"></a>Açıklamalar

Yeni konum _ *SP*'dir.

Genellikle, **& ios_base:: ın** sıfır değilse, giriş akışı etkilenir ve **hangi & ios_base:: Out** sıfır değilse, çıkış akışı etkilenir. Bu parametrenin gerçek kullanımı, türetilmiş akış arabellekleri arasında farklılık gösterir.

İşlev, akış konumunu veya konumlarını değiştirmek için başarılı olursa, sonuçta elde edilen akış konumunu veya sonuç akış konumlarından birini döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür (-1). Varsayılan davranış, geçersiz bir akış konumu döndürmaktır.

## <a name="basic_streambufsetbuf"></a><a name="setbuf"></a> basic_streambuf:: setarabelleğe

Her türetilmiş akış arabelleğine özgü bir işlem gerçekleştiren korumalı bir sanal üye işlevi.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
Arabellek işaretçisi.

*biriktirme*\
Arabelleğin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan davranış döndürülür **`this`** .

### <a name="remarks"></a>Açıklamalar

Bkz. [basic_filebuf](../standard-library/basic-filebuf-class.md). `setbuf` nesnenin kullanacağı bir bellek alanı sağlar `streambuf` . Arabelleğin türetilmiş sınıflarda tanımlı olarak nasıl kullanıldığı.

## <a name="basic_streambufsetg"></a><a name="setg"></a> basic_streambuf:: setg

_ *Gbeg* 'yi başlangıç işaretçisine, `_Gnext` sonraki işaretçiye ve `_Gend` giriş arabelleğinin bitiş işaretçisine depolayan korumalı bir işlev.

```cpp
void setg(char_type* _Gbeg,
    char_type* _Gnext,
    char_type* _Gend);
```

### <a name="parameters"></a>Parametreler

*_Gbeg*\
Arabelleğin başlangıcına yönelik bir işaretçi.

*_Gnext*\
Arabelleğin ortasında bir yere işaretçi.

*_Gend*\
Arabelleğin sonuna yönelik bir işaretçi.

## <a name="basic_streambufsetp"></a><a name="setp"></a> basic_streambuf:: setp

Başlangıç İşaretçisinde *_Pbeg* depolayan ve çıkış arabelleğinin bitiş işaretçisindeki *_Pend* korunan bir işlev.

```cpp
void setp(char_type* _Pbeg, char_type* _Pend);
```

### <a name="parameters"></a>Parametreler

*_Pbeg*\
Arabelleğin başlangıcına yönelik bir işaretçi.

*_Pend*\
Arabelleğin sonuna yönelik bir işaretçi.

## <a name="basic_streambufsgetc"></a><a name="sgetc"></a> basic_streambuf:: sgetc

Akışta konum değişikliği yapmadan geçerli öğeyi döndürür.

```cpp
int_type sgetc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Bir okuma konumu varsa, üye işlevi **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `*` [gptr](#gptr)) döndürür. Aksi takdirde, bu, [yetersiz kalması](#underflow)sonucunu döndürür.

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

## <a name="basic_streambufsgetn"></a><a name="sgetn"></a> basic_streambuf:: sgetn

Giriş arabelleğinden karakter *sayısına* kadar ayıklar ve bunları, belirtilen arabellek *PTR* içinde depolar.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir.

```cpp
streamsize sgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Ayıklanan karakterleri içeren arabellek.

*biriktirme*\
Okunacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Okunan öğe sayısı. Daha fazla bilgi için bkz. [streamsize](../standard-library/ios-typedefs.md#streamsize) .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [xsgetn](#xsgetn)( `ptr` , `count` ) döndürür.

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

## <a name="basic_streambufshowmanyc"></a><a name="showmanyc"></a> basic_streambuf:: showmanyc

Giriş akışından ayıklanabilen karakter sayısının sayısını döndüren ve programın sonsuz bir beklemeye tabi olmamasını sağlamak için korunan bir sanal üye işlevi.

```cpp
virtual streamsize showmanyc();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan davranış sıfır değerini döndürmemelidir.

## <a name="basic_streambufsnextc"></a><a name="snextc"></a> basic_streambuf:: snextc

Geçerli öğeyi okur ve aşağıdaki öğeyi döndürür.

```cpp
int_type snextc();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki sonraki öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [ssekmeli c](#sbumpc) çağırır ve bu işlev **traits_type::**[EOF](../standard-library/char-traits-struct.md#eof)döndürürse, **traits_type:: EOF** döndürür. Aksi takdirde, [sgetc](#sgetc)döndürür.

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

## <a name="basic_streambufsputbackc"></a><a name="sputbackc"></a> basic_streambuf:: sputbackc

Akışa bir char_type koyar.

```cpp
int_type sputbackc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Karakter.

### <a name="return-value"></a>Dönüş Değeri

Karakteri veya hatayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bir Putback konumu kullanılabiliyorsa ve *_Ch* bu konumda depolanan karakterle eşit olarak karşılaştırıyorsa, üye işlevi giriş arabelleği için bir sonraki işaretçiyi azaltır ve **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `_Ch` ) döndürür. Aksi takdirde, [pbackfail](#pbackfail)( `_Ch` ) döndürür.

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

## <a name="basic_streambufsputc"></a><a name="sputc"></a> basic_streambuf:: sputc

Akışa bir karakter koyar.

```cpp
int_type sputc(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Karakter.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa karakteri döndürür.

### <a name="remarks"></a>Açıklamalar

Bir varsa `write position` , üye işlevi yazma konumunda *_Ch* depolar, çıkış arabelleği için sonraki işaretçiyi artırır ve **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `_Ch` ) döndürür. Aksi takdirde, [taşma](#overflow)( `_Ch` ) döndürür.

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

## <a name="basic_streambufsputn"></a><a name="sputn"></a> basic_streambuf:: sputn

Akışa bir karakter dizesi koyar.

```cpp
streamsize sputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Karakter dizesi.

*biriktirme*\
Karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Akışa gerçekten akışa yerleştirilmiş olan karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [xsputn](#xsputn)( `ptr` ,) döndürür `count` . Daha fazla bilgi için bu üyenin açıklamalar bölümüne bakın.

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

## <a name="basic_streambufstossc"></a><a name="stossc"></a> basic_streambuf:: stossc

Akıştaki geçerli öğeyi geçmiş olarak taşıyın.

```cpp
void stossc();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [stamponc](#sbumpc)çağırır. Bu üye işlevi sağlamak için bir uygulamanın gerekli olmadığına unutmayın.

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

## <a name="basic_streambufsungetc"></a><a name="sungetc"></a> basic_streambuf:: sungetc

Akıştan bir karakter alır.

```cpp
int_type sungetc();
```

### <a name="return-value"></a>Dönüş Değeri

Karakteri ya da başarısızlığı döndürür.

### <a name="remarks"></a>Açıklamalar

Bir Putback konumu kullanılabiliyorsa, üye işlevi giriş arabelleği için bir sonraki işaretçiyi azaltır ve `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `*` [gptr](#gptr)) döndürür. Ancak, geçerli arabelleğin yakalanabilmesi için son karakterin okunmasının belirlenmesi her zaman mümkün değildir. Bu doğruysa, işlev [pbackfail](#pbackfail)değerini döndürür. Bu durumdan kaçınmak için, geri dönüp çağrılacak karakteri takip edin, bu da `sputbackc(ch)` başarısız olmayacak ve bu, akışın başlangıcında çağırmazsınız ve birden fazla karakter geri yerleştirmenize çalışmayın.

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

## <a name="basic_streambufswap"></a><a name="swap"></a> basic_streambuf:: swap

Bu nesnedeki değerleri, belirtilen nesnedeki değerler için değiştirir `basic_streambuf` .

```cpp
void swap(basic_streambuf& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`basic_streambuf`Değer değişimi için kullanılan nesneye bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, ve ' i *denetleyen tüm* işaretçilerle birlikte değiş tokuş eder `input buffer` `output buffer` . Ayrıca `right.` , nesnesi ile [getloc ()](#getloc) öğesini de değiş tokuş eder `locale` .

## <a name="basic_streambufsync"></a><a name="sync"></a> basic_streambuf:: Sync

Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışan korumalı bir sanal işlev.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa,-1 döndürür. Varsayılan davranış sıfır değerini döndürmemelidir.

### <a name="remarks"></a>Açıklamalar

`sync` çıkış arabelleği için başlangıç ve sonraki işaretçiler arasındaki öğelerin yazılmasını içerir. Giriş arabelleğinin sonraki ve bitiş işaretçileri arasında herhangi bir öğenin geri yerleştirilmesi gerekmez.

## <a name="basic_streambuftraits_type"></a><a name="traits_type"></a> basic_streambuf:: traits_type

Bir tür adını **tr** şablon parametresiyle ilişkilendirir.

```cpp
typedef Tr traits_type;
```

## <a name="basic_streambufuflow"></a><a name="uflow"></a> basic_streambuf:: uflow

Giriş akışından geçerli öğeyi çıkaran korumalı bir sanal işlev.

```cpp
virtual int_type uflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş akışından o geçerli öğeyi çıkarmaya çalışır, sonra geçerli akış konumunu **ilerletin ve** öğeyi **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **ch**) olarak döndürür. Bunu çeşitli yollarla yapabilirsiniz:

- Bir okuma konumu varsa, okuma konumunda depolanan öğe **olarak girer** ve giriş arabelleği için sonraki işaretçiyi ilerletir.

- Bir öğeyi bir dış kaynaktan doğrudan okuyabilir ve bu değeri **ch** değeri olarak teslim edebilir.

- Ortak giriş ve Çıkış akışlarına sahip bir akış arabelleği için, bir okuma konumunu, bazı dış hedeflere, bazı veya tüm öğeleri, çıkış arabelleğinin başlangıç ve sonraki işaretçileri arasında yazarak kullanılabilir hale getirebilirsiniz. Ya da giriş arabelleği için yeni veya ek depolama alanı ayırabilirler. Daha sonra işlevi, bazı dış kaynaklardan, bir veya daha fazla öğeden ' de okur.

İşlev başarılı olmazsa, **traits_type::**[EOF](../standard-library/char-traits-struct.md#eof)döndürür veya bir özel durum oluşturur. Aksi halde, `ch` yukarıda açıklandığı gibi dönüştürülmüş olarak çevrilmiş şekilde, giriş akışındaki geçerli öğeyi döndürür ve giriş arabelleği için sonraki işaretçiyi ilerletir. Varsayılan davranış, [yetersiz kalması](#underflow) ve bu işlev **traits_type::** eof ' u döndürürse **traits_type:: EOF** döndürmek için kullanılır. Aksi takdirde, işlev giriş akışında **ch** öğesini döndürür, daha önce açıklandığı gibi dönüştürülür ve giriş arabelleği için sonraki işaretçiyi ilerletir.

## <a name="basic_streambufunderflow"></a><a name="underflow"></a> basic_streambuf:: yetersiz

Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğe.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, geçerli akış konumunu ilerlemeden ve  bunu `traits_type::` [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **ch**) olarak döndürecek şekilde, geçerli öğeyi giriş akışından ayıklamak için endeavors. Bunu çeşitli yollarla yapabilirsiniz:

- Bir okuma konumu varsa **ch** , okuma konumunda saklanan öğedir. Bunun hakkında daha fazla bilgi için [Basic_streambuf sınıfının](../standard-library/basic-streambuf-class.md)açıklamalar bölümüne bakın.

- Giriş arabelleği için yeni veya ek depolama alanı ayırarak, daha sonra bazı dış kaynaklardan, bir veya daha fazla öğeden okunarak bir okuma konumu kullanılabilir hale getirir. Bunun hakkında daha fazla bilgi için [Basic_streambuf sınıfının](../standard-library/basic-streambuf-class.md)açıklamalar bölümüne bakın.

İşlev başarılı olmazsa, `traits_type::` [EOF](../standard-library/char-traits-struct.md#eof) döndürür `()` veya bir özel durum oluşturur. Aksi halde, daha önce açıklandığı gibi çevrilmiş şekilde, giriş akışındaki geçerli öğeyi döndürür. Varsayılan davranış döndürülür `traits_type::eof()` .

`underflow` [Eşitleme](#sync) ve [taşma](#overflow) işlevleri ile sanal işlev, `streambuf` -türetilmiş sınıfın özelliklerini tanımlar. Her türetilmiş sınıf `underflow` farklı şekilde uygulayabilir, ancak çağıran Stream sınıfına sahip arabirim aynı olur.

`underflow`İşlevi, `streambuf` Get alanı boş olduğunda en sık [sgetc](#sgetc) ve [sgetn](#sgetn) gibi genel işlevlerle çağrılır, ancak Stream sınıfları dahil diğer sınıflar `underflow` her zaman çağırabilir.

`underflow`İşlevi, giriş kaynağındaki karakterlerle Get alanını sağlar. Get alanı karakterler içeriyorsa, `underflow` ilk karakteri döndürür. Get alanı boşsa, Get alanını doldurur ve sonraki karakteri (get alanında bırakır) döndürür. Kullanılabilecek daha fazla karakter yoksa, `underflow` `EOF` Get alanını boş bırakır.

`strstreambuf`Sınıfında, `underflow` bir çağrısıyla dinamik olarak ayrılan depolamaya erişmek için [egptr](#egptr) işaretçisini ayarlar `overflow` .

## <a name="basic_streambufxsgetn"></a><a name="xsgetn"></a> basic_streambuf:: xsgetn

Giriş akışından öğeleri ayıklamak için korumalı, sanal işlev.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir.

```cpp
virtual streamsize xsgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Ayıklanan karakterleri içeren arabellek.

*biriktirme*\
Ayıklanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayıklanan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş akışındaki öğeleri *saymak* için, yinelenen [ssekmeli c](#sbumpc)çağrıları tarafından olduğu gibi ayıklar ve bunları *PTR*'den başlayan dizide depolar. Aslında ayıklanan öğe sayısını döndürür.

## <a name="basic_streambufxsputn"></a><a name="xsputn"></a> basic_streambuf:: xsputn

Çıkış akışına öğe eklemek için korumalı, sanal işlev.

```cpp
virtual streamsize xsputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Eklenecek öğelere yönelik işaretçi.

*biriktirme*\
Eklenecek öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekten akışa ekli olan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi,, *PTR*'den başlayan diziden yinelenen [sputc](#sputc)çağrıları tarafından gösterildiği gibi, çıkış akışına en *fazla öğe ekler* . Çıkış akışına karakter ekleme, tüm *sayma* karakterleri yazıldıktan sonra veya çağırma `sputc( count)` geri dönebilmesine sonra duraklar `traits::eof()` . Gerçekte ekli olan öğe sayısını döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
