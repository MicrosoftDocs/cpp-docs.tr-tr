---
description: 'Daha fazla bilgi edinin: eşzamanlılık ad alanı işleçleri (AMP)'
title: Eşzamanlılık ad alanı işleçleri (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: d57edbf790a1ebc4da179878dcf5082f53b45400
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211732"
---
# <a name="concurrency-namespace-operators-amp"></a>Eşzamanlılık ad alanı işleçleri (AMP)

:::row:::
   :::column span="":::
      [`operator==`](#operator_eq_eq)\
      [`operator!=`](#operator_neq)
   :::column-end:::
   :::column span="":::
      [`operator+`](#operator_add)\
      [`operator-`](#operator-)
   :::column-end:::
   :::column span="":::
      [`operator*`](#operator_star)\
      [`operator/`](#operator_div)
   :::column-end:::
   :::column span="":::
      [`operator%`](#operator_mod)
   :::column-end:::
:::row-end:::

## <a name="operator"></a><a name="operator_eq_eq"></a> işleç = =

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Karşılaştırılacak bir tanımlama grubu.

*_Rhs*<br/>
Karşılaştırılacak bir tanımlama grubu.

### <a name="return-value"></a>Dönüş Değeri

**`true`** tanımlama grupları eşitse; Aksi takdirde, **`false`** .

## <a name="operator"></a><a name="operator_neq"></a> işleç! =

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Karşılaştırılacak bir tanımlama grubu.

*_Rhs*<br/>
Karşılaştırılacak bir tanımlama grubu.

### <a name="return-value"></a>Dönüş Değeri

**`true`** tanımlama grupları eşitse; Aksi takdirde, **`false`** .

## <a name="operator"></a><a name="operator_add"></a> işleç +

Belirtilen bağımsız değişkenlerin bileşen temelinde toplamını hesaplar.

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Eklenecek bağımsız değişkenlerden biri.

*_Rhs*<br/>
Eklenecek bağımsız değişkenlerden biri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen temelinde toplamı.

## <a name="operator-"></a><a name="operator-"></a> işlecinde

Belirtilen bağımsız değişkenler arasındaki bileşen temelinde farkı hesaplar.

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Çıkarılacak bağımsız değişken.

*_Rhs*<br/>
Çıkarılacak bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenler arasındaki bileşen temelinde fark.

## <a name="operator"></a><a name="operator_star"></a> işlecinde

Belirtilen bağımsız değişkenlerin bileşen odaklı ürününü hesaplar.

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Çarpılacak tanımlama gruplarının biri.

*_Rhs*<br/>
Çarpılacak tanımlama gruplarının biri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen odaklı ürünü.

## <a name="operator"></a><a name="operator_div"></a> işlecinde

Belirtilen bağımsız değişkenlerin bileşen temelinde bölümünü hesaplar.

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Bölünecek kayıt düzeni.

*_Rhs*<br/>
Bölünecek kayıt düzeni.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen temelinde bölümü.

## <a name="operator"></a><a name="operator_mod"></a> işlecinde

Belirtilen ikinci bağımsız değişken tarafından belirtilen ilk bağımsız değişkenin mod sayısını hesaplar.

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
Demet bağımsız değişkenlerinin sıralaması.

*_Lhs*<br/>
Modülün hesaplandığı kayıt düzeni.

*_Rhs*<br/>
Modül için kullanılacak kayıt düzeni.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen ilk bağımsız değişkenin sonucu ikinci belirtilen bağımsız değişkeni mod.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace-cpp-amp.md)
