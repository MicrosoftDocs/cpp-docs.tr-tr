---
title: '&lt;sstream &gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 3f1fb202692d09fa87eb775677e46e1c3f36dbad
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688940"
---
# <a name="ltsstreamgt"></a>&lt;sstream &gt;

Ayrılmış bir dizi nesnesinde depolanan diziler üzerinde Iostreams işlemlerini destekleyen çeşitli sınıf şablonları tanımlar. Bu tür diziler kolayca sınıf şablonu [basic_string](../standard-library/basic-string-class.md)nesnelerinden ve bu nesnelerden dönüştürülür.

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
|*tarafta*|@No__t_0 nesnesine başvuru.|
|*Right*|@No__t_0 nesnesine başvuru.|

## <a name="remarks"></a>Açıklamalar

@No__t_0 nesne türleri, akış için [\<strstream >](../standard-library/strstream.md) işlevselliğini kullanabilir. Ancak, \<strstream > kullanım dışıdır ve \<sstream > kullanılması önerilir.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Bir **char** Şablon parametresinde özelleştirilmiş `basic_istringstream` bir tür oluşturur.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Bir **char** Şablon parametresinde özelleştirilmiş `basic_ostringstream` bir tür oluşturur.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Bir **char** Şablon parametresinde özelleştirilmiş `basic_stringbuf` bir tür oluşturur.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Bir **char** Şablon parametresinde özelleştirilmiş `basic_stringstream` bir tür oluşturur.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|**Wchar_t** Şablon parametresinde özelleştirilmiş `basic_istringstream` bir tür oluşturur.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|**Wchar_t** Şablon parametresinde özelleştirilmiş `basic_ostringstream` bir tür oluşturur.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|**Wchar_t** Şablon parametresinde özelleştirilmiş `basic_stringbuf` bir tür oluşturur.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|**Wchar_t** Şablon parametresinde özelleştirilmiş `basic_stringstream` bir tür oluşturur.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[Kur](../standard-library/sstream-functions.md#sstream_swap)|İki `sstream` nesne arasındaki değerleri değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Karakter nitelikleri, bir dizi nesnesinde depolanan bir öğe dizisine ve bu dizi `Tr` tarafından belirlenen `Elem` türünde öğelerin aktarımını denetleyen bir akış arabelleğini açıklar.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**eled**, **tr**, `Alloc` > sınıfının bir akış arabelleğinden, karakter nitelikleri tarafından belirlenen `Elem` türündeki öğelerle öğelerin ayıklanmasını ve kodlanmış nesneleri denetleyen bir nesneyi tanımlar. sınıfı `Tr` ve öğeleri bir sınıf `Alloc` ayırıcısı tarafından ayrılır.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Öğe ve kodlanmış nesnelerin, [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**eled**, **tr**`Alloc` > sınıfının bir akış arabelleğine, karakter nitelikleri tarafından belirlenen `Elem` türü öğeleriyle birlikte eklenmesini denetleyen bir nesneyi tanımlar. sınıf `Tr` ve öğeleri bir sınıf `Alloc` ayırıcısı tarafından ayrılır.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|[Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**eled**, **tr**, `Alloc` > sınıfının bir akış arabelleğini kullanarak öğelerin ve ayıklamanın, karakter nitelikleri olan `Elem` türündeki öğelerle birlikte eklenmesini ve ayıklanmasını denetleyen bir nesne açıklar `Tr` sınıfı tarafından belirlenir ve öğeleri bir sınıf `Alloc` ayırıcısı tarafından ayrılır.|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:** \<sstream >

- **Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
