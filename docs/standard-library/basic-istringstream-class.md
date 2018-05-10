---
title: basic_istringstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0754ba9dc63f77793ced17e7950c7fc3ea3290d7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="basicistringstream-class"></a>basic_istringstream Sınıfı

Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

`Alloc` Allocator sınıfı.

`Elem` Dizenin temel öğe türü.

*Tr* karakter nitelikler dize temel öğede özelleştirilmiş.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı öğelerinin ayıklama denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, ve öğeleri, bir sınıf ayırıcıtarafındanayrılır`Alloc`. Nesne sınıfı basic_stringbuf bir nesne depolar < **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istringstream](#basic_istringstream)|Türünde bir nesne oluşturur `basic_istringstream`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eş anlamlı türüdür `Alloc`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Tür saklı Akış Arabellek adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.|
|[Değiştirme](#swap)|Bu değerler alış verişleri `basic_istringstream` için sağlanan nesne içeriğiyle nesnesi.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu değerler atayan `basic_istringstream` nesne parametresi nesnesinden.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_istringstream::allocator_type

Şablon parametresi için bir eş anlamlı türüdür `Alloc`.

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

`_Mode` Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`str` Türünde bir nesne `basic_string`.

`right` Rvalue başvuru, bir `basic_istringstream` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_istream](../standard-library/basic-istream-class.md)( `sb`), burada `sb` saklı nesne sınıfının [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`, `Tr`, `Alloc`>. Ayrıca başlatır `sb` çağırarak `basic_stringbuf` <  `Elem`, `Tr`, `Alloc`> ( `_Mode` &#124; `ios_base::in`).

İkinci oluşturucu çağırarak temel sınıfı başlatır `basic_istream(sb)`. Ayrıca başlatır `sb` çağırarak `basic_stringbuf` <  `Elem`, `Tr`, `Alloc`> ( `str`, `_Mode` &#124; `ios_base::in`).

Nesne içeriğini üçüncü Oluşturucu başlatır `right`, rvalue başvuru olarak işlem görür.

## <a name="op_eq"></a>  basic_istringstream::operator =

Bu değerler atayan `basic_istringstream` nesne parametresi nesnesinden.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Parametreler

`right` Rvalue başvuru için bir `basic_istringstream` nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işleci nesnesinin içeriğini içeriğiyle değiştirir `right`, kabul rvalue başvuru taşımak gibi atama.

## <a name="rdbuf"></a>  basic_istringstream::rdbuf

Tür saklı Akış Arabellek adresini döndürür **işaretçi** için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Dönüş Değeri

Adres türü saklı Akış Arabellek **işaretçi** basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek `rdbuf`.

## <a name="str"></a>  basic_istringstream::Str

Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.

```cpp
basic_string<Elem, Tr, Alloc> str() const;


void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

`_Newstr` Yeni bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi döndüren [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, yalnızca denetlenen sırasıdır denetlediği dizisinin bir kopyasını oluşturur  **\*bu**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevinin döndürdüğü [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). İkinci üye işlev çağrılarını `rdbuf`  ->  **str**( `_Newstr`).

### <a name="example"></a>Örnek

Bkz: [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) kullanan bir örnek **str**.

## <a name="swap"></a>  basic_istringstream::Swap

İki değerlerini alış verişleri `basic_istringstream` nesneleri.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`right`|Bir `lvalue` başvuru bir `basic_istringstream` nesnesi.|

### <a name="remarks"></a>Açıklamalar

Bu nesnenin değerlerini ve değerlerini üye fonksiyonu alış verişleri `right`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
