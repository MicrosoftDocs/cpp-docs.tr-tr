---
description: 'Hakkında daha fazla bilgi edinin: basic_fstream sınıfı'
title: basic_fstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
helpviewer_keywords:
- std::basic_fstream [C++]
- std::basic_fstream [C++], close
- std::basic_fstream [C++], is_open
- std::basic_fstream [C++], open
- std::basic_fstream [C++], rdbuf
- std::basic_fstream [C++], swap
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
ms.openlocfilehash: df8ad83696422737b5b368b39bf21c82506e8b65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321579"
---
# <a name="basic_fstream-class"></a>basic_fstream Sınıfı

[](../standard-library/basic-filebuf-class.md) <  `Elem` `Tr` `Elem` Karakter nitelikleri sınıfı tarafından belirlendiği şekilde, öğe basic_filebuf,>, türü öğeleri olan öğelerin ve ayıklamanın bir akış arabelleğini kullanarak ekleme ve ayıklamayı denetleyen bir nesne tanımlar `Tr` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_fstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Nesnesi `basic_filebuf` <  `Elem` ,> sınıfının bir nesnesini depolar `Tr` .

> [!NOTE]
> Bir fstream nesnesinin al işaretçisi ve put işaretçisi birbirinden bağımsız **değildir** . Al işaretçisi taşınırsa, put işaretçisini yapar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `basic_fstream` okunabilecek ve üzerine yazılabilen bir nesnenin nasıl oluşturulacağını gösterir.

```cpp
// basic_fstream_class.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);
    if (!fs.bad())
    {
        // Write to the file.
        fs << "Writing to a basic_fstream object..." << endl;
        fs.close();

        // Dump the contents of the file to cout.
        fs.open("fstream.txt", ios::in);
        cout << fs.rdbuf();
        fs.close();
    }
}
```

```Output
Writing to a basic_fstream object...
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_fstream](#basic_fstream)|Türünde bir nesne oluşturur `basic_fstream` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[~eksik](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[açın](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|[Basic_filebuf](../standard-library/basic-filebuf-class.md) <  ,> işaretçisi türünde depolanan akış arabelleğinin adresini döndürür `Elem` `Tr` .|
|[Kur](#swap)|Bu nesnenin içeriğini başka bir nesnenin içeriğiyle değiş tokuş eder `basic_fstream` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<fstream>

**Ad alanı:** std

## <a name="basic_fstreambasic_fstream"></a><a name="basic_fstream"></a> basic_fstream:: basic_fstream

Türünde bir nesne oluşturur `basic_fstream` .

```cpp
basic_fstream();

explicit basic_fstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```

### <a name="parameters"></a>Parametreler

*_Filename*\
Açılacak dosyanın adı.

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) *shflag* parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [](../standard-library/basic-iostream-class.md) `sb` `sb` [basic_filebuf](../standard-library/basic-filebuf-class.md)sınıfının saklı nesnesi olan basic_iostream () öğesini çağırarak temel sınıfı başlatır \< **Elem**, **Tr**> . Çağırarak da başlatılır `sb` `basic_filebuf` \< **Elem**, **Tr**> .

İkinci ve üçüncü oluşturucular, temel sınıfı çağırarak `basic_iostream` ( **SB**) başlatır. Ayrıca `sb` `basic_filebuf` \< **Elem**, **Tr**> , çağırarak ve sonra **SB.**[Open](../standard-library/basic-filebuf-class.md#open)(_ *filename*,) ile başlatılır `_Mode` . İkinci işlev null bir işaretçi döndürürse, Oluşturucu [SetState](../standard-library/basic-ios-class.md#setstate)() öğesini çağırır `failbit` .

Dördüncü Oluşturucu, nesnesini, `right` bir rvalue başvurusu olarak kabul edilen içeriğiyle başlatır.

### <a name="example"></a>Örnek

Kullanan bir örnek için bkz. [streampos](../standard-library/ios-typedefs.md#streampos) `basic_fstream` .

## <a name="basic_fstreamclose"></a><a name="close"></a> basic_fstream:: Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Kapat](../standard-library/basic-filebuf-class.md#close)'ı çağırır.

### <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `close` .

## <a name="basic_fstreamis_open"></a><a name="is_open"></a> basic_fstream:: is_open

Bir dosyanın açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** dosya açıksa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf:: is_open](../standard-library/basic-filebuf-class.md#is_open) nasıl kullanılacağına ilişkin bir örnek `is_open` .

## <a name="basic_fstreamopen"></a><a name="open"></a> basic_fstream:: Open

Bir dosya açar.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
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
Varsayılan dosya açma koruması, [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) *shflag* parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Açık](../standard-library/basic-filebuf-class.md#open)' ı (_ *filename*, `_Mode` ) çağırır. Bu işlev null bir işaretçi döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)() yöntemini çağırır `failbit` .

### <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) `open` .

## <a name="basic_fstreamoperator"></a><a name="op_eq"></a> basic_fstream:: operator =

Belirtilen Stream nesnesinden bu nesneye içerik atar. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_fstream& operator=(basic_fstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir nesneye lvalue başvurusu `basic_fstream` .

### <a name="return-value"></a>Dönüş Değeri

Döndürür **`*this`** .

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ* içeriğini kullanarak nesnesinin içeriğini değiştirir.

## <a name="basic_fstreamrdbuf"></a><a name="rdbuf"></a> basic_fstream:: rdarabelleğe

[Basic_filebuf](../standard-library/basic-filebuf-class.md)işaretçisinin türü olan depolanan akış arabelleğinin adresini döndürür \< **Elem**, **Tr**> .

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleğinin adresi.

### <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `rdbuf` .

## <a name="basic_fstreamswap"></a><a name="swap"></a> basic_fstream:: swap

İki nesnenin içeriğini değiş tokuş eder `basic_fstream` .

```cpp
void swap(basic_fstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`lvalue`Bir `basic_fstream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi bu nesnenin içeriğini ve *sağ* içeriğini değiş tokuş eder.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
