---
title: basic_ofstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31637c1c194754e193970a4ff5efef500228115b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105256"
---
# <a name="basicofstream-class"></a>basic_ofstream Sınıfı

Sınıfı bir akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Dosya tamponunun temel öğe.

*tr*<br/>
Temel öğesinin dosya arabelleğinin nitelikler (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Zaman **wchar_t** alt uzmanlaşması `basic_ofstream` dosya metin modunda açılırsa, yazacak bir MBCS dizisi dosyasına yazar. İç gösterimine bir arabellek kullanacağı `wchar_t` karakter.

Sınıfın bir nesnesi nesneyi depolar `basic_filebuf` <  `Elem`, `Tr`>.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `basic_ofstream` nesnesi ve bir metin yazın.

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
|[basic_ofstream](#basic_ofstream)|Türünde bir nesne oluşturur `basic_ofstream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosya açık olup olmadığını belirler.|
|[open](#open)|Bir dosya açar.|
|[rdbuf](#rdbuf)|Depolanmış bir akış arabelleğinin adresini döndürür.|
|[değiştirme](#swap)|Bu içeriği exchange `basic_ofstream` sağlanan içeriklerinin `basic_ofstream`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu akış nesnesi içeriğini atar. Bu, bir taşıma ataması ilgili bir `rvalue reference` , olmayan bir kopyasını gerisine bırakmak.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream >

**Namespace:** std

## <a name="basic_ofstream"></a>  basic_ofstream::basic_ofstream

Türünde bir nesne oluşturur `basic_ofstream`.

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

*sağ*<br/>
Rvalue başvuru `basic_ofstream` bu başlatmak için kullanılan nesne `basic_ofstream` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_ostream](../standard-library/basic-ostream-class.md)(`sb`), burada `sb` depolanan nesne sınıfının [basic_filebuf](../standard-library/basic-filebuf-class.md) <  `Elem`, `Tr`>. Ayrıca başlatır `sb` çağırarak `basic_filebuf` <  `Elem`, `Tr`>.

İkinci ve üçüncü oluşturucular çağırarak temel sınıfı başlatır `basic_ostream`( **sb**). Ayrıca başlatır `sb` çağırarak `basic_filebuf` <  `Elem`, `Tr`> ardından `sb`. [Açık](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::out`). İkinci işlev bir null işaretçiyi döndürürse, oluşturucuyu çağırır [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

Dördüncü Oluşturucu bir kopya işlevidir. İçeriğini nesnesiyle başlatır *doğru*, bir rvalue başvurusu olarak kabul edilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `basic_ofstream` nesnesi ve bir metin yazın.

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

## <a name="close"></a>  basic_ofstream::Close

Bir dosyayı kapatır.

```cpp
void close();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[kapatmak](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `close`.

## <a name="is_open"></a>  basic_ofstream::is_open

Bir dosya açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya açıksa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open).

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

## <a name="open"></a>  basic_ofstream::Open

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](#rdbuf) **->** [açın](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; `ios_base::out` ). Bu işlev bir null işaretçiyi döndürürse, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) kullanan bir örnek için `open`.

## <a name="op_eq"></a>  basic_ofstream::operator =

Bu akış nesnesi içeriğini atar. Bu, bir taşıma ataması ilgili bir `rvalue reference` , olmayan bir kopyasını gerisine bırakmak.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Rvalue başvurusuna bir `basic_ofstream` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `*this`.

### <a name="remarks"></a>Açıklamalar

İçeriğini kullanarak üye işleci nesnenin içeriğini değiştirir *doğru*, bir rvalue başvurusu olarak kabul edilir.

## <a name="rdbuf"></a>  basic_ofstream::rdbuf

Depolanmış bir akış arabelleğinin adresini döndürür.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Depolanmış bir akış arabelleğinin adresini döndürür.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `rdbuf`.

## <a name="swap"></a>  basic_ofstream::Swap

İki içeriğini birbiriyle değiştirir `basic_ofstream` nesneleri.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `lvalue` başka bir başvuru `basic_ofstream` nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevi içeriğini bu nesnenin içeriğini değiştirir *doğru*.

## <a name="see-also"></a>Ayrıca bkz.

[basic_ostream Sınıfı](../standard-library/basic-ostream-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
