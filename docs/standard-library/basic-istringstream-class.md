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
ms.openlocfilehash: 685195b13960c325076f1a38461394ada374d4b1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452541"
---
# <a name="basicistringstream-class"></a>basic_istringstream Sınıfı

`Alloc` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **eled**, **tr**, > sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

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

Şablon sınıfı, öğeleri ve kodlanmış nesneleri [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **eled**, **tr**, `Alloc`> sınıfının bir akış arabelleğinden, *eled*türünde öğelerle birlikte ayıkladığını denetleyen bir nesneyi tanımlar. karakter nitelikleri, *tr*sınıfı tarafından belirlenir ve öğeleri bir sınıf *ayırma*ayırıcısı tarafından ayrılır. Nesnesi, basic_stringbuf < **eled**, **tr**, `Alloc`> sınıfının bir nesnesini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istringstream](#basic_istringstream)|Türünde `basic_istringstream`bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, şablon parametresi `Alloc`için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Türünde `pointer` depolanan akış arabelleğinin adresini [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, >döndürür.`Alloc`|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|
|[Kur](#swap)|Bu `basic_istringstream` nesnedeki değerleri, belirtilen nesne için değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Nesne parametresinden bu `basic_istringstream` nesneye değerleri atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sstream >

**Ad alanı:** std

## <a name="allocator_type"></a>  basic_istringstream::allocator_type

Tür, şablon parametresi `Alloc`için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a>basic_istringstream::basic_istringstream

Türünde `basic_istringstream`bir nesne oluşturur.

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

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
Türünde `basic_string`bir nesne.

*Right*\
Bir `basic_istringstream` nesnenin rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [basic_istream](../standard-library/basic-istream-class.md)(`sb`) yöntemini çağırarak temel sınıfı başlatır, burada `sb` [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem` `Tr`sınıfının `Alloc`saklı nesnesidir, > . Ayrıca `sb` , >(`ios_base::in`) çağırarak <  `basic_stringbuf`dabaşlatılır &#124; . `Elem` `Tr` `Alloc` `_Mode`

İkinci Oluşturucu çağırarak `basic_istream(sb)`temel sınıfı başlatır. Ayrıca `sb` , >(`ios_base::in`, `basic_stringbuf`)çağırarak `Elem` < da &#124; başlatılır .`str` `Tr` `Alloc` `_Mode`

Üçüncü Oluşturucu nesneyi *sağ*içeriğiyle başlatır ve rvalue başvurusu olarak değerlendirilir.

## <a name="op_eq"></a>basic_istringstream:: operator =

Nesne parametresinden bu `basic_istringstream` nesneye değerleri atar.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_istringstream` nesneye rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işleci, nesne içeriğini *sağ*içeriğiyle değiştirir ve rvalue başvurusu taşıma ataması olarak işlenir.

## <a name="rdbuf"></a>basic_istringstream:: rdarabelleğe

`pointer` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)**eled**, **tr**, >`Alloc`türünde depolanan akış arabelleğinin adresini döndürür.< 

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basic_stringbuf `pointer` < **eled**, **tr**, `Alloc`> olarak bulunan depolanan akış arabelleğinin adresi.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [basic_filebuf:: Close](../standard-library/basic-filebuf-class.md#close) .

## <a name="str"></a>basic_istringstream:: Str

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

## <a name="swap"></a>basic_istringstream:: swap

İki `basic_istringstream` nesnenin değerlerini değiş tokuş eder.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Right*|`lvalue` Bir`basic_istringstream` nesneye başvuru.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi bu nesnenin değerlerini ve *sağ*değerlerini değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
