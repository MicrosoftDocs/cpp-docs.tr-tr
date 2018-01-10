---
title: "Iumscompletionlist yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs: C++
helpviewer_keywords: IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50fd2381174e947e243ad6aa40516be5fd728902
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
##  <a name="getunblocknotifications"></a>Iumscompletionlist::getunblocknotifications yöntemi  
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
