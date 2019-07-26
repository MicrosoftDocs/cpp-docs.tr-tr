---
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
ms.openlocfilehash: 8d26d0fe0e4e4152cf05476f546b753650209dfe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459595"
---
# <a name="basicfstream-class"></a>basic_fstream Sınıfı

[Basic_filebuf](../standard-library/basic-filebuf-class.md)<  sınıfınınbir`Elem`akış arabelleğini kullanarak öğeleri ve ayıklamayı ve kodlanmış nesneleri, türü öğeleri olan > `Tr``Elem` nitelikleri sınıfına `Tr`göre belirlenir.

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

`basic_filebuf`Nesnesi, <  >sınıfının`Elem`bir nesnesini depolar. `Tr`

> [!NOTE]
> Bir fstream nesnesinin al işaretçisi ve put işaretçisi birbirinden bağımsız **değildir** . Al işaretçisi taşınırsa, put işaretçisini yapar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, okunabilecek ve üzerine yazılabilen bir `basic_fstream` nesnenin nasıl oluşturulacağını gösterir.

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
|[basic_fstream](#basic_fstream)|Türünde `basic_fstream`bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|[Basic_filebuf](../standard-library/basic-filebuf-class.md)<  ,`Tr`>işaretçisi türünde depolanan akış arabelleğinin adresini döndürür.`Elem`|
|[Kur](#swap)|Bu nesnenin içeriğini başka bir `basic_fstream` nesnenin içeriğiyle değiş tokuş eder.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<fstream >

**Ad alanı:** std

## <a name="basic_fstream"></a>basic_fstream::basic_fstream

Türünde `basic_fstream`bir nesne oluşturur.

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

*_Dosya adı*\
Açılacak dosyanın adı.

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)içindeki *shflag* parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [basic_filebuf](../standard-library/basic-filebuf-class.md) `sb` `sb`   [](../standard-library/basic-iostream-class.md)eled,tr>sınıfınınsaklınesnesiolanbasic_iostream()öğesiniçağıraraktemelsınıfıbaşlatır.\< `sb` Ayrıca, **eled**, `basic_filebuf` **tr**> çağırarak \< da başlatılır.

İkinci ve üçüncü oluşturucular, temel sınıfı çağırarak `basic_iostream`( **SB**) başlatır. Ayrıca, `sb` **elee**, `basic_filebuf` **tr**> ve sonra **SB.** [Open](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode`) çağırarak \< da başlatılır. İkinci işlev null bir işaretçi döndürürse, Oluşturucu [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır.

Dördüncü Oluşturucu, nesnesini, bir rvalue başvurusu olarak kabul `right`edilen içeriğiyle başlatır.

### <a name="example"></a>Örnek

Kullanan`basic_fstream`bir örnek için bkz. [streampos](../standard-library/ios-typedefs.md#streampos) .

## <a name="close"></a>basic_fstream:: Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Kapat](../standard-library/basic-filebuf-class.md#close)'ı çağırır.

### <a name="example"></a>Örnek

Nasıl kullanılacağına `close`ilişkin bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="is_open"></a>basic_fstream::is_open

Bir dosyanın açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya açıksa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

Nasıl kullanılacağına `is_open`ilişkin bir örnek için bkz. [basic_filebuf:: is_open](../standard-library/basic-filebuf-class.md#is_open) .

## <a name="open"></a>basic_fstream:: Open

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

*_Dosya adı*\
Açılacak dosyanın adı.

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)içindeki *shflag* parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Açık](../standard-library/basic-filebuf-class.md#open)' ı (_ *filename*, `_Mode`) çağırır. Bu işlev null bir işaretçi döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)( `failbit`) yöntemini çağırır.

### <a name="example"></a>Örnek

Nasıl kullanılacağına `open`ilişkin bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) .

## <a name="op_eq"></a>basic_fstream:: operator =

Belirtilen Stream nesnesinden bu nesneye içerik atar. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_fstream& operator=(basic_fstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_fstream` nesneye lvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `*this`.

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ*içeriğini kullanarak nesnesinin içeriğini değiştirir.

## <a name="rdbuf"></a>basic_fstream:: rdarabelleğe

[Basic_filebuf](../standard-library/basic-filebuf-class.md) \< **eled**, **tr**> işaretçisi türünde depolanan akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleğinin adresi.

### <a name="example"></a>Örnek

Nasıl kullanılacağına `rdbuf`ilişkin bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="swap"></a>basic_fstream:: swap

İki `basic_fstream` nesnenin içeriğini değiş tokuş eder.

```cpp
void swap(basic_fstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`lvalue` Bir`basic_fstream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi bu nesnenin içeriğini ve *sağ*içeriğini değiş tokuş eder.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
