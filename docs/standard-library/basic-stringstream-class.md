---
description: 'Hakkında daha fazla bilgi edinin: basic_stringstream sınıfı'
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
ms.openlocfilehash: a236f8b382a2c0f8d77f971493fc16b9ac9da81f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325592"
---
# <a name="basic_stringstream-class"></a>basic_stringstream Sınıfı

Öğelerin ve ayıklamanın [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**> bir akış arabelleği kullanılarak eklenmesini ve ayıklanmasını denetleyen bir nesne tanımlar `Alloc` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Tahsis*\
Ayırıcı sınıf.

*Elem*\
Dizenin temel öğe öğesi türü.

*Tr*\
Dizenin temel öğesi üzerinde özelleştirilmiş karakter nitelikleri.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, öğe ekleme ve ayıklamayı ve kodlanmış nesneleri [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**> sınıfının bir akış arabelleğini kullanarak, `Alloc` `Elem` karakter nitelikleri sınıf tarafından belirlendiği `Tr` ve öğeleri bir sınıf ayırıcısı tarafından ayrılmış olan öğe türünü içeren `Alloc` bir nesne tanımlar. Nesnesi basic_stringbuf< **Eled**, **tr**> sınıfının bir nesnesini saklar `Alloc` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringstream](#basic_stringstream)|Türünde bir nesne oluşturur `basic_stringstream` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, şablon parametresi için bir eş anlamlı `Alloc` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` , `Tr`> için depolanan akış arabelleğinin adresini döndürür `Alloc` .|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<sstream>

**Ad alanı:** std

## <a name="basic_stringstreamallocator_type"></a><a name="allocator_type"></a> basic_stringstream:: allocator_type

Tür, şablon parametresi için bir eş anlamlı `Alloc` .

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstreambasic_stringstream"></a><a name="basic_stringstream"></a> basic_stringstream:: basic_stringstream

Türünde bir nesne oluşturur `basic_stringstream` .

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mode*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
`basic_string` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [](../standard-library/basic-iostream-class.md)  `sb` [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**> sınıfının saklı nesnesi olan basic_iostream (SB) çağırarak temel sınıfı başlatır `Alloc` . Ayrıca `sb` , basic_stringbuf< **eled**, **tr** `Alloc`> () çağırarak da başlatılır `_Mode` .

İkinci Oluşturucu, basic_iostream ( **SB**) çağırarak temel sınıfı başlatır. Ayrıca, `sb` basic_stringbuf< **eled**, **tr** `Alloc`> (_ *Str*,) çağırarak da başlatılır `_Mode` .

## <a name="basic_stringstreamrdbuf"></a><a name="rdbuf"></a> basic_stringstream:: rdarabelleğe

 [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**,> için işaretçi türünde depolanan akış arabelleğinin adresini döndürür `Alloc` .

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

`pointer`Basic_stringbuf< **eled**, **tr**> ' e kadar depolanan akış arabelleğinin adresi `Alloc` .

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `rdbuf` .

## <a name="basic_stringstreamstr"></a><a name="str"></a> basic_stringstream:: Str

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
