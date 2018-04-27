---
title: '&lt;ostream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 620017d55c00ebca2be29bc855f9e77413941961
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
