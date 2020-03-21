---
title: in_place_t yapısı
ms.date: 11/04/2016
f1_keywords:
- utility<in_place_t>
- utility/std::in_place_t
helpviewer_keywords:
- utility<in_place_t> struct
ms.openlocfilehash: d7dad4f6ffbbf7111016bffdd087b5e9b1599c87
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076489"
---
# <a name="in_place_t-struct"></a>in_place_t yapısı

## <a name="syntax"></a>Sözdizimi

```cpp
struct in_place_t {
    explicit in_place_t() = default;
};

inline constexpr in_place_t in_place{};

template <class T>
    struct in_place_type_t {
        explicit in_place_type_t() = default;
    };

template <class T> inline constexpr in_place_type_t<T> in_place_type{};

template <size_t I>
    struct in_place_index_t {
        explicit in_place_index_t() = default;
    };

template <size_t I> inline constexpr in_place_index_t<I> in_place_index{};
```
