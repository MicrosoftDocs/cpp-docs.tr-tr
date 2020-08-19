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
ms.openlocfilehash: fd2ab79466c01343cbdadbcb649e3b05eee3c2a0
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561784"
---
# <a name="basic_istringstream-class"></a>basic_istringstream Sınıfı

[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**,> sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar `Alloc` .

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Tahsis*\
Ayırıcı sınıf.

*Elem*\
Dizenin temel öğe öğesi türü.

*Tr*\
Dizenin temel öğesi üzerinde özelleştirilmiş karakter nitelikleri.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, öğe ve kodlanmış nesneleri [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**,> sınıfının bir akış arabelleğinden `Alloc` ayıkladıktan sonra, karakter nitelikleri *tr*sınıfı tarafından belirlenen ve öğeleri bir sınıf *ayırma*ayırıcısı tarafından ayrılmış olan *eled*türünde öğeler içeren bir nesneyi tanımlar. Nesnesi basic_stringbuf< **Eled**, **tr**> sınıfının bir nesnesini saklar `Alloc` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istringstream](#basic_istringstream)|Türünde bir nesne oluşturur `basic_istringstream` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, şablon parametresi için bir eş anlamlı `Alloc` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` , `Tr`> için depolanan akış arabelleğinin adresini döndürür `Alloc` .|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|
|[Kur](#swap)|Bu nesnedeki değerleri, `basic_istringstream` belirtilen nesne için değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|`basic_istringstream`Nesne parametresinden bu nesneye değerleri atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<sstream>

**Ad alanı:** std

## <a name="basic_istringstreamallocator_type"></a><a name="allocator_type"></a> basic_istringstream:: allocator_type

Tür, şablon parametresi için bir eş anlamlı `Alloc` .

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstreambasic_istringstream"></a><a name="basic_istringstream"></a> basic_istringstream:: basic_istringstream

Türünde bir nesne oluşturur `basic_istringstream` .

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
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
`basic_string` türünün bir nesnesi.

*Right*\
Bir nesnenin rvalue başvurusu `basic_istringstream` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [basic_istream](../standard-library/basic-istream-class.md) `sb` `sb` [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` ,> sınıfının saklı nesnesi olduğu `Tr` `Alloc` basic_istream () çağırarak temel sınıfı başlatır. Ayrıca `sb` `basic_stringbuf` <  `Elem` , `Tr` `Alloc`> ( `_Mode` &#124; `ios_base::in` ) çağırarak da başlatılır.

İkinci Oluşturucu çağırarak temel sınıfı başlatır `basic_istream(sb)` . Ayrıca `sb` `basic_stringbuf` <  `Elem` , `Tr` `Alloc`> ( `str` , `_Mode` &#124; `ios_base::in` ) çağırarak da başlatılır.

Üçüncü Oluşturucu nesneyi *sağ*içeriğiyle başlatır ve rvalue başvurusu olarak değerlendirilir.

## <a name="basic_istringstreamoperator"></a><a name="op_eq"></a> basic_istringstream:: operator =

`basic_istringstream`Nesne parametresinden bu nesneye değerleri atar.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir nesneye rvalue başvurusu `basic_istringstream` .

### <a name="remarks"></a>Açıklamalar

Üye işleci, nesne içeriğini *sağ*içeriğiyle değiştirir ve rvalue başvurusu taşıma ataması olarak işlenir.

## <a name="basic_istringstreamrdbuf"></a><a name="rdbuf"></a> basic_istringstream:: rdarabelleğe

`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **eled**, **tr**,> için türünde depolanan akış arabelleğinin adresini döndürür `Alloc` .

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

`pointer`Basic_stringbuf< **eled**, **tr**> ' e kadar depolanan akış arabelleğinin adresi `Alloc` .

### <a name="example"></a>Örnek

' In kullandığı bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) `rdbuf` .

## <a name="basic_istringstreamstr"></a><a name="str"></a> basic_istringstream:: Str

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

[basic_string](../standard-library/basic-string-class.md) <  **Elem** **Tr** `Alloc` Denetlenen sırası ** \* Bu**tarafından denetlenen sıranın bir kopyası olan basic_string eled, tr,> sınıfının bir nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [rdarabelleğe](#rdbuf)  ->  [Str](../standard-library/basic-stringbuf-class.md#str)döndürür. İkinci üye işlevi `rdbuf`  ->  **Str**() öğesini çağırır `_Newstr` .

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [basic_stringbuf:: Str](../standard-library/basic-stringbuf-class.md#str) `str` .

## <a name="basic_istringstreamswap"></a><a name="swap"></a> basic_istringstream:: swap

İki nesnenin değerlerini değiş tokuş eder `basic_istringstream` .

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir nesneye lvalue başvurusu `basic_istringstream` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi bu nesnenin değerlerini ve *sağ*değerlerini değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
