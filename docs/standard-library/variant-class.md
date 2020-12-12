---
description: 'Hakkında daha fazla bilgi edinin: varyant sınıfı'
title: varyant sınıfı
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
ms.openlocfilehash: 0fc2887def147b458e63bc316f211e62a5eba879
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305110"
---
# <a name="variant-class"></a>varyant sınıfı

Herhangi bir değişkenin herhangi bir örneği, alternatif türlerinden birinin bir değerini tutar ya da hiçbir değer içermez.

## <a name="syntax"></a>Syntax

```cpp
template <class... Types>
    class variant
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[varyantı](#variant)|Türünde bir nesne oluşturur `variant` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[Emplace](#emplace)|Yeni içerilen bir değer oluşturur.|
|[indeks](#index)|İçerilen değerin dizinini döndürür.|
|[Kur](#swap)||
|[valueless_by_exception](#emplace)|**`false`** Varyantın bir değer bulundurduğunu döndürür.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#op_eq)|Değişkeni başka bir varyantın kopyasıyla değiştirir.|

## <a name="emplace"></a><a name="emplace"></a> Emplace

Yeni içerilen bir değer oluşturur.

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

## <a name="index"></a><a name="index"></a> indeks

İçerilen değerin dizinini döndürür.

```cpp
constexpr size_t index() const noexcept;
```

## <a name="variant"></a><a name="variant"></a> varyantı

Türünde bir nesne oluşturur `variant` . Ayrıca bir yıkıcı içerir.

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

*Eşkenar*\
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

## <a name="operator"></a><a name="op_eq"></a> işleç =

Değişkeni başka bir varyantın kopyasıyla değiştirir.

```cpp
variant& operator=(const variant&);
variant& operator=(variant&&) noexcept(see below);
template <class T>
    variant& operator=(T&&) noexcept(see below);
```

## <a name="swap"></a><a name="swap"></a> Kur

```cpp
void swap(variant&) noexcept(see below);
```

## <a name="valueless_by_exception"></a><a name="valueless"></a> valueless_by_exception

**`false`** Varyantın bir değer bulundurduğunu döndürür.

```cpp
constexpr bool valueless_by_exception() const noexcept;
```
