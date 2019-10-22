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
ms.openlocfilehash: b88411316ae247499100a044a0a2dfb3c53bc84f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689992"
---
# <a name="basic_istringstream-class"></a>basic_istringstream Sınıfı

[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**, `Alloc` > sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma* \
Ayırıcı sınıf.

*Eled* \
Dizenin temel öğe öğesi türü.

*Tr* \
Dizenin temel öğesi üzerinde özelleştirilmiş karakter nitelikleri.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**, `Alloc` > sınıfının bir akış arabelleğinden öğe ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar. nitelikleri, *tr*sınıfı tarafından belirlenir ve öğeleri bir sınıf *ayırma*ayırıcısı tarafından ayrılır. Nesnesi, basic_stringbuf < **Eled**, **tr**`Alloc` > sınıfının bir nesnesini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istringstream](#basic_istringstream)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, `Alloc` şablon parametresi için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`, `Tr` `Alloc` > `pointer` türünde depolanan akış arabelleğinin adresini döndürür.|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|
|[Kur](#swap)|Bu `basic_istringstream` nesnesindeki değerleri, belirtilen nesne için değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Değerleri nesne parametresinden bu `basic_istringstream` nesnesine atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sstream >

**Ad alanı:** std

## <a name="allocator_type"></a>basic_istringstream::allocator_type

Tür, `Alloc` şablon parametresi için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a>basic_istringstream::basic_istringstream

@No__t_0 türünde bir nesne oluşturur.

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

*_Mod* \
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*str* \
@No__t_0 türünde bir nesne.

*sağ* \
Bir `basic_istringstream` nesnesinin rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [basic_istream](../standard-library/basic-istream-class.md)(`sb`) çağırarak temel sınıfı başlatır; burada `sb`, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`, `Tr`, `Alloc` > sınıfının saklı nesnesidir. Ayrıca, `basic_stringbuf` <  `Elem`, `Tr`, `Alloc` > (`_Mode` &#124; `ios_base::in`) çağırarak `sb` başlatır.

İkinci Oluşturucu, `basic_istream(sb)` çağırarak temel sınıfı başlatır. Ayrıca, `basic_stringbuf` <  `Elem`, `Tr`, `Alloc` > (`str`, `_Mode` &#124; `ios_base::in`) çağırarak `sb` başlatır.

Üçüncü Oluşturucu nesneyi *sağ*içeriğiyle başlatır ve rvalue başvurusu olarak değerlendirilir.

## <a name="op_eq"></a>basic_istringstream:: operator =

Değerleri nesne parametresinden bu `basic_istringstream` nesnesine atar.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
@No__t_0 nesnesine bir rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işleci, nesne içeriğini *sağ*içeriğiyle değiştirir ve rvalue başvurusu taşıma ataması olarak işlenir.

## <a name="rdbuf"></a>basic_istringstream:: rdarabelleğe

[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**`Alloc` > için `pointer` türünde depolanan akış arabelleğinin adresini döndürür.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basic_stringbuf < **Eled**, **Tr**, `Alloc` > `pointer` türünde depolanan akış arabelleğinin adresi.

### <a name="example"></a>Örnek

@No__t_1 kullanan bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="str"></a>basic_istringstream:: Str

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

## <a name="swap"></a>basic_istringstream:: swap

İki `basic_istringstream` nesnesinin değerlerini değiş tokuş eder.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Right*|Bir `basic_istringstream` nesnesine `lvalue` başvurusu.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi bu nesnenin değerlerini ve *sağ*değerlerini değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
