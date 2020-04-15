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
ms.openlocfilehash: 9e10474d3e4fb2a37e8ab52f77495758c37e8a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376777"
---
# <a name="basic_ostringstream-class"></a>basic_ostringstream Sınıfı

**Elem**, **Tr**, `Alloc`> [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< bir akış arabelleği içine öğeleri ve kodlanmış nesnelerin ekleme denetimi bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*\
Ayırıcı sınıf.

*Elem*\
Dize temel öğenin türü.

*Tr*\
Karakter özellikleri dize temel öğesi üzerinde uzmanlaşmıştır.

## <a name="remarks"></a>Açıklamalar

Sınıf, karakter özellikleri sınıf tarafından belirlenen ve öğeleri sınıfın `Elem` `Tr` `Alloc`bir ayırıcısı tarafından ayrılan tür öğeleriyle, öğelerin ve kodlanmış nesnelerin bir akış arabelleği nesle eklenmesini denetleyen bir nesneyi açıklar. Nesne **elem,** **Tr**, `Alloc`>< sınıf basic_stringbuf bir nesne depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Türünde `basic_ostringstream`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Tür, şablon parametresi *Alloc*ile eş anlamlıdır.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Rdbuf](#rdbuf)|Depolanan akış `pointer` arabelleği adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`> `Alloc` olarak verir.|
|[Str](#str)|Yazma konumunu değiştirmeden metni bir dize arabelleği içinde ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<sstream>

**Ad alanı:** std

## <a name="basic_ostringstreamallocator_type"></a><a name="allocator_type"></a>basic_ostringstream::allocator_type

Tür, şablon parametresi *Alloc*ile eş anlamlıdır.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstreambasic_ostringstream"></a><a name="basic_ostringstream"></a>basic_ostringstream:basic_ostringstream

Tür basic_ostringstream bir nesne oluşturuyor.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mode*\
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*Str*\
`basic_string` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, [basic_ostream](../standard-library/basic-ostream-class.md) **(sb)** çağırarak taban `sb` sınıfı,< **elem**, **Tr**, `Alloc`> [basic_stringbuf](../standard-library/basic-stringbuf-class.md)sınıfın depolanan nesnesi olarak adlandırır. Ayrıca **elem,** **Tr** `Alloc` ,> `_Mode` (&#124;) `ios_base::out`< basic_stringbuf arayarak **sb'yi** de ilk kez basic_stringbuf.

İkinci oluşturucu basic_ostream **(sb)** çağırarak taban sınıfı başlatifleştirir. Ayrıca **elem,** **tr** `Alloc` ,>(_ *Str*, `_Mode` &#124;) `ios_base::out`< basic_stringbuf `sb` arayarak da başlar.

## <a name="basic_ostringstreamrdbuf"></a><a name="rdbuf"></a>basic_ostringstream::rdbuf

Basic_stringbuf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr**, `Alloc`> `pointer` türünün depolanan akış arabelleği adresini verir.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış tampon adresi, **elem,** **Tr**, `Alloc`>< basic_stringbuf türü. `pointer`

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan tür akış arabelleği `pointer` adresini **elem,** **Tr**, `Alloc`>< basic_stringbuf döndürür.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `rdbuf`bir örnek için kapat.

## <a name="basic_ostringstreamstr"></a><a name="str"></a>basic_ostringstream::str

Yazma konumunu değiştirmeden metni bir dize arabelleği içinde ayarlar veya alır.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*\
Yeni dize.

### <a name="return-value"></a>Dönüş Değeri

**Elem**, **Tr**,>, `Alloc` kontrollü sırası ** \*bu**tarafından kontrol edilen sıranın bir kopyası dır sınıf [basic_string](../standard-library/basic-string-class.md)< bir nesne döndürür .

### <a name="remarks"></a>Açıklamalar

İlk üye işlev [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str)döndürür. İkinci üye işlev `rdbuf`  ->  **str**( `_Newstr`çağırır.

### <a name="example"></a>Örnek

Bkz. [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) kullanan `str`bir örnek için.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
