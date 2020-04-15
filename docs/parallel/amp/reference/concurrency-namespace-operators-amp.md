---
title: Eşzamanlılık ad alanı işleçleri (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: c4086029b71d71091a12b9b6023cc6098faf2f85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376300"
---
# <a name="concurrency-namespace-operators-amp"></a>Eşzamanlılık ad alanı işleçleri (AMP)

||||
|-|-|-|
|[işleç!=](#operator_neq)|[operatör%](#operator_mod)|[işleç*](#operator_star)|
|[işleç+](#operator_add)|[işleç-](#operator-)|[işleç/](#operator_div)|
|[işleç==](#operator_eq_eq)|

## <a name="operator"></a><a name="operator_eq_eq"></a>işleç==

Belirtilen bağımsız değişkenlerin eşit olup olmadığını belirler.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Karşılaştırmak için tuples biri.

*_Rhs*<br/>
Karşılaştırmak için tuples biri.

### <a name="return-value"></a>Dönüş Değeri

tuples eşit ise **doğru;** aksi takdirde, **yanlış**.

## <a name="operator"></a><a name="operator_neq"></a>işleç!=

Belirtilen bağımsız değişkenlerin eşit olup olmadığını belirler.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Karşılaştırmak için tuples biri.

*_Rhs*<br/>
Karşılaştırmak için tuples biri.

### <a name="return-value"></a>Dönüş Değeri

tuples eşit değilse **doğru;** aksi takdirde, **yanlış**.

## <a name="operator"></a><a name="operator_add"></a>işleç+

Belirtilen bağımsız değişkenlerin bileşen açısından toplamını hesaplar.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Eklenecek argümanlardan biri.

*_Rhs*<br/>
Eklenecek argümanlardan biri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen açısından toplamı.

## <a name="operator-"></a><a name="operator-"></a>işleç-

Belirtilen bağımsız değişkenler arasındaki bileşen açısından farkı hesaplar.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Çıkarılacak argüman.

*_Rhs*<br/>
Çıkarılması gereken argüman.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenler arasındaki bileşen açısından fark.

## <a name="operator"></a><a name="operator_star"></a>işleç*

Belirtilen bağımsız değişkenlerin bileşen açısından ürünlerini hesaplar.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Çoğalacak tuple'lardan biri.

*_Rhs*<br/>
Çoğalacak tuple'lardan biri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen açısından ürünü.

## <a name="operator"></a><a name="operator_div"></a>işleç/

Belirtilen bağımsız değişkenlerin bileşen açısından bölümlerini hesaplar.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Tuple bölünecek.

*_Rhs*<br/>
Bölünecek tuple.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen açısından bölüm.

## <a name="operator"></a><a name="operator_mod"></a>operatör%

Belirtilen ilk bağımsız değişkenin modüllerini ikinci belirtilen bağımsız değişkenle hesaplar.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Tuple bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Modulo'nun hesaplandığı tuple.

*_Rhs*<br/>
Modulo'ya kadar olan tuple.

### <a name="return-value"></a>Dönüş Değeri

İlk belirtilen bağımsız değişkenin sonucu, ikinci belirtilen bağımsız değişkeni modüle.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlı Ad Alanı](concurrency-namespace-cpp-amp.md)
