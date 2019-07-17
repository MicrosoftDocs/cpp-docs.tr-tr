---
title: değişken sınıfı
ms.date: 04/04/2019
f1_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
helpviewer_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
ms.openlocfilehash: 9bfdf644374a0b825fd0ca02bf4164a766cb42a3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268146"
---
# <a name="variant-class"></a>değişken sınıfı

Herhangi bir örneğini belirtilen herhangi bir zamanda değişken ya da alternatif türlerinden değerini tutan veya herhangi bir değer tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class... Types>
    class variant
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[Değişken](#variant)|Türünde bir nesne oluşturur `variant`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[emplace](#emplace)|Yeni bir kapsanan değeri oluşturur.|
|[Dizin](#index)|Bir kapsanan değerinin indisini döndürür.|
|[değiştirme](#swap)||
|[valueless_by_exception](#emplace)|Döndürür **false** , değişken bir değer tutuyor.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator=](#op_eq)|Değişken, başka bir değişken bir kopyasıyla değiştirir.|

## <a name="emplace"></a> emplace

Yeni bir kapsanan değeri oluşturur.

```cpp
template <class T, class... Args>
    T& emplace(Args&&...);
template <class T, class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(Args&&...);
template <size_t I, class U, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(initializer_list<U>, Args&&...);
```

## <a name="index"></a> Dizin

Bir kapsanan değerinin indisini döndürür.

```cpp
constexpr size_t index() const noexcept;
```

## <a name="variant"></a> Değişken

Türünde bir nesne oluşturur `variant`. Ayrıca bir yok edici içerir.

```cpp
constexpr variant() noexcept(see below);
variant(const variant&);
variant(variant&&) noexcept(see below);
template <class T>
    constexpr variant(T&&) noexcept(see below);
template <class T, class... Args>
    constexpr explicit variant(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    constexpr explicit variant(in_place_type_t<T>, initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    constexpr explicit variant(in_place_index_t<I>, Args&&...);
template <size_t I, class U, class... Args>
    constexpr explicit variant(in_place_index_t<I>, initializer_list<U>, Args&&...);

template <class Alloc>
    variant(allocator_arg_t, const Al&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, const variant&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, variant&&);
template <class Alloc, class T>
    variant(allocator_arg_t, const Al&, T&&);
template <class Alloc, class T, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, Args&&...);
template <class Alloc, class T, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, initializer_list<U>, Args&&...);
template <class Alloc, size_t I, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, Args&&...);
template <class Alloc, size_t I, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, initializer_list<U>, Args&&...);

~variant();
```

### <a name="parameters"></a>Parametreler

*Al*\
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

## <a name="op_eq"></a> işleç =

Değişken, başka bir değişken bir kopyasıyla değiştirir.

```cpp
variant& operator=(const variant&);
variant& operator=(variant&&) noexcept(see below);
template <class T>
    variant& operator=(T&&) noexcept(see below);
```

## <a name="swap"></a> değiştirme

```cpp
void swap(variant&) noexcept(see below);
```

## <a name="valueless"></a> valueless_by_exception

Döndürür **false** , değişken bir değer tutuyor.

```cpp
constexpr bool valueless_by_exception() const noexcept;
```
