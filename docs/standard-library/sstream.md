---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: cc08fb426df289b3478ad9d29b03f9a6dd5d3978
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412481"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Ayrılan dizi nesnesinde depolanan dizileri iostreams işlemleri destekleyen çeşitli şablon sınıfları tanımlar. Tür dizilerini kolayca şablon sınıfının nesneleri gelen ve giden dönüştürülür [basic_string](../standard-library/basic-string-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Başvuru bir `sstream` nesne.|
|*sağ*|Başvuru bir `sstream` nesne.|

## <a name="remarks"></a>Açıklamalar

Türündeki nesneler `char *` işlevleri kullanabilirsiniz [ \<strstream >](../standard-library/strstream.md) akış. Ancak, \<strstream > kullanım dışıdır ve kullanımını \<sstream > önerilir.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Bir türü oluşturur `basic_istringstream` üzerinde özel bir **char** şablon parametresi.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Bir türü oluşturur `basic_ostringstream` üzerinde özel bir **char** şablon parametresi.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Bir türü oluşturur `basic_stringbuf` üzerinde özel bir **char** şablon parametresi.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Bir türü oluşturur `basic_stringstream` üzerinde özel bir **char** şablon parametresi.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Bir türü oluşturur `basic_istringstream` üzerinde özel bir **wchar_t** şablon parametresi.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Bir türü oluşturur `basic_ostringstream` üzerinde özel bir **wchar_t** şablon parametresi.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Bir türü oluşturur `basic_stringbuf` üzerinde özel bir **wchar_t** şablon parametresi.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Bir türü oluşturur `basic_stringstream` üzerinde özel bir **wchar_t** şablon parametresi.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[değiştirme](../standard-library/sstream-functions.md#sstream_swap)|İki değeri birbiriyle değiştirir `sstream` nesneleri.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Türünde öğeler aktarımını denetleyen bir akış arabelleğinin açıklar `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, için ve bir dizi nesnesinde saklanan öğe dizisi.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Öğelerin ayıklama denetleyen bir nesne ve bir akış arabelleğinin sınıfın kodlanmış nesnelerden açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, ve öğeleri bir sınıf ayırıcısı tarafından ayrılan `Alloc`.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Sınıfı bir akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, ve öğeleri bir sınıf ayırıcısı tarafından ayrılan `Alloc`.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Ekleme ve çıkarma öğelerin denetleyen bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesne açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, ve öğeleri bir sınıf ayırıcısı tarafından ayrılan `Alloc`.|

## <a name="requirements"></a>Gereksinimler

- **Başlık:** \<sstream >

- **Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
