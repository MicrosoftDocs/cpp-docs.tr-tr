---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 31a445fcc7deb5e5bade5437058cb36e28dacd40
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844333"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Ayrılmış bir dizi nesnesinde depolanan diziler üzerinde Iostreams işlemlerini destekleyen çeşitli sınıf şablonları tanımlar. Bu tür diziler, [basic_string](../standard-library/basic-string-class.md)sınıf şablonu nesnelerinden kolayca ve bu nesnelerden dönüştürülür.

## <a name="syntax"></a>Söz dizimi

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

*tarafta*\
Bir nesneye başvuru `sstream` .

*Right*\
Bir nesneye başvuru `sstream` .

## <a name="remarks"></a>Açıklamalar

Türündeki nesneler `char *` , akış için içindeki işlevleri kullanabilir [\<strstream>](../standard-library/strstream.md) . Ancak \<strstream> kullanım dışıdır ve kullanımı \<sstream> önerilir.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|`basic_istringstream`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`char`** .|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|`basic_ostringstream`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`char`** .|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|`basic_stringbuf`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`char`** .|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|`basic_stringstream`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`char`** .|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|`basic_istringstream`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`wchar_t`** .|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|`basic_ostringstream`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`wchar_t`** .|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|`basic_stringbuf`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`wchar_t`** .|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|`basic_stringstream`Şablon parametresi üzerinde özelleştirilmiş bir tür oluşturur **`wchar_t`** .|

### <a name="manipulators"></a>Manipülatörleri

|Ad|Açıklama|
|-|-|
|[Kur](../standard-library/sstream-functions.md#sstream_swap)|İki nesne arasındaki değerleri değiş tokuş eder `sstream` .|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|`Elem`Karakter nitelikleri, `Tr` bir dizi nesnesinde depolanan öğelerin dizisine ve türüne göre belirlenen, türü öğelerin aktarımını denetleyen bir akış arabelleğini açıklar.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Öğelerinin ve kodlanmış nesnelerin [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**> sınıfının bir akış arabelleğinden, `Alloc` `Elem` karakter nitelikleri sınıf tarafından belirlendiği `Tr` ve öğeleri bir sınıf ayırıcısı tarafından ayrıldığı `Alloc` şekilde, öğe ve kodlandığı öğelerin ayıklanmasını denetleyen bir nesne tanımlar.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Öğelerin ve kodlanmış nesnelerin [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**, `Alloc`>, `Elem` karakter nitelikleri sınıf tarafından belirlendiği `Tr` ve öğeleri bir sınıf ayırıcısı tarafından ayrılmış `Alloc` olan öğelerin bir akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Öğe ekleme ve ayıklamayı ve kodlanmış nesneleri [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **eled**, **tr**> sınıfının bir akış arabelleğini kullanarak, `Alloc` `Elem` karakter nitelikleri sınıf tarafından belirlendiği `Tr` ve öğeleri bir sınıf ayırıcısı tarafından ayrıldığı `Alloc` şekilde denetleyen bir nesne tanımlar.|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:**\<sstream>

- **Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
