---
title: "completion_future sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
dev_langs:
- C++
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24f7012f7fdd9aaeb2443665187aba4eef483e0f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="completionfuture-class"></a>completion_future Sınıfı
Gelecekteki karşılık gelen bir C++ AMP zaman uyumsuz işlemi temsil eder.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
class completion_future;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[completion_future Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `completion_future` sınıfı.|  
|[~completion_future Destructor](#dtor)|Bozar `completion_future` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get](#get)|İlişkili zaman uyumsuz işlemi tamamlanana kadar bekler.|  
|[ardından](#then)|Bir geri çağırma işlevi nesnesine zincir `completion_future` yürütme ilişkili zaman uyumsuz işlemi bittikten sonra yürütülecek nesne.|  
|[to_task](#to_task)|Döndürür bir `task` ilişkili zaman uyumsuz işlemi karşılık gelen nesne.|  
|[valid](#valid)|Nesne bir zaman uyumsuz işlemle ilişkili olup olmadığını belirten bir Boole değeri alır.|  
|[bekleme](#wait)|İlişkili zaman uyumsuz işlemi tamamlanana kadar engeller.|  
|[wait_for](#wait_for)|İlişkili zaman uyumsuz işlemi tamamlanana kadar blokları veya tarafından belirtilen süre `_Rel_time` geçti.|  
|[wait_until](#wait_until)|İlişkili zaman uyumsuz işlemi tamamlanana kadar veya geçerli saati tarafından belirtilen değeri aşarsa kadar engeller `_Abs_time`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç std::shared_future\<void >](#operator_shared_future)|Örtük olarak dönüştürür `completion_future` nesnesine bir `std::shared_future` nesnesi.|  
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `completion_future` bunu nesnesine.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `completion_future`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  


## <a name="ctor"></a> completion_future 

Yeni bir örneğini başlatır `completion_future` sınıfı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
completion_future();  
  
completion_future(  
    const completion_future& _Other );  
  
completion_future(  
    completion_future&& _Other );  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `completion_future` Kopyalama veya taşıma için nesne.  
  
### <a name="overloads-list"></a>Aşırı yükleme listesi  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`completion_future();`|Yeni bir örneğini başlatır `completion_future` sınıfı|  
|`completion_future(const completion_future& _Other);`|Yeni bir örneğini başlatır `completion_future` bir oluşturucu kopyalayarak sınıfı.|  
|`completion_future(completion_future&& _Other);`|Yeni bir örneğini başlatır `completion_future` bir oluşturucu taşıyarak sınıfı.|  
  
## <a name="get"></a> Al 

İlişkili zaman uyumsuz işlemi tamamlanana kadar bekler. Bir zaman uyumsuz işlemi sırasında karşılaşılması durumunda depolanan özel durum oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void get() const;  
```  
  
## <a name="operator_shared_future"></a> işleç std::shared_future<void> 

Örtük olarak dönüştürür `completion_future` nesnesine bir `std::shared_future` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
operator std::shared_future<void>() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `std::shared_future` nesnesi.  
  
## <a name="operator_eq"></a> işleç = 

Belirtilen içeriğini kopyalar `completion_future` bunu nesnesine.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
completion_future&  operator= (const completion_future& _Other );    
completion_future&  operator= (completion_future&& _Other );  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `completion_future` nesnesi.  
  
## <a name="overloads-list"></a>Aşırı yükleme listesi  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`completion_future& operator=(const completion_future& _Other);`|Belirtilen içeriğini kopyalar `completion_future` derin bir kopyasını kullanarak bunu nesnesine.|  
|`completion_future& operator=(completion_future&& _Other);`|Belirtilen içeriğini kopyalar `completion_future` taşıma atama kullanarak bunu nesnesine.|  
  
## <a name="then">ardından</a> 

Bir geri çağırma işlevi nesnesine zincir `completion_future` yürütme ilişkili zaman uyumsuz işlemi bittikten sonra yürütülecek nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template <typename _Functor>  
void then(const _Functor & _Func ) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Functor`  
 Geri çağırma functor.  
  
 `_Func`  
 Geri çağırma işlevi nesnesi.  
  
## <a name="to_task"></a> to_task 

Döndürür bir `task` ilişkili zaman uyumsuz işlemi karşılık gelen nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
concurrency::task<void> to_task() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `task` ilişkili zaman uyumsuz işlemi karşılık gelen nesne.  
  
## <a name="valid"></a> Geçerli 

Nesne bir zaman uyumsuz işlemle ilişkili olup olmadığını belirten bir Boole değeri alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool valid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Nesne zaman uyumsuz bir işlem ile ilişkili ise; Aksi takdirde `false`.  
  
## <a name="wait">bekleme</a> 

İlişkili zaman uyumsuz işlemi tamamlanana kadar engeller.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void wait() const;  
```  
  
## <a name="wait_for"></a> wait_for 

İlişkili zaman uyumsuz işlemi tamamlanana kadar blokları veya tarafından belirtilen zaman `_Rel_time` geçti.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template <  
    class _Rep,  
    class _Period  
>  
std::future_status::future_status wait_for(  
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rep`  
 Ticks sayısını temsil eden bir aritmetik türü.  
  
 `_Period`  
 Sayaç değeri başına beklenecek saniye sayısını temsil eden std::ratio.  
  
 `_Rel_time`  
 İşlemin tamamlanması için beklenecek süreyi maksimum tutar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 döndürür:  
  
-   `std::future_status::deferred` ilişkili zaman uyumsuz işlemi çalışmıyorsa.  
  
-   `std::future_status::ready` ilişkili zaman uyumsuz işlemi tamamlandıysa.  
  
-   `std::future_status::timeout` Belirtilen zaman süresi dolmuşsa.  
  
## <a name="wait_until"></a> wait_until 

İlişkili zaman uyumsuz işlemi tamamlanana kadar veya geçerli saati tarafından belirtilen değeri aşarsa kadar engeller `_Abs_time`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template <  
    class _Clock,  
    class _Duration  
>  
std::future_status::future_status wait_until(  
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Clock`  
 Bu zaman noktası ölçülen saat.  
  
 `_Duration`  
 Zaman aralığı başladığından bu yana `_Clock`'s dönem, işlev sonra zaman aşımına gösterir.  
  
 `_Abs_time`  
 Daha sonra işlevi zaman aşımına uğrayacaktır zaman içinde nokta.  
  
### <a name="return-value"></a>Dönüş Değeri  
 döndürür:  
  
1.  `std::future_status::deferred` ilişkili zaman uyumsuz işlemi çalışmıyorsa.  
  
2.  `std::future_status::ready` ilişkili zaman uyumsuz işlemi tamamlandıysa.  
  
3.  `std::future_status::timeout` Belirtilen süre geçti.  
  
## <a name="dtor"></a> ~ completion_future 

Bozar `completion_future` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
~completion_future();  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
