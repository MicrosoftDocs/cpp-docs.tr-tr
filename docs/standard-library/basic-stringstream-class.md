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
ms.openlocfilehash: 50ec60ef094660dfa722a3a5c1f73fd9141aeef4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912764"
---
# <a name="basicstringstream-class"></a>basic_stringstream Sınıfı

Ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

`Alloc` Allocator sınıfı.

`Elem` Dizenin temel öğe türü.

*Tr* karakter nitelikler dize temel öğede özelleştirilmiş.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri tanımlar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, ve öğeleri tarafından ayrılmış bir Allocator sınıfı `Alloc`. Nesne sınıfı basic_stringbuf bir nesne depolar < **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringstream](#basic_stringstream)|Türünde bir nesne oluşturur `basic_stringstream`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eş anlamlı türüdür `Alloc`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Tür saklı Akış Arabellek adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_stringstream::allocator_type

Şablon parametresi için bir eş anlamlı türüdür `Alloc`.

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

`_Mode` Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`str` Türünde bir nesne `basic_string`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**), burada **sb** saklı nesne sınıfının [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**, **Tr**, `Alloc`>. Ayrıca başlatır **sb** arama basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> ( `_Mode`).

İkinci Oluşturucu, arama basic_iostream tarafından temel sınıfı başlatır ( **sb**). Ayrıca başlatır **sb** arama basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> (_ *Str*, `_Mode`).

## <a name="rdbuf"></a>  basic_stringstream::rdbuf

Tür saklı Akış Arabellek adresini döndürür **işaretçi** için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Adres türü saklı Akış Arabellek **işaretçi** basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek `rdbuf`.

## <a name="str"></a>  basic_stringstream::Str

Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.

```cpp
basic_string<Elem, Tr, Alloc> str() const;


void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

`_Newstr` Yeni bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi döndüren [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, yalnızca denetlenen sırasıdır denetlediği dizisinin bir kopyasını oluşturur  **\*bu**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevinin döndürdüğü [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). İkinci üye işlev çağrılarını `rdbuf`  ->  **str**( `_Newstr`).

### <a name="example"></a>Örnek

Bkz: [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) kullanan bir örnek **str**.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
