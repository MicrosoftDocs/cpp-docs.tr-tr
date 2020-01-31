---
title: eşzamanlılık ad alanı İşleçleri
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 00accee4f28167b94b9193aec6d90f32ed242dbe
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821134"
---
# <a name="concurrency-namespace-operators"></a>eşzamanlılık ad alanı İşleçleri

||||
|-|-|-|
|[operator!=](#operator_neq)|[işleç&amp;&amp;](#operator_amp_amp)|[işleç&gt;](#operator_gt)|
|[işleç&gt;=](#operator_gt_eq)|[işleç&lt;](#operator_lt)|[işleç&lt;=](#operator_lt_eq)|
|[operator==](#operator_eq_eq)|[operator&#124;&#124;](#operator_lor)| |

##  <a name="operator_lor"></a>işleç&#124; &#124; işleci

Bağımsız değişken olarak sağlanan görevlerden biri başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.

```
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

Giriş görevlerinden herhangi biri başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri `T`türünde ise, bu işlevin çıktısı bir `task<std::vector<T>`olur. Giriş görevleri türü `void`, çıkış görevi de bir `task<void>`olacaktır.

### <a name="remarks"></a>Açıklamalar

Görevlerin her ikisi de iptal edilirse veya özel durum fırlalırsa, döndürülen görev iptal edildi durumunda tamamlanır ve bu görevde karşılaşılırsa, bu görevde `get()` veya `wait()` çağırdığınızda oluşturulur.

##  <a name="operator_amp_amp"></a>işleç&amp;&amp; Işleci

Bağımsız değişken olarak sağlanan görevlerin her ikisi de başarıyla tamamlandığında başarıyla tamamlanacak bir görev oluşturur.

```
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

Giriş görevlerinin her ikisi de başarıyla tamamlandığında başarıyla tamamlanan bir görev. Giriş görevleri `T`türünde ise, bu işlevin çıktısı bir `task<std::vector<T>>`olur. Giriş görevleri türü `void`, çıkış görevi de bir `task<void>`olacaktır.

### <a name="remarks"></a>Açıklamalar

Görevlerden biri iptal edildiğinde veya bir özel durum oluşturursa, döndürülen görev erken tamamlanır, iptal edildi durumunda ve bir özel durum, bu görevde `get()` veya `wait()` çağırdıysanız oluşturulur.

##  <a name="operator_eq_eq"></a>operator = = Işleci

İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesine eşit olup olmadığını sınar.

```
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*Sırasıyla*<br/>
İlk `concurrent_vector` nesnesinin ayırıcı türü.

*Y2*<br/>
İkinci `concurrent_vector` nesnesinin ayırıcı türü.

*_A*<br/>
`concurrent_vector`türünde bir nesne.

*_B*<br/>
`concurrent_vector`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektöre eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olmaları durumunda iki eşzamanlı vektör eşittir. Aksi takdirde, bunlar eşit değildir.

Bu yöntem, eşzamanlı vektörlerle `_A` ya da `_B`değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir.

##  <a name="operator_neq"></a>operator! = Işleci

İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesine eşit olup olmadığını sınar.

```
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*Sırasıyla*<br/>
İlk `concurrent_vector` nesnesinin ayırıcı türü.

*Y2*<br/>
İkinci `concurrent_vector` nesnesinin ayırıcı türü.

*_A*<br/>
`concurrent_vector`türünde bir nesne.

*_B*<br/>
`concurrent_vector`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

eşzamanlı vektörler eşit değilse **doğru** ; eşzamanlı vektörler eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Aynı sayıda öğe varsa ve ilgili öğeleri aynı değere sahip olmaları durumunda iki eşzamanlı vektör eşittir. Aksi takdirde, bunlar eşit değildir.

Bu yöntem, eşzamanlı vektörlerle `_A` ya da `_B`değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir.

##  <a name="operator_lt"></a>işleç&lt; Işleci

İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden küçük olup olmadığını sınar.

```
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*Sırasıyla*<br/>
İlk `concurrent_vector` nesnesinin ayırıcı türü.

*Y2*<br/>
İkinci `concurrent_vector` nesnesinin ayırıcı türü.

*_A*<br/>
`concurrent_vector`türünde bir nesne.

*_B*<br/>
`concurrent_vector`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `std` ad alanındaki `vector` sınıfı için eşdeğer işleçle aynıdır.

Bu yöntem, eşzamanlı vektörlerle `_A` ya da `_B`değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir.

##  <a name="operator_lt_eq"></a>operator&lt;= Işleci

İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden küçük veya ona eşit olup olmadığını sınar.

```
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*Sırasıyla*<br/>
İlk `concurrent_vector` nesnesinin ayırıcı türü.

*Y2*<br/>
İkinci `concurrent_vector` nesnesinin ayırıcı türü.

*_A*<br/>
`concurrent_vector`türünde bir nesne.

*_B*<br/>
`concurrent_vector`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden küçük veya bu değere eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `std` ad alanındaki `vector` sınıfı için eşdeğer işleçle aynıdır.

Bu yöntem, eşzamanlı vektörlerle `_A` ya da `_B`değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir.

##  <a name="operator_gt"></a>işleç&gt; Işleci

İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden büyük olup olmadığını sınar.

```
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*Sırasıyla*<br/>
İlk `concurrent_vector` nesnesinin ayırıcı türü.

*Y2*<br/>
İkinci `concurrent_vector` nesnesinin ayırıcı türü.

*_A*<br/>
`concurrent_vector`türünde bir nesne.

*_B*<br/>
`concurrent_vector`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden büyükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `std` ad alanındaki `vector` sınıfı için eşdeğer işleçle aynıdır.

Bu yöntem, eşzamanlı vektörlerle `_A` ya da `_B`değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir.

##  <a name="operator_gt_eq"></a>operator&gt;= Işleci

İşlecin sol tarafındaki `concurrent_vector` nesnesinin sağ taraftaki `concurrent_vector` nesnesinden büyük veya ona eşit olup olmadığını sınar.

```
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Eşzamanlı vektörde depolanan öğelerin veri türü.

*Sırasıyla*<br/>
İlk `concurrent_vector` nesnesinin ayırıcı türü.

*Y2*<br/>
İkinci `concurrent_vector` nesnesinin ayırıcı türü.

*_A*<br/>
`concurrent_vector`türünde bir nesne.

*_B*<br/>
`concurrent_vector`türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki eşzamanlı vektör, işlecin sağ tarafındaki eşzamanlı vektörden büyükse veya buna eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecin davranışı, `std` ad alanındaki `vector` sınıfı için eşdeğer işleçle aynıdır.

Bu yöntem, eşzamanlı vektörlerle `_A` ya da `_B`değiştirebilen diğer yöntemlere göre eşzamanlılık açısından güvenli değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
