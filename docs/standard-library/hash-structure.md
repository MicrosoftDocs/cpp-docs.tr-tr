---
title: hash Yapısı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: 4f73d1bfe7f3370d76b39b95f740a4d3a759b908
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421606"
---
# <a name="hash-structure"></a>hash Yapısı

Sınıf şablonu, yöntemini döndüren `val.hash_code()`olarak tanımlar. Yöntemi, [type_index](../standard-library/type-index-class.md) türündeki değerleri dizin değerlerinin bir dağıtımına eşlemek için kullanılan bir karma işlevi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <> struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;
};
```

## <a name="specialized-types"></a>Özelleştirilmiş türler

### <a name="system_error"></a>\<system_error >

```cpp
template <class T> struct hash;
template <> struct hash<error_code>;
template <> struct hash<error_condition>;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<typeındex >](../standard-library/typeindex.md)
