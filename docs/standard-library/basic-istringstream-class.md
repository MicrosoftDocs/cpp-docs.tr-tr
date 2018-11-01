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
ms.openlocfilehash: fdf622bbef370e8b3625f419be29f293bc06eacc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643280"
---
# <a name="basicistringstream-class"></a>basic_istringstream Sınıfı

Öğelerin ayıklama denetleyen bir nesne ve bir akış arabelleğinin sınıfın kodlanmış nesnelerden açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*<br/>
Ayırıcı sınıf.

*Elem*<br/>
Dizenin temel öğe türü.

*tr*<br/>
Karakter nitelikleri temel dize öğesinde anlayışıyla çalışır.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı öğelerin ayıklama denetleyen bir nesne ve kodlanmış bir akış arabelleğinin sınıfın nesneleri tanımlar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, türü öğeler ile *Elem*, olan karakter nitelikleri sınıfı tarafından belirlenen *Tr*, ve öğeleri sınıfınbirayırıcıayrılır *Ayırma*. Basic_stringbuf sınıfı bir nesnenin nesneyi depolar < **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istringstream](#basic_istringstream)|Türünde bir nesne oluşturur `basic_istringstream`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eşanlamlı türüdür `Alloc`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.|
|[değiştirme](#swap)|Bu değeri birbiriyle değiştirir `basic_istringstream` olanlar sağlanan nesne için nesne.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu değerleri atar `basic_istringstream` nesnesinden nesne parametresi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_istringstream::allocator_type

Şablon parametresi için bir eşanlamlı türüdür `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream

Türünde bir nesne oluşturur `basic_istringstream`.

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

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*<br/>
Bir nesne türü `basic_string`.

*sağ*<br/>
Bir rvalue başvurusunu bir `basic_istringstream` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_istream](../standard-library/basic-istream-class.md)(`sb`), burada `sb` depolanan nesne sınıfının [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`, `Tr`, `Alloc`>. Ayrıca başlatır `sb` çağırarak `basic_stringbuf` <  `Elem`, `Tr`, `Alloc`> ( `_Mode` &#124; `ios_base::in`).

İkinci oluşturucu çağırarak temel sınıfı başlatır `basic_istream(sb)`. Ayrıca başlatır `sb` çağırarak `basic_stringbuf` <  `Elem`, `Tr`, `Alloc`> ( `str`, `_Mode` &#124; `ios_base::in`).

Üçüncü Oluşturucu içeriğini nesnesiyle başlatır *doğru*, bir rvalue başvurusu olarak kabul edilir.

## <a name="op_eq"></a>  basic_istringstream::operator =

Bu değerleri atar `basic_istringstream` nesnesinden nesne parametresi.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Rvalue başvurusuna bir `basic_istringstream` nesne.

### <a name="remarks"></a>Açıklamalar

Üye işleci içeriğiyle nesnenin içeriğini değiştirir *doğru*, kabul olarak atama bir rvalue başvurusuna taşıyın.

## <a name="rdbuf"></a>  basic_istringstream::rdbuf

Türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türünde depolanmış bir akış arabelleğinin adresini `pointer` basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  basic_istringstream::Str

Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*<br/>
Yeni bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi döndürür [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, denetlenen sırasıdır tarafından denetlenen dizinin bir kopyasını  **\*bu**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). İkinci üye işlev çağrıları `rdbuf`  ->  **str**( `_Newstr`).

### <a name="example"></a>Örnek

Bkz: [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) kullanan bir örnek için `str`.

## <a name="swap"></a>  basic_istringstream::Swap

İki değeri birbiriyle değiştirir `basic_istringstream` nesneleri.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Bir `lvalue` başvurusu bir `basic_istringstream` nesne.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bu nesnenin değerleri ve değerlerini birbiriyle değiştirir *doğru*.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
