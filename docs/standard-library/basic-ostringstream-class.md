---
title: basic_ostringstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03c45cad9e29221926eafd4d0b40410e5f9b89e2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068001"
---
# <a name="basicostringstream-class"></a>basic_ostringstream Sınıfı

Sınıfı bir akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*<br/>
Ayırıcı sınıf.

*Elem*<br/>
Dizenin temel öğe türü.

*tr*<br/>
Karakter nitelikleri temel dize öğesinde anlayışıyla çalışır.

## <a name="remarks"></a>Açıklamalar

Sınıf türünde öğelere sahip bir akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri açıklar `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, ve öğeleri bir ayırıcı tarafından ayrılır sınıf `Alloc`. Basic_stringbuf sınıfı bir nesnenin nesneyi depolar < **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Türünde bir nesne oluşturur `basic_ostringstream`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eşanlamlı türüdür *ayırma*.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_ostringstream::allocator_type

Şablon parametresi için bir eşanlamlı türüdür *ayırma*.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstream"></a>  basic_ostringstream::basic_ostringstream

Basic_ostringstream türü bir nesne oluşturur.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*<br/>
Bir nesne türü `basic_string`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_ostream](../standard-library/basic-ostream-class.md)( **sb**), burada `sb` depolanan nesne sınıfının [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**, **Tr**, `Alloc`>. Ayrıca başlatır **sb** çağıran basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> ( `_Mode` &#124; `ios_base::out`).

İkinci Oluşturucu tarafından çağıran basic_ostream temel sınıfı başlatır ( **sb**). Ayrıca başlatır `sb` çağıran basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> (_ *Str*, `_Mode` &#124; `ios_base::out`).

## <a name="rdbuf"></a>  basic_ostringstream::rdbuf

Türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Saklı akış arabelleğini türündeki adresi `pointer` basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.

### <a name="remarks"></a>Açıklamalar

Üye işlevi türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  basic_ostringstream::Str

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
