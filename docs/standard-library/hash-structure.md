---
title: hash Yapısı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: ef620867a5c31c7bd2030803edd6eaea6bbb5726
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243719"
---
# <a name="hash-structure"></a>hash Yapısı

Şablon sınıfı, yöntemini olarak tanılar `val.hash_code()`. Yöntemi, tür değerlerini kullanılacak bir karma işlevi tanımlar [type_index](../standard-library/type-index-class.md) dizin değerlerinin dağıtımına.

## <a name="syntax"></a>Sözdizimi

```cpp
template <> struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;
};
```

## <a name="specialized-types"></a>Özel türleri

### <a name="system_error"></a> \<system_error >

```cpp
template <class T> struct hash;
template <> struct hash<error_code>;
template <> struct hash<error_condition>;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<typeindex >](../standard-library/typeindex.md)<br/>
