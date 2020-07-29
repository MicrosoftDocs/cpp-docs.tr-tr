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
ms.openlocfilehash: f4f5ddd3d1c0c595dd1661fab73f5267fb161593
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219293"
---
# <a name="basic_ifstream-class"></a>basic_ifstream Sınıfı

[basic_filebuf](../standard-library/basic-filebuf-class.md) <  `Elem` `Tr` `Elem` Karakter nitelikleri sınıfı tarafından belirlendiği şekilde, öğe basic_filebuf,>, türü öğelerin bir akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar `Tr` .

## <a name="syntax"></a>Söz dizimi

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

Nesnesi `basic_filebuf` <  `Elem` ,> sınıfının bir nesnesini depolar `Tr` .

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

## <a name="input-basic_ifstream_classtxt"></a>Giriş: basic_ifstream_class.txt

```cpp
This is the contents of basic_ifstream_class.txt.
```

## <a name="output"></a>Çıktı

```cpp
This is the contents of basic_ifstream_class.txt.
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ifstream](#basic_ifstream)|Bir nesnenin yeni bir örneğini başlatır `basic_ifstream` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[~eksik](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|
|[açın](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanan akış arabelleğinin adresini döndürür.|
|[Kur](#swap)|Bunun içeriğini, `basic_ifstream` belirtilen içeriği için değiştirir `basic_ifstream` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bu Stream nesnesinin içeriğini atar. Bu, `rvalue` arkasında bir kopya bırakmayan bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<fstream>

**Ad alanı:** std

## <a name="basic_ifstreambasic_ifstream"></a><a name="basic_ifstream"></a>basic_ifstream:: basic_ifstream

Türünde bir nesne oluşturur `basic_ifstream` .

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

*_Filename*\
Açılacak dosyanın adı.

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, `shflag` [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [basic_istream](../standard-library/basic-istream-class.md) `sb` `sb` [basic_filebuf](../standard-library/basic-filebuf-class.md)sınıfının saklı nesnesi olan> basic_istream () çağırarak temel sınıfı başlatır <  `Elem` `Tr` . `sb`> çağırarak da başlatılır `basic_filebuf` <  `Elem` `Tr` .

İkinci ve üçüncü oluşturucular, () öğesini çağırarak temel sınıfı `basic_istream` başlatır `sb` . `sb` [Basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf) <  `Elem` , `Tr`> çağırarak da başlatılır `sb` . [open](../standard-library/basic-filebuf-class.md#open)( `_Filename` , `_Mode` &#124;) öğesini açın `ios_base::in` . İkinci işlev null bir işaretçi döndürürse, Oluşturucu **SetState**() öğesini çağırır `failbit` .

Dördüncü Oluşturucu, nesnesini, `right` bir rvalue başvurusu olarak kabul edilen içeriğiyle başlatır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metinde nasıl okunacağını gösterir. Dosyayı oluşturmak için [basic_ofstream:: basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream)örneğine bakın.

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

## <a name="basic_ifstreamclose"></a><a name="close"></a>basic_ifstream:: Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Kapat](../standard-library/basic-filebuf-class.md#close)'ı çağırır.

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `close` .

## <a name="basic_ifstreamis_open"></a><a name="is_open"></a>basic_ifstream:: is_open

Bir dosyanın açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** dosya açıksa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [basic_filebuf:: is_open](../standard-library/basic-filebuf-class.md#is_open) `is_open` .

## <a name="basic_ifstreamopen"></a><a name="open"></a>basic_ifstream:: Open

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

*_Filename*\
Açılacak dosyanın adı.

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, `shflag` [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) **->** [Açık](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode` &#124; **ios_base:: ın**) yöntemini çağırır. Open başarısız olursa, işlev [SetState](../standard-library/basic-ios-class.md#setstate)() yöntemini çağırır `failbit` . bu, bir ios_base:: hata özel durumu oluşturabilir.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) `open` .

## <a name="basic_ifstreamoperator"></a><a name="op_eq"></a>basic_ifstream:: operator =

Bu Stream nesnesinin içeriğini atar. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_ifstream& operator=(basic_ifstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir nesneye rvalue başvurusu `basic_ifstream` .

### <a name="return-value"></a>Dönüş Değeri

Döndürür **`*this`** .

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ*içeriğini kullanarak nesnesinin içeriğini değiştirir. Daha fazla bilgi için bkz. [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md).

## <a name="basic_ifstreamrdbuf"></a><a name="rdbuf"></a>basic_ifstream:: rdarabelleğe

Depolanan akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleğini temsil eden [basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesine yönelik bir işaretçi.

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `rdbuf` .

## <a name="basic_ifstreamswap"></a><a name="swap"></a>basic_ifstream:: swap

İki nesnenin içeriğini değiş tokuş eder `basic_ifstream` .

```cpp
void swap(basic_ifstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Başka bir akış arabelleğine başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin içeriğini *sağ*İçindekiler olarak değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
