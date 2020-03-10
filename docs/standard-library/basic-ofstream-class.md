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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865879"
---
# <a name="basic_ofstream-class"></a>basic_ofstream Sınıfı

Öğelerin ve kodlanmış nesnelerin bir akış arabelleğine [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, karakter nitelikleri sınıf `Elem`tarafından belirlendiği şekilde, `Tr`türündeki öğeleri içeren bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Eled*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits`< `Elem`>).

## <a name="remarks"></a>Açıklamalar

`basic_ofstream` **wchar_t** özelleştirmesi dosyaya yazdığında, dosya metin modunda açılırsa, bir MBCS sırası yazar. İç gösterim `wchar_t` karakter arabelleği kullanır.

Nesnesi `basic_filebuf`< `Elem`, `Tr`> bir nesne saklar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `basic_ofstream` nesnesinin nasıl oluşturulduğunu ve ona nasıl metin yazılacağını gösterir.

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
|[basic_ofstream](#basic_ofstream)|`basic_ofstream`türünde bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanan akış arabelleğinin adresini döndürür.|
|[Kur](#swap)|Bu `basic_ofstream` içeriğini, belirtilen `basic_ofstream`içerikleri için Exchange.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bu Stream nesnesinin içeriğini atar. Bu, arkasında bir kopya bırakmayan bir `rvalue reference` içeren bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<fstream >

**Ad alanı:** std

## <a name="basic_ofstream"></a>basic_ofstream:: basic_ofstream

`basic_ofstream`türünde bir nesne oluşturur.

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

*_Filename*\
Açılacak dosyanın adı.

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, _fsopen `shflag` parametresine eşdeğer [_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

*sağ*\
Bu `basic_ofstream` nesnesini başlatmak için kullanılan `basic_ofstream` nesnesine rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu [basic_ostream](../standard-library/basic-ostream-class.md)(`sb`) çağırarak temel sınıfı başlatır; burada `sb`, [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> sınıfının saklı nesnesidir. Ayrıca, `basic_filebuf`< `Elem`, `Tr`> çağırarak `sb` başlatır.

İkinci ve üçüncü oluşturucular `basic_ostream`( **SB**) çağırarak temel sınıfı başlatır. Ayrıca, `basic_filebuf`< `Elem`, `Tr`> çağırarak ve ardından `sb``sb` başlatır. [açın](../standard-library/basic-filebuf-class.md#open)(`_Filename`, `_Mode` &#124; `ios_base::out`). İkinci işlev null bir işaretçi döndürürse, Oluşturucu [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır.

Dördüncü Oluşturucu bir kopyalama işlevidir. Nesneyi *sağ*içeriğiyle başlatır ve rvalue başvurusu olarak değerlendirilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir `basic_ofstream` nesnesinin nasıl oluşturulduğunu ve ona nasıl metin yazılacağını gösterir.

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

`close`kullanan bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="is_open"></a>basic_ofstream:: is_open

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

*_Filename*\
Açılacak dosyanın adı.

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, _fsopen `shflag` parametresine eşdeğer [_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode` &#124; `ios_base::out`) yöntemini çağırır. Bu işlev null bir işaretçi döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır.

### <a name="example"></a>Örnek

`open`kullanan bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) .

## <a name="op_eq"></a>basic_ofstream:: operator =

Bu Stream nesnesinin içeriğini atar. Bu, arkasında bir kopya bırakmayan bir `rvalue reference` içeren bir taşıma atamasıdır.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
`basic_ofstream` nesnesine bir rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

`*this` döndürür.

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

`rdbuf`kullanan bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="swap"></a>basic_ofstream:: swap

İki `basic_ofstream` nesnesinin içeriğini değiş tokuş eder.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
`lvalue` başka bir `basic_ofstream` nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin içeriğini *sağ*İçindekiler olarak değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[basic_ostream sınıfı](../standard-library/basic-ostream-class.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
