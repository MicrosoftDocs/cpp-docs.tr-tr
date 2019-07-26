---
title: basic_ifstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
helpviewer_keywords:
- std::basic_ifstream [C++]
- std::basic_ifstream [C++], close
- std::basic_ifstream [C++], is_open
- std::basic_ifstream [C++], open
- std::basic_ifstream [C++], rdbuf
- std::basic_ifstream [C++], swap
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
ms.openlocfilehash: 1e5e22c837ca2d6389591cec6d2cdd256ca50b1a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455511"
---
# <a name="basicifstream-class"></a>basic_ifstream Sınıfı

Öğelerinin ve kodlanmış nesnelerinin `Tr`> [](../standard-library/basic-filebuf-class.md)< `Elem` basic_filebufsınıfınınbirakışarabelleğindenayıklanmasınıvekarakter`Elem`nitelikleri olan sınıfı `Tr`tarafından belirlenir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ifstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

`basic_filebuf`Nesnesi, <  >sınıfının`Elem`bir nesnesini depolar. `Tr`

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metinde nasıl okunacağını gösterir.

```cpp
// basic_ifstream_class.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    ifstream ifs("basic_ifstream_class.txt");
    if (!ifs.bad())
    {
        // Dump the contents of the file to cout.
        cout << ifs.rdbuf();
        ifs.close();
    }
}
```

## <a name="input-basicifstreamclasstxt"></a>Giriş: basic_ifstream_class. txt

```cpp
This is the contents of basic_ifstream_class.txt.
```

## <a name="output"></a>Çıkış

```cpp
This is the contents of basic_ifstream_class.txt.
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ifstream](#basic_ifstream)|Bir `basic_ifstream` nesnenin yeni bir örneğini başlatır.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanan akış arabelleğinin adresini döndürür.|
|[Kur](#swap)|Bunun `basic_ifstream` içeriğini, belirtilen `basic_ifstream`içeriği için değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu Stream nesnesinin içeriğini atar. Bu, arkasında bir kopya bırakmayan `rvalue` bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<fstream >

**Ad alanı:** std

## <a name="basic_ifstream"></a>basic_ifstream::basic_ifstream

Türünde `basic_ifstream`bir nesne oluşturur.

```cpp
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```

### <a name="parameters"></a>Parametreler

*_Dosya adı*\
Açılacak dosyanın adı.

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, `shflag` [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)içindeki parametreye eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `sb` [basic_filebuf](../standard-library/basic-filebuf-class.md) `sb` sınıfınınsaklı`Elem`nesnesi olan [basic_istream](../standard-library/basic-istream-class.md)() öğesini çağırarak temel sınıfı başlatır, burada >.`Tr`<  >`Tr`Çağırarak `basic_filebuf` `sb` dabaşlatılır`Elem`. < 

İkinci ve üçüncü oluşturucular, ( `basic_istream` `sb`) öğesini çağırarak temel sınıfı başlatır. Ayrıca `sb` , [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)<  ve`Tr`>çağırarak da başlatılır .`sb``Elem` [Açık](../standard-library/basic-filebuf-class.md#open) ( `_Filename`, `_Mode` &#124; `ios_base::in`). İkinci işlev null bir işaretçi döndürürse, Oluşturucu **SetState**( `failbit`) öğesini çağırır.

Dördüncü Oluşturucu, nesnesini, bir rvalue başvurusu olarak kabul `right`edilen içeriğiyle başlatır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metinde nasıl okunacağını gösterir. Dosyayı oluşturmak için, [basic_ofstream:: basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream)örneğine bakın.

```cpp
// basic_ifstream_ctor.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    ifstream ifs("basic_ifstream_ctor.txt");
    if (!ifs.bad())
    {
        // Dump the contents of the file to cout.
        cout << ifs.rdbuf();
        ifs.close();
    }
}
```

## <a name="close"></a>basic_ifstream:: Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Kapat](../standard-library/basic-filebuf-class.md#close)'ı çağırır.

### <a name="example"></a>Örnek

Tarafından kullanılan `close`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="is_open"></a>basic_ifstream::is_open

Bir dosyanın açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya açıksa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `is_open`bir örnek için bkz. [basic_filebuf:: is_open](../standard-library/basic-filebuf-class.md#is_open) .

## <a name="open"></a>basic_ifstream:: Open

Bir dosya açar.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in,
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

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Açık](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode` &#124; **ios_base:: ın**) yöntemini çağırır. Open başarısız olursa, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır, bu da bir ios_base:: Failure özel durumu oluşturabilir.

### <a name="example"></a>Örnek

Tarafından kullanılan `open`bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) .

## <a name="op_eq"></a>basic_ifstream:: operator =

Bu Stream nesnesinin içeriğini atar. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_ifstream& operator=(basic_ifstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_ifstream` nesneye rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `*this`.

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ*içeriğini kullanarak nesnesinin içeriğini değiştirir. Daha fazla bilgi için bkz. [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md).

## <a name="rdbuf"></a>basic_ifstream:: rdarabelleğe

Depolanan akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleğini temsil eden bir [basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesine yönelik bir işaretçi.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="swap"></a>basic_ifstream:: swap

İki `basic_ifstream` nesnenin içeriğini değiş tokuş eder.

```cpp
void swap(basic_ifstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Başka bir akış arabelleğine başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin içeriğini *sağ*İçindekiler olarak değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
