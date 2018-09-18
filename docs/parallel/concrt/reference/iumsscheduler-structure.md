---
title: Iumsscheduler yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46ed7dac35dce4b5df51cd4c218a1a70a84d21df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079069"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler Yapısı
Eşzamanlılık çalışma zamanının Resource Manager'ı, kullanıcı modunda zamanlanabilen (UMS) iş parçacıklarını teslim etmek isteyen bir iş Zamanlayıcı bir Özet için arabirim. UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için bu arabirimi Resource Manager'ı kullanır. `IUMSScheduler` Arabirimi devralır `IScheduler` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iumsscheduler::setcompletionlist](#setcompletionlist)|Atayan bir `IUMSCompletionList` UMS iş parçacığı Zamanlayıcısı arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Resource Manager ile iletişim kuran özel bir zamanlayıcı uyguluyor ve sıradan Win32 iş parçacığı yerine scheduler verilmesini UMS iş parçacıkları istiyorsanız bir uygulamasını sağlamalıdır `IUMSScheduler` arabirimi. Ayrıca, Zamanlayıcı ilkesini anahtar ilke değeri ayarlamalısınız `SchedulerKind` olmasını `UmsThreadDefault`. UMS iş parçacığı, ilke belirtiyorsa `IScheduler` bir parametre olarak geçirilen arabirimi [Iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler) yöntemi olmalıdır bir `IUMSScheduler` arabirimi.  
  
 Kaynak Yöneticisi, yalnızca işletim sistemlerinde UMS özelliğinin UMS iş parçacıkları el kuramıyor. Windows 7 ve üzeri sürümlü 64-bit işletim sistemlerinde UMS iş parçacıklarını destekler. Bir zamanlayıcı İlkesi oluşturursanız `SchedulerKind` anahtar değerine ayarlayın `UmsThreadDefault` ve temel alınan platformu UMS, değerini desteklemiyor `SchedulerKind` Bu ilke anahtarı değere değiştirilir `ThreadScheduler`. Her zaman UMS iş parçacıkları almayı beklemeden önce bu ilke değeri geri okumanız gerekir.  
  
 `IUMSScheduler` Bir Zamanlayıcı ve Resource Manager arasındaki iletişim çift yönlü bir kanalı ucunu arabirimidir. Diğer uç tarafından temsil edilen `IResourceManager` ve `ISchedulerProxy` kaynak yöneticisi tarafından uygulanan arabirimler.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Ischeduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="setcompletionlist"></a>  Iumsscheduler::setcompletionlist yöntemi  
 Atayan bir `IUMSCompletionList` UMS iş parçacığı Zamanlayıcısı arabirimi.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*pCompletionList*<br/>
Tamamlanma listesi Zamanlayıcı için arabirim. Zamanlayıcı başına tek bir liste yoktur.  
  
### <a name="remarks"></a>Açıklamalar  
 Resource Manager kaynakların ilk Ayırma Zamanlayıcı istedi sonra UMS iş parçacıkları, istediği belirten bir zamanlayıcı üzerinde bu yöntemi çağırır. Zamanlayıcı'yı kullanabilirsiniz `IUMSCompletionList` zaman UMS iş parçacığı proxy engeli kaldırılmış belirlemek için arabirim. Yalnızca bu arabirim için UMS Zamanlayıcısını atanmış bir sanal işlemci kökünde çalışan iş parçacığı proxy erişmek için geçerli değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Ischeduler yapısı](ischeduler-structure.md)   
 [Iumscompletionlist yapısı](iumscompletionlist-structure.md)   
 [IResourceManager Yapısı](iresourcemanager-structure.md)
