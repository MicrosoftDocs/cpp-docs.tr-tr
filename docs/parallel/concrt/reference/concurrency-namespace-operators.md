---
title: "Eşzamanlılık ad alanı işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
dev_langs: C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9305f860fb393d2f5d3149300d8df4cfa9f6e5a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="concurrency-namespace-operators"></a>Eşzamanlılık ad alanı işleçleri
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[işleci&amp;&amp;](#operator_amp_amp)|[işleci&gt;](#operator_gt)|  
|[işleci&gt;=](#operator_gt_eq)|[işleci&lt;](#operator_lt)|[işleci&lt;=](#operator_lt_eq)|  
|[operator ==](#operator_eq_eq)|[işleci||](#operator_lor)|  
  
##  <a name="operator_lor"></a>operator &#124; &#124; İşleci  
 Bağımsız değişkenler tamamladıkça başarıyla görevlerin birini ne zaman sağlanan başarıyla tamamlanır bir görev oluşturur.  
  
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
 `ReturnType`  
 Döndürülen görev türü.  
  
 `lhs`  
 Sonuçta elde edilen göreve birleştirmek için ilk görev.  
  
 `rhs`  
 Sonuçta elde edilen göreve birleştirmek için ikinci görev.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş görevlerin birini tamamlandı zaman başarıyla başarıyla tamamlanan bir görev. Giriş görevleri türdeyse `T`, bu işlevin çıktı bir `task<std::vector<T>`. Giriş görevleri türdeyse `void` çıkışı da bu durumda görev bir `task<void>`.  
  
### <a name="remarks"></a>Açıklamalar  
 Görevleri her ikisi de iptal edildi veya özel durumlar oluşturma, döndürülen görevi iptal edilmiş durumda tamamlayacak ve özel durumları, biri herhangi bir hata oluşursa, durum çağırdığınızda `get()` veya `wait()` bu görevde.  
  
##  <a name="operator_amp_amp"></a>İşleç&amp; &amp; işleci  
 Bağımsız değişkenler olarak verilen görevleri her ikisi de başarıyla tamamlandığında, başarılı bir şekilde tamamlanır bir görev oluşturur.  
  
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
 `ReturnType`  
 Döndürülen görev türü.  
  
 `lhs`  
 Sonuçta elde edilen göreve birleştirmek için ilk görev.  
  
 `rhs`  
 Sonuçta elde edilen göreve birleştirmek için ikinci görev.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş görevleri her ikisi de başarıyla tamamladığınızda başarıyla tamamlanan bir görev. Giriş görevleri türdeyse `T`, bu işlevin çıktı bir `task<std::vector<T>>`. Giriş görevleri türdeyse `void` çıkışı da bu durumda görev bir `task<void>`.  
  
### <a name="remarks"></a>Açıklamalar  
 Görevlerden birini iptal veya bir özel durum oluşturur, döndürülen görevi erken, iptal edilmiş durumda tamamlayacak ve encoutered, ise çağırırsanız özel durum oluşturulacak `get()` veya `wait()` bu görevde.  
  
##  <a name="operator_eq_eq"></a>operator == işleci  
 Varsa testleri `concurrent_vector` nesne işlecinin sol tarafındaki eşittir `concurrent_vector` sağ tarafında nesne.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `A1`  
 İlk ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `A2`  
 İkinci ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `_A`  
 Türünde bir nesne `concurrent_vector`.  
  
 `_B`  
 Türünde bir nesne `concurrent_vector`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı vektör işlecinin sol tarafındaki işlecinin sağ tarafında eşzamanlı vektör eşitse; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 İki eşzamanlı vektör aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşit. Aksi takdirde, bunlar eşit.  
  
 Bu yöntem eşzamanlılık uyumlu ya da eş zamanlı vektörlerinin değiştirebileceği diğer yöntemleri göre değil `_A` veya `_B`.  
  
##  <a name="operator_neq"></a>operator! = işleci  
 Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesi eşit değil `concurrent_vector` sağ tarafında nesne.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `A1`  
 İlk ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `A2`  
 İkinci ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `_A`  
 Türünde bir nesne `concurrent_vector`.  
  
 `_B`  
 Türünde bir nesne `concurrent_vector`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı vektörlerinin eşit değilse; `false` eşzamanlı vektörlerinin eşit olması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 İki eşzamanlı vektör aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşit. Aksi takdirde, bunlar eşit.  
  
 Bu yöntem eşzamanlılık uyumlu ya da eş zamanlı vektörlerinin değiştirebileceği diğer yöntemleri göre değil `_A` veya `_B`.  
  
##  <a name="operator_lt"></a>İşleç&lt; işleci  
 Varsa testleri `concurrent_vector` nesne işlecinin sol tarafındaki küçük `concurrent_vector` sağ tarafında nesne.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `A1`  
 İlk ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `A2`  
 İkinci ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `_A`  
 Türünde bir nesne `concurrent_vector`.  
  
 `_B`  
 Türünde bir nesne `concurrent_vector`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı vektör işlecinin sol tarafındaki işlecinin sağ tarafında eşzamanlı vektör azsa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç davranışını eşdeğer işleci için aynı olan `vector` sınıfını `std` ad alanı.  
  
 Bu yöntem eşzamanlılık uyumlu ya da eş zamanlı vektörlerinin değiştirebileceği diğer yöntemleri göre değil `_A` veya `_B`.  
  
##  <a name="operator_lt_eq"></a>İşleç&lt;= işleci  
 Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesidir küçük veya eşit `concurrent_vector` sağ tarafında nesne.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `A1`  
 İlk ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `A2`  
 İkinci ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `_A`  
 Türünde bir nesne `concurrent_vector`.  
  
 `_B`  
 Türünde bir nesne `concurrent_vector`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı vektör işlecinin sol tarafındaki işlecinin sağ tarafında eşzamanlı vektör eşit veya daha azsa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç davranışını eşdeğer işleci için aynı olan `vector` sınıfını `std` ad alanı.  
  
 Bu yöntem eşzamanlılık uyumlu ya da eş zamanlı vektörlerinin değiştirebileceği diğer yöntemleri göre değil `_A` veya `_B`.  
  
##  <a name="operator_gt"></a>İşleç&gt; işleci  
 Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesidir büyük `concurrent_vector` sağ tarafında nesne.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `A1`  
 İlk ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `A2`  
 İkinci ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `_A`  
 Türünde bir nesne `concurrent_vector`.  
  
 `_B`  
 Türünde bir nesne `concurrent_vector`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı vektör işlecinin sol tarafındaki işlecinin sağ tarafında eşzamanlı vektör büyükse; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç davranışını eşdeğer işleci için aynı olan `vector` sınıfını `std` ad alanı.  
  
 Bu yöntem eşzamanlılık uyumlu ya da eş zamanlı vektörlerinin değiştirebileceği diğer yöntemleri göre değil `_A` veya `_B`.  
  
##  <a name="operator_gt_eq"></a>İşleç&gt;= işleci  
 Varsa testleri `concurrent_vector` işlecinin sol tarafındaki nesnesidir değerinden büyük veya eşit `concurrent_vector` sağ tarafında nesne.  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Eşzamanlı vektörler depolanan öğelerin veri türü.  
  
 `A1`  
 İlk ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `A2`  
 İkinci ayırıcısı türünü `concurrent_vector` nesnesi.  
  
 `_A`  
 Türünde bir nesne `concurrent_vector`.  
  
 `_B`  
 Türünde bir nesne `concurrent_vector`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`eşzamanlı vektör işlecinin sol tarafındaki işlecinin sağ tarafında eşzamanlı vektör eşit veya daha büyük ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç davranışını eşdeğer işleci için aynı olan `vector` sınıfını `std` ad alanı.  
  
 Bu yöntem eşzamanlılık uyumlu ya da eş zamanlı vektörlerinin değiştirebileceği diğer yöntemleri göre değil `_A` veya `_B`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
