---
description: 'Hakkında daha fazla bilgi edinin: basic_ofstream sınıfı'
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
ms.openlocfilehash: 10bb7ee14ea6b126ee907cbb8b56b3b3c31188a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325673"
---
# <a name="basic_ofstream-class"></a>basic_ofstream Sınıfı

Öğelerin ve kodlanmış nesnelerin, [](../standard-library/basic-filebuf-class.md) <  `Elem` `Tr` `Elem` karakter nitelikleri sınıf tarafından belirlendiği şekilde, türü öğelerin basic_filebuf,> `Tr` bir akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.

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

Dosya **`wchar_t`** yazma özelleştirmesi, `basic_ofstream` Dosya metin modunda açılırsa, bir MBCS sırası yazar. İç gösterim, bir karakter arabelleği kullanır **`wchar_t`** .

Nesnesi `basic_filebuf` <  `Elem` ,> sınıfının bir nesnesini depolar `Tr` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `basic_ofstream` ve bir metnin nasıl yazılacağını gösterir.

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
|[basic_ofstream](#basic_ofstream)|Türünde bir nesne oluşturur `basic_ofstream` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[~eksik](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[açın](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanan akış arabelleğinin adresini döndürür.|
|[Kur](#swap)|Bunun içeriğini, `basic_ofstream` belirtilen içeriği için Exchange `basic_ofstream` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bu Stream nesnesinin içeriğini atar. Bu, `rvalue reference` arkasında bir kopya bırakmayan bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<fstream>

**Ad alanı:** std

## <a name="basic_ofstreambasic_ofstream"></a><a name="basic_ofstream"></a> basic_ofstream:: basic_ofstream

Türünde bir nesne oluşturur `basic_ofstream` .

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
Varsayılan dosya açma koruması, `shflag` [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)parametresine eşdeğerdir.

*Right*\
`basic_ofstream`Bu nesneyi başlatmak için kullanılan nesneye rvalue başvurusu `basic_ofstream` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [](../standard-library/basic-ostream-class.md) `sb` `sb` [basic_filebuf](../standard-library/basic-filebuf-class.md)sınıfının saklı nesnesi olan> basic_ostream () çağırarak temel sınıfı başlatır <  `Elem` `Tr` . `sb`> çağırarak da başlatılır `basic_filebuf` <  `Elem` `Tr` .

İkinci ve üçüncü oluşturucular, temel sınıfı çağırarak `basic_ostream` ( **SB**) başlatır. Ayrıca `sb` `basic_filebuf` <  `Elem` , `Tr`> çağırarak ve sonra `sb` da başlatılır. [](../standard-library/basic-filebuf-class.md#open)( `_Filename` , `_Mode` &#124;) öğesini açın `ios_base::out` . İkinci işlev null bir işaretçi döndürürse, Oluşturucu [SetState](../standard-library/basic-ios-class.md#setstate)() öğesini çağırır `failbit` .

Dördüncü Oluşturucu bir kopyalama işlevidir. Nesneyi *sağ* içeriğiyle başlatır ve rvalue başvurusu olarak değerlendirilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `basic_ofstream` ve bir metnin nasıl yazılacağını gösterir.

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

## <a name="basic_ofstreamclose"></a><a name="close"></a> basic_ofstream:: Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](../standard-library/basic-ifstream-class.md#rdbuf) **->** [Kapat](../standard-library/basic-filebuf-class.md#close)'ı çağırır.

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `close` .

## <a name="basic_ofstreamis_open"></a><a name="is_open"></a> basic_ofstream:: is_open

Bir dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** dosya açıksa, **`false`** tersi durumda.

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

## <a name="basic_ofstreamopen"></a><a name="open"></a> basic_ofstream:: Open

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
Varsayılan dosya açma koruması, `shflag` [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Açık](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode` &#124;) yöntemini çağırır `ios_base::out` . Bu işlev null bir işaretçi döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)() yöntemini çağırır `failbit` .

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) `open` .

## <a name="basic_ofstreamoperator"></a><a name="op_eq"></a> basic_ofstream:: operator =

Bu Stream nesnesinin içeriğini atar. Bu, `rvalue reference` arkasında bir kopya bırakmayan bir taşıma atamasıdır.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir nesneye rvalue başvurusu `basic_ofstream` .

### <a name="return-value"></a>Dönüş Değeri

Döndürür **`*this`** .

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ* içeriğini kullanarak nesnesinin içeriğini değiştirir.

## <a name="basic_ofstreamrdbuf"></a><a name="rdbuf"></a> basic_ofstream:: rdarabelleğe

Depolanan akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleğinin adresini döndürür.

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `rdbuf` .

## <a name="basic_ofstreamswap"></a><a name="swap"></a> basic_ofstream:: swap

İki nesnenin içeriğini değiş tokuş eder `basic_ofstream` .

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`lvalue`Başka bir nesneye başvuru `basic_ofstream` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin içeriğini *sağ* İçindekiler olarak değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[basic_ostream sınıfı](../standard-library/basic-ostream-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
