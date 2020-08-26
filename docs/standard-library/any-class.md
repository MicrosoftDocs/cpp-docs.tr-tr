---
title: herhangi bir sınıf
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: defec0f6ab8f59219afddcefc67ea93435347978
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844749"
---
# <a name="any-class"></a>herhangi bir sınıf

Oluşturucu gereksinimlerini karşılayan herhangi bir türün bir örneğini depolar ya da herhangi bir nesne sınıfının durumu olarak adlandırılan değer içermez.

Saklı örneğe içerilen değer denir. İki durum, her ikisi de bir değere sahip değilse ya da her ikisinde de bir değer varsa ve içerilen değerler aynıysa aynıdır.

## <a name="syntax"></a>Syntax

```cpp
class any
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[kaydedilmemiş](#any)|Türünde bir nesne oluşturur `any` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[Emplace](#emplace)|Herhangi bir değer ayarlar.|
|[has_value](#has_value)|**`true`** Herhangi birinin bir değere sahip olup olmadığını döndürür.|
|[döndürmek](#reset)|Herhangi birini sıfırlar.|
|[Kur](#swap)|İki nesneyi değiştirir.|
|[türüyle](#type)|Herhangi bir türü döndürür.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#op_eq)|Herhangi birinin bir kopyasını diğerinin kopyasıyla değiştirir.|

## <a name="any"></a><a name="any"></a> kaydedilmemiş

Türünde bir nesne oluşturur `any` . Ayrıca bir yıkıcı içerir.

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a><a name="emplace"></a> Emplace

Herhangi bir değer ayarlar.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a><a name="has_value"></a> has_value

**`true`** Herhangi birinin bir değere sahip olup olmadığını döndürür.

```cpp
bool has_value() const noexcept;
```

## <a name="operator"></a><a name="op_eq"></a> işleç =

Herhangi birinin bir kopyasını diğerinin kopyasıyla değiştirir.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Herhangi birine kopyalanırlar.

## <a name="reset"></a><a name="reset"></a> döndürmek

Herhangi birini sıfırlar.

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a> Kur

İki nesneyi değiştirir.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a><a name="type"></a> türüyle

Herhangi bir türü döndürür.

```cpp
const type_info& type() const noexcept;
```
