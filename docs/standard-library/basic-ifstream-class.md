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
ms.openlocfilehash: 85a315ee393a002da4d0999569d4af6c34a37ee3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376840"
---
# <a name="basic_ifstream-class"></a>basic_ifstream Sınıfı

Basic_filebuf [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`bir akış arabellesinden öğelerin ve kodlanmış nesnelerin ayıklamalarını kontrol eden bir nesneyi açıklar>, `Tr` `Elem`karakter özellikleri sınıf `Tr`tarafından belirlenir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ifstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleği temel öğesi.

*Tr*\
Dosya arabelleği temel öğesinin özellikleri `char_traits` <  `Elem` (genellikle>).

## <a name="remarks"></a>Açıklamalar

Nesne `basic_filebuf` <  `Elem`sınıf bir nesne `Tr` depolar ,>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metin olarak nasıl okunduğunu gösterir.

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
|[basic_ifstream](#basic_ifstream)|`basic_ifstream` Nesnenin yeni bir örneğini başolarak karşılar.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Yakın](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Dosyanın açık olup olmadığını belirler.|
|[açık](#open)|Bir dosyayı açar.|
|[Rdbuf](#rdbuf)|Depolanan akış arabelleği adresini döndürür.|
|[Takas](#swap)|Sağlanan `basic_ifstream`içeriği için `basic_ifstream` bu içeriği alışverişi .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bu akış nesnesinin içeriğini atar. Bu, bir kopyasını `rvalue` geride bırakmayan bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream>

**Ad alanı:** std

## <a name="basic_ifstreambasic_ifstream"></a><a name="basic_ifstream"></a>basic_ifstream:basic_ifstream

Türünde `basic_ifstream`bir nesne oluşturuyor.

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
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Varsayılan dosya açma koruması, `shflag` _fsopen parametreye [eşdeğer, _wfsopen.](../c-runtime-library/reference/fsopen-wfsopen.md)

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, [sınıf](../standard-library/basic-istream-class.md) [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> depolanan `sb` nesne basic_istream ( `sb`), çağırarak taban sınıf ı devreye ait. Ayrıca `sb` , `basic_filebuf` <  `Tr`> arayarak `Elem`da baş harfe çevrilir.

İkinci ve üçüncü yapıcılar ( `basic_istream` `sb`) çağırarak taban sınıfı başharflerini `sb` Ayrıca [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem`arayarak, `Tr`>, sonra. `sb` [açık](../standard-library/basic-filebuf-class.md#open) `_Filename`( `_Mode` `ios_base::in`, &#124; ). İkinci işlev bir null işaretçisi döndürürse, oluşturucu **setstate**() `failbit`çağırır.

Dördüncü oluşturucu, bir rvalue başvurusu `right`olarak kabul edilen içeriği yle nesneyi başharfe ait hale sağlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metin olarak nasıl okunduğunu gösterir. Dosyayı oluşturmak için [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream)için örneğe bakın.

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

## <a name="basic_ifstreamclose"></a><a name="close"></a>basic_ifstream::kapat

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close)çağırır.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `close`bir örnek için kapat.

## <a name="basic_ifstreamis_open"></a><a name="is_open"></a>basic_ifstream::is_open

Dosyanın açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya açıksa **doğru,** aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) kullanan `is_open`bir örnek için.

## <a name="basic_ifstreamopen"></a><a name="open"></a>basic_ifstream::açık

Bir dosyayı açar.

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
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Varsayılan dosya açma koruması, `shflag` _fsopen parametreye [eşdeğer, _wfsopen.](../c-runtime-library/reference/fsopen-wfsopen.md)

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [açık](../standard-library/basic-filebuf-class.md#open)çağırır (_ *Dosya Adı*, `_Mode` &#124; **ios_base::in).** Açık başarısız olursa, işlev [setstate](../standard-library/basic-ios-class.md#setstate)(),`failbit`bir ios_base atabilir çağırır::hata özel durumu.

### <a name="example"></a>Örnek

[Bkz. basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#open) `open`bir örnek için açık.

## <a name="basic_ifstreamoperator"></a><a name="op_eq"></a>basic_ifstream::operator=

Bu akış nesnesinin içeriğini atar. Bu, bir kopyasını geride bırakmayan bir rvalue içeren bir taşıma atamasIdır.

```cpp
basic_ifstream& operator=(basic_ifstream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `basic_ifstream` nesneye rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

`*this` döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleç, nesnenin *içeriğini, rvalue*referansı olarak kabul edilen sağın içeriğini kullanarak değiştirir. Daha fazla bilgi için [Lvalues ve Rvalues'e](../cpp/lvalues-and-rvalues-visual-cpp.md)bakın.

## <a name="basic_ifstreamrdbuf"></a><a name="rdbuf"></a>basic_ifstream::rdbuf

Depolanan akış arabelleği adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleği temsil eden [bir basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesi için bir işaretçi.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `rdbuf`bir örnek için kapat.

## <a name="basic_ifstreamswap"></a><a name="swap"></a>basic_ifstream::takas

İki `basic_ifstream` nesnenin içeriğini değiştirir.

```cpp
void swap(basic_ifstream& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Başka bir akış arabelleği için bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlev, bu nesnenin içeriğini *sağın*içeriği yle değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
