---
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: ffcb6c7b2f95b0b62659f6080c9ed0d1f111237c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846400"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

İostreams için eklemeleri gösteren [basic_ostream](../standard-library/basic-ostream-class.md)sınıf şablonunu tanımlar. Üst bilgi ayrıca birkaç ilgili işleyici tanımlar. (Bu üst bilgi genellikle sizin için iostreams başlıklarınızdan biri tarafından eklenir. Genellikle bunu doğrudan eklemeniz gerekir.)

## <a name="syntax"></a>Syntax

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Üzerinde `basic_ostream` özelleştirilmiş ve özelleştirilmiş bir tür oluşturur **`char`** `char_traits` **`char`** .|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Üzerinde `basic_ostream` özelleştirilmiş ve özelleştirilmiş bir tür oluşturur **`wchar_t`** `char_traits` **`wchar_t`** .|

### <a name="manipulators"></a>Manipülatörleri

|Ad|Açıklama|
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Bir satırı sonlandırır ve arabelleği boşaltır.|
|[ucundaki](../standard-library/ostream-functions.md#ends)|Bir dizeyi sonlandırır.|
|[flush](../standard-library/ostream-functions.md#flush)|Arabelleği boşaltır.|
|[Kur](../standard-library/ostream-functions.md#swap)|`basic_ostream`Sağ nesne parametresi için sol nesne parametresinin değerlerini değiştirir `basic_ostream` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç<<](../standard-library/ostream-operators.md#op_lt_lt)|Akışa çeşitli türler yazar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Sınıf şablonu, öğelerin ve kodlanmış nesnelerin bir akış arabelleğine eklenmesini denetleyen bir nesneyi tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
