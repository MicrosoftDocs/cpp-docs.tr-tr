---
title: '&lt;İTO&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 398e2429c38cffb454c7b510aa5ab44fbe4cfef6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421935"
---
# <a name="ltchronogt-operators"></a>&lt;İTO&gt; işleçleri

## <a name="operator-"></a>işlecinde

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

*Zaman*\
Bir `time_point` nesnesi.

*Süre*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, Aralık uzunluğu iki bağımsız değişkenin zaman aralıkları arasındaki fark olan bir `duration` nesnesi döndürür.

İkinci işlev *, zaman içinde*belirtilen zaman aralığından *itibaren, süresi ile temsil*edilen zaman aralığının ne kadar süre içinde olduğunu gösteren bir `time_point` nesnesini döndürür.

Üçüncü işlev, *sol* ve *sağ*arasındaki zaman aralığını temsil eden bir `duration` nesnesi döndürür.

## <a name="op_neq"></a>işleç! =

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `!(Left == Right)`döndürür.

## <a name="op_star"></a>işlecinde

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

*Süre*\
Bir `duration` nesnesi.

*Mult*\
Bir tamsayı değeri.

### <a name="return-value"></a>Dönüş Değeri

Her işlev, Aralık uzunluğu, *süre*uzunluğu *ile çarpıldığı* `duration` nesnesini döndürür.

`is_convertible<Rep2, common_type<Rep1, Rep2>>`*true olarak saklanmamışsa*, ilk işlev aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz [< type_traits >](../standard-library/type-traits.md).

`is_convertible<Rep1, common_type<Rep1, Rep2>>`*true olarak saklanmadıkça*ikinci işlev aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [< type_traits >](../standard-library/type-traits.md).

## <a name="op_div"></a>işlecinde

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

*Süre*\
Bir `duration` nesnesi.

*Div*\
Bir tamsayı değeri.

*Sol*\
Sol `duration` nesnesi.

*Sağ*\
Doğru `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk operatör, Aralık uzunluğu *div* *değerine bölünen süre uzunluğu olan Duration* nesnesini döndürür.

İkinci işleç, *sol* ve *sağ*Aralık uzunluklarının oranını döndürür.

`is_convertible<Rep2, common_type<Rep1, Rep2>>`*true*olarak yoksa ve `Rep2` `duration`örneklemesi değilse, ilk işleç aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [< type_traits >](../standard-library/type-traits.md).

## <a name="op_add"></a>işleç +

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

*Zaman*\
Bir `time_point` nesnesi.

*Süre*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, *sol* ve *sağ*aralıkların toplamına eşit olan bir zaman aralığına sahip bir `duration` nesnesi döndürür.

İkinci ve üçüncü işlevleri, zaman aralığı ile zaman *içinde zaman içindeki* *noktadan sonra gelen*zaman aralığını temsil eden bir `time_point` nesnesi döndürür.

## <a name="op_lt"></a>işleç&lt;

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin başka bir `duration` veya `time_point` nesnesinden küçük olup olmadığını belirler.

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Aralık uzunluğu *sağdaki*Aralık uzunluğundan *küçükse, ilk* işlev **true** değerini döndürür. Aksi takdirde, işlev **false**döndürür.

İkinci işlev, *sağ* *den önce,* **doğru** değerini döndürür. Aksi takdirde, işlev **false**döndürür.

## <a name="op_lt_eq"></a>işleç&lt;=

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin, başka bir `duration` veya `time_point` nesnesinden küçük veya ona eşit olup olmadığını belirler.

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `!(Right < Left)`döndürür.

## <a name="op_eq_eq"></a>işleç = =

İki `duration` nesnenin aynı uzunluğa sahip zaman aralıklarını mi temsil ettiğini yoksa iki `time_point` nesnesinin de aynı noktayı temsil edip etmediğini belirler.

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, *sol* ve *sağ* aynı uzunlukta olan zaman aralıklarını temsil ediyorsa **true** değerini döndürür. Aksi takdirde, işlev **false**döndürür.

İkinci işlev, *sol* ve *sağ* aynı anda aynı noktayı temsil ediyorsa **true** değerini döndürür. Aksi takdirde, işlev **false**döndürür.

## <a name="op_gt"></a>işleç&gt;

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin başka bir `duration` veya `time_point` nesnesinden büyük olup olmadığını belirler.

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `Right < Left`döndürür.

## <a name="op_gt_eq"></a>işleç&gt;=

Bir [sürenin](../standard-library/duration-class.md) veya [time_point](../standard-library/time-point-class.md) nesnesinin, başka bir `duration` veya `time_point` nesnesinden büyük veya ona eşit olup olmadığını belirler.

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

*Sol*\
Sol `duration` veya `time_point` nesnesi.

*Sağ*\
Sağ `duration` veya `time_point` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Her işlev `!(Left < Right)`döndürür.

## <a name="op_modulo"></a>işleç modül

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

*Süre*\
Bir `duration` nesnesi.

*Div*\
Bir tamsayı değeri.

*Sol*\
Sol `duration` nesnesi.

*Sağ*\
Doğru `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk işlev, Aralık uzunluğu *süre* mod *Div*olan bir `duration` nesnesi döndürür.

İkinci işlev, *sol* modül *hakkını*temsil eden bir değer döndürür.
