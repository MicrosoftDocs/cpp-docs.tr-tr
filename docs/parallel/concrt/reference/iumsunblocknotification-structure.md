---
title: "Iumsunblocknotification yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs: C++
helpviewer_keywords: IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3febe10f7c71e1c1d478dd6f6b6f565c4134e033
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification Yapısı
Bildirim kaynağı engellenen ve zamanlama içeriği belirlenen Zamanlayıcının dönün tetiklenen bir iş parçacığı proxy engellemesini ve zamanlanması hazır Yöneticisi'nden temsil eder. İş parçacığı proxy'nin ilişkili yürütme bağlamı, döndürülen sonra bu arabirimi geçersiz `GetContext` yöntemi, yeniden.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IUMSUnblockNotification;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iumsunblocknotification::getcontext](#getcontext)|Döndürür `IExecutionContext` hangi engeli kaldırılmış iş parçacığı proxy ile ilişkili yürütme bağlamı için arabirim. Bu yöntemi döndürür ve temel yürütme bağlamı için bir çağrı aracılığıyla yeniden sonra `IThreadProxy::SwitchTo` yöntemi, bu arabirim artık geçerli değil.|  
|[Iumsunblocknotification::getnextunblocknotification](#getnextunblocknotification)|Sonraki döndürür `IUMSUnblockNotification` yönteminden döndürülen zinciri arabiriminde `IUMSCompletionList::GetUnblockNotifications`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getcontext"></a>Iumsunblocknotification::getcontext yöntemi  
 Döndürür `IExecutionContext` hangi engeli kaldırılmış iş parçacığı proxy ile ilişkili yürütme bağlamı için arabirim. Bu yöntemi döndürür ve temel yürütme bağlamı için bir çağrı aracılığıyla yeniden sonra `IThreadProxy::SwitchTo` yöntemi, bu arabirim artık geçerli değil.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `IExecutionContext` engeli kaldırılmış bir iş parçacığı proxy yürütme bağlamı için arabirim.  
  
##  <a name="getnextunblocknotification"></a>Iumsunblocknotification::getnextunblocknotification yöntemi  
 Sonraki döndürür `IUMSUnblockNotification` yönteminden döndürülen zinciri arabiriminde `IUMSCompletionList::GetUnblockNotifications`.  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki `IUMSUnblockNotification` yönteminden döndürülen zinciri arabiriminde `IUMSCompletionList::GetUnblockNotifications`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Iumsscheduler yapısı](iumsscheduler-structure.md)   
 [IUMSCompletionList Yapısı](iumscompletionlist-structure.md)
