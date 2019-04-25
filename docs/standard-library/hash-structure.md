---
title: hash Yapısı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: ba05d70692b2f85c1a14f319fb1e92dcadc0ccce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158787"
---
# <a name="hash-structure"></a>hash Yapısı

Şablon sınıfı, yöntemini olarak tanılar `val.hash_code()`. Yöntemi, tür değerlerini kullanılacak bir karma işlevi tanımlar [type_index](../standard-library/type-index-class.md) dizin değerlerinin dağıtımına.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;

};
```

## <a name="see-also"></a>Ayrıca bkz.

[\<typeindex >](../standard-library/typeindex.md)<br/>
