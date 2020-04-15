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
ms.openlocfilehash: 80992430d6bef6fc46106452dfaa44cc0ed9e71c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376855"
---
# <a name="basic_fstream-class"></a>basic_fstream Sınıfı

Sınıf [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`bir akış arabelleği kullanarak öğeleri ve kodlanmış nesnelerin ekleme ve ayıklama kontrol eden bir nesne açıklar , `Tr`>, türü `Elem`öğeleri ile , olan karakter özellikleri sınıf `Tr`tarafından belirlenir .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_fstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleği temel öğesi.

*Tr*\
Dosya arabelleği temel öğesinin özellikleri `char_traits` <  `Elem` (genellikle>).

## <a name="remarks"></a>Açıklamalar

Nesne `basic_filebuf` <  `Elem`sınıf bir nesne `Tr` depolar ,>.

> [!NOTE]
> Bir fstream nesnesinin işaretçisi ve koymak işaretçisi birbirinden bağımsız **DeğİlDIR.** Al işaretçisi hareket ederse, put işaretçisi de hareket eder.

## <a name="example"></a>Örnek

Aşağıdaki örnek, okunabilir ve `basic_fstream` yazılabilir bir nesnenin nasıl oluşturulabileceğini gösterir.

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
|[Basic_fstream](#basic_fstream)|Türünde `basic_fstream`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Yakın](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Dosyanın açık olup olmadığını belirler.|
|[açık](#open)|Bir dosyayı açar.|
|[Rdbuf](#rdbuf)|Depolanan akış arabelleği adresini, tür işaretçisinin `Tr` [adresini basic_filebuf,](../standard-library/basic-filebuf-class.md)< `Elem`> verir.|
|[Takas](#swap)|Bu nesnenin içeriğini başka bir `basic_fstream` nesnenin içeriğiyle değiştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream>

**Ad alanı:** std

## <a name="basic_fstreambasic_fstream"></a><a name="basic_fstream"></a>basic_fstream:basic_fstream

Türünde `basic_fstream`bir nesne oluşturuyor.

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
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Varsayılan dosya açma koruması, [_fsopen'daki](../c-runtime-library/reference/fsopen-wfsopen.md) *_wfsopen'* daki dalga parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, [basic_iostream](../standard-library/basic-iostream-class.md)`sb`( `sb` ), [basic_filebuf](../standard-library/basic-filebuf-class.md) \< sınıfın depolanan nesnesi olan **Elem**, **Tr**>'i arayarak taban sınıfı devreye sarar. Ayrıca `sb` `basic_filebuf` \< **Elem,** **Tr**> arayarak da baş harflerini karşılar.

İkinci ve üçüncü yapıcılar ( **sb)** `basic_iostream`çağırarak taban sınıfı başharflerine Ayrıca `sb` `basic_filebuf` \< **Elem,** **Tr**>' yi arayarak ve sonra **sb.** `_Mode`[open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, ) adlarını arayarak da açılır. İkinci işlev bir null işaretçisi döndürürse, oluşturucu [setstate](../standard-library/basic-ios-class.md#setstate)()`failbit`çağırır.

Dördüncü oluşturucu, bir rvalue başvurusu `right`olarak kabul edilen içeriği yle nesneyi başharfe ait hale sağlar.

### <a name="example"></a>Örnek

Kullanan `basic_fstream`bir örnek için [akış şekillerine](../standard-library/ios-typedefs.md#streampos) bakın.

## <a name="basic_fstreamclose"></a><a name="close"></a>basic_fstream::kapat

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close)çağırır.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::nasıl](../standard-library/basic-filebuf-class.md#close) kullanılacağına `close`bir örnek için kapatın.

## <a name="basic_fstreamis_open"></a><a name="is_open"></a>basic_fstream:is_open

Dosyanın açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya açıksa **doğru,** aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open)döndürür.

### <a name="example"></a>Örnek

[Bkz. basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) nasıl kullanılacağına `is_open`bir örnek için.

## <a name="basic_fstreamopen"></a><a name="open"></a>basic_fstream::açık

Bir dosyayı açar.

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
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Varsayılan dosya açma koruması, [_fsopen'daki](../c-runtime-library/reference/fsopen-wfsopen.md) *_wfsopen'* daki dalga parametresine eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) **->** [açık](../standard-library/basic-filebuf-class.md#open)çağırır (_ *Dosya Adı*, `_Mode`). Bu işlev bir null işaretçisi döndürürse, işlev [setstate](../standard-library/basic-ios-class.md#setstate)() `failbit`çağırır.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::nasıl](../standard-library/basic-filebuf-class.md#open) kullanılacağına `open`bir örnek için açın.

## <a name="basic_fstreamoperator"></a><a name="op_eq"></a>basic_fstream::operator=

Bu nesneye içeriği belirtilen bir akış nesnesinden atar. Bu, bir kopyasını geride bırakmayan bir rvalue içeren bir taşıma atamasIdır.

```cpp
basic_fstream& operator=(basic_fstream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `basic_fstream` nesneye bir lvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

`*this` döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleç, nesnenin *içeriğini, rvalue*referansı olarak kabul edilen sağın içeriğini kullanarak değiştirir.

## <a name="basic_fstreamrdbuf"></a><a name="rdbuf"></a>basic_fstream::rdbuf

Depolanan akış arabelleği adresini, basic_filebuf [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem,** **Tr**> türü işaretçisi adresini verir.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış arabelleği adresi.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::nasıl](../standard-library/basic-filebuf-class.md#close) kullanılacağına `rdbuf`bir örnek için kapatın.

## <a name="basic_fstreamswap"></a><a name="swap"></a>basic_fstream::takas

İki `basic_fstream` nesnenin içeriğini değiştirir.

```cpp
void swap(basic_fstream& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `lvalue` `basic_fstream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlev, bu nesnenin içeriğini ve *sağın*içeriğini değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
