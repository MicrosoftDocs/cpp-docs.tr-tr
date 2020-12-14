---
description: 'Daha fazla bilgi edinin: karma yapısı'
title: hash Yapısı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: 6fa848be3a10c2a0ae1b325d25f31eb73adb527a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231777"
---
# <a name="hash-structure"></a>hash Yapısı

Sınıf şablonu, yöntemini döndürüyor olarak tanımlar `val.hash_code()` . Yöntemi, [type_index](../standard-library/type-index-class.md) türündeki değerleri dizin değerlerinin bir dağıtımına eşlemek için kullanılan bir karma işlevi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
template <> struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;
};
```

## <a name="specialized-types"></a>Özelleştirilmiş türler

### <a name="system_error"></a><a name="system_error"></a> \<system_error>

```cpp
template <class T> struct hash;
template <> struct hash<error_code>;
template <> struct hash<error_condition>;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<typeindex>](../standard-library/typeindex.md)
