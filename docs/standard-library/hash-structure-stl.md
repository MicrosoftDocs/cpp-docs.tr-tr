---
title: hash yapısı (Standart C++ Kitaplığı) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: bb230d401d5061f4951f8007f93c3a28ce3dab03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579877"
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
