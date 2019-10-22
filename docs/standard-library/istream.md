---
title: '&lt;istream &gt;'
ms.date: 11/04/2016
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 8e9675a673462c8eaab94d29a3ae36a4786737b7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687850"
---
# <a name="ltistreamgt"></a>&lt;istream &gt;

İostreams için dışlamaları gösteren basic_istream sınıf şablonunu ve hem eklemeleri hem de dışlamaları içeren basic_iostream sınıf şablonunu tanımlar. Üst bilgi ayrıca ilgili bir işleici tanımlar. Bu üst bilgi dosyası, genellikle başka bir Iostreams üst bilgisi tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <istream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Bir tür, **char**üzerinde özelleştirilmiş `basic_iostream`.|
|[istream](../standard-library/istream-typedefs.md#istream)|Bir tür, **char**üzerinde özelleştirilmiş `basic_istream`.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|**Wchar**üzerinde özelleştirilmiş bir tür `basic_iostream`.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|**Wchar**üzerinde özelleştirilmiş bir tür `basic_istream`.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[RW](../standard-library/istream-functions.md#ws)|Akıştaki boşluğu atlar.|
|[Kur](../standard-library/istream-functions.md#istream_swap)|İki Stream nesnesi değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç > >](../standard-library/istream-operators.md#op_gt_gt)|Akıştan karakterler ve dizeler ayıklar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Hem giriş hem de çıkış yapan bir akış sınıfı.|
|[basic_istream](../standard-library/basic-istream-class.md)|Sınıf şablonu, [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen, karakter nitelikleri bir sınıf `Tr` tarafından belirlendiği şekilde [, bir akış arabelleğindeki öğe ve kodlanmış nesne ayıklamanın `Elem`, traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
