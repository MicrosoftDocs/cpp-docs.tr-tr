---
description: 'Hakkında daha fazla bilgi edinin: variant_size struct'
title: variant_size yapısı
ms.date: 04/04/2019
f1_keywords:
- variant/std::variant_size
helpviewer_keywords:
- variant_size struct
ms.openlocfilehash: dcdc15c7f04f61a5bf22eba63eaf9f0600e60c8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305097"
---
# <a name="variant_size-struct"></a>variant_size yapısı

Değişken nesnelerine yardımcı olur.

## <a name="syntax"></a>Syntax

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
