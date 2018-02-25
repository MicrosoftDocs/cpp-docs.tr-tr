---
title: "condition_variable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: d3d4f917bd9057eed6dfcd2b480bbb8afb2f7ccf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="conditionvariable-class"></a>condition_variable Sınıfı
Kullanım `condition_variable` varsa bir olay için beklemeye sınıfı bir `mutex` türü `unique_lock<mutex>`. Bu tür nesneler türündeki nesneleri daha iyi performans olabilir [condition_variable_any < unique_lock\<mutex >>](../standard-library/condition-variable-any-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class condition_variable;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[condition_variable](#condition_variable)|Oluşturan bir `condition_variable` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[native_handle](#native_handle)|Condition_variable tanıtıcısı temsil eden uygulamaya özel türü döndürür.|  
|[notify_all](#notify_all)|Bekleyen tüm iş parçacıklarının engelini kaldırır `condition_variable` nesnesi.|  
|[notify_one](#notify_one)|Bekleyen iş parçacıklarının birini engelini kaldırır `condition_variable` nesnesi.|  
|[bekleme](#wait)|Bir iş parçacığı engeller.|  
|[wait_for](#wait_for)|Bir iş parçacığı engeller ve daha sonra iş parçacığı engelini kaldırır bir zaman aralığı ayarlar.|  
|[wait_until](#wait_until)|Bir iş parçacığı engeller ve hangi iş parçacığı engelini kaldırır zamanında maksimum noktasını ayarlar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<condition_variable >  
  
 **Namespace:** std  
  
##  <a name="condition_variable"></a>  condition_variable::condition_variable Constructor  
 Oluşturan bir `condition_variable` nesnesi.  
  
```
condition_variable();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeterli bellek varsa, Oluşturucusu oluşturur bir [system_error](../standard-library/system-error-class.md) olan nesneyi bir `not_enough_memory` hata kodu. Başka bir kaynak kullanılabilir olmadığından nesne oluşturulamıyor, Oluşturucusu döndürürse bir `system_error` olan nesneyi bir `resource_unavailable_try_again` hata kodu.  
  
##  <a name="native_handle"></a>  condition_variable::native_handle  
 Condition_variable tanıtıcısı temsil eden uygulamaya özel tür döndürür.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `native_handle_type` Eşzamanlılık Çalışma zamanı iç veri yapılarını gösteren bir işaretçi olarak tanımlanır.  
  
##  <a name="notify_all"></a>  condition_variable::notify_all  
 Bekleyen tüm iş parçacıklarının engelini kaldırır `condition_variable` nesnesi.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="notify_one"></a>  condition_variable::notify_one  
 Üzerinde bekleyen iş parçacığı birini engelini kaldırır `condition_variable` nesnesi.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="wait"></a>  condition_variable::wait  
 Bir iş parçacığı engeller.  
  
```
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `Lck`  
 A [unique_lock\<mutex >](../standard-library/unique-lock-class.md) nesnesi.  
  
 `Pred`  
 Döndüren herhangi bir ifade `true` veya `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk yöntem engeller kadar `condition_variable` nesne için bir çağrı tarafından durdurulma [notify_one](#notify_one) veya [notify_all](#notify_all). Bu ayrıca spuriously uyandırmak.  
  
 Uygulamada ikinci yöntem aşağıdaki kodu yürütür.  
  
```cpp  
while(!Pred())
    wait(Lck);
```    
  
##  <a name="wait_for"></a>  condition_variable::wait_for  
 Bir iş parçacığı engeller ve daha sonra iş parçacığı engelini kaldırır bir zaman aralığı ayarlar.  
  
```
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `Lck`  
 A [unique_lock\<mutex >](../standard-library/unique-lock-class.md) nesnesi.  
  
 `Rel_time`  
 A `chrono::duration` iş parçacığı önce geçen süreyi belirtir nesne uyanır.  
  
 `Pred`  
 Döndüren herhangi bir ifade `true` veya `false`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yöntem döndürür `cv_status::timeout` bekleme ne zaman sona ererse `Rel_time` geçti. Aksi durumda, yöntem döndürür `cv_status::no_timeout`.  
  
 İkinci yöntem değerini döndürür `Pred`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk yöntem engeller kadar `condition_variable` nesne için bir çağrı tarafından durdurulma [notify_one](#notify_one) veya [notify_all](#notify_all) veya zaman aralığı kadar `Rel_time` geçti. Bu ayrıca spuriously uyandırmak.  
  
 Uygulamada ikinci yöntem aşağıdaki kodu yürütür.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="wait_until"></a>  condition_variable::wait_until  
 Bir iş parçacığı engeller ve hangi iş parçacığı engelini kaldırır zamanında maksimum noktasını ayarlar.  
  
```
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time, 
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `Lck`  
 A [unique_lock\<mutex >](../standard-library/unique-lock-class.md) nesnesi.  
  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) nesnesi.  
  
 `Pred`  
 Döndüren herhangi bir ifade `true` veya `false`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndüren yöntemler bir `cv_status` yazın return `cv_status::timeout` bekleme ne zaman sona ererse `Abs_time` sona erdiğinde. Aksi takdirde, yöntemleri döndürür `cv_status::no_timeout`.  
  
 Döndüren yöntemler bir `bool` değeri döndürmesi `Pred`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk yöntem engeller kadar `condition_variable` nesne için bir çağrı tarafından durdurulma [notify_one](#notify_one) veya [notify_all](#notify_all) veya kadar `Abs_time`. Bu ayrıca spuriously uyandırmak.  
  
 Etkin, ikinci yöntem aşağıdaki kodu yürütür  
  
```cpp  
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 Bir nesne türü için bir işaretçi üçüncü ve dördüncü yöntemleri kullanın `xtime` değiştirmek için `chrono::time_point` nesnesi. `xtime` Nesnesini bir sinyal için beklenecek en uzun süreyi belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)



