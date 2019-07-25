---
title: basic_ofstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
ms.openlocfilehash: a73803f25c4fb9e54703b8bca93e68fedb63074e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452515"
---
# <a name="basicofstream-class"></a>basic_ofstream Sınıfı

Öğelerin ve kodlanmış nesnelerin [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem` `Elem`sınıfının bir akış arabelleğine eklenmesini ve karakter nitelikleri belirlenen tür öğeleri olan >olduğunudenetleyenbirnesneyiaçıklar`Tr` sınıf `Tr`tarafından.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Dosyaya `basic_ofstream` yazdığı **wchar_t** özelleştirmesi, dosya metin modunda açılırsa bir MBCS sırası yazar. İç gösterim, bir `wchar_t` karakter arabelleği kullanır.

`basic_filebuf`Nesnesi, <  >sınıfının`Elem`bir nesnesini depolar. `Tr`

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu ve `basic_ofstream` bir metnin nasıl yazılacağını gösterir.

```cpp
// basic_ofstream_class.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ofstream](#basic_ofstream)|Türünde `basic_ofstream`bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanan akış arabelleğinin adresini döndürür.|
|[Kur](#swap)|Bunun `basic_ofstream` içeriğini, belirtilen `basic_ofstream`içeriği için Exchange.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu Stream nesnesinin içeriğini atar. Bu, arkasında bir kopya bırakmayan `rvalue reference` bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<fstream >

**Ad alanı:** std

## <a name="basic_ofstream"></a>basic_ofstream::basic_ofstream

Türünde `basic_ofstream`bir nesne oluşturur.

```cpp
basic_ofstream();

explicit basic_ofstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ofstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_ofstream(
    basic_ofstream&& right);
```

### <a name="parameters"></a>Parametreler

*_Dosya adı*\
Açılacak dosyanın adı.

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, `shflag` [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)içindeki parametreye eşdeğerdir.

*Right*\
`basic_ofstream` Bu`basic_ofstream` nesneyi başlatmak için kullanılan nesneye rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu,`sb` [basic_filebuf](../standard-library/basic-filebuf-class.md) `sb` sınıfınınsaklı`Elem`nesnesi olan [basic_ostream](../standard-library/basic-ostream-class.md)() öğesini çağırarak temel sınıfı başlatır, burada >.`Tr`<  >`Tr`Çağırarak `basic_filebuf` `sb` dabaşlatılır`Elem`. < 

İkinci ve üçüncü oluşturucular, temel sınıfı çağırarak `basic_ostream`( **SB**) başlatır. Ayrıca `sb` , `basic_filebuf` >çağırarak<  vesonra`sb`da başlatılır. `Elem` `Tr` [Açık](../standard-library/basic-filebuf-class.md#open) ( `_Filename`, `_Mode` &#124; `ios_base::out`). İkinci işlev null bir işaretçi döndürürse, Oluşturucu [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır.

Dördüncü Oluşturucu bir kopyalama işlevidir. Nesneyi *sağ*içeriğiyle başlatır ve rvalue başvurusu olarak değerlendirilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu ve `basic_ofstream` bir metnin nasıl yazılacağını gösterir.

```cpp
// basic_ofstream_ctor.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("C:\\ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

## <a name="close"></a>basic_ofstream:: Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](../standard-library/basic-ifstream-class.md#rdbuf) **->** [Kapat](../standard-library/basic-filebuf-class.md#close)'ı çağırır.

### <a name="example"></a>Örnek

Tarafından kullanılan `close`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="is_open"></a>basic_ofstream::is_open

Bir dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya açıksa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ofstream_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   // Open and close with a basic_filebuf
   file.rdbuf( )->open( "basic_ofstream_is_open.txt", ios::in );
   file.close( );
   if (file.is_open())
      cout << "it's open" << endl;
   else
      cout << "it's closed" << endl;
}
```

## <a name="open"></a>basic_ofstream:: Open

Bir dosya açar.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Parametreler

*_Dosya adı*\
Açılacak dosyanın adı.

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, `shflag` [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)içindeki parametreye eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Açık](../standard-library/basic-filebuf-class.md#open)' ı (_ *filename*, `_Mode` &#124; `ios_base::out`) çağırır. Bu işlev null bir işaretçi döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) yöntemini çağırır.

### <a name="example"></a>Örnek

Tarafından kullanılan `open`bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) .

## <a name="op_eq"></a>basic_ofstream:: operator =

Bu Stream nesnesinin içeriğini atar. Bu, arkasında bir kopya bırakmayan `rvalue reference` bir taşıma atamasıdır.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_ofstream` nesneye rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `*this`.

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ*içeriğini kullanarak nesnesinin içeriğini değiştirir.

## <a name="rdbuf"></a>basic_ofstream:: rdarabelleğe

Depolanan akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleğinin adresini döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="swap"></a>basic_ofstream:: swap

İki `basic_ofstream` nesnenin içeriğini değiş tokuş eder.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`lvalue` Başka`basic_ofstream` bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin içeriğini *sağ*İçindekiler olarak değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[basic_ostream sınıfı](../standard-library/basic-ostream-class.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
