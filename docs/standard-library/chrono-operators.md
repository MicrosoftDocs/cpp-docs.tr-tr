---
title: '&lt;chrono&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: d86fbf15313c25dd28b9220c654750ee8bc96d81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279079"
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt; işleçleri

||||
|-|-|-|
|[mod işleci](#op_modulo)|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|
|[İşleci&gt;=](#op_gt_eq)|[İşleci&lt;](#op_lt)|[İşleci&lt;=](#op_lt_eq)|
|[operator *](#op_star)|[operator +](#op_add)|[operator-](#operator-)|
|[operator /](#op_div)|[operator==](#op_eq_eq)|

## <a name="operator-"></a>  operator-

Veya negation işleci [süresi](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md) nesneleri.

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

*saat*<br/>
A `time_point` nesne.

*Süre*<br/>
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev bir `duration` aralığına iki bağımsız zaman aralıkları arasındaki farkı nesnesi.

İkinci işlevi döndürür bir `time_point` zamanında, tarafından olumsuzlama tarafından temsil edilen zaman aralığının değişmiş olan zamanda bir noktayı temsil eden bir nesne *süre*, tarafından belirtilen bir zaman noktasından *zaman*.

Üçüncü işlevi döndürür bir `duration` arasındaki zaman aralığını temsil eden nesne *sol* ve *sağ*.

## <a name="op_neq"></a>  işleç! =

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `!(Left == Right)`.

## <a name="op_star"></a>  operator *

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

*Süre*<br/>
A `duration` nesne.

*Mult*<br/>
Bir tamsayı değeri.

### <a name="return-value"></a>Dönüş Değeri

Her işlev bir `duration` aralığına nesne *Mult* çarpılan *süre*.

Sürece `is_convertible<Rep2, common_type<Rep1, Rep2>>` *korumadıkça*, ilk işlev aşırı yükleme çözünürlüğü içinde yer almaz. Daha fazla bilgi için bkz [< type_traits >](../standard-library/type-traits.md).

Sürece `is_convertible<Rep1, common_type<Rep1, Rep2>>` *korumadıkça*, ikinci işlev aşırı yükleme çözünürlüğü içinde yer almaz. Daha fazla bilgi için [< type_traits >](../standard-library/type-traits.md).

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

*Süre*<br/>
A `duration` nesne.

*div*<br/>
Bir tamsayı değeri.

*Sol*<br/>
Sol `duration` nesne.

*sağ*<br/>
Sağa `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç, aralığı bir süre nesnesi döndürür uzunluğunda uzunluğunu *süre* değeriyle bölünmüş *Div*.

İkinci işleç aralık uzunluğu oranını döndürür *sol* ve *sağ*.

Sürece `is_convertible<Rep2, common_type<Rep1, Rep2>>` *korumadıkça*, ve `Rep2` örneklemesi değil `duration`, ilk operatör aşırı yükleme çözünürlüğü içinde yer almaz. Daha fazla bilgi için [< type_traits >](../standard-library/type-traits.md).

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

*saat*<br/>
A `time_point` nesne.

*Süre*<br/>
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev bir `duration` aralıklarına toplamına eşit bir zaman aralığına sahip bir nesne *sol* ve *sağ*.

İkinci ve üçüncü işlevler döndürür bir `time_point` zamanında, aralığa göre değişmiş olan zamanda bir noktayı temsil eden bir nesne *süre*, zaman içerisinde bir noktadan *zaman*.

## <a name="op_lt"></a>  İşleci&lt;

Az olup olmadığını belirler [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnedir daha az `duration` veya `time_point` nesne.

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev **true** , aralık uzunluğu *sol* aralık uzunluğu'dan küçük *sağ*. Aksi halde, işlev döndürür **false**.

İkinci işlevi döndürür **true** varsa *sol* önündeki *sağ*. Aksi halde, işlev döndürür **false**.

## <a name="op_lt_eq"></a>  İşleci&lt;=

Az olup olmadığını belirler [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnedir küçüktür veya eşittir diğerine `duration` veya `time_point` nesne.

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `!(Right < Left)`.

## <a name="op_eq_eq"></a>  işleç ==

İki olup olmadığını belirler `duration` nesneleri aynı uzunluğa sahip zaman aralıklarını temsil etmek veya iki olduğunu `time_point` nesneleri zaman içinde aynı noktaya temsil eder.

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev **true** varsa *sol* ve *sağ* aynı uzunluğa sahip zaman aralıklarını temsil eder. Aksi halde, işlev döndürür **false**.

İkinci işlevi döndürür **true** varsa *sol* ve *sağ* zaman içinde aynı noktaya temsil eder. Aksi halde, işlev döndürür **false**.

## <a name="op_gt"></a>  İşleci&gt;

Az olup olmadığını belirler [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnedir diğerinden daha büyük `duration` veya `time_point` nesne.

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `Right < Left`.

## <a name="op_gt_eq"></a>  İşleci&gt;=

Az olup olmadığını belirler [süresi](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnedir büyüktür veya eşittir diğerine `duration` veya `time_point` nesne.

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

*Sol*<br/>
Sol `duration` veya `time_point` nesne.

*sağ*<br/>
Sağa `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `!(Left < Right)`.

## <a name="op_modulo"></a>  mod işleci

Modül işlemleri için işleç [süresi](../standard-library/duration-class.md) nesneleri.

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

*Süre*<br/>
A `duration` nesne.

*div*<br/>
Bir tamsayı değeri.

*Sol*<br/>
Sol `duration` nesne.

*sağ*<br/>
Sağa `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev bir `duration` aralığına nesne *süre* modül *Div*.

İkinci işlevi temsil eden bir değer döndürür *sol* modül *sağ*.

## <a name="see-also"></a>Ayrıca bkz.

[\<chrono >](../standard-library/chrono.md)<br/>
