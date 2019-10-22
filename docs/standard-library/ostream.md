---
title: '&lt;ostream &gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: 3838e215ffac42ec6902ab6a9837f638153cf184
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689162"
---
# <a name="ltostreamgt"></a>&lt;ostream &gt;

İostreams için eklemeleri gösteren [basic_ostream](../standard-library/basic-ostream-class.md)sınıf şablonunu tanımlar. Üst bilgi ayrıca birkaç ilgili işleyici tanımlar. (Bu üst bilgi genellikle sizin için iostreams başlıklarınızdan biri tarafından eklenir. Genellikle bunu doğrudan eklemeniz gerekir.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Char **üzerinde özelleştirilmiş** `basic_ostream`, **char**üzerinde özelleştirilmiş `char_traits` bir tür oluşturur.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|**Wchar_t üzerinde özelleştirilmiş `basic_ostream` ve** **wchar_t**üzerinde özelleştirilmiş `char_traits` bir tür oluşturur.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Bir satırı sonlandırır ve arabelleği boşaltır.|
|[ucundaki](../standard-library/ostream-functions.md#ends)|Bir dizeyi sonlandırır.|
|[temizlenemiyor](../standard-library/ostream-functions.md#flush)|Arabelleği boşaltır.|
|[Kur](../standard-library/ostream-functions.md#swap)|Sağ `basic_ostream` nesne parametresi için sol `basic_ostream` nesne parametresinin değerlerini değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç < <](../standard-library/ostream-operators.md#op_lt_lt)|Akışa çeşitli türler yazar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Sınıf şablonu, öğelerin ve kodlanmış nesnelerin bir akış arabelleğine eklenmesini denetleyen bir nesneyi tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
