---
title: "&lt;iş parçacığı&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: 54e4c09c7db5fb29cdfb067b47d8584451277d4a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltthreadgt-functions"></a>&lt;iş parçacığı&gt; işlevleri
||||  
|-|-|-|  
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|  
|[Değiştirme](#swap)|[yield](#yield)|  
  
##  <a name="get_id"></a>  get_id  
 Geçerli yürütme iş parçacığı benzersiz olarak tanımlar.  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne [thread::id](../standard-library/thread-class.md) , geçerli yürütme iş parçacığı benzersiz şekilde tanımlar.  
  
##  <a name="sleep_for"></a>  sleep_for  
 Çağıran iş parçacığı engeller.  
  
```  
template <class Rep,  
class Period>  
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Parametreler  
 `Rel_time`  
 A [süresi](../standard-library/duration-class.md) nesne bir zaman aralığı belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi çağıran iş parçacığı için en az tarafından belirtilen zaman blokları `Rel_time`. Bu işlev, tüm özel durumlar oluşturmadığını.  
  
##  <a name="sleep_until"></a>  sleep_until  
 Çağıran iş parçacığı en az belirtilen zamana kadar engeller.  
  
```  
template <class Clock, class Duration>  
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```  
  
### <a name="parameters"></a>Parametreler  
 `Abs_time`  
 Bir noktayı zamanında temsil eder.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, tüm özel durumlar oluşturmadığını.  
  
##  <a name="swap">Değiştirme</a>  
 İki durumunu değiştirir `thread` nesneleri.  
  
```  
void swap(thread& Left, thread& Right) noexcept;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Left`  
 Sol `thread` nesnesi.  
  
 `Right`  
 Sağa `thread` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev çağrıları `Left.swap(Right)`.  
  
##  <a name="yield"></a>  uyarı simgesi  
 Geçerli iş parçacığının normal şekilde çalışmaya devam eder olsa bile diğer iş parçacıklarını çalıştırmak için işletim sistemi işaret eder.  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<iş parçacığı >](../standard-library/thread.md)

