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
ms.openlocfilehash: 050276da665ab6ed3eb53d9e65bfea06b88bcbea
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267981"
---
# <a name="any-class"></a>herhangi bir sınıf

Herhangi bir nesne veya Oluşturucu gereksinimleri karşılayan herhangi bir türde bir örnek var olan hiçbir değer depoları adlı sınıfı durumu.

Saklı örneği içindeki değeri olarak adlandırılır. İki durumlu ya da her ikisi de herhangi bir değer varsa veya her ikisi de bir değere sahip ve içerdiği değerlerin aynı olduğundan aynıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
class any
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[Tüm](#any)|Türünde bir nesne oluşturur `any`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[emplace](#emplace)|Herhangi bir değer ayarlar.|
|[has_value](#has_value)|Döndürür **true** varsa bir değer.|
|[Sıfırlama](#reset)|Herhangi bir sıfırlar.|
|[değiştirme](#swap)|İki değiştirir herhangi bir nesne.|
|[type](#type)|Herhangi bir türü döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator=](#op_eq)|Herhangi başka bir kopyasına sahip olan tüm değiştirir.|

## <a name="any"></a> Tüm

Türünde bir nesne oluşturur `any`. Ayrıca bir yok edici içerir.

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

## <a name="emplace"></a> emplace

Herhangi bir değer ayarlar.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a> has_value

Döndürür **true** varsa bir değer.

```cpp
bool has_value() const noexcept;
```

## <a name="op_eq"></a> işleç =

Herhangi başka bir kopyasına sahip olan tüm değiştirir.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Tüm hiçbir kopyalanıyor.

## <a name="reset"></a> Sıfırlama

Herhangi bir sıfırlar.

```cpp
void reset() noexcept;
```

## <a name="swap"></a> değiştirme

İki değiştirir herhangi bir nesne.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a> Türü

Herhangi bir türü döndürür.

```cpp
const type_info& type() const noexcept;
```
