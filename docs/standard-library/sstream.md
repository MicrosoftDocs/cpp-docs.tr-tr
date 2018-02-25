---
title: '&lt;sstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <sstream>
dev_langs:
- C++
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 319c9cc1b61565eaeffb442b2f4e280aab9b720c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;
Ayrılmış bir dizi nesnesi içinde depolanan sıraları iostreams işlemlerini destekleyen birkaç şablon sınıfları tanımlar. Bu tür dizileri şablon sınıfın nesnelerini gelen ve giden kolayca dönüştürülür [basic_string](../standard-library/basic-string-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```
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
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Başvuru bir `sstream` nesnesi.|  
|`right`|Başvuru bir `sstream` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne türü `char *` işlevleri kullanabilirsiniz [ \<strstream >](../standard-library/strstream.md) akış. Ancak, `<strstream>` kullanım dışıdır ve kullanılmasını `<sstream>` önerilir.  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Bir türü oluşturur `basic_istringstream` üzerinde özel bir `char` şablon parametresi.|  
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Bir türü oluşturur `basic_ostringstream` üzerinde özel bir `char` şablon parametresi.|  
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Bir türü oluşturur `basic_stringbuf` üzerinde özel bir `char` şablon parametresi.|  
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Bir türü oluşturur `basic_stringstream` üzerinde özel bir `char` şablon parametresi.|  
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Bir türü oluşturur `basic_istringstream` üzerinde özel bir `wchar_t` şablon parametresi.|  
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Bir türü oluşturur `basic_ostringstream` üzerinde özel bir `wchar_t` şablon parametresi.|  
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Bir türü oluşturur `basic_stringbuf` üzerinde özel bir `wchar_t` şablon parametresi.|  
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Bir türü oluşturur `basic_stringstream` üzerinde özel bir `wchar_t` şablon parametresi.|  
  
### <a name="manipulators"></a>Manipülatörleri  
  
|||  
|-|-|  
|[Değiştirme](../standard-library/sstream-functions.md#sstream_swap)|İkisi arasındaki değerleri alış verişleri `sstream` nesneleri.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Türündeki öğeler iletimini denetleyen bir Akış Arabellek açıklar **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, gelen ve giden bir dizi nesnesi içinde depolanan öğeleri dizisi.|  
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, ve öğeleri sınıfı bir ayırıcı tarafından ayrılan `Alloc`.|  
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Öğeler ekleme denetimlerini bir nesne ve kodlanmış nesneleri bir sınıf akışı arabelleğe açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, ve öğeleri sınıfı bir ayırıcı tarafından ayrılan `Alloc`.|  
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, ve öğeleri bir sınıf ayırıcıtarafındanayrılan`Alloc`.|  
  
## <a name="requirements"></a>Gereksinimler  
  
- **Başlık:** \<sstream >  
  
- **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams Kuralları](../standard-library/iostreams-conventions.md)



