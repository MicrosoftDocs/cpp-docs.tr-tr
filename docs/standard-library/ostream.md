---
title: '&lt;ostream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
dev_langs:
- C++
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf7b8bf3015879643728358258cfe4a67536b3ea
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Şablon sınıfı tanımlayan [basic_ostream](../standard-library/basic-ostream-class.md), iostreams eklemeler aracılık. Üstbilgi ayrıca çeşitli ilgili manipülatörleri tanımlar. (Bu başlığı, genellikle başka iostreams üstbilgilerinin eklenmiştir. Nadiren doğrudan içermesi gerekir.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <ostream>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Bir türden oluşturur `basic_ostream` üzerinde özelleştirilmiş `char` ve `char_traits` üzerinde özel `char`.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Bir türden oluşturur `basic_ostream` üzerinde özelleştirilmiş `wchar_t` ve `char_traits` üzerinde özel `wchar_t`.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Bir satır sonlandırır ve arabelleği temizler.|
|[sona erer](../standard-library/ostream-functions.md#ends)|Bir dize sonlandırır.|
|[Temizleme](../standard-library/ostream-functions.md#flush)|Arabelleği temizler.|
|[Değiştirme](../standard-library/ostream-functions.md#swap)|Sol değerlerini alış verişleri `basic_ostream` parametresi bu hakkı nesne `basic_ostream` parametre nesnesi.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç <<](../standard-library/ostream-operators.md#op_lt_lt)|Çeşitli türleri akışa yazar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Şablon sınıfı öğelerinin ekleme denetimlerini bir nesne ve kodlanmış nesneleri akışı arabelleğe açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
