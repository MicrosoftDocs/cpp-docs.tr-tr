---
title: "Iumsscheduler yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da35fe5ae8d00ee537674fd689fd7f27074b0355
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler Yapısı
Kullanıcı modu zamanlanabilir (UMS) iş parçacıklarının el için Kaynak Yöneticisi'ni eşzamanlılık çalışma zamanı istediği bir iş Zamanlayıcı bir soyutlamasını bir arabirim. Kaynak Yöneticisi bu arabirimi UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için kullanır. `IUMSScheduler` Arabirimi devraldığı `IScheduler` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Atayan bir `IUMSCompletionList` UMS iş parçacığı Zamanlayıcı arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Resource Manager ile iletişim kuran özel Zamanlayıcısı'nı uygulama ve sıradan Win32 iş parçacığı yerine, Zamanlayıcı verilmesini UMS iş parçacığı istiyorsanız uygulaması sağlamalıdır `IUMSScheduler` arabirimi. Ayrıca, Zamanlayıcı İlkesi anahtarı için ilke değeri ayarlamalısınız `SchedulerKind` olmasını `UmsThreadDefault`. İlke UMS iş parçacığı, belirtiyorsa `IScheduler` bir parametre olarak geçirilen arabirimi [Iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler) yöntemi olmalıdır bir `IUMSScheduler` arabirimi.  
  
 Resource Manager UMS iş parçacıklarında yalnızca UMS özelliği yüklü işletim sistemlerini el yapabiliyor. 64-bit işletim sistemleri sürümü Windows 7 ve üzeri ile UMS iş parçacığı destekler. Bir zamanlayıcı ilkesiyle oluşturursanız `SchedulerKind` anahtarı değerine ayarlayın `UmsThreadDefault` ve temel platform UMS, değerini desteklemez `SchedulerKind` bu ilkedeki anahtarı değerine değişeceği `ThreadScheduler`. Her zaman UMS iş parçacığı almak beklemeden önce bu ilke değeri geri okumanız gerekir.  
  
 `IUMSScheduler` Bir Zamanlayıcı ve kaynak yöneticisi arasındaki iletişim çift yönlü bir kanal ucunu bir arabirimdir. Diğer uçtaki tarafından temsil edilen `IResourceManager` ve `ISchedulerProxy` kaynak yöneticisi tarafından uygulanan arabirimler.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="setcompletionlist"></a>  Iumsscheduler::setcompletionlist yöntemi  
 Atayan bir `IUMSCompletionList` UMS iş parçacığı Zamanlayıcı arabirimi.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pCompletionList`  
 Zamanlayıcı tamamlanma listesi arabirimi. Zamanlayıcı başına tek bir listede yoktur.  
  
### <a name="remarks"></a>Açıklamalar  
 Resource Manager kaynakların ilk bir ayırma Zamanlayıcı istedi sonra UMS iş parçacıkları, istediği belirten bir Zamanlayıcı bu yöntemi çağırır. Zamanlayıcı'yı kullanabilirsiniz `IUMSCompletionList` zaman UMS iş parçacığı proxy'leri engeli kaldırılmış belirlemek için arabirim. Yalnızca bu arabirim UMS Zamanlayıcısını atanan sanal işlemci kök üzerinde çalışan bir iş parçacığı proxy erişmek için geçerli değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Ischeduler yapısı](ischeduler-structure.md)   
 [Iumscompletionlist yapısı](iumscompletionlist-structure.md)   
 [IResourceManager Yapısı](iresourcemanager-structure.md)
