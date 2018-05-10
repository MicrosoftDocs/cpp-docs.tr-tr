---
title: Iumscompletionlist yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ee957355510a2f62f5317d330403dc246ee8f2e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList Yapısı
UMS tamamlanma listesini temsil eder. Zamanlama scheduler'ın UMS iş parçacığı blokları belirlenmiş olduğunda içeriği ne özgün iş parçacığı engellendi karşın temel alınan sanal işlemci kök'zamanlamak bir karar vermek için gönderilir. Özgün iş parçacığı engelini kaldırır, işletim sistemi, bu arabirimi üzerinden erişilebilir olan tamamlanma listesini sıralar. Zamanlayıcı atanmış zamanlama bağlamı veya iş için arar başka bir yerde tamamlanma listesi sorgulayabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iumscompletionlist::getunblocknotifications](#getunblocknotifications)|Zinciri alır `IUMSUnblockNotification` proxy'leri engellemesini son tarihten itibaren bu yöntem, ilişkili iş parçacığı çağrıldığı yürütme bağlamı temsil eden arabirim.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir zamanlayıcı hangi eylemleri tamamlanma listesi öğeleri dequeue için bu arabirimi kullanılarak sonra gerçekleştirilen hakkında çok dikkatli olmanız gerekir. Öğeler scheduler'ın runnable bağlamları listesinde yerleştirilmelidir ve mümkün olan en kısa sürede genellikle erişilemiyor. Dequeued öğelerden birini rastgele bir kilit sahipliğini verildiğini tamamen mümkündür. Zamanlayıcı öğeleri dequeue için arama ve genellikle Zamanlayıcı içinde erişilebilen bir listedeki öğelerden yerleşimini arasında engelleyebilir hiçbir rasgele işlev çağrıları yapabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getunblocknotifications"></a>  Iumscompletionlist::getunblocknotifications yöntemi  
 Zinciri alır `IUMSUnblockNotification` proxy'leri engellemesini son tarihten itibaren bu yöntem, ilişkili iş parçacığı çağrıldığı yürütme bağlamı temsil eden arabirim.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zinciri `IUMSUnblockNotification` arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yürütme bağlamı yeniden sonra döndürülen bildirimleri geçersizdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Iumsscheduler yapısı](iumsscheduler-structure.md)   
 [IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)
