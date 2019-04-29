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
ms.openlocfilehash: eb73c77f0e2658cf750cf17ca85549a09d1cbe51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370937"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Şablon sınıfı tanımlar [basic_ostream](../standard-library/basic-ostream-class.md), iostreams eklemeler aracılık. Üst bilgi, ayrıca birçok ilgili manipülatörleri tanımlar. (Bu başlığı, genellikle başka iostreams üst bilgi bulunur. Nadiren doğrudan dahil etmek ihtiyacınız.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Bir türden oluşturur `basic_ostream` üzerinde özelleştirilmiş **char** ve `char_traits` üzerinde özelleştirilmiş **char**.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Bir türden oluşturur `basic_ostream` üzerinde özelleştirilmiş **wchar_t** ve `char_traits` üzerinde özelleştirilmiş **wchar_t**.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Bir satır sonlandırır ve arabelleğini aktarır.|
|[sona erer](../standard-library/ostream-functions.md#ends)|Bir dize sonlandırır.|
|[Temizleme](../standard-library/ostream-functions.md#flush)|Arabelleği temizler.|
|[değiştirme](../standard-library/ostream-functions.md#swap)|Sol değerlerini birbiriyle değiştirir `basic_ostream` parametresi bu hakkı nesne `basic_ostream` parametresi nesne.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç <<](../standard-library/ostream-operators.md#op_lt_lt)|Çeşitli türleri, akışa yazar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Şablon sınıfı, bir akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
