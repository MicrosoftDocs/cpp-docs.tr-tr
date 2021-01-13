---
description: 'Daha fazla bilgi edinin: &lt; IStream&gt;'
title: '&lt;istream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 9b9b647b044cd0333349931285c4bffce000d062
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126539"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

İostreams için dışlamaları sunan basic_istream sınıf şablonunu ve hem eklemeleri hem de dışlamaları içeren sınıf şablonunu basic_iostream tanımlar. Üst bilgi ayrıca ilgili bir işleici tanımlar. Bu üst bilgi dosyası, genellikle başka bir Iostreams üst bilgisi tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Syntax

```cpp
#include <istream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Description|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|`basic_iostream`Üzerinde özelleştirilmiş bir tür **`char`** .|
|[istream](../standard-library/istream-typedefs.md#istream)|`basic_istream`Üzerinde özelleştirilmiş bir tür **`char`** .|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|`basic_iostream` **Wchar** üzerinde özelleştirilmiş bir tür.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|`basic_istream` **Wchar** üzerinde özelleştirilmiş bir tür.|

### <a name="manipulators"></a>Manipülatörleri

|Ad|Açıklama|
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|Akıştaki boşluğu atlar.|
|[Kur](../standard-library/istream-functions.md#istream_swap)|İki Stream nesnesi değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç>>](../standard-library/istream-operators.md#op_gt_gt)|Akıştan karakterler ve dizeler ayıklar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Hem giriş hem de çıkış yapan bir akış sınıfı.|
|[basic_istream](../standard-library/basic-istream-class.md)|Sınıf şablonu, bir akış arabelleğindeki öğe ve kodlanmış nesneleri, `Elem` [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen ve karakter nitelikleri, `Tr` [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da bilinen sınıf tarafından belirlendiği şekilde, öğelerin ayıklanmasını denetleyen bir nesne tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
