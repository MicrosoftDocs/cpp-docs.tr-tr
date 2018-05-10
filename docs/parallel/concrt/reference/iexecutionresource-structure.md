---
title: Iexecutionresource yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc69c30f30d25179427ee8e59c536bb7cb5b483d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="iexecutionresource-structure"></a>IExecutionResource Yapısı
Bir donanım iş parçacığı için bir Özet.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iexecutionresource::currentsubscriptionlevel](#currentsubscriptionlevel)|Etkinleştirilen sanal işlemci sayısı kökleri ve şu anda bu yürütme kaynak temsil eden temel alınan donanım iş parçacığı ile ilişkili dış iş parçacıkları abone döndürür.|  
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Bu yürütme kaynak temsil eden donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.|  
|[IExecutionResource::GetNodeId](#getnodeid)|Bu yürütme kaynağa ait işlemci düğümü için benzersiz bir tanımlayıcı döndürür.|  
|[Iexecutionresource::Remove](#remove)|Bu yürütme kaynak Resource Manager döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yürütme kaynaklar sanal işlemci kökleri ile ilişkili veya tek başına olabilir. Bir iş parçacığı, uygulamanızdaki bir iş parçacığı abonelik oluşturduğunda, bir tek başına yürütme kaynak oluşturulur. Yöntemleri [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) ve [Ischedulerproxy::requestınitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) iş parçacığı abonelikleri oluşturma ve geri dönüp bir `IExecutionResource` arabirimi temsil eden aboneliği. Bir iş parçacığı abonelik oluşturmak için Zamanlayıcı'yı Kaynak Yöneticisi'ni atar sanal işlemci kökleri birlikte bir zamanlayıcı için belirli bir iş parçacığı iş katılacak olan Kaynak Yöneticisi'ni bildirmek için bir yol sıraya olur. Resource Manager bunu yapabileceğiniz donanım iş parçacığı oversubscribing önlemek için bilgileri kullanır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IExecutionResource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="currentsubscriptionlevel"></a>  Iexecutionresource::currentsubscriptionlevel yöntemi  
 Etkinleştirilen sanal işlemci sayısı kökleri ve şu anda bu yürütme kaynak temsil eden temel alınan donanım iş parçacığı ile ilişkili dış iş parçacıkları abone döndürür.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli abonelik düzeyi.  
  
### <a name="remarks"></a>Açıklamalar  
 Abonelik düzeyinde kaç tane çalışan iş parçacıkları donanım iş parçacığı ile ilişkili olduğunu gösterir. Bu, yalnızca Resource Manager abone iş parçacıkları ve iş parçacığı proxy'leri çalışmakta sanal işlemci kökleri biçiminde bilmektedir iş parçacığı içerir.  
  
 Yöntemini çağırarak [Ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread), veya yöntem [Ischedulerproxy::requestınitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) parametresiyle `doSubscribeCurrentThread` değerineayarlayın`true`bire bir donanım iş parçacığı abonelik düzeyini artırır. Ayrıca döndürmeleri bir `IExecutionResource` abonelik temsil eden arabirim. Karşılık gelen çağrıyı [Iexecutionresource::Remove](#remove) azaltır donanım iş parçacığının abonelik düzeyinde bir.  
  
 Yöntemini kullanarak bir sanal işlemcinin kök etkinleştirme işlemi [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate) bire bir donanım iş parçacığı abonelik düzeyini artırır. Yöntemleri [Ivirtualprocessorroot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), veya [Iexecutionresource::Remove](#remove) tek bir etkinleştirilmiş sanal işlemci kökünde çağrıldığında abonelik düzeyinde azaltma.  
  
 Resource Manager kaynakları zamanlayıcılar arasında taşımak ne zaman belirlemek üzere yollarından biri olarak abonelik düzeyi bilgileri kullanır.  
  
##  <a name="getexecutionresourceid"></a>  Iexecutionresource::getexecutionresourceıd yöntemi  
 Bu yürütme kaynak temsil eden donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yürütme kaynak temel alınan donanım iş parçacığı için benzersiz bir tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Her bir donanım iş parçacığı benzersiz bir tanımlayıcı eşzamanlılık çalışma zamanı tarafından atanır. Birden çok yürütme kaynakları ilişkili donanım varsa, iş parçacığı tüm aynı yürütme kaynak tanımlayıcısına sahip olacaktır.  
  
##  <a name="getnodeid"></a>  Iexecutionresource::getnodeıd yöntemi  
 Bu yürütme kaynağa ait işlemci düğümü için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işlemci düğümü için benzersiz bir tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık Çalışma zamanı işlemci düğümlerinin gruplarındaki sistem üzerinde donanım iş parçacığı temsil eder. Düğümleri genellikle sistem donanım topolojisine türetilir. Örneğin, belirli bir yuva veya belirli bir NUMA düğümünde tüm işlemcilerin aynı işlemci düğüme ait olabilir. Resource Manager başlayarak bu düğümler benzersiz tanımlayıcı atar `0` dahil `nodeCount - 1`, burada `nodeCount` işlemci düğümleri sistemdeki toplam sayısını temsil eder.  
  
 Düğüm sayısı işlevinden elde edilebilir [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="remove"></a>  Iexecutionresource::Remove yöntemi  
 Bu yürütme kaynak Resource Manager döndürür.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pScheduler`  
 Bu yürütme kaynağı kaldırmak için istekte Zamanlayıcı bir arabirim.  
  
### <a name="remarks"></a>Açıklamalar  
 Tek başına yürütme kaynakların yanı sıra sanal işlemci kökleri için Resource Manager ile ilişkili yürütme kaynakları döndürmek için bu yöntemi kullanın.  
  
 Bu bir tek başına yürütme kaynak ise yöntemlerden birini alınan [Ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread) veya [Ischedulerproxy::requestınitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), arama yöntem `Remove` kaynak için oluşturulmuş iş parçacığı abonelik sona erer temsil eder. Bir zamanlayıcı proxy kapatmadan önce tüm iş parçacığı abonelikleri sonlandırmak için gereklidir ve çağırmalısınız `Remove` abonelik oluşturulan iş.  
  
 Sanal işlemci kökleri de döndürülmesi için Kaynak Yöneticisi'ni çağırarak `Remove` yöntemi, çünkü arabirimi `IVirtualProcessorRoot` devraldığı `IExecutionResource` arabirimi. Yanıt için bir çağrı olarak ya da bir sanal işlemcinin kök döndürmesi gerekebilir [Ischeduler::removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors) yöntemi, ya da aldığınız ve bir talep sanal işlemci kök ile bittiğinde [ Ischedulerproxy::createoversubscriber](ischedulerproxy-structure.md#createoversubscriber) yöntemi. Sanal işlemci kökler için bir kısıtlama yoktur hangi iş parçacığında çağırabileceği `Remove` yöntemi.  
  
 `invalid_argument` varsa durum parametresi `pScheduler` ayarlanır `NULL`.  
  
 `invalid_operation` varsa durum parametresi `pScheduler` geçerli iş parçacığının iş parçacığı abonelik oluşturulan iş parçacığından farklı olması durumunda bu yürütme kaynak için veya, bir tek başına yürütme kaynakla oluşturulmuş Zamanlayıcı farklıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)
