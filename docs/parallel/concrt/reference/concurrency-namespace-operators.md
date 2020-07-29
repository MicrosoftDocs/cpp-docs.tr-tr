---
title: eşzamanlılık ad alanı İşleçleri
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 6cef9304be17dd39e0f0b020133abd08f07fba7c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87194387"
---
# <a name="concurrency-namespace-operators"></a>eşzamanlılık ad alanı İşleçleri

||||
|-|-|-|
|[işleç! =](#operator_neq)|[işleç&amp;&amp;](#operator_amp_amp)|[işleç&gt;](#operator_gt)|
|[işleç&gt;=](#operator_gt_eq)|[işleç&lt;](#operator_lt)|[işleç&lt;=](#operator_lt_eq)|
|[işleç = =](#operator_eq_eq)|[işleç&#124;&#124;](#operator_lor)| |

## <a name="operator124124-operator"></a><a name="operator_lor"></a>işleç&#124;&#124; Işleci

Bağımsız değişken olarak sağlanan görevlerden biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.

```cpp
template<typename ReturnType>
task<ReturnType> operator||(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void> operator||(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>Parametreler

*'Indaki*<br/>
Döndürülen görevin türü.

*Point*<br/>
Elde edilen görevde birleştirilecek ilk görev.

*sağ taraftan*<br/>
Elde edilen görevde birleştirilecek ikinci görev.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevlerinden herhangi biri başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri tür ise `T` , bu işlevin çıktısı bir olur `task<std::vector<T>` . Giriş görevleri tür ise, **`void`** çıkış görevi de olur `task<void>` .

### <a name="remarks"></a>Açıklamalar

Görevlerin her ikisi de iptal edilirse veya özel durum fırlalırsa, döndürülen görev iptal edildi durumunda tamamlanır ve herhangi bir durum oluşursa, `get()` `wait()` Bu görevde veya bu görevi çağırdığınızda oluşturulur.

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>işleç &amp; &amp; işleci

Bağımsız değişken olarak sağlanan görevlerin her ikisi de başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.

```cpp
template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void>  operator&&(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>Parametreler

*'Indaki*<br/>
Döndürülen görevin türü.

*Point*<br/>
Elde edilen görevde birleştirilecek ilk görev.

*sağ taraftan*<br/>
Elde edilen görevde birleştirilecek ikinci görev.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevlerinin her ikisi de başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri tür ise `T` , bu işlevin çıktısı bir olur `task<std::vector<T>>` . Giriş görevleri tür ise, **`void`** çıkış görevi de olur `task<void>` .

### <a name="remarks"></a>Açıklamalar

Görevlerden biri iptal edildiğinde veya bir özel durum oluşturursa, döndürülen görev erken tamamlanır, iptal edildi durumunda ve bir istisna varsa, `get()` `wait()` Bu görevde ya da bu görevi çağırdığınızda oluşur.

## <a name="operator-operator"></a><a name="operator_eq_eq"></a>operator = = Işleci

`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar `concurrent_vector` .

```cpp
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*A1*<br/>
İlk nesnenin ayırıcı türü `concurrent_vector` .

*A2*<br/>
İkinci nesnenin ayırıcı türü `concurrent_vector` .

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektöre eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olmaları durumunda iki eşzamanlı vektör eşittir. Aksi takdirde, bunlar eşit değildir.

Bu yöntem, eş zamanlı vektörlerle ya da başka yöntemlerle değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir `_A` `_B` .

## <a name="operator-operator"></a><a name="operator_neq"></a>operator! = Işleci

`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar `concurrent_vector` .

```cpp
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*A1*<br/>
İlk nesnenin ayırıcı türü `concurrent_vector` .

*A2*<br/>
İkinci nesnenin ayırıcı türü `concurrent_vector` .

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** eşzamanlı vektörler eşit değilse; **`false`** eş zamanlı vektörler eşitse.

### <a name="remarks"></a>Açıklamalar

Aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olmaları durumunda iki eşzamanlı vektör eşittir. Aksi takdirde, bunlar eşit değildir.

Bu yöntem, eş zamanlı vektörlerle ya da başka yöntemlerle değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir `_A` `_B` .

## <a name="operatorlt-operator"></a><a name="operator_lt"></a>işleç &lt; işleci

`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar `concurrent_vector` .

```cpp
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*A1*<br/>
İlk nesnenin ayırıcı türü `concurrent_vector` .

*A2*<br/>
İkinci nesnenin ayırıcı türü `concurrent_vector` .

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden azsa; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `vector` ad alanındaki sınıfı için eşdeğer işleçle aynıdır `std` .

Bu yöntem, eş zamanlı vektörlerle ya da başka yöntemlerle değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir `_A` `_B` .

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a>operator &lt; = işleci

`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden küçük veya ona eşit olup olmadığını sınar `concurrent_vector` .

```cpp
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*A1*<br/>
İlk nesnenin ayırıcı türü `concurrent_vector` .

*A2*<br/>
İkinci nesnenin ayırıcı türü `concurrent_vector` .

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden küçük veya bu değere eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `vector` ad alanındaki sınıfı için eşdeğer işleçle aynıdır `std` .

Bu yöntem, eş zamanlı vektörlerle ya da başka yöntemlerle değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir `_A` `_B` .

## <a name="operatorgt-operator"></a><a name="operator_gt"></a>işleç &gt; işleci

`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar `concurrent_vector` .

```cpp
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*A1*<br/>
İlk nesnenin ayırıcı türü `concurrent_vector` .

*A2*<br/>
İkinci nesnenin ayırıcı türü `concurrent_vector` .

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `vector` ad alanındaki sınıfı için eşdeğer işleçle aynıdır `std` .

Bu yöntem, eş zamanlı vektörlerle ya da başka yöntemlerle değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir `_A` `_B` .

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a>operator &gt; = işleci

`concurrent_vector`İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden büyük veya ona eşit olup olmadığını sınar `concurrent_vector` .

```cpp
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*A1*<br/>
İlk nesnenin ayırıcı türü `concurrent_vector` .

*A2*<br/>
İkinci nesnenin ayırıcı türü `concurrent_vector` .

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden büyükse veya buna eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `vector` ad alanındaki sınıfı için eşdeğer işleçle aynıdır `std` .

Bu yöntem, eş zamanlı vektörlerle ya da başka yöntemlerle değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir `_A` `_B` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
