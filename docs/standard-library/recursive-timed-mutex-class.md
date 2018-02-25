---
title: recursive_timed_mutex Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::recursive_timed_mutex [C++]
- std::recursive_timed_mutex [C++], recursive_timed_mutex
- std::recursive_timed_mutex [C++], lock
- std::recursive_timed_mutex [C++], try_lock
- std::recursive_timed_mutex [C++], try_lock_for
- std::recursive_timed_mutex [C++], try_lock_until
- std::recursive_timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec98e8c357bf1f40fdc608873dbbb18f0f5f18f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex Sınıfı
Temsil eden bir *mutex türü zaman aşımına*. Bu tür nesneler, zaman sınırlı bir program içinden engelleme kullanarak karşılıklı dışlama zorlamak için kullanılır. Nesne türü aksine [timed_mutex](../standard-library/timed-mutex-class.md), kilitleme yöntemleri çağırma etkisini `recursive_timed_mutex` nesneleri iyi tanımlanmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class recursive_timed_mutex;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[recursive_timed_mutex](#recursive_timed_mutex)|Oluşturan bir `recursive_timed_mutex` nesnesi kilitli değil.|  
|[~recursive_timed_mutex Destructor](#dtorrecursive_timed_mutex_destructor)|Tarafından kullanılan tüm kaynakları serbest `recursive_timed_mutex` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[lock](#lock)|İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.|  
|[try_lock](#try_lock)|Sahipliğini almayı denediğinde `mutex` engelleme olmadan.|  
|[try_lock_for](#try_lock_for)|Sahipliğini almayı denediğinde `mutex` belirtilen zaman aralığı.|  
|[try_lock_until](#try_lock_until)|Sahipliğini almayı denediğinde `mutex` belirtilen süre kadar.|  
|[kilidini aç](#unlock)|Serbest sahipliğini `mutex`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<mutex >  
  
 **Namespace:** std  
  
##  <a name="lock"></a>  kilitleme  
 İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı zaten sahipse `mutex`yöntemi hemen döndürür ve önceki kilit yürürlükte kalır.  
  
##  <a name="recursive_timed_mutex"></a>  recursive_timed_mutex Constructor  
 Oluşturan bir `recursive_timed_mutex` nesnesi kilitli değil.  
  
```cpp  
recursive_timed_mutex();
```  
  
##  <a name="dtorrecursive_timed_mutex_destructor"></a>  ~recursive_timed_mutex Destructor  
 Tarafından kullanılan tüm kaynakları serbest `recursive_timed_mutex` nesnesi.  
  
```cpp  
~recursive_timed_mutex();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi çalıştığında nesne kilitliyse tanımlanmamış bir davranıştır.  
  
##  <a name="try_lock"></a>  try_lock  
 Sahipliğini almayı denediğinde `mutex` engelleme olmadan.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Yöntem başarıyla sahipliğini aldıysanız `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı zaten sahipse `mutex`, işlevi hemen döndürür `true`, ve önceki kilit yürürlükte kalır.  
  
##  <a name="try_lock_for"></a>  try_lock_for  
 Sahipliğini almayı denediğinde `mutex` engelleme olmadan.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Parametreler  
 `Rel_time`  
 A [chrono::duration](../standard-library/duration-class.md) yöntemi sahipliğini almayı denediğinde en uzun süreyi belirtir nesne `mutex`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Yöntem başarıyla sahipliğini elde ederse `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı zaten sahipse `mutex`, yöntem hemen döndürür `true`, ve önceki kilit yürürlükte kalır.  
  
##  <a name="try_lock_until"></a>  try_lock_until  
 Sahipliğini almayı denediğinde `mutex` engelleme olmadan.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Parametreler  
 `Abs_time`  
 Daha sonra yöntemi artık çalışır sahipliğini almak eşik belirtir zaman içinde nokta `mutex`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Yöntem başarıyla sahipliğini elde ederse `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı zaten sahipse `mutex`, yöntem hemen döndürür `true`, ve önceki kilit yürürlükte kalır.  
  
##  <a name="unlock">kilidini aç</a>  
 Serbest sahipliğini `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sahipliğini serbest `mutex` yalnızca olarak gibi birçok kez çağrıldıktan sonra [kilit](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for), ve [try_lock_ kadar](#try_lock_until) üzerinde başarıyla çağrılmış `recursive_timed_mutex` nesnesi.  
  
 Çağıran iş parçacığı kendi değil, `mutex`, tanımlanmamış bir davranıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



