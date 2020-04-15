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
ms.openlocfilehash: f2d0facd92e0ef1935f8218a6d323a62edb81e5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376788"
---
# <a name="basic_ofstream-class"></a>basic_ofstream Sınıfı

Öğelerin ve kodlanmış nesnelerin sınıf [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`bir akış arabelleği içine eklemeyi `Tr` kontrol eden bir `Elem`nesne açıklar ,>, `Tr`tür öğeleri ile , olan karakter özellikleri sınıf tarafından belirlenir .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleği temel öğesi.

*Tr*\
Dosya arabelleği temel öğesinin özellikleri `char_traits` <  `Elem` (genellikle>).

## <a name="remarks"></a>Açıklamalar

**Dosyaya** yazmanın `basic_ofstream` wchar_t uzmanlığı, dosya metin modunda açıldığında bir MBCS dizisi yazar. İç gösterim, `wchar_t` bir karakter arabelleği kullanır.

Nesne `basic_filebuf` <  `Elem`sınıf bir nesne `Tr` depolar ,>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `basic_ofstream` nesnenin nasıl oluşturulup ona metin yazılmasıgerektiğini gösterir.

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

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Yakın](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Dosyanın açık olup olmadığını belirler.|
|[açık](#open)|Bir dosyayı açar.|
|[Rdbuf](#rdbuf)|Depolanan akış arabelleği adresini döndürür.|
|[Takas](#swap)|Sağlanan `basic_ofstream`içeriği için `basic_ofstream` bu içeriğini değiştirin.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bu akış nesnesinin içeriğini atar. Bu, bir kopyasını `rvalue reference` geride bırakmayan bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream>

**Ad alanı:** std

## <a name="basic_ofstreambasic_ofstream"></a><a name="basic_ofstream"></a>basic_ofstream::basic_ofstream

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

*_Filename*\
Açılacak dosyanın adı.

*_Mode*\
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Varsayılan dosya açma koruması, `shflag` _fsopen parametreye [eşdeğer, _wfsopen.](../c-runtime-library/reference/fsopen-wfsopen.md)

*Doğru*\
Bu `basic_ofstream` `basic_ofstream` nesneyi başlatmada kullanılan nesnenin rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, [sınıf](../standard-library/basic-ostream-class.md) [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> depolanan `sb` nesne basic_ostream (`sb`), çağırarak taban sınıf ı devreye ait. Ayrıca `sb` , `basic_filebuf` <  `Tr`> arayarak `Elem`da baş harfe çevrilir.

İkinci ve üçüncü yapıcılar ( **sb)** `basic_ostream`çağırarak taban sınıfı başharflerine Ayrıca arayarak, `sb` `basic_filebuf` <  `Elem` `Tr`> ve sonra `sb`baş harflerini de. [açık](../standard-library/basic-filebuf-class.md#open) `_Filename`( `_Mode` `ios_base::out`, &#124; ). İkinci işlev bir null işaretçisi döndürürse, oluşturucu [setstate](../standard-library/basic-ios-class.md#setstate)()`failbit`çağırır.

Dördüncü oluşturucu bir kopyalama işlevidir. Nesneyi, rvalue referansı olarak kabul edilen *sağın*içeriğiyle başharfe salar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir `basic_ofstream` nesnenin nasıl oluşturulup ona metin yazılmasıgerektiğini gösterir.

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

## <a name="basic_ofstreamclose"></a><a name="close"></a>basic_ofstream::kapat

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[close](../standard-library/basic-filebuf-class.md#close)çağırır.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `close`bir örnek için kapat.

## <a name="basic_ofstreamis_open"></a><a name="is_open"></a>basic_ofstream:is_open

Dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya açıksa **doğru,** aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

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

## <a name="basic_ofstreamopen"></a><a name="open"></a>basic_ofstream::açık

Bir dosyayı açar.

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
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Varsayılan dosya açma koruması, `shflag` _fsopen parametreye [eşdeğer, _wfsopen.](../c-runtime-library/reference/fsopen-wfsopen.md)

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [açık](../standard-library/basic-filebuf-class.md#open)çağırır (_ *Dosya Adı*, `_Mode` &#124; `ios_base::out`). Bu işlev bir null işaretçisi döndürürse, işlev [setstate](../standard-library/basic-ios-class.md#setstate)()`failbit`çağırır.

### <a name="example"></a>Örnek

[Bkz. basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#open) `open`bir örnek için açık.

## <a name="basic_ofstreamoperator"></a><a name="op_eq"></a>basic_ofstream::operator=

Bu akış nesnesinin içeriğini atar. Bu, bir kopyasını `rvalue reference` geride bırakmayan bir taşıma atamasıdır.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `basic_ofstream` nesneye rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

`*this` döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleç, nesnenin *içeriğini, rvalue*referansı olarak kabul edilen sağın içeriğini kullanarak değiştirir.

## <a name="basic_ofstreamrdbuf"></a><a name="rdbuf"></a>basic_ofstream::rdbuf

Depolanan akış arabelleği adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleği adresini döndürür.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `rdbuf`bir örnek için kapat.

## <a name="basic_ofstreamswap"></a><a name="swap"></a>basic_ofstream::takas

İki `basic_ofstream` nesnenin içeriğini değiştirir.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Başka `lvalue` bir `basic_ofstream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlev, bu nesnenin içeriğini *sağın*içeriği yle değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[basic_ostream Sınıfı](../standard-library/basic-ostream-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
