---
description: 'Hakkında daha fazla bilgi edinin: basic_ostringstream Sınıfı'
title: basic_ostringstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: b745f6b733d093b620e15d0aa22593713988caf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325647"
---
# <a name="basic_ostringstream-class"></a>basic_ostringstream Sınıfı

Öğelerin ve kodlanmış nesnelerin [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**> sınıfının Akış arabelleğine eklenmesini denetleyen bir nesne tanımlar `Alloc` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Tahsis*\
Ayırıcı sınıf.

*Elem*\
Dizenin temel öğe öğesi türü.

*Tr*\
Dizenin temel öğesi üzerinde özelleştirilmiş karakter nitelikleri.

## <a name="remarks"></a>Açıklamalar

Sınıfı, öğelerin ve kodlanmış nesnelerin, `Elem` karakter nitelikleri sınıf tarafından belirlendiği `Tr` ve öğeleri bir sınıf ayırıcısı tarafından ayrılmış olan öğeleri ile bir akış arabelleğine eklenmesini denetleyen bir nesne tanımlar `Alloc` . Nesnesi basic_stringbuf< **Eled**, **tr**> sınıfının bir nesnesini saklar `Alloc` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Türünde bir nesne oluşturur `basic_ostringstream` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, bir şablon parametresi *ayırma* için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` , `Tr`> için depolanan akış arabelleğinin adresini döndürür `Alloc` .|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<sstream>

**Ad alanı:** std

## <a name="basic_ostringstreamallocator_type"></a><a name="allocator_type"></a> basic_ostringstream:: allocator_type

Tür, bir şablon parametresi *ayırma* için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstreambasic_ostringstream"></a><a name="basic_ostringstream"></a> basic_ostringstream:: basic_ostringstream

Basic_ostringstream türünde bir nesne oluşturur.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
`basic_string` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [](../standard-library/basic-ostream-class.md)  `sb` [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**> sınıfının saklı nesnesi olan basic_ostream (SB) çağırarak temel sınıfı başlatır `Alloc` . Ayrıca, basic_stringbuf < **eled**, **tr** `Alloc`> (&#124;) çağırarak SB 'yi `_Mode` başlatır `ios_base::out` .

İkinci Oluşturucu, basic_ostream ( **SB**) çağırarak temel sınıfı başlatır. Ayrıca `sb` , basic_stringbuf< **eled**, **tr** `Alloc`> (_ *Str*, `_Mode` &#124;) çağırarak da başlatılır `ios_base::out` .

## <a name="basic_ostringstreamrdbuf"></a><a name="rdbuf"></a> basic_ostringstream:: rdarabelleğe

`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**,> için türünde depolanan akış arabelleğinin adresini döndürür `Alloc` .

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

`pointer`Basic_stringbuf< **eled**, **tr**> ' e kadar olan depolanan akış arabelleğinin adresi `Alloc` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, türünde depolanan akış arabelleğinin adresini `pointer` basic_stringbuf< **eled**, **tr**> ' e döndürür `Alloc` .

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `rdbuf` .

## <a name="basic_ostringstreamstr"></a><a name="str"></a> basic_ostringstream:: Str

Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*\
Yeni dize.

### <a name="return-value"></a>Dönüş Değeri

[](../standard-library/basic-string-class.md) <    `Alloc` Denetlenen sırası **\* Bu** tarafından denetlenen sıranın bir kopyası olan basic_string eled, tr,> sınıfının bir nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [rdarabelleğe](#rdbuf)  ->  [Str](../standard-library/basic-stringbuf-class.md#str)döndürür. İkinci üye işlevi `rdbuf`  ->  **Str**() öğesini çağırır `_Newstr` .

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [basic_stringbuf:: Str](../standard-library/basic-stringbuf-class.md#str) `str` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
