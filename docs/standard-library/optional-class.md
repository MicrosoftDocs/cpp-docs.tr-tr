---
title: isteğe bağlı sınıf
ms.date: 11/04/2016
f1_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
helpviewer_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
ms.openlocfilehash: d9c4bf5356e6ff163ecdf7e1a80bc55453d59003
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689154"
---
# <a name="optional-class"></a>isteğe bağlı sınıf

Sınıf şablonu `optional<T>`, *içerilen değer*olarak bilinen `T` türünde bir değer içerebilen veya içermeyen bir nesneyi tanımlar.

Bir `optional<T>` örneği bir değer içerdiğinde, içerilen değer `T` tür için uygun şekilde hizalı bir bölgede `optional` nesnesinin depolaması içinde ayrılır. Bir `optional<T>` `bool` dönüştürüldüğünde sonuç, nesne bir değer içeriyorsa `true`. Aksi takdirde, `false`.

Kapsanan nesne türü `T` [in_place_t](in-place-t-struct.md) veya [nullopt_t](nullopt-t-structure.md)olmamalı. `T`, geri *dönüşlü*olmalıdır, yani yıkıcının sahip olduğu tüm kaynakları geri kazanmalıdır ve hiçbir özel durum oluşturmamalıdır.

@No__t_0 sınıfı C++ 17 ' de yenidir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
| **Oluşturucular ve yıkıcısı** | |
|[optional](#optional) | @No__t_0 türünde bir nesne oluşturur. |
|[~ isteğe bağlı](#optional-destructor) | @No__t_0 türünde bir nesneyi yok eder. |
| **Atama** | |
| [işleç =](#op_eq) | @No__t_0 başka bir `optional` kopyasıyla değiştirir. |
| [Emplace](#op_eq) | İçerilen değeri belirtilen bağımsız değişkenlerle başlatır. |
| **Kur** | |
| [Kur](#swap) | İçerilen değeri veya boş durumu başka bir `optional` değiştirir. |
| **Gözlemcilerin** | |
| [has_value](#has_value) | Bir `optional` nesnesinin bir değer içerip içermediğini döndürür. |
| [value](#value) | İçerilen değeri döndürür. |
| [value_or](#value_or) | İçerilen değeri veya hiçbir değer yoksa bir alternatif döndürür. |
| [operator->](#op_as) | @No__t_0 nesnesinin içerilen değerine başvurur. |
| [işlecinde](#op_mem) | @No__t_0 nesnesinin içerilen değerine başvurur. |
| [işleç bool](#op_bool) | Bir `optional` nesnesinin bir değer içerip içermediğini döndürür. |
| **Değiştiriciler** | |
| [döndürmek](#reset) | İçerilen her türlü değeri yok ederek `optional` sıfırlar. |

## <a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional"></a>isteğe bağlı Oluşturucu

@No__t_0 türünde bir nesne oluşturur.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t nullopt) noexcept;
constexpr optional(const optional& rhs);
constexpr optional(optional&& rhs) noexcept;

template <class... Args>
constexpr explicit optional(in_place_t, Args&&... args);

template <class U, class... Args>
constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);

template <class U = T>
explicit constexpr optional(U&& rhs);

template <class U>
explicit optional(const optional<U>& rhs);

template <class U>
explicit optional(optional<U>&& rhs);
```

### <a name="parameters"></a>Parametreler

*rhs* \
Kapsanan değeri kopyalamanın veya taşımanın `optional`.

*i_list* \
Kapsanan değerin oluşturulması için Başlatıcı listesi.

*bağımsız değişkenler* \
Kapsanan değerin oluşturulması için bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

`constexpr optional() noexcept;` 
 `constexpr optional(nullopt_t nullopt) noexcept;` bu oluşturucular bir değer içermeyen bir `optional` oluşturur.

`constexpr optional(const optional& rhs);` kopya Oluşturucu, bağımsız değişkenin içerilen değerinden içerilen değeri başlatır. @No__t_1 true olmadığı sürece **silindi** olarak tanımlanır ve `is_trivially_copy_constructible_v<T>` true ise önemsiz olur.

taşıma Oluşturucusu `constexpr optional(optional&& rhs) noexcept;` bağımsız değişkenin içerilen değerinden taşıyarak içerilen değeri başlatır. @No__t_0 true olmadığı müddetçe aşırı yükleme çözümüne katılmaz ve `is_trivially_move_constructible_v<T>` true ise önemsiz olur.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);` doğrudan, içerilen değeri bağımsız değişkenleri `std::forward<Args>(args)` gibi olarak başlatır. Kullanılan `T` Oluşturucu `constexpr` ise bu Oluşturucu `constexpr`. @No__t_0 true olmadığı takdirde aşırı yükleme çözümüne katılmaz.

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);` doğrudan, içerilen değeri bağımsız değişkenleri `i_list, std::forward<Args>(args)` gibi olarak başlatır. Kullanılan `T` Oluşturucu `constexpr` ise bu Oluşturucu `constexpr`. @No__t_0 true olmadığı takdirde aşırı yükleme çözümüne katılmaz.

`template <class U = T> explicit constexpr optional(U&& rhs);` doğrudan, içerilen değeri `std::forward<U>(v)` kullanıyor gibi başlatır. Kullanılan `T` Oluşturucu `constexpr` ise bu Oluşturucu `constexpr`. @No__t_0 true olmadığı ve `is_same_v<remove_cvref_t<U>, in_place_t>` ve `is_same_v<remove_cvref_t<U>, optional>` false olmadığı takdirde aşırı yükleme çözümüne katılmaz.

*RHS* bir değer içeriyorsa `template <class U> explicit optional(const optional<U>& rhs);`, doğrudan bağımsız değişkenin içerilen değerinden içerilen değeri başlatır. @No__t_0 true olmadığı ve `is_constructible_v<T, optional<U>&>`, `is_constructible_v<T, optional<U>&&>`, `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`, `is_convertible_v<optional<U>&, T>`, `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>` ve `is_convertible_v<const optional<U>&&, T>` tamamen yanlış olduğu müddetçe aşırı yükleme çözümüne katılmaz.

*RHS* bir değer içeriyorsa `template <class U> explicit optional(optional<U>&& rhs);`, doğrudan içerilen değeri `std::move(*rhs)` kullanıyor gibi başlatır. @No__t_0 true olmadığı ve `is_constructible_v<T, optional<U>&>`, `is_constructible_v<T, optional<U>&&>`, `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`, `is_convertible_v<optional<U>&, T>`, `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>` ve `is_convertible_v<const optional<U>&&, T>` tamamen yanlış olduğu müddetçe aşırı yükleme çözümüne katılmaz.

## <a name="optional-destructor"></a>~ isteğe bağlı yok edicisi

Varsa, yıkıcısız geri dönüşlü bir değeri yok eder, yok ediciyi çağırarak yok edilir.

```cpp
~optional();
```

### <a name="remarks"></a>Açıklamalar

@No__t_0, önemli ölçüde geri çevrilebilir ise, `optional<T>` de oldukça yeniden çevrilebilir.

## <a name="op_eq"></a>işleç =

Bir `optional` içerilen değerini bir kopyayla değiştirir veya başka bir `optional` bulunan değerden geçer.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional& rhs);
optional& operator=(optional&&) noexcept( /* see below */ );

template <class U = T>
    optional& operator=(U&&);

template <class U>
optional& operator=(const optional<U>&);

template <class U>
    optional& operator=(optional<U>&&);

template <class... Args>
T& emplace(Args&&...);

template <class U, class... Args>
T& emplace(initializer_list<U>, Args&&...);
```

## <a name="op_as"></a>operator->

Bir `optional` nesnesinin içerilen değerine başvurur.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>işlecinde

Bir `optional` nesnesinin içerilen değerine başvurur.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>işleç bool

@No__t_0 nesnesinin içerilen bir değere sahip olup olmadığını bildirir.

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a>döndürmek

Etkin olarak, varsa kapsanan nesnenin yok edicisini çağırır ve bunu başlatılmamış bir duruma getirir.

```cpp
void reset() noexcept;
```

## <a name="swap"></a>Kur

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a>deeri

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a>value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<optional >](optional.md)
