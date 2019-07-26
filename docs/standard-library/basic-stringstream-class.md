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
ms.openlocfilehash: 9278b6ce0fa23fa875f1af57ea15719111439372
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447804"
---
# <a name="basicstringstream-class"></a>basic_stringstream Sınıfı

Öğelerin ve ayıklamanın [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **eled**, **tr**, `Alloc`> bir akış arabelleği kullanılarak eklenmesini ve ayıklanmasını denetleyen bir nesne tanımlar.

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

Şablon sınıfı, öğe ekleme ve ayıklamayı ve kodlanmış nesneleri [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **eled**, **tr**, `Alloc`> sınıfının bir akış arabelleğini kullanarak ve türü öğeleriyledenetleyenşekildetanımlar`Elem`, karakter nitelikleri sınıfı `Tr`tarafından belirlenir ve öğeleri bir sınıf `Alloc`ayırıcısı tarafından ayrılır. Nesnesi, basic_stringbuf < **eled**, **tr**, `Alloc`> sınıfının bir nesnesini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringstream](#basic_stringstream)|Türünde `basic_stringstream`bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, şablon parametresi `Alloc`için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Türünde `pointer` depolanan akış arabelleğinin adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, >döndürür.`Alloc`|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sstream >

**Ad alanı:** std

## <a name="allocator_type"></a>basic_stringstream::allocator_type

Tür, şablon parametresi `Alloc`için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstream"></a>basic_stringstream::basic_stringstream

Türünde `basic_stringstream`bir nesne oluşturur.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
Türünde `basic_string`bir nesne.

### <a name="remarks"></a>Açıklamalar

`sb` İlk Oluşturucu, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) [](../standard-library/basic-iostream-class.md) `Alloc`  eled, tr, > sınıfının saklı nesnesi olan basic_iostream (SB) öğesini çağırarak temel sınıfı başlatır.<  Ayrıca, basic_stringbuf `sb` < **eled**, **tr**, `Alloc`> ( `_Mode`) çağırarak da başlatılır.

İkinci Oluşturucu, basic_iostream ( **SB**) öğesini çağırarak temel sınıfı başlatır. Ayrıca, basic_stringbuf `sb` < **eled**, **tr** `Alloc`, > (_ *Str*, `_Mode`) çağırarak da başlatılır.

## <a name="rdbuf"></a>basic_stringstream:: rdarabelleğe

[Basic_stringbuf](../standard-library/basic-stringbuf-class.md)  `Alloc`  eled,tr,>< işaretçisinin tür saklı akış arabelleğinin adresini döndürür.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basic_stringbuf `pointer` < **eled**, **tr**, `Alloc`> olarak bulunan depolanan akış arabelleğinin adresi.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="str"></a>basic_stringstream:: Str

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
