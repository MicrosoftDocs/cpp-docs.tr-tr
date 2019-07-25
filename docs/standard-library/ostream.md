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
ms.openlocfilehash: 8de66718dab10b5c95e8c1ab7fd0bd17e9b4ee5e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448167"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

İostreams için eklemeleri gösteren [basic_ostream](../standard-library/basic-ostream-class.md)şablon sınıfını tanımlar. Üst bilgi ayrıca birkaç ilgili işleyici tanımlar. (Bu üst bilgi genellikle sizin için iostreams başlıklarınızdan biri tarafından eklenir. Genellikle bunu doğrudan eklemeniz gerekir.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Char üzerinde özelleştirilmiş ve `basic_ostream` `char_traits` **char**üzerinde özelleştirilmiş bir  tür oluşturur.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Wchar_t üzerinde özelleştirilmiş ve `basic_ostream` `char_traits` **wchar_t**üzerinde özelleştirilmiş bir  tür oluşturur.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Bir satırı sonlandırır ve arabelleği boşaltır.|
|[ucundaki](../standard-library/ostream-functions.md#ends)|Bir dizeyi sonlandırır.|
|[temizlenemiyor](../standard-library/ostream-functions.md#flush)|Arabelleği boşaltır.|
|[Kur](../standard-library/ostream-functions.md#swap)|`basic_ostream` Sağ`basic_ostream` nesne parametresi için sol nesne parametresinin değerlerini değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç < <](../standard-library/ostream-operators.md#op_lt_lt)|Akışa çeşitli türler yazar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Şablon sınıfı, öğelerin ve kodlanmış nesnelerin bir akış arabelleğine eklenmesini denetleyen bir nesneyi tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
