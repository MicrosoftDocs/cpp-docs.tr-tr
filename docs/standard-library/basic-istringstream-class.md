---
title: basic_istringstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: 6a8ead5f1014e7f750e01988241ab020431312da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376797"
---
# <a name="basic_istringstream-class"></a>basic_istringstream Sınıfı

**Elem**, **Tr**, `Alloc`> [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< sınıf bir akış arabellesinden öğelerin ve kodlanmış nesnelerin ayıklama denetleyen bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*\
Ayırıcı sınıf.

*Elem*\
Dize temel öğenin türü.

*Tr*\
Karakter özellikleri dize temel öğesi üzerinde uzmanlaşmıştır.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu,**elem**, **Tr** `Alloc` ,> sınıfının bir akış arabelleğinden öğeler [basic_stringbufin](../standard-library/basic-stringbuf-class.md)< ve *Elem*kodlanmış nesnelerin çıkarılmasını kontrol eden bir nesneyi açıklar, karakter özellikleri *Tr*sınıfı tarafından belirlenir ve öğeleri *Alloc*sınıfının bir ayırıcısı tarafından ayrılır. Nesne **elem,** **Tr**, `Alloc`>< sınıf basic_stringbuf bir nesne depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istringstream](#basic_istringstream)|Türünde `basic_istringstream`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Tür, şablon parametresi `Alloc`ile eş anlamlıdır.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Rdbuf](#rdbuf)|Depolanan akış `pointer` arabelleği adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`> `Alloc` olarak verir.|
|[Str](#str)|Yazma konumunu değiştirmeden metni bir dize arabelleği içinde ayarlar veya alır.|
|[Takas](#swap)|Bu `basic_istringstream` nesnedeki değerleri sağlanan nesnenin değerleriyle değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Nesne parametresinden `basic_istringstream` bu nesneye değerleri atar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<sstream>

**Ad alanı:** std

## <a name="basic_istringstreamallocator_type"></a><a name="allocator_type"></a>basic_istringstream::allocator_type

Tür, şablon parametresi `Alloc`ile eş anlamlıdır.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstreambasic_istringstream"></a><a name="basic_istringstream"></a>basic_istringstream:basic_istringstream

Türünde `basic_istringstream`bir nesne oluşturuyor.

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

*_Mode*\
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*Str*\
`basic_string` türünün bir nesnesi.

*Doğru*\
Bir `basic_istringstream` nesnenin rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, sınıf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`> `Alloc` depolanan `sb` nesnesi olan [basic_istream](../standard-library/basic-istream-class.md)(`sb`) çağırarak taban sınıfı başladayleştirir. Ayrıca , , `sb` `basic_stringbuf` <  `Elem` `Tr` `Alloc`> (&#124;) `_Mode` `ios_base::in`çağırarak da baş harflerini alar.

İkinci oluşturucu çağırarak `basic_istream(sb)`taban sınıfı başharfe ait hale Ayrıca , , `sb` `basic_stringbuf` <  `Elem` `Tr` `Alloc`>( `str`, `_Mode` &#124;) `ios_base::in`çağırarak da baş harflerini çıkarır.

Üçüncü oluşturucu, nesneyi *hakkın*içeriğiyle başolarak ele alar, rvalue başvurusu olarak kabul edilir.

## <a name="basic_istringstreamoperator"></a><a name="op_eq"></a>basic_istringstream::operator=

Nesne parametresinden `basic_istringstream` bu nesneye değerleri atar.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `basic_istringstream` nesneye rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işleç, nesnenin içeriğini *hakkın*içeriğiyle değiştirir , rvalue referans taşıma ataması olarak kabul edilir.

## <a name="basic_istringstreamrdbuf"></a><a name="rdbuf"></a>basic_istringstream::rdbuf

Basic_stringbuf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr**, `Alloc`> `pointer` türünün depolanan akış arabelleği adresini verir.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

**Elem,** **Tr**, `Alloc`>< `pointer` basic_stringbuf için türü nde depolanan akış tampon adresi.

### <a name="example"></a>Örnek

Bkz. [basic_filebuf::kullanan](../standard-library/basic-filebuf-class.md#close) `rdbuf`bir örnek için kapat.

## <a name="basic_istringstreamstr"></a><a name="str"></a>basic_istringstream::str

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

## <a name="basic_istringstreamswap"></a><a name="swap"></a>basic_istringstream::takas

İki `basic_istringstream` nesnenin değerlerini değiştirir.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Doğru*|Bir `lvalue` `basic_istringstream` nesneye başvuru.|

### <a name="remarks"></a>Açıklamalar

Üye işlev, bu nesnenin değerlerini ve *hakkın*değerlerini değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
