---
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
ms.openlocfilehash: aa25c379e47bbe22efc78d65b3f6745e98098cbd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453516"
---
# <a name="basicostringstream-class"></a>basic_ostringstream Sınıfı

Öğelerin ve kodlanmış nesnelerin [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **eled**, **tr**, `Alloc`> sınıfının Akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.

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

Sınıfı, öğe ve kodlanmış nesnelerin, karakter nitelikleri sınıf `Elem` `Tr`tarafından belirlendiği ve öğeleri bir ayırıcı tarafından ayrılmış olan öğeler ile bir akış arabelleğine eklenmesini denetleyen bir nesneyi tanımlar. sınıf `Alloc`. Nesnesi, basic_stringbuf < **eled**, **tr**, `Alloc`> sınıfının bir nesnesini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Türünde `basic_ostringstream`bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, bir şablon parametresi *ayırma*için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Türünde `pointer` depolanan akış arabelleğinin adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, >döndürür.`Alloc`|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sstream >

**Ad alanı:** std

## <a name="allocator_type"></a>  basic_ostringstream::allocator_type

Tür, bir şablon parametresi *ayırma*için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstream"></a>basic_ostringstream::basic_ostringstream

Basic_ostringstream türünde bir nesne oluşturur.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
Türünde `basic_string`bir nesne.

### <a name="remarks"></a>Açıklamalar

`sb` İlk Oluşturucu, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) [](../standard-library/basic-ostream-class.md) `Alloc`  eled, tr, > sınıfının saklı nesnesi olan basic_ostream (SB) öğesini çağırarak temel sınıfı başlatır.<  Ayrıca, basic_stringbuf < **eled**, **tr**, > `Alloc`( &#124; `ios_base::out` `_Mode` ) çağırarak **SB** 'yi başlatır.

İkinci Oluşturucu, basic_ostream ( **SB**) öğesini çağırarak temel sınıfı başlatır. Ayrıca, basic_stringbuf `sb` < **eled**, **tr**, `Alloc`> (_ &#124; `ios_base::out` *Str*, `_Mode` ) çağırarak da başlatılır.

## <a name="rdbuf"></a>basic_ostringstream:: rdarabelleğe

`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)**eled**, **tr**, >`Alloc`türünde depolanan akış arabelleğinin adresini döndürür.< 

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basic_stringbuf `pointer` < **eled**, **tr**, `Alloc`> türünde depolanan akış arabelleğinin adresi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan `pointer` akış arabelleğinin adresini basic_stringbuf < **eled**, **tr**, `Alloc`> olarak döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="str"></a>basic_ostringstream:: Str

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

Denetlenen< sırası **Bu tarafından\*** denetlenen sıranın bir kopyası olan  `Alloc` [basic_string](../standard-library/basic-string-class.md)**eled**, tr > sınıfının bir nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [rdarabelleğe](#rdbuf) -> [Str](../standard-library/basic-stringbuf-class.md#str)döndürür. İkinci üye işlevi **Str**( `rdbuf` `_Newstr`) öğesini çağırır  -> .

### <a name="example"></a>Örnek

Tarafından kullanılan `str`bir örnek için bkz. [basic_stringbuf:: Str](../standard-library/basic-stringbuf-class.md#str) .

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
