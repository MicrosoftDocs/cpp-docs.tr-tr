---
title: Eşzamanlılık ad alanı işleçleri
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 5982ae0ec3baff38b43b0ce504a47d512559390d
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521615"
---
# <a name="concurrency-namespace-operators"></a>Eşzamanlılık ad alanı işleçleri

||||
|-|-|-|
|[operator!=](#operator_neq)|[İşleci&amp;&amp;](#operator_amp_amp)|[İşleci&gt;](#operator_gt)|
|[İşleci&gt;=](#operator_gt_eq)|[İşleci&lt;](#operator_lt)|[İşleci&lt;=](#operator_lt_eq)|
|[operator==](#operator_eq_eq)|[operator&#124;&#124;](#operator_lor)| |

##  <a name="operator_lor"></a>  İşleç&#124; &#124; işleci

Ne zaman görevlerden birini sağlanan bağımsız değişkenler tamamladıkça başarıyla başarıyla tamamlanacak bir görev oluşturur.

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

*ReturnType*<br/>
Döndürülen görevin türü.

*lhs*<br/>
Sonuçta elde edilen görevle birleştirilecek için ilk görev.

*Sol*<br/>
Sonuçta elde edilen görevle birleştirilecek ikinci görev.

### <a name="return-value"></a>Dönüş Değeri

Giriş görevleri birini tamamlandı, başarıyla başarıyla tamamlanan bir görev. Giriş görevleri türündeyse `T`, bu işlevin çıktısı olacak bir `task<std::vector<T>`. Giriş görevleri türündeyse `void` çıktı görevi de olacak bir `task<void>`.

### <a name="remarks"></a>Açıklamalar

Hem görev iptal edilir ya da özel durumlar, iptal edildi durumunda getirilen görev tamamlanır ve özel durumları, biri herhangi karşılaşılırsa oluşturulur çağırdığınızda `get()` veya `wait()` o görevde.

##  <a name="operator_amp_amp"></a>  İşleç&amp; &amp; işleci

Her iki bağımsız değişken olarak sağlanan görevler başarıyla tamamladığında başarıyla tamamlanacak bir görev oluşturur.

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

*ReturnType*<br/>
Döndürülen görevin türü.

*lhs*<br/>
Sonuçta elde edilen görevle birleştirilecek için ilk görev.

*Sol*<br/>
Sonuçta elde edilen görevle birleştirilecek ikinci görev.

### <a name="return-value"></a>Dönüş Değeri

Başarılı bir şekilde ne zaman hem de giriş görevleri başarıyla tamamlanan bir görev. Giriş görevleri türündeyse `T`, bu işlevin çıktısı olacak bir `task<std::vector<T>>`. Giriş görevleri türündeyse `void` çıktı görevi de olacak bir `task<void>`.

### <a name="remarks"></a>Açıklamalar

Görevlerden birini iptal edilir ya da bir özel durum oluşturur, döndürülen görev iptal edildi durumunda erkenden tamamlanır ve çağırırsanız, karşılaşıldıysa özel durum oluşturulur `get()` veya `wait()` o görevde.

##  <a name="operator_eq_eq"></a>  operator == işleci

Olmadığını test eder `concurrent_vector` işlecin sol tarafındaki nesnesinin eşit olup `concurrent_vector` işlecin sağ tarafındaki nesne.

```
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*A1*<br/>
İlk ayırıcı türünü `concurrent_vector` nesne.

*A2*<br/>
İkinci ayırıcı türünü `concurrent_vector` nesne.

*_A*<br/>
Bir nesne türü `concurrent_vector`.

*_B*<br/>
Bir nesne türü `concurrent_vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki eşzamanlı vektör Aksi takdirde işlecin sağ tarafındaki eşzamanlı vektör eşit ise **false**.

### <a name="remarks"></a>Açıklamalar

Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki eş zamanlı vektör eşit olur. Aksi takdirde, eşit oldukları.

Bu yöntem eşzamanlı güvenli eş zamanlı vektör birini değiştirebilir diğer yöntemleri göre değil `_A` veya `_B`.

##  <a name="operator_neq"></a>  işleç! = işleci

Olmadığını test eder `concurrent_vector` işlecinin sol tarafındaki nesnesi eşit değil `concurrent_vector` işlecin sağ tarafındaki nesne.

```
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*A1*<br/>
İlk ayırıcı türünü `concurrent_vector` nesne.

*A2*<br/>
İkinci ayırıcı türünü `concurrent_vector` nesne.

*_A*<br/>
Bir nesne türü `concurrent_vector`.

*_B*<br/>
Bir nesne türü `concurrent_vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** eş zamanlı vektör eşit; değilse, **false** eş zamanlı vektör eşitse.

### <a name="remarks"></a>Açıklamalar

Bunlar aynı sayıda öğe varsa ve ilgili öğeleri aynı değerlere sahip iki eş zamanlı vektör eşit olur. Aksi takdirde, eşit oldukları.

Bu yöntem eşzamanlı güvenli eş zamanlı vektör birini değiştirebilir diğer yöntemleri göre değil `_A` veya `_B`.

##  <a name="operator_lt"></a>  İşleç&lt; işleci

Olmadığını test eder `concurrent_vector` nesne işlecinin sol tarafındaki küçüktür `concurrent_vector` işlecin sağ tarafındaki nesne.

```
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*A1*<br/>
İlk ayırıcı türünü `concurrent_vector` nesne.

*A2*<br/>
İkinci ayırıcı türünü `concurrent_vector` nesne.

*_A*<br/>
Bir nesne türü `concurrent_vector`.

*_B*<br/>
Bir nesne türü `concurrent_vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki eşzamanlı vektör; işlecin sağ tarafındaki eşzamanlı vektör altındaysa Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç davranışını eşdeğer operatör için aynı `vector` sınıfını `std` ad alanı.

Bu yöntem eşzamanlı güvenli eş zamanlı vektör birini değiştirebilir diğer yöntemleri göre değil `_A` veya `_B`.

##  <a name="operator_lt_eq"></a>  İşleç&lt;= işleci

Olmadığını test eder `concurrent_vector` işlecin sol tarafındaki nesnesinin değerinden küçük veya buna eşit olup `concurrent_vector` işlecin sağ tarafındaki nesne.

```
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*A1*<br/>
İlk ayırıcı türünü `concurrent_vector` nesne.

*A2*<br/>
İkinci ayırıcı türünü `concurrent_vector` nesne.

*_A*<br/>
Bir nesne türü `concurrent_vector`.

*_B*<br/>
Bir nesne türü `concurrent_vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki eşzamanlı vektör daha veya işlecin sağ tarafındaki eşzamanlı vektör eşit Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç davranışını eşdeğer operatör için aynı `vector` sınıfını `std` ad alanı.

Bu yöntem eşzamanlı güvenli eş zamanlı vektör birini değiştirebilir diğer yöntemleri göre değil `_A` veya `_B`.

##  <a name="operator_gt"></a>  İşleç&gt; işleci

Olmadığını test eder `concurrent_vector` nesne işlecinin sol tarafındaki büyük `concurrent_vector` işlecin sağ tarafındaki nesne.

```
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*A1*<br/>
İlk ayırıcı türünü `concurrent_vector` nesne.

*A2*<br/>
İkinci ayırıcı türünü `concurrent_vector` nesne.

*_A*<br/>
Bir nesne türü `concurrent_vector`.

*_B*<br/>
Bir nesne türü `concurrent_vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki eşzamanlı vektör ise, aksi takdirde eşzamanlı vektör işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç davranışını eşdeğer operatör için aynı `vector` sınıfını `std` ad alanı.

Bu yöntem eşzamanlı güvenli eş zamanlı vektör birini değiştirebilir diğer yöntemleri göre değil `_A` veya `_B`.

##  <a name="operator_gt_eq"></a>  İşleç&gt;= işleci

Olmadığını test eder `concurrent_vector` işlecin sol tarafındaki nesnesinin değerinden büyük veya ona eşit olup `concurrent_vector` işlecin sağ tarafındaki nesne.

```
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşzamanlı vektör içinde depolanan öğelerin veri türü.

*A1*<br/>
İlk ayırıcı türünü `concurrent_vector` nesne.

*A2*<br/>
İkinci ayırıcı türünü `concurrent_vector` nesne.

*_A*<br/>
Bir nesne türü `concurrent_vector`.

*_B*<br/>
Bir nesne türü `concurrent_vector`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki eşzamanlı vektör büyüktür veya eşittir eşzamanlı vektör işlecin sağ tarafındaki; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç davranışını eşdeğer operatör için aynı `vector` sınıfını `std` ad alanı.

Bu yöntem eşzamanlı güvenli eş zamanlı vektör birini değiştirebilir diğer yöntemleri göre değil `_A` veya `_B`.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
