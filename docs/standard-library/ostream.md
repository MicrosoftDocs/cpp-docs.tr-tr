---
description: 'Daha fazla bilgi edinin: &lt; ostream&gt;'
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: a31ffe801fca16e3b7fc1037c59613150e383933
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126435"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

İostreams için eklemeleri gösteren [basic_ostream](../standard-library/basic-ostream-class.md)sınıf şablonunu tanımlar. Üst bilgi ayrıca birkaç ilgili işleyici tanımlar. (Bu üst bilgi genellikle sizin için iostreams başlıklarınızdan biri tarafından eklenir. Genellikle bunu doğrudan eklemeniz gerekir.)

## <a name="syntax"></a>Syntax

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Description|
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
