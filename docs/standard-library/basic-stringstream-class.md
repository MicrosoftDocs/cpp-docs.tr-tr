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
ms.openlocfilehash: ebf9b87b60cf790a2ca032eb805095f277324178
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688418"
---
# <a name="basic_stringstream-class"></a>basic_stringstream Sınıfı

Öğelerin ve ayıklamanın [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**`Alloc` > sınıfının akış arabelleğini kullanarak eklenmesini ve ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma* \
Ayırıcı sınıf.

*Eled* \
Dizenin temel öğe öğesi türü.

*Tr* \
Dizenin temel öğesi üzerinde özelleştirilmiş karakter nitelikleri.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**, `Alloc` > sınıfının bir akış arabelleğini kullanarak öğe ekleme ve ayıklamanın yanı sıra `Elem` türündeki öğeleri içeren bir nesneyi tanımlar. karakter nitelikleri, sınıf `Tr` tarafından belirlenir ve öğeleri bir sınıf `Alloc` ayırıcısı tarafından ayrılır. Nesnesi, basic_stringbuf < **Eled**, **tr**`Alloc` > sınıfının bir nesnesini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringstream](#basic_stringstream)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, `Alloc` şablon parametresi için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`, `Tr` `Alloc` > `pointer` türünde depolanan akış arabelleğinin adresini döndürür.|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sstream >

**Ad alanı:** std

## <a name="allocator_type"></a>basic_stringstream::allocator_type

Tür, `Alloc` şablon parametresi için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstream"></a>basic_stringstream::basic_stringstream

@No__t_0 türünde bir nesne oluşturur.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mod* \
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*str* \
@No__t_0 türünde bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [basic_iostream](../standard-library/basic-iostream-class.md)( **SB**) öğesini çağırarak temel sınıfı başlatır; burada `sb`, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**`Alloc` > sınıfının saklı nesnesidir. Ayrıca, basic_stringbuf < **Eled**, **tr**`Alloc` > (`_Mode`) çağırarak `sb` başlatır.

İkinci Oluşturucu, basic_iostream ( **SB**) öğesini çağırarak temel sınıfı başlatır. Ayrıca, basic_stringbuf < **Eled**, **Tr**, `Alloc` > (_ *Str*, `_Mode`) çağırarak `sb` başlatır.

## <a name="rdbuf"></a>basic_stringstream:: rdarabelleğe

**İşaretçi** türündeki depolanan akış arabelleğinin adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**`Alloc` > için döndürür.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basic_stringbuf < **Eled**, **Tr**, `Alloc` > `pointer` türünde depolanan akış arabelleğinin adresi.

### <a name="example"></a>Örnek

@No__t_1 kullanan bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="str"></a>basic_stringstream:: Str

Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr* \
Yeni dize.

### <a name="return-value"></a>Dönüş Değeri

Denetlenen sırası **\*this**tarafından denetlenen sıranın bir kopyası olan [basic_string](../standard-library/basic-string-class.md) < **eled**, **tr**`Alloc` > sınıfının bir nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [rdarabelleğe](#rdbuf)  -> [Str](../standard-library/basic-stringbuf-class.md#str)döndürür. İkinci üye işlevi `rdbuf`  -> **Str**(`_Newstr`) öğesini çağırır.

### <a name="example"></a>Örnek

@No__t_1 kullanan bir örnek için bkz. [basic_stringbuf:: Str](../standard-library/basic-stringbuf-class.md#str) .

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
