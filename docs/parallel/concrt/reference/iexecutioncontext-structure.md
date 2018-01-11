---
title: "Iexecutioncontext yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
dev_langs: C++
helpviewer_keywords: IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e3edffb10aad7b5793907c8c95ad5028f4d1d23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext Yapısı
Belirli bir sanal işlemcinin çalıştırabilir ve işbirliği ile anahtarlı bağlamının olması bir yürütme bağlamı için bir arabirim.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iexecutioncontext::Dispatch](#dispatch)|Bir iş parçacığı proxy belirli yürütme bağlamı yürütme başlatıldığında çağrılan yöntem. Bu, scheduler ana çalışan yordamı olmalıdır.|  
|[Iexecutioncontext::GetID](#getid)|Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.|  
|[Iexecutioncontext::getproxy](#getproxy)|Arabirim bu bağlamda yürütme iş parçacığı proxy döndürür.|  
|[Iexecutioncontext::getscheduler](#getscheduler)|Bu yürütme bağlamı ait olduğu bir arabirim Zamanlayıcı geri döner.|  
|[Iexecutioncontext::setproxy](#setproxy)|Bir iş parçacığı proxy bu yürütme bağlamı ile ilişkilendirir. Bağlamın yürütülmeye başlamadan önce bu yöntemi hak ilişkili iş parçacığı proxy çağırır `Dispatch` yöntemi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık Çalışma zamanı Resource Manager ile arabirimleri özel bir zamanlayıcı uyguluyorsanız, uygulamak gerekir `IExecutionContext` arabirimi. Kaynak Yöneticisi tarafından oluşturulan iş parçacığı adına, Zamanlayıcı İş yürüterek gerçekleştirmek `IExecutionContext::Dispatch` yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IExecutionContext`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dispatch"></a>Iexecutioncontext::Dispatch yöntemi  
 Bir iş parçacığı proxy belirli yürütme bağlamı yürütme başlatıldığında çağrılan yöntem. Bu, scheduler ana çalışan yordamı olmalıdır.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pDispatchState`  
 Bu yürütme bağlamı altında dağıtıldığı durumunu gösteren bir işaretçi. Dağıtım durumu hakkında daha fazla bilgi için bkz: [DispatchState](dispatchstate-structure.md).  
  
##  <a name="getid"></a>Iexecutioncontext::GetID yöntemi  
 Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı benzersiz tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemini kullanmalıdır `GetExecutionContextId` uygulayan nesnenin için benzersiz bir tanımlayıcı elde etmek için `IExecutionContext` arabirimi arabirim yöntemleri için bir parametre olarak kullanmadan önce kaynak yöneticisi tarafından sağlanan. Aynı tanımlayıcısı döndürmesi bekleniyor zaman `GetId` işlevi çağrılır.  
  
 Farklı bir kaynaktan alınan tanımlayıcı tanımsız davranışlara neden.  
  
##  <a name="getproxy"></a>Iexecutioncontext::getproxy yöntemi  
 Arabirim bu bağlamda yürütme iş parçacığı proxy döndürür.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `IThreadProxy` arabirimi. Yürütme bağlamın iş parçacığı proxy çağrısıyla başlatılmadı, `SetProxy`, işlevi döndürmelidir `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Resource Manager çağıracağı `SetProxy` bir yürütme bağlamı yöntemi ile bir `IThreadProxy` arabirimi girme önce bir parametre olarak `Dispatch` yöntemi içeriği üzerinde. Bu bağımsız değişken depolamak ve çağrıları üzerinde dönmek için beklenen `GetProxy()`.  
  
##  <a name="getscheduler"></a>Iexecutioncontext::getscheduler yöntemi  
 Bu yürütme bağlamı ait olduğu bir arabirim Zamanlayıcı geri döner.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `IScheduler` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli bir yürütme bağlamla başlatmak için gerekli `IScheduler` yöntem için parametre olarak kullanmadan önce arabirimi kaynak yöneticisi tarafından sağlanan.  
  
##  <a name="setproxy"></a>Iexecutioncontext::setproxy yöntemi  
 Bir iş parçacığı proxy bu yürütme bağlamı ile ilişkilendirir. Bağlamın yürütülmeye başlamadan önce bu yöntemi hak ilişkili iş parçacığı proxy çağırır `Dispatch` yöntemi.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pThreadProxy`  
 Bir arabirim hakkında girmektir iş parçacığı proxy `Dispatch` bu yürütme bağlamı yöntemi.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre kaydetmek için beklenen `pThreadProxy` ve bir çağrıda döndürün `GetProxy` yöntemi. İş parçacığı proxy yürütülürken yürütme bağlamla ilişkili iş parçacığı proxy değiştirmez Resource Manager garanti `Dispatch` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Ischeduler yapısı](ischeduler-structure.md)   
 [IThreadProxy Yapısı](ithreadproxy-structure.md)
