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
ms.openlocfilehash: b1e77325cc485da1caec91316ce5d46cfa6357dc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841941"
---
# <a name="optional-class"></a>isteğe bağlı sınıf

Sınıf şablonu, `optional<T>` `T` *içerilen değer*olarak bilinen türünde bir değer içerebilen veya içermeyen bir nesneyi tanımlar.

Bir örneği `optional<T>` bir değer içerdiğinde, içerilen değer nesnenin depolama alanı içinde `optional` , tür için uygun şekilde hizalı bir bölgede ayrılır `T` . `optional<T>` **`bool`** ' A dönüştürüldüğünde, sonuç **`true`** nesnenin bir değer içermesidir; Aksi takdirde, olur **`false`** .

Kapsanan nesne türü `T` [in_place_t](in-place-t-struct.md) veya [nullopt_t](nullopt-t-structure.md)olmamalıdır. `T`*ters çevrilebilir*olmalıdır, yani yıkıcının sahip olduğu tüm kaynakları geri kazanmalıdır ve hiçbir özel durum oluşturmamalıdır.

`optional`Sınıfı c++ 17 ' de yenidir.

## <a name="syntax"></a>Syntax

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

|Ad|Açıklama|
|-|-|
| **Oluşturucular ve yıkıcısı** | |
|[seçim](#optional) | Türünde bir nesne oluşturur `optional` . |
|[~ isteğe bağlı](#optional-destructor) | Türünde bir nesneyi yok eder `optional` . |
| **Atama** | |
| [işleç =](#op_eq) | Öğesini `optional` diğerinin bir kopyasıyla değiştirir `optional` . |
| [Emplace](#op_eq) | İçerilen değeri belirtilen bağımsız değişkenlerle başlatır. |
| **Kur** | |
| [Kur](#swap) | İçerilen değeri veya boş durumu başka bir metinle değiştirir `optional` . |
| **Gözlemciler** | |
| [has_value](#has_value) | Bir `optional` nesnenin bir değer içerip içermediğini döndürür. |
| [deeri](#value) | İçerilen değeri döndürür. |
| [value_or](#value_or) | İçerilen değeri veya hiçbir değer yoksa bir alternatif döndürür. |
| [operator->](#op_as) | Bir nesnenin içerilen değerine başvurur `optional` . |
| [işlecinde](#op_mem) | Bir nesnenin içerilen değerine başvurur `optional` . |
| [işleç bool](#op_bool) | Bir `optional` nesnenin bir değer içerip içermediğini döndürür. |
| **Değiştiriciler** | |
| [döndürmek](#reset) | `optional`İçerilen tüm değeri yok ederek sıfırlar. |

## <a name="has_value"></a><a name="has_value"></a> has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional-constructor"></a><a name="optional"></a> isteğe bağlı Oluşturucu

Türünde bir nesne oluşturur `optional` .

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

*sağ taraftan*\
`optional`İçindeki değeri kopyalama veya taşıma.

*i_list*\
Kapsanan değerin oluşturulması için Başlatıcı listesi.

*args*\
Kapsanan değerin oluşturulması için bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;` Bu oluşturucular `optional` bir değer içermeyen bir yapı oluşturur.

`constexpr optional(const optional& rhs);` Kopya Oluşturucu bağımsız değişkenin içerilen değerinden içerilen değeri başlatır. Doğru olmadığı sürece **silindi** olarak tanımlanır `is_copy_constructible_v<T>` ve doğru ise önemsiz olur `is_trivially_copy_constructible_v<T>` .

`constexpr optional(optional&& rhs) noexcept;` Taşıma Oluşturucusu, bağımsız değişkenin içerilen değerinden taşıyarak içerilen değeri başlatır. Doğru olmadığı takdirde aşırı yükleme çözümüne katılmaz `is_move_constructible_v<T>` ve doğru ise önemsiz olur `is_trivially_move_constructible_v<T>` .

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);` Doğrudan, içerilen değeri bağımsız değişkenleri kullanıyor gibi başlatır `std::forward<Args>(args)` . Bu Oluşturucu, **`constexpr`** `T` kullanılan oluşturucunun ise olur **`constexpr`** . Doğru olmadığı takdirde aşırı yükleme çözümüne katılmaz `is_constructible_v<T, Args...>` .

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);` Doğrudan, içerilen değeri bağımsız değişkenleri kullanıyor gibi başlatır `i_list, std::forward<Args>(args)` . Bu Oluşturucu, **`constexpr`** `T` kullanılan oluşturucunun ise olur **`constexpr`** . Doğru olmadığı takdirde aşırı yükleme çözümüne katılmaz `is_constructible_v<T, initializer_list<U>&, Args&&...>` .

`template <class U = T> explicit constexpr optional(U&& rhs);` Doğrudan içerilen değeri kullanıyor gibi başlatır `std::forward<U>(v)` . Bu Oluşturucu, **`constexpr`** `T` kullanılan oluşturucunun ise olur **`constexpr`** . True, ve false olmadığı takdirde aşırı yükleme çözümüne katılmaz `is_constructible_v<T, U&&>` `is_same_v<remove_cvref_t<U>, in_place_t>` `is_same_v<remove_cvref_t<U>, optional>` .

`template <class U> explicit optional(const optional<U>& rhs);`*RHS* bir değer içeriyorsa, doğrudan bağımsız değişkenin içerilen değerinden içerilen değeri başlatır. Doğru olmadığı ve,,,,,, `is_constructible_v<T, const U&>` `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>` ve `is_convertible_v<const optional<U>&&, T>` tamamen yanlış olmadığı takdirde aşırı yükleme çözümüne katılmaz.

`template <class U> explicit optional(optional<U>&& rhs);`*RHS* bir değer içeriyorsa, doğrudan içerilen değeri kullanıyor gibi başlatır `std::move(*rhs)` . Doğru olmadığı ve,,,,,, `is_constructible_v<T, U&&>` `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>` ve `is_convertible_v<const optional<U>&&, T>` tamamen yanlış olmadığı takdirde aşırı yükleme çözümüne katılmaz.

## <a name="optional-destructor"></a><a name="optional-destructor"></a> ~ isteğe bağlı yok edicisi

Varsa, yıkıcısız geri dönüşlü bir değeri yok eder, yok ediciyi çağırarak yok edilir.

```cpp
~optional();
```

### <a name="remarks"></a>Açıklamalar

`T`, Daha düşük bir şekilde yeniden çevrilebilir ise, daha sonra `optional<T>` da oldukça geri alınabilir.

## <a name="operator"></a><a name="op_eq"></a> işleç =

İçerilen değerini bir `optional` kopyayla değiştirir veya başka bir `optional` içerilen değerden geçer.

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

## <a name="operator-"></a><a name="op_as"></a> operator->

Bir nesnenin içerilen değerine başvurur `optional` .

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="operator"></a><a name="op_mem"></a> işlecinde

Bir nesnenin içerilen değerine başvurur `optional` .

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="operator-bool"></a><a name="op_bool"></a> işleç bool

`optional`Nesnenin içerilen bir değere sahip olup olmadığını bildirir.

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a><a name="reset"></a> döndürmek

Etkin olarak, varsa kapsanan nesnenin yok edicisini çağırır ve bunu başlatılmamış bir duruma getirir.

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a> Kur

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a><a name="value"></a> deeri

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a><a name="value_or"></a> value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<optional>](optional.md)
