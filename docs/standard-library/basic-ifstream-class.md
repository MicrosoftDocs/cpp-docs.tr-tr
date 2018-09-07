---
title: basic_ifstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ifstream [C++]
- std::basic_ifstream [C++], close
- std::basic_ifstream [C++], is_open
- std::basic_ifstream [C++], open
- std::basic_ifstream [C++], rdbuf
- std::basic_ifstream [C++], swap
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63712f6eb7efd9c52db5480b7f13babe9601dea2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110233"
---
# <a name="basicifstream-class"></a>basic_ifstream Sınıfı

Öğelerin ayıklama denetleyen bir nesne ve bir akış arabelleğinin sınıfın kodlanmış nesnelerden açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ifstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Dosya tamponunun temel öğe.

*tr*<br/>
Temel öğesinin dosya arabelleğinin nitelikler (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi nesneyi depolar `basic_filebuf` <  `Elem`, `Tr`>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metin okuma gösterilmektedir.

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

## <a name="input-basicifstreamclasstxt"></a>Giriş: basic_ifstream_class.txt

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
|[basic_ifstream](#basic_ifstream)|Yeni bir örneğini başlatır bir `basic_ifstream` nesne.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosya açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanmış bir akış arabelleğinin adresini döndürür.|
|[değiştirme](#swap)|Bu içeriği birbiriyle değiştirir `basic_ifstream` içeriği sağlanan `basic_ifstream`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu akış nesnesi içeriğini atar. Bu, bir taşıma ataması ilgili bir `rvalue` , olmayan bir kopyasını gerisine bırakmak.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream >

**Namespace:** std

## <a name="basic_ifstream"></a>  basic_ifstream::basic_ifstream

Türünde bir nesne oluşturur `basic_ifstream`.

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_istream](../standard-library/basic-istream-class.md)( `sb`), burada `sb` depolanan nesne sınıfının [basic_filebuf](../standard-library/basic-filebuf-class.md) <  `Elem`, `Tr`>. Ayrıca başlatır `sb` çağırarak `basic_filebuf` <  `Elem`, `Tr`>.

İkinci ve üçüncü oluşturucular çağırarak temel sınıfı başlatır `basic_istream`( `sb`). Ayrıca başlatır `sb` çağırarak [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem`, `Tr`>, ardından `sb`. [Açık](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::in`). İkinci işlev bir null işaretçiyi döndürürse, oluşturucuyu çağırır **setstate**( `failbit`).

Dördüncü Oluşturucu içeriğini nesnesiyle başlatır `right`, bir rvalue başvurusu olarak kabul edilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir dosyadan metin okuma gösterilmektedir. Dosyayı oluşturmak için örnek için bkz. [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).

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

## <a name="close"></a>  basic_ifstream::Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](#rdbuf) **->** [kapatmak](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `close`.

## <a name="is_open"></a>  basic_ifstream::is_open

Bir dosya açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya açıksa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) kullanan bir örnek için `is_open`.

## <a name="open"></a>  basic_ifstream::Open

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](#rdbuf) **->** [açın](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124;  **ios_base::in**). Açık olan işlev çağrıları başarısız olursa [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`), hangi ios_base::failure özel durum throw.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) kullanan bir örnek için `open`.

## <a name="op_eq"></a>  basic_ifstream::operator =

Bu akış nesnesi içeriğini atar. Bir kopya bırakmaz arkasındaki bir rvalue içeren bir taşıma ataması budur.

```cpp
basic_ifstream& operator=(basic_ifstream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Rvalue başvurusuna bir `basic_ifstream` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `*this`.

### <a name="remarks"></a>Açıklamalar

İçeriğini kullanarak üye işleci nesnenin içeriğini değiştirir *doğru*, bir rvalue başvurusu olarak kabul edilir. Daha fazla bilgi için [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md).

## <a name="rdbuf"></a>  basic_ifstream::rdbuf

Depolanmış bir akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [basic_filebuf](../standard-library/basic-filebuf-class.md) saklı akış arabelleğini temsil eden nesne.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `rdbuf`.

## <a name="swap"></a>  basic_ifstream::Swap

İki içeriğini birbiriyle değiştirir `basic_ifstream` nesneleri.

```cpp
void swap(basic_ifstream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Başka bir akış arabelleği için bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi içeriğini bu nesnenin içeriğini değiştirir *doğru*.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
