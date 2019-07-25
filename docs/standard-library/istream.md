---
title: '&lt;istream&gt;'
ms.date: 11/04/2016
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 0ad27bf849e8d4b9188868b9a29bf423b4cafafa
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458739"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

İostreams için dışlamaları gösteren basic_istream şablon sınıfını ve hem eklemeleri hem de dışlamaları içeren basic_iostream şablon sınıfını tanımlar. Üst bilgi ayrıca ilgili bir işleici tanımlar. Bu üst bilgi dosyası, genellikle başka bir Iostreams üst bilgisi tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <istream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Char üzerinde `basic_iostream` özelleştirilmiş bir tür.|
|[istream](../standard-library/istream-typedefs.md#istream)|Char üzerinde `basic_istream` özelleştirilmiş bir tür.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|`basic_iostream` **Wchar**üzerinde özelleştirilmiş bir tür.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|`basic_istream` **Wchar**üzerinde özelleştirilmiş bir tür.|

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
|[basic_istream](../standard-library/basic-istream-class.md)|Şablon sınıfı, öğe ve karakter nitelikleri sınıf `Elem` `Tr`tarafından belirlendiği şekilde [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen öğe ve kodlanmış nesneleri içeren bir akış arabelleğinden öğelerin ayıklanmasını denetleyen bir nesneyi tanımlar. [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak bilinir.|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
