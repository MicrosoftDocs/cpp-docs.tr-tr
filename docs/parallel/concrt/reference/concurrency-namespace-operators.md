---
title: eşzamanlılık ad alanı İşleçleri
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: aac43a15b09bd792118fbfe7ea51493b73b8ac9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374388"
---
# <a name="concurrency-namespace-operators"></a>eşzamanlılık ad alanı İşleçleri

||||
|-|-|-|
|[işleç!=](#operator_neq)|[Işleç&amp;&amp;](#operator_amp_amp)|[Işleç&gt;](#operator_gt)|
|[Işleç&gt;=](#operator_gt_eq)|[Işleç&lt;](#operator_lt)|[Işleç&lt;=](#operator_lt_eq)|
|[işleç==](#operator_eq_eq)|[operatör&#124;&#124;](#operator_lor)| |

## <a name="operator124124-operator"></a><a name="operator_lor"></a>operatör&#124;&#124; Operatörü

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

*Returntype*<br/>
Döndürülen görevin türü.

*Lhs*<br/>
Elde edilen görev de birleştirmek için ilk görev.

*Rhs*<br/>
İkinci görev ortaya çıkan görev içine birleştirmek için.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevlerinden biri başarıyla tamamlandığında başarıyla tamamlayan bir görev. Giriş görevleri türde `T`ise, bu işlevin çıktısı `task<std::vector<T>`. Giriş görevleri tür `void` varsa çıktı görevi de bir `task<void>`.

### <a name="remarks"></a>Açıklamalar

Görevlerin her ikisi de iptal edilirse veya özel durumlar atılırsa, döndürülen görev iptal edilen durumda tamamlanır ve karşılaşırsa `get()` özel `wait()` durumlardan biri, aradığınızda veya bu görevde atılır.

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>operatör&amp; &amp; Operatörü

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

*Returntype*<br/>
Döndürülen görevin türü.

*Lhs*<br/>
Elde edilen görev de birleştirmek için ilk görev.

*Rhs*<br/>
İkinci görev ortaya çıkan görev içine birleştirmek için.

### <a name="return-value"></a>Dönüş Değeri

Her iki giriş görevi de başarıyla tamamlandığında başarıyla tamamlayan bir görev. Giriş görevleri türde `T`ise, bu işlevin çıktısı `task<std::vector<T>>`. Giriş görevleri tür `void` varsa çıktı görevi de bir `task<void>`.

### <a name="remarks"></a>Açıklamalar

Görevlerden biri iptal edilirse veya özel bir durum atarsa, döndürülen görev iptal edilen durumda erken tamamlanır ve biri oluşursa, bu görevde `get()` veya `wait()` bu görevde özel durum atılır.

## <a name="operator-operator"></a><a name="operator_eq_eq"></a>işleç== Operatör

Işlecinin `concurrent_vector` sol tarafındaki nesnenin sağ taraftaki `concurrent_vector` nesneye eşit olup olmadığını test edin.

```cpp
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*A1*<br/>
İlk `concurrent_vector` nesnenin ayırıcı türü.

*A2*<br/>
İkinci `concurrent_vector` nesnenin ayırıcı türü.

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki eşzamanlı vektör işlecinin sağ tarafındaki eşzamanlı vektöre eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Aynı sayıda eleman varsa ve ilgili öğeleri aynı değerlere sahipse, iki eşzamanlı vektör eşittir. Aksi takdirde, eşit değildir.

Bu yöntem, eşzamanlı vektörlerden `_A` herhangi birini değiştirebilecek diğer yöntemlerle ilgili `_B`olarak eşzamanlılık açısından güvenli değildir veya.

## <a name="operator-operator"></a><a name="operator_neq"></a>işleç!= Operatör

Işlecinin `concurrent_vector` sol tarafındaki nesnenin sağ taraftaki `concurrent_vector` nesneye eşit olmamasını test edin.

```cpp
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*A1*<br/>
İlk `concurrent_vector` nesnenin ayırıcı türü.

*A2*<br/>
İkinci `concurrent_vector` nesnenin ayırıcı türü.

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

eşzamanlı vektörler eşit değilse **doğrudur;** eşzamanlı vektörler eşitse **yanlış** olur.

### <a name="remarks"></a>Açıklamalar

Aynı sayıda eleman varsa ve ilgili öğeleri aynı değerlere sahipse, iki eşzamanlı vektör eşittir. Aksi takdirde, eşit değildir.

Bu yöntem, eşzamanlı vektörlerden `_A` herhangi birini değiştirebilecek diğer yöntemlerle ilgili `_B`olarak eşzamanlılık açısından güvenli değildir veya.

## <a name="operatorlt-operator"></a><a name="operator_lt"></a>operatör&lt; Operatörü

İşleticinin `concurrent_vector` sol tarafındaki nesnenin sağ taraftaki `concurrent_vector` nesneden daha az olup olmadığını test edin.

```cpp
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*A1*<br/>
İlk `concurrent_vector` nesnenin ayırıcı türü.

*A2*<br/>
İkinci `concurrent_vector` nesnenin ayırıcı türü.

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki eşzamanlı vektör işlecinin sağ tarafındaki eşzamanlı vektörden daha azsa **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecinin `vector` `std` davranışı, ad alanındaki sınıfın eşdeğer işleciyle aynıdır.

Bu yöntem, eşzamanlı vektörlerden `_A` herhangi birini değiştirebilecek diğer yöntemlerle ilgili `_B`olarak eşzamanlılık açısından güvenli değildir veya.

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a>işleç&lt;= Operatör

İşleticinin `concurrent_vector` sol tarafındaki nesnenin sağ taraftaki `concurrent_vector` nesneye daha az veya eşit olup olmadığını test edin.

```cpp
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*A1*<br/>
İlk `concurrent_vector` nesnenin ayırıcı türü.

*A2*<br/>
İkinci `concurrent_vector` nesnenin ayırıcı türü.

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki eşzamanlı vektör operatörün sağ tarafındaki eşzamanlı vektörden daha az veya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecinin `vector` `std` davranışı, ad alanındaki sınıfın eşdeğer işleciyle aynıdır.

Bu yöntem, eşzamanlı vektörlerden `_A` herhangi birini değiştirebilecek diğer yöntemlerle ilgili `_B`olarak eşzamanlılık açısından güvenli değildir veya.

## <a name="operatorgt-operator"></a><a name="operator_gt"></a>operatör&gt; Operatörü

İşleticinin `concurrent_vector` sol tarafındaki nesnenin sağ taraftaki `concurrent_vector` nesneden büyük olup olmadığını test edin.

```cpp
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*A1*<br/>
İlk `concurrent_vector` nesnenin ayırıcı türü.

*A2*<br/>
İkinci `concurrent_vector` nesnenin ayırıcı türü.

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki eşzamanlı vektör işlecinin sağ tarafındaki eşzamanlı vektörden büyükse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecinin `vector` `std` davranışı, ad alanındaki sınıfın eşdeğer işleciyle aynıdır.

Bu yöntem, eşzamanlı vektörlerden `_A` herhangi birini değiştirebilecek diğer yöntemlerle ilgili `_B`olarak eşzamanlılık açısından güvenli değildir veya.

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a>işleç&gt;= Operatör

İşleticinin `concurrent_vector` sol tarafındaki nesnenin sağ taraftaki `concurrent_vector` nesneyden büyük veya eşit olup olmadığını test edin.

```cpp
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektörlerde depolanan öğelerin veri türü.

*A1*<br/>
İlk `concurrent_vector` nesnenin ayırıcı türü.

*A2*<br/>
İkinci `concurrent_vector` nesnenin ayırıcı türü.

*_A*<br/>
`concurrent_vector` türünün bir nesnesi.

*_B*<br/>
`concurrent_vector` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecinin sol tarafındaki eşzamanlı vektör operatörün sağ tarafındaki eşzamanlı vektörden büyük veya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlecinin `vector` `std` davranışı, ad alanındaki sınıfın eşdeğer işleciyle aynıdır.

Bu yöntem, eşzamanlı vektörlerden `_A` herhangi birini değiştirebilecek diğer yöntemlerle ilgili `_B`olarak eşzamanlılık açısından güvenli değildir veya.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
