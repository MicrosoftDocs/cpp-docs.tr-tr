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
ms.openlocfilehash: f664df6493a7ee20361d49531a930aeb810d3d2a
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957155"
---
# <a name="optional-class"></a>isteğe bağlı sınıf

Şablon sınıfı `optional<T>` , *içerilen değer*olarak bilinen türünde `T`bir değer içerebilen veya içermeyen bir nesneyi tanımlar.

Bir örneği `optional<T>` bir değer içerdiğinde, içerilen değer `optional` nesnenin depolama alanı içinde, tür `T`için uygun şekilde hizalı bir bölgede ayrılır. ' A dönüştürüldüğünde, sonuç nesnenin bir değer `false`içermesidir `true` ; Aksi takdirde, olur. `optional<T>` `bool`

Kapsanan nesne türü `T` [in_place_t](in-place-t-struct.md) veya [nullopt_t](nullopt-t-structure.md)olmamalı. `T`*ters çevrilebilir*olmalıdır, yani yıkıcının sahip olduğu tüm kaynakları geri kazanmalıdır ve hiçbir özel durum oluşturmamalıdır.

`optional` Sınıfı c++ 17 ' de yenidir.

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
|[optional](#optional) | Türünde `optional`bir nesne oluşturur. |
|[~ isteğe bağlı](#optional-destructor) | Türünde `optional`bir nesneyi yok eder. |
| **Atama** | |
| [operator=](#op_eq) | `optional` Öğesini diğerinin`optional`bir kopyasıyla değiştirir. |
| [Emplace](#op_eq) | İçerilen değeri belirtilen bağımsız değişkenlerle başlatır. |
| **Kur** | |
| [Kur](#swap) | İçerilen değeri veya boş durumu başka bir `optional`metinle değiştirir. |
| **Gözlemcilerin** | |
| [has_value](#has_value) | Bir `optional` nesnenin bir değer içerip içermediğini döndürür. |
| [value](#value) | İçerilen değeri döndürür. |
| [value_or](#value_or) | İçerilen değeri veya hiçbir değer yoksa bir alternatif döndürür. |
| [operator->](#op_as) | Bir `optional` nesnenin içerilen değerine başvurur. |
| [işlecinde](#op_mem) | Bir `optional` nesnenin içerilen değerine başvurur. |
| [işleç bool](#op_bool) | Bir `optional` nesnenin bir değer içerip içermediğini döndürür. |
| **Değiştiriciler** | |
| [döndürmek](#reset) | İçerilen tüm değeri yok edereksıfırlar.`optional` |

## <a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional"></a>isteğe bağlı Oluşturucu

Türünde `optional`bir nesne oluşturur.

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
`optional` İçindeki değeri kopyalama veya taşıma.

*i_list*\
Kapsanan değerin oluşturulması için Başlatıcı listesi.

*args*\
Kapsanan değerin oluşturulması için bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;`Bu oluşturucular bir değer `optional` içermeyen bir yapı oluşturur.

`constexpr optional(const optional& rhs);`Kopya Oluşturucu bağımsız değişkenin içerilen değerinden içerilen değeri başlatır. Doğru olmadığı sürece `is_copy_constructible_v<T>` **silindi** olarak tanımlanır ve doğru ise önemsiz `is_trivially_copy_constructible_v<T>` olur.

`constexpr optional(optional&& rhs) noexcept;`Taşıma Oluşturucusu, bağımsız değişkenin içerilen değerinden taşıyarak içerilen değeri başlatır. Doğru olmadığı takdirde `is_move_constructible_v<T>` aşırı yükleme çözümüne katılmaz ve doğru ise `is_trivially_move_constructible_v<T>` önemsiz olur.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);`Doğrudan, içerilen değeri bağımsız değişkenleri `std::forward<Args>(args)`kullanıyor gibi başlatır. Bu Oluşturucu `constexpr` `T` , kullanılan`constexpr`oluşturucunun ise olur. Doğru olmadığı takdirde `is_constructible_v<T, Args...>` aşırı yükleme çözümüne katılmaz.

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);`Doğrudan, içerilen değeri bağımsız değişkenleri `i_list, std::forward<Args>(args)`kullanıyor gibi başlatır. Bu Oluşturucu `constexpr` `T` , kullanılan`constexpr`oluşturucunun ise olur. Doğru olmadığı takdirde `is_constructible_v<T, initializer_list<U>&, Args&&...>` aşırı yükleme çözümüne katılmaz.

`template <class U = T> explicit constexpr optional(U&& rhs);`Doğrudan içerilen değeri kullanıyor `std::forward<U>(v)`gibi başlatır. Bu Oluşturucu `constexpr` `T` , kullanılan`constexpr`oluşturucunun ise olur. True `is_constructible_v<T, U&&>` ,vefalse`is_same_v<remove_cvref_t<U>, optional>` olmadığı takdirde aşırı yükleme çözümüne katılmaz. `is_same_v<remove_cvref_t<U>, in_place_t>`

`template <class U> explicit optional(const optional<U>& rhs);`*RHS* bir değer içeriyorsa, doğrudan bağımsız değişkenin içerilen değerinden içerilen değeri başlatır. Doğru olmadığı ve `is_constructible_v<T, const U&>` `is_constructible_v<T, optional<U>&>` ,`is_constructible_v<T, const optional<U>&&>` ,,`is_convertible_v<const optional<U>&&, T>` ,,, ve tamamen yanlış olmadığı takdirde aşırı yükleme çözümüne katılmaz. `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>`

`template <class U> explicit optional(optional<U>&& rhs);`*RHS* bir değer içeriyorsa, doğrudan içerilen değeri kullanıyor `std::move(*rhs)`gibi başlatır. Doğru olmadığı ve `is_constructible_v<T, U&&>` `is_constructible_v<T, optional<U>&>` ,`is_constructible_v<T, const optional<U>&&>` ,,`is_convertible_v<const optional<U>&&, T>` ,,, ve tamamen yanlış olmadığı takdirde aşırı yükleme çözümüne katılmaz. `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>`

## <a name="optional-destructor"></a>~ isteğe bağlı yok edicisi

Varsa, yıkıcısız geri dönüşlü bir değeri yok eder, yok ediciyi çağırarak yok edilir.

```cpp
~optional();
```

### <a name="remarks"></a>Açıklamalar

, Daha düşük bir şekilde yeniden çevrilebilir ise, `optional<T>` daha sonra da oldukça geri alınabilir. `T`

## <a name="op_eq"></a>işleç =

İçerilen değerini `optional` bir kopyayla değiştirir veya başka `optional` bir içerilen değerden geçer.

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

Bir `optional` nesnenin içerilen değerine başvurur.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>işlecinde

Bir `optional` nesnenin içerilen değerine başvurur.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>işleç bool

`optional` Nesnenin içerilen bir değere sahip olup olmadığını bildirir.

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

[\<isteğe bağlı >](optional.md)
