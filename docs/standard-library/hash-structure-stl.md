---
title: Karma yapısı (C++ standart kitaplık) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: e6d0cea7bfc8cd745e7276f7fc29d493f178fc9b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451959"
---
# <a name="hash-structure-c-standard-library"></a>Karma yapısı (C++ standart kitaplık)

Tarafından `Val`benzersiz olarak belirlenen bir değer döndüren bir üye işlevi tanımlar. Üye işlevi, türündeki `thread::id` değerleri dizin değerlerinin bir dağıtımına eşlemek için uygun bir [karma](../standard-library/hash-class.md) işlevi tanımlar.

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

**Üst bilgi:** \<iş parçacığı >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<iş parçacığı >](../standard-library/thread.md)\
[unary_function Yapısı](../standard-library/unary-function-struct.md)
