---
title: variant_size yapısı
ms.date: 04/04/2019
f1_keywords:
- variant/std::variant_size
helpviewer_keywords:
- variant_size struct
ms.openlocfilehash: cc707e0eea2d071098caccab3839bc802318ce1e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267972"
---
# <a name="variantsize-struct"></a>variant_size yapısı

Değişken nesneleri yardımcı olur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
    struct variant_size; // not defined
template <class T>
    struct variant_size<const T>;
template <class T>
    struct variant_size<volatile T>;
template <class T>
    struct variant_size<const volatile T>;
template <class T>
    inline constexpr size_t variant_size_v = variant_size<T>::value;
template <class... Types>
    struct variant_size<variant<Types...>>;
```
