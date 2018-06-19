---
title: Iumsunblocknotification yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bda4f6e2b0565d39fd604767f3a89bcdd9a6df2c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687013"
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
  
##  <a name="getcontext"></a>  Iumsunblocknotification::getcontext yöntemi  
 Döndürür `IExecutionContext` hangi engeli kaldırılmış iş parçacığı proxy ile ilişkili yürütme bağlamı için arabirim. Bu yöntemi döndürür ve temel yürütme bağlamı için bir çağrı aracılığıyla yeniden sonra `IThreadProxy::SwitchTo` yöntemi, bu arabirim artık geçerli değil.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `IExecutionContext` engeli kaldırılmış bir iş parçacığı proxy yürütme bağlamı için arabirim.  
  
##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification::getnextunblocknotification yöntemi  
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
