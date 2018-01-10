---
title: "condition_variable_any sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
dev_langs: C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.workload: cplusplus
ms.openlocfilehash: c3acad50f9dec8e3384d0b811045f95843f40b92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="conditionvariableany-class"></a>condition_variable_any Sınıfı
Bir sınıf kullanma `condition_variable_any` içeren bir olay için beklemeye `mutex` türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class condition_variable_any;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[condition_variable_any](#condition_variable_any)|Oluşturan bir `condition_variable_any` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[notify_all](#notify_all)|Bekleyen tüm iş parçacıklarının engelini kaldırır `condition_variable_any` nesnesi.|  
|[notify_one](#notify_one)|Bekleyen iş parçacıklarının birini engelini kaldırır `condition_variable_any` nesnesi.|  
|[bekleme](#wait)|Bir iş parçacığı engeller.|  
|[wait_for](#wait_for)|Bir iş parçacığı engeller ve daha sonra iş parçacığı engelini kaldırır bir zaman aralığı ayarlar.|  
|[wait_until](#wait_until)|Bir iş parçacığı engeller ve hangi iş parçacığı engelini kaldırır zamanında maksimum noktasını ayarlar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<condition_variable >  
  
 **Namespace:** std  
  
##  <a name="condition_variable_any"></a>condition_variable_any::condition_variable_any Oluşturucusu  
 Oluşturan bir `condition_variable_any` nesnesi.  
  
```
condition_variable_any();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeterli bellek varsa, Oluşturucusu oluşturur bir [system_error](../standard-library/system-error-class.md) olan nesneyi bir `not_enough_memory` hata kodu. Başka bir kaynak kullanılabilir olmadığından nesne oluşturulamıyor, Oluşturucusu döndürürse bir `system_error` olan nesneyi bir `resource_unavailable_try_again` hata kodu.  
  
##  <a name="notify_all"></a>condition_variable_any::notify_all  
 Bekleyen tüm iş parçacıklarının engelini kaldırır `condition_variable_any` nesnesi.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="notify_one"></a>condition_variable_any::notify_one  
 Üzerinde bekleyen iş parçacığı birini engelini kaldırır `condition_variable_any` nesnesi.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="wait"></a>condition_variable_any::wait  
 Bir iş parçacığı engeller.  
  
```
template <class Lock>  
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `Lck`  
 A `mutex` herhangi türde nesne.  
  
 `Pred`  
 Döndüren herhangi bir ifade `true` veya `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk yöntem engeller kadar `condition_variable_any` nesne için bir çağrı tarafından durdurulma [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all). Bu ayrıca spuriously uyandırmak.  
  
 İkinci yöntem, aşağıdaki kodu yürürlükte yürütür.  
  
```
while (!Pred())
    wait(Lck);
```    
  
##  <a name="wait_for"></a>condition_variable_any::wait_for  
 Bir iş parçacığı engeller ve daha sonra iş parçacığı engelini kaldırır bir zaman aralığı ayarlar.  
  
```
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `Lck`  
 A `mutex` herhangi türde nesne.  
  
 `Rel_time`  
 A `chrono::duration` iş parçacığı önce geçen süreyi belirtir nesne uyanır.  
  
 `Pred`  
 Döndüren herhangi bir ifade `true` veya `false`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yöntem döndürür `cv_status::timeout` bekleme ne zaman sona ererse `Rel_time` geçti. Aksi durumda, yöntem döndürür `cv_status::no_timeout`.  
  
 İkinci yöntem değerini döndürür `Pred`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk yöntem engeller kadar `condition_variable_any` nesne için bir çağrı tarafından durdurulma [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all), veya zaman aralığı kadar `Rel_time` geçti. Bu ayrıca spuriously uyandırmak.  
  
 İkinci yöntem, aşağıdaki kodu yürürlükte yürütür.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="wait_until"></a>condition_variable_any::wait_until  
 Bir iş parçacığı engeller ve hangi iş parçacığı engelini kaldırır zamanında maksimum noktasını ayarlar.  
  
```
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `Lck`  
 Mutex nesnesi.  
  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) nesnesi.  
  
 `Pred`  
 Döndüren herhangi bir ifade `true` veya `false`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndüren yöntemler bir `cv_status` yazın return `cv_status::timeout` bekleme ne zaman sona ererse `Abs_time` sona erdiğinde. Aksi takdirde, yöntemleri döndürür `cv_status::no_timeout`.  
  
 Döndüren yöntemler bir `bool` değeri döndürmesi `Pred`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk yöntem engeller kadar `condition_variable` nesne için bir çağrı tarafından durdurulma [notify_one](../standard-library/condition-variable-class.md#notify_one) veya [notify_all](../standard-library/condition-variable-class.md#notify_all), veya kadar `Abs_time`. Bu ayrıca spuriously uyandırmak.  
  
 İkinci yöntem, aşağıdaki kodu yürürlükte yürütür.  
  
```
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 Bir nesne türü için bir işaretçi üçüncü ve dördüncü yöntemleri kullanın `xtime` değiştirmek için `chrono::time_point` nesnesi. `xtime` Nesnesini bir sinyal için beklenecek en uzun süreyi belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)



