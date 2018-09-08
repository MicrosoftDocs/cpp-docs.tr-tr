---
title: basic_fstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_fstream [C++]
- std::basic_fstream [C++], close
- std::basic_fstream [C++], is_open
- std::basic_fstream [C++], open
- std::basic_fstream [C++], rdbuf
- std::basic_fstream [C++], swap
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b4712a76be411d237ee2abc97ddbdd4b67e57f2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108364"
---
# <a name="basicfstream-class"></a>basic_fstream Sınıfı

Ekleme ve çıkarma öğelerin denetleyen bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesne açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, öğelerini türle `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_fstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Dosya tamponunun temel öğe.

*tr*<br/>
Temel öğesinin dosya arabelleğinin nitelikler (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi nesneyi depolar `basic_filebuf` <  `Elem`, `Tr`>.

> [!NOTE]
> İşaretçi get ve put işaretçi fstream nesnenin **değil** birbirine bağımsızdır. Bu nedenle get işaretçi geçerse put işaretçisi yapar.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `basic_fstream` nesnesini okuyabileceği ve yazılan.

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
|[basic_fstream](#basic_fstream)|Türünde bir nesne oluşturur `basic_fstream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosya açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|İşaretçi türüne saklı akış arabelleğini adresini döndürür [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>.|
|[değiştirme](#swap)|Başka içeriğini bu nesnenin içeriğini değiştirir `basic_fstream` nesne.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream >

**Namespace:** std

## <a name="basic_fstream"></a>  basic_fstream::basic_fstream

Türünde bir nesne oluşturur `basic_fstream`.

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya *shflag* parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_iostream](../standard-library/basic-iostream-class.md)(`sb`), burada `sb` depolanan nesne sınıfının [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>. Ayrıca başlatır `sb` çağırarak `basic_filebuf` \< **Elem**, **Tr**>.

İkinci ve üçüncü oluşturucular çağırarak temel sınıfı başlatır `basic_iostream`( **sb**). Ayrıca başlatır `sb` çağırarak `basic_filebuf` \< **Elem**, **Tr**> ve ardından **sb.**[açın](../standard-library/basic-filebuf-class.md#open)() _ *Filename*, `_Mode`). İkinci işlev bir null işaretçiyi döndürürse, oluşturucuyu çağırır [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

Dördüncü Oluşturucu içeriğini nesnesiyle başlatır `right`, bir rvalue başvurusu olarak kabul edilir.

### <a name="example"></a>Örnek

Bkz: [streampos](../standard-library/ios-typedefs.md#streampos) kullanan bir örnek için `basic_fstream`.

## <a name="close"></a>  basic_fstream::Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](#rdbuf) **->** [kapatmak](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) nasıl kullanılacağına ilişkin bir örnek `close`.

## <a name="is_open"></a>  basic_fstream::is_open

Bir dosya açık olup olmadığını belirler.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya açıksa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) nasıl kullanılacağına ilişkin bir örnek `is_open`.

## <a name="open"></a>  basic_fstream::Open

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya *shflag* parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](#rdbuf) **->** [açın](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Bu işlev bir null işaretçiyi döndürürse, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( `failbit`).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) nasıl kullanılacağına ilişkin bir örnek `open`.

## <a name="op_eq"></a>  basic_fstream::operator =

Bu nesne için içeriği bir belirtilen stream nesnesi atar. Bir kopya bırakmaz arkasındaki bir rvalue içeren bir taşıma ataması budur.

```cpp
basic_fstream& operator=(basic_fstream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir lvalue başvurusuna bir `basic_fstream` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `*this`.

### <a name="remarks"></a>Açıklamalar

İçeriğini kullanarak üye işleci nesnenin içeriğini değiştirir *doğru*, bir rvalue başvurusu olarak kabul edilir.

## <a name="rdbuf"></a>  basic_fstream::rdbuf

İşaretçi türüne saklı akış arabelleğini adresini döndürür [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanmış bir akış arabelleğinin adresi.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) nasıl kullanılacağına ilişkin bir örnek `rdbuf`.

## <a name="swap"></a>  basic_fstream::Swap

İki içeriğini birbiriyle değiştirir `basic_fstream` nesneleri.

```cpp
void swap(basic_fstream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `lvalue` başvurusu bir `basic_fstream` nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin içeriğini ve içeriğini birbiriyle değiştirir *doğru*.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
