---
title: Eşzamanlılık ad alanı işleçleri (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: 3b536f75e4ef6405b60d45e89290a7d97a01707d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126932"
---
# <a name="concurrency-namespace-operators-amp"></a>Eşzamanlılık ad alanı işleçleri (AMP)

||||
|-|-|-|
|[operator!=](#operator_neq)|[işlecinde](#operator_mod)|[işlecinde](#operator_star)|
|[işleç +](#operator_add)|[işlecinde](#operator-)|[işlecinde](#operator_div)|
|[işleç = =](#operator_eq_eq)|

## <a name="operator_eq_eq"></a>işleç = =

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

tanımlama grupları eşitse **true** ; Aksi takdirde, **false**.

## <a name="operator_neq"></a>işleç! =

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

tanımlama grupları eşitse **true** ; Aksi takdirde, **false**.

## <a name="operator_add"></a>işleç +

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

## <a name="operator-"></a>işlecinde

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

## <a name="operator_star"></a>işlecinde

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

## <a name="operator_div"></a>işlecinde

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

## <a name="operator_mod"></a>işlecinde

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
