---
title: "&lt;chrono&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 41ea765f98882bb0f3f1531e284ca06a6fb79067
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; işlevleri
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>  duration_cast
 Atamalar bir `duration` nesne belirtilen türe.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `duration` nesne türü `To` zaman aralığını temsil eden `Dur`, hedef türe uyacak şekilde varsa kesildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `To` bir, oluşturulmadan `duration`, bu işlev aşırı yük çözüm katılmıyor.  
  
##  <a name="time_point_cast"></a>  time_point_cast
 Atamalar bir [time_point](../standard-library/time-point-class.md) belirtilen bir türün nesnesine.  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `time_point` türünde bir süresi olan nesneyi `To`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürece `To` bir, oluşturulmadan [süresi](../standard-library/duration-class.md), bu işlev aşırı yük çözüm katılmıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<chrono >](../standard-library/chrono.md)

