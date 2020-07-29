---
title: '&lt;Tarih/ç &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 82f0b7b0f55cf4d71ef7c0ed92a55ca0fa1139e0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230149"
---
# <a name="ltchronogt-operators"></a>&lt;Tarih/ç &gt; işleçleri

## <a name="operator-"></a><a name="operator-"></a>işlecinde

[Süre](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md) nesnelerinin çıkarma veya olumsuzlama işleci.

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

*Işınızda*\
Bir `time_point` nesnesi.

*Hecesi*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, `duration` Aralık uzunluğu iki bağımsız değişkenin zaman aralıkları arasındaki fark olan bir nesne döndürür.

İkinci işlev, zaman `time_point` içinde belirtilen zaman aralığında, *süresi ile*temsil edilen zaman aralığının ne kadar süre içinde olduğunu gösteren bir noktayı temsil eden bir nesne döndürür. *Time*

Üçüncü işlev, `duration` *sol* ve *sağ*arasındaki zaman aralığını temsil eden bir nesne döndürür.

## <a name="operator"></a><a name="op_neq"></a>işleç! =

[Süre](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesneleri için eşitsizlik işleci.

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev döndürür `!(Left == Right)` .

## <a name="operator"></a><a name="op_star"></a>işlecinde

[Duration](../standard-library/chrono-operators.md#op_star) nesneleri için çarpma işleci.

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

*Hecesi*\
Bir `duration` nesnesi.

*Mult*\
Bir tamsayı değeri.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `duration` , Aralık uzunluğu, *süre*uzunluğu ile *Mult* çarpıldığı bir nesne döndürür.

`is_convertible<Rep2, common_type<Rep1, Rep2>>` *Doğru tutmadığı*takdirde, ilk işlev aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz [<type_traits>](../standard-library/type-traits.md).

`is_convertible<Rep1, common_type<Rep1, Rep2>>` *Doğru tutmadığı*takdirde, ikinci işlev aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [<type_traits>](../standard-library/type-traits.md).

## <a name="operator"></a><a name="op_div"></a>işlecinde

[Duration](../standard-library/chrono-operators.md#op_star) nesneleri için bölme işleci.

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

*Hecesi*\
Bir `duration` nesnesi.

*DIV*\
Bir tamsayı değeri.

*Tarafta*\
Sol `duration` nesne.

*Right*\
Doğru `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, Aralık uzunluğu *div* *değerine bölünen süre uzunluğu olan Duration* nesnesini döndürür.

İkinci işleç, *sol* ve *sağ*Aralık uzunluklarının oranını döndürür.

`is_convertible<Rep2, common_type<Rep1, Rep2>>` *True*ve `Rep2` örneklemesi olmadığından, `duration` ilk işleç aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [<type_traits>](../standard-library/type-traits.md).

## <a name="operator"></a><a name="op_add"></a>işleç +

[Süre](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md) nesneleri ekler.

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

*Işınızda*\
Bir `time_point` nesnesi.

*Hecesi*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, `duration` *sol* ve *sağ*aralıkların toplamına eşit bir zaman aralığına sahip bir nesne döndürür.

İkinci ve üçüncü işlevleri, zaman aralığı ile zaman içinde zaman içindeki noktadan sonra gelen zaman `time_point` aralığını temsil eden bir *Time*nesne döndürür *Dur*.

## <a name="operatorlt"></a><a name="op_lt"></a>işlecinde&lt;

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin başka bir veya nesneden daha az olup olmadığını belirler `duration` `time_point` .

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, **`true`** *sol* Aralık uzunluğu *sağdaki*Aralık uzunluğundan küçükse döndürür. Aksi takdirde, işlev döndürür **`false`** .

İkinci işlev, **`true`** *sol* , *sağ*den önce dönerse döndürür. Aksi takdirde, işlev döndürür **`false`** .

## <a name="operatorlt"></a><a name="op_lt_eq"></a>işlecinde&lt;=

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin, başka bir veya nesneden küçük veya ona eşit olup olmadığını belirler `duration` `time_point` .

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev döndürür `!(Right < Left)` .

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

İki `duration` nesnenin aynı uzunluğa sahip zaman aralıklarını mi temsil ettiğini yoksa iki `time_point` nesnenin de aynı noktayı temsil edip etmediğini belirler.

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, **`true`** *sol* ve *sağ* aynı uzunlukta olan zaman aralıklarını temsil ediyorsa döndürür. Aksi takdirde, işlev döndürür **`false`** .

İkinci işlev, **`true`** *sol* ve *sağ* aynı anda aynı noktayı temsil ediyorsa döndürür. Aksi takdirde, işlev döndürür **`false`** .

## <a name="operatorgt"></a><a name="op_gt"></a>işlecinde&gt;

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin başka bir veya nesnesinden büyük olup olmadığını belirler `duration` `time_point` .

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev döndürür `Right < Left` .

## <a name="operatorgt"></a><a name="op_gt_eq"></a>işlecinde&gt;=

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin, başka bir veya nesneden büyük veya ona eşit olup olmadığını belirler `duration` `time_point` .

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

*Tarafta*\
Sol `duration` veya `time_point` nesne.

*Right*\
Sağ `duration` veya `time_point` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her işlev döndürür `!(Left < Right)` .

## <a name="operator-modulo"></a><a name="op_modulo"></a>işleç modül

[Duration](../standard-library/duration-class.md) nesnelerinde modül işlemleri için işleç.

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

*Hecesi*\
Bir `duration` nesnesi.

*DIV*\
Bir tamsayı değeri.

*Tarafta*\
Sol `duration` nesne.

*Right*\
Doğru `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, `duration` Aralık uzunluğu *süre* mod *div*olan bir nesne döndürür.

İkinci işlev, *sol* modül *hakkını*temsil eden bir değer döndürür.
