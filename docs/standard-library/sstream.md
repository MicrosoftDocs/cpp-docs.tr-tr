---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 8284e56e8afb1e5518cbcbb772079b4f19d57b18
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451725"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Ayrılmış bir dizi nesnesinde depolanan diziler üzerinde Iostreams işlemlerini destekleyen çeşitli şablon sınıflarını tanımlar. Bu tür diziler, [basic_string](../standard-library/basic-string-class.md)şablon sınıfının nesnelerine ve nesnelerden kolayca dönüştürülür.

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
|*tarafta*|Bir `sstream` nesneye başvuru.|
|*Right*|Bir `sstream` nesneye başvuru.|

## <a name="remarks"></a>Açıklamalar

Türündeki `char *` nesneler, akış için [ \<strstream >](../standard-library/strstream.md) işlevlerini kullanabilir. Ancak, \<strstream > kullanım dışıdır ve \<sstream > kullanılması önerilir.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Bir Char şablon `basic_istringstream` parametresi üzerinde özelleştirilmiş  bir tür oluşturur.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Bir Char şablon `basic_ostringstream` parametresi üzerinde özelleştirilmiş  bir tür oluşturur.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Bir Char şablon `basic_stringbuf` parametresi üzerinde özelleştirilmiş  bir tür oluşturur.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Bir Char şablon `basic_stringstream` parametresi üzerinde özelleştirilmiş  bir tür oluşturur.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Wchar_t Şablon parametresinde `basic_istringstream` özelleştirilmiş bir tür  oluşturur.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Wchar_t Şablon parametresinde `basic_ostringstream` özelleştirilmiş bir tür  oluşturur.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Wchar_t Şablon parametresinde `basic_stringbuf` özelleştirilmiş bir tür  oluşturur.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Wchar_t Şablon parametresinde `basic_stringstream` özelleştirilmiş bir tür  oluşturur.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[Kur](../standard-library/sstream-functions.md#sstream_swap)|İki `sstream` nesne arasındaki değerleri değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Karakter nitelikleri, bir dizi nesnesinde depolanan öğelerin dizisine ve türüne göre `Elem` `Tr`belirlenen, türü öğelerin aktarımını denetleyen bir akış arabelleğini açıklar.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|`Alloc` [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**eled**, **tr**, > `Elem`sınıfının bir akış arabelleğinden öğe ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesneyi nitelikleri sınıfı `Tr`tarafından belirlenir ve öğeleri bir sınıf `Alloc`ayırıcısı tarafından ayrılır.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Öğelerin ve kodlanmış nesnelerin [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**eled**, **tr**, `Alloc`> `Elem`sınıfının bir akış arabelleğine eklenmesini denetleyen ve karakter nitelikleri olan bir nesneyi tanımlar. sınıfı `Tr`tarafından belirlenir ve öğeleri bir sınıf `Alloc`ayırıcısı tarafından ayrılır.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Öğelerin ve ayıklamanın [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**eled**, **tr**, `Alloc`> sınıfının bir akış arabelleğini kullanarak, türü `Elem`öğeleri olan bir nesne ve karakter nitelikleri sınıfı `Tr`tarafından belirlenir ve öğeleri bir sınıf `Alloc`ayırıcısı tarafından ayrılır.|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:** \<sstream >

- **Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
