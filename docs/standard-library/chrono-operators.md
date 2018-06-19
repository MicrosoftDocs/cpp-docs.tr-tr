---
title: '&lt;chrono&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 1ac1051ddaa67dc1970119586ecb9e937583c58a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847406"
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt; işleçleri

||||
|-|-|-|
|[mod işleci](#op_modulo)|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|
|[işleci&gt;=](#op_gt_eq)|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|
|[işleç *](#op_star)|[operator +](#op_add)|[operator-](#operator-)|
|[operator /](#op_div)|[operator==](#op_eq_eq)|

## <a name="operator-"></a>  operator-

İşleç çıkarması veya değilleme işlemi için [süresi](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md) nesneleri.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);


template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

`Time` A `time_point` nesnesi.

`Dur` A `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev döndüren bir `duration` aralığı uzunluğunu iki bağımsız değişkenlerin zaman aralıkları arasındaki fark nedir nesnesi.

İkinci işlevi döndürür bir `time_point` bir nokta, tarafından temsil edilen zaman aralığını değilleme tarafından hatalı yerleştirilen süreyi temsil eder nesne `Dur`, tarafından belirtilen zaman noktasından `Time`.

Üçüncü işlevi döndürür bir `duration` arasındaki zaman aralığını gösteren nesne `Left` ve `Right`.

## <a name="op_neq"></a>  operator! =

Eşitsizlik işleci için [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesneleri.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür `!(Left == Right)`.

## <a name="op_star"></a>  işleç *

Çarpma işleci için [süresi](../standard-library/chrono-operators.md#op_star) nesneleri.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);


template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

`Mult` Bir tam sayı değeri.

### <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür bir `duration` , aralığı uzunluğu nesne `Mult` uzunluğuna çarpılan `Dur`.

Sürece `is_convertible<Rep2, common_type<Rep1, Rep2>>` *doğru kalıp*, ilk işlev aşırı yük çözüm katılmıyor. Daha fazla bilgi için sssee [< type_traits >](../standard-library/type-traits.md).

Sürece `is_convertible<Rep1, common_type<Rep1, Rep2>>` *doğru kalıp*, ikinci işlev aşırı yük çözüm katılmıyor. Daha fazla bilgi için bkz: [< type_traits >](../standard-library/type-traits.md).

## <a name="op_div"></a>  operator /

Bölme işleci için [süresi](../standard-library/chrono-operators.md#op_star) nesneleri.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);


template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

`Div` Bir tam sayı değeri.

`Left` Sol `duration` nesnesi.

`Right` Sağa `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işleci bir süre nesnesi, aralığını döndürür uzunluğudur uzunluğu `Dur` değeri tarafından bölünmüş `Div`.

İkinci işleci aralığı uzunluklarının oranını döndürür `Left` ve `Right`.

Sürece `is_convertible<Rep2, common_type<Rep1, Rep2>>` *doğru kalıp*, ve `Rep2` sayısı örneklemesi değil `duration`, ilk işleci aşırı yük çözüm katılmıyor. Daha fazla bilgi için bkz: [< type_traits >](../standard-library/type-traits.md).

## <a name="op_add"></a>  operator +

Ekler [süresi](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md) nesneleri.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);


template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

`Time` A `time_point` nesnesi.

`Dur` A `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev döndüren bir `duration` aralıklarına toplamına eşittir bir zaman aralığı olan nesneyi `Left` ve `Right`.

İkinci ve üçüncü işlevler döndürür bir `time_point` bir nokta, aralığa göre hatalı yerleştirilen süreyi temsil eder nesne `Dur`, zaman içinde noktasından `Time`.

## <a name="op_lt"></a>  işleci&lt;

Bir olup olmadığını belirleyen [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesi, başka değerinden `duration` veya `time_point` nesnesi.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlevi döndürür `true` varsa aralığı uzunluğu `Left` aralığı uzunluğu'dan küçük `Right`. Aksi takdirde işlevi döndürür `false`.

İkinci işlevi döndürür `true` varsa `Left` önündeki `Right`. Aksi takdirde işlevi döndürür `false`.

## <a name="op_lt_eq"></a>  işleci&lt;=

Bir olup olmadığını belirleyen [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesidir değerinden küçük veya eşit başka `duration` veya `time_point` nesnesi.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür `!(Right < Left)`.

## <a name="op_eq_eq"></a>  operator ==

İki olup olmadığını belirleyen `duration` nesneleri temsil aynı uzunlukta olan zaman aralıkları mı iki `time_point` nesneleri zamanında aynı noktasını temsil eder.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlevi döndürür `true` varsa `Left` ve `Right` aynı uzunlukta olan zaman aralıklarıyla temsil eder. Aksi takdirde işlevi döndürür `false`.

İkinci işlevi döndürür `true` varsa `Left` ve `Right` zamanında aynı noktasını temsil eder. Aksi takdirde işlevi döndürür `false`.

## <a name="op_gt"></a>  işleci&gt;

Bir olup olmadığını belirleyen [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesidir diğerinden daha büyük `duration` veya `time_point` nesnesi.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür `Right < Left`.

## <a name="op_gt_eq"></a>  işleci&gt;=

Bir olup olmadığını belirleyen [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesidir büyük veya ona eşit başka bir `duration` veya `time_point` nesnesi.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parametreler

`Left` Sol `duration` veya `time_point` nesnesi.

`Right` Sağa `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlevi döndürür `!(Left < Right)`.

## <a name="op_modulo"></a>  mod işleci

İşlemler modulo işleci için [süresi](../standard-library/duration-class.md) nesneleri.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

`Div` Bir tam sayı değeri.

`Left` Sol `duration` nesnesi.

`Right` Sağa `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev döndüren bir `duration` , aralığı uzunluğu nesne `Dur` modulo `Div`.

İkinci işlevi temsil eden bir değer döndürür `Left` modulo `Right`.

## <a name="see-also"></a>Ayrıca bkz.

[\<chrono >](../standard-library/chrono.md)<br/>
