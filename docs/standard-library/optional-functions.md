---
title: '&lt;isteğe bağlı &gt; işlevler'
ms.date: 11/04/2016
f1_keywords:
- optional/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: ebb7ccfb8a39bf1f45c7003d7c38e503ab20c89b
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274540"
---
# <a name="ltoptionalgt-functions"></a>&lt;isteğe bağlı &gt; işlevler

## <a name="make_optional"></a><a name="make_optional"></a> make_optional

Bir nesneyi isteğe bağlı hale getirir.

```cpp
template <class T>
    constexpr optional<see below> make_optional(T&&);
template <class T, class... Args>
    constexpr optional<T> make_optional(Args&&... args);
template <class T, class U, class... Args>
    constexpr optional<T> make_optional(initializer_list<U> il, Args&&... args);
```

## <a name="nullopt"></a><a name="nullopt"></a> nullopt

```cpp
inline constexpr nullopt_t nullopt(unspecified );
```

## <a name="swap"></a><a name="swap"></a> Kur

```cpp
template <class T>
    void swap(optional<T>&, optional<T>&) noexcept(see below );
```
