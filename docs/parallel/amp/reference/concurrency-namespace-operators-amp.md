---
title: Eşzamanlılık ad alanı işleçleri (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: e2957aa84ffbf420dcf2672359a442b754866649
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283351"
---
# <a name="concurrency-namespace-operators-amp"></a>Eşzamanlılık ad alanı işleçleri (AMP)

||||
|-|-|-|
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator *](#operator_star)|
|[operator +](#operator_add)|[operator-](#operator-)|[operator /](#operator_div)|
|[operator==](#operator_eq_eq)|

##  <a name="operator_eq_eq"></a>  işleç ==

Belirtilen bağımsız değişkenlerin eşit olup olmadığını belirler.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Karşılaştırılacak tanımlama gruplarından biri.

*_Rhs*<br/>
Karşılaştırılacak tanımlama gruplarından biri.

### <a name="return-value"></a>Dönüş Değeri

**doğru** diziler durumunda eşit; Aksi takdirde **false**.

##  <a name="operator_neq"></a>  işleç! =

Belirtilen bağımsız değişkenlerin eşit olup olmadığını belirler.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Karşılaştırılacak tanımlama gruplarından biri.

*_Rhs*<br/>
Karşılaştırılacak tanımlama gruplarından biri.

### <a name="return-value"></a>Dönüş Değeri

**doğru** diziler değilse, eşit; Aksi takdirde **false**.

##  <a name="operator_add"></a>  operator +

Belirtilen bağımsız değişkenlerin bileşen odaklı toplamını hesaplar.

```
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

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Toplanacak bağımsız değişkenlerden biri.

*_Rhs*<br/>
Toplanacak bağımsız değişkenlerden biri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen düzeyinde toplamı.

##  <a name="operator-"></a>  operator-

Belirtilen bağımsız değişkenlerin bileşen odaklı farkı hesaplar.

```
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

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Çıkarmanın yapılacağı bağımsız değişken.

*_Rhs*<br/>
Çıkarılacak bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen odaklı farkı.

##  <a name="operator_star"></a>  operator *

Belirtilen bağımsız değişkenlerin bileşen odaklı çarpımını hesaplar.

```
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

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Çarpılacak dizlerden biri.

*_Rhs*<br/>
Çarpılacak dizlerden biri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen odaklı çarpımı.

##  <a name="operator_div"></a>  operator /

Belirtilen bağımsız değişkenlerin bileşen odaklı bölümünü hesaplar.

```
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

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Bölünecek kayıt düzeni.

*_Rhs*<br/>
Bölmede kullanılacak kayıt düzeni.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenlerin bileşen odaklı bölümü.

##  <a name="operator_mod"></a>  operator %

İkinci belirtilen bağımsız değişken tarafından belirtilen ilk bağımsız değişken modüllerini hesaplar.

```
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

*_Dizin*<br/>
Tanımlama grubu bağımsız boyut.

*_Lhs*<br/>
Kayıt düzeni hesaplanmasında kullanılan.

*_Rhs*<br/>
Ölçeklemede kullanılacak kayıt düzeni tarafından.

### <a name="return-value"></a>Dönüş Değeri

İlk belirtilen bağımsız değişken modulus belirtilen ikinci bağımsız değişken sonucu.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Namespace ](concurrency-namespace-cpp-amp.md)
