---
title: basic_stringstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60a12c18ec4e174087900f7386d948ea3ab16a89
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102492"
---
# <a name="basicstringstream-class"></a>basic_stringstream Sınıfı

Ekleme ve çıkarma öğelerin denetleyen bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesne açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*<br/>
Ayırıcı sınıf.

*Elem*<br/>
Dizenin temel öğe türü.

*tr*<br/>
Karakter nitelikleri temel dize öğesinde anlayışıyla çalışır.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, denetimleri ekleme ve çıkarma öğelerin bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesneleri tanımlar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, ve öğeleri bir sınıf ayırıcısı tarafından ayrılan `Alloc`. Basic_stringbuf sınıfı bir nesnenin nesneyi depolar < **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringstream](#basic_stringstream)|Türünde bir nesne oluşturur `basic_stringstream`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eşanlamlı türüdür `Alloc`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_stringstream::allocator_type

Şablon parametresi için bir eşanlamlı türüdür `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstream"></a>  basic_stringstream::basic_stringstream

Türünde bir nesne oluşturur `basic_stringstream`.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*<br/>
Bir nesne türü `basic_string`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**), burada `sb` depolanan nesne sınıfının [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**, **Tr**, `Alloc`>. Ayrıca başlatır `sb` çağıran basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> ( `_Mode`).

İkinci Oluşturucu tarafından çağıran basic_iostream temel sınıfı başlatır ( **sb**). Ayrıca başlatır `sb` çağıran basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> (_ *Str*, `_Mode`).

## <a name="rdbuf"></a>  basic_stringstream::rdbuf

Türünde depolanmış bir akış arabelleğinin adresini döndürür **işaretçi** için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türünde depolanmış bir akış arabelleğinin adresini `pointer` basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  basic_stringstream::Str

Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.

```cpp
basic_string<Elem, Tr, Alloc> str() const;


void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*<br/>
Yeni bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi döndürür [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, denetlenen sırasıdır tarafından denetlenen dizinin bir kopyasını  **\*bu**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). İkinci üye işlev çağrıları `rdbuf`  ->  **str**( `_Newstr`).

### <a name="example"></a>Örnek

Bkz: [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) kullanan bir örnek için `str`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
