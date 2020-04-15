---
title: basic_stringstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
ms.openlocfilehash: f08689b1080837f042abfb3c4c52bb0ad558a448
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364863"
---
# <a name="basic_stringstream-class"></a>basic_stringstream Sınıfı

[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> sınıfının akış arabelleği kullanarak öğelerin ve kodlanmış nesnelerin ekleme ve ayıklama denetimleri bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*\
Ayırıcı sınıf.

*Elem*\
Dize temel öğenin türü.

*Tr*\
Karakter özellikleri dize temel öğesi üzerinde uzmanlaşmıştır.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu ekleme ve öğeleri ve kodlanmış nesnelerin sınıf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr**, `Alloc`>, tür `Elem`öğeleri , karakter özellikleri sınıf `Tr`tarafından belirlenir ve öğeleri sınıf `Alloc`bir ayırıcı tarafından tahsis edilir bir akış arabelleği kullanarak kodlanmış nesnelerin ayıklama kontrol eden bir nesne açıklar . Nesne **elem,** **Tr**, `Alloc`>< sınıf basic_stringbuf bir nesne depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringstream](#basic_stringstream)|Türünde `basic_stringstream`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Tür, şablon parametresi `Alloc`ile eş anlamlıdır.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Rdbuf](#rdbuf)|Depolanan akış `pointer` arabelleği adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`> `Alloc` olarak verir.|
|[Str](#str)|Yazma konumunu değiştirmeden metni bir dize arabelleği içinde ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<sstream>

**Ad alanı:** std

## <a name="basic_stringstreamallocator_type"></a><a name="allocator_type"></a>basic_stringstream:allocator_type

Tür, şablon parametresi `Alloc`ile eş anlamlıdır.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstreambasic_stringstream"></a><a name="basic_stringstream"></a>basic_stringstream:basic_stringstream

Türünde `basic_stringstream`bir nesne oluşturuyor.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mode*\
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*Str*\
`basic_string` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu [basic_iostream](../standard-library/basic-iostream-class.md) **(sb)** çağırarak taban sınıfı `sb` başladay,**elem**, **Tr** `Alloc` ,> [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< sınıfın depolanan nesnesi nerede. Ayrıca **elem** `sb` , **Tr**, `Alloc`>< `_Mode`basic_stringbuf arayarak da başlar.

İkinci oluşturucu, basic_iostream **(sb)** çağırarak taban sınıfı başlarayarak başlatifleştirir. Ayrıca **elem** `sb` , **Tr**, `Alloc`>(_ *Str*, `_Mode`basic_stringbuf< arayarak da başlar.

## <a name="basic_stringstreamrdbuf"></a><a name="rdbuf"></a>basic_stringstream::rdbuf

Tür **işaretçisinin** depolanan akış arabelleği adresini**elem,** **Tr**, `Alloc`> [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< verir.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

**Elem,** **Tr**, `Alloc`>< `pointer` basic_stringbuf için türü nde depolanan akış tampon adresi.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `rdbuf`bir örnek için kapat.

## <a name="basic_stringstreamstr"></a><a name="str"></a>basic_stringstream::str

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
