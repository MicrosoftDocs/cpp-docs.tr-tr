---
title: hash yapısı (Standart C++ Kitaplığı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6f00b3c3136a4a2df96667d0f99f195339c60f1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056626"
---
# <a name="hash-structure-c-standard-library"></a>hash yapısı (Standart C++ Kitaplığı)

Benzersiz tarafından belirlenen bir değer döndüren bir üye işlev tanımlar `Val`. Üye işlevini tanımlayan bir [karma](../standard-library/hash-class.md) eşleme türü değerleri için uygun işlevi `thread::id` dizin değerlerinin dağıtımına.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;

};
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<iş parçacığı >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<iş parçacığı >](../standard-library/thread.md)<br/>
[unary_function Yapısı](../standard-library/unary-function-struct.md)<br/>
