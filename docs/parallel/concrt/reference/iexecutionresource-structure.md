---
title: IExecutionResource Yapısı
ms.date: 11/04/2016
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
ms.openlocfilehash: 4305948aa4e5da36023c1d4fe8b0b84aa4d59e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377305"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource Yapısı

Donanım iş parçacığı için bir soyutlama.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|Bu yürütme kaynağının temsil eder temel donanım iş parçacığı ile ilişkili şu anda etkinleştirilen sanal işlemci kökleri ve abone dış iş parçacığı sayısını döndürür.|
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Bu yürütme kaynağının temsil ettiği donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionResource::GetNodeId](#getnodeid)|Bu yürütme kaynağının ait olduğu işlemci düğümü için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionResource::Kaldır](#remove)|Bu yürütme kaynağını Kaynak Yöneticisi'ne verir.|

## <a name="remarks"></a>Açıklamalar

Yürütme kaynakları tek başına veya sanal işlemci kökleri ile ilişkili olabilir. Uygulamanızdaki bir iş parçacığı bir iş parçacığı aboneliği oluşturduğunda tek başına bir yürütme kaynağı oluşturulur. [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) ve [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) iş parçacığı abonelikleri `IExecutionResource` oluşturmak ve aboneliği temsil eden bir arayüz döndürür. İş parçacığı aboneliği oluşturmak, Kaynak Yöneticisi'ne kaynak yöneticisinin zamanlayıcıya atadığı sanal işlemci kökleriyle birlikte, belirli bir iş parçacığının zamanlayıcıya sıralanmış çalışmaya katılacağını bildirmenin bir yoludur. Kaynak Yöneticisi, donanım iş parçacığının aboneliğini yapabildiği yere aboneliği önlemek için bilgileri kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionResource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iexecutionresourcecurrentsubscriptionlevel-method"></a><a name="currentsubscriptionlevel"></a>IExecutionResource::CurrentSubscriptionLevel Yöntemi

Bu yürütme kaynağının temsil eder temel donanım iş parçacığı ile ilişkili şu anda etkinleştirilen sanal işlemci kökleri ve abone dış iş parçacığı sayısını döndürür.

```cpp
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli abonelik düzeyi.

### <a name="remarks"></a>Açıklamalar

Abonelik düzeyi, donanım iş parçacığıyla kaç çalışan iş parçacığının ilişkili olduğunu söyler. Bu yalnızca Kaynak Yöneticisi'nin abone olan iş parçacıkları biçiminde farkında olduğu iş parçacıklarını ve iş parçacığı eklerini etkin olarak yürüten sanal işlemci köklerini içerir.

[ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread)veya [iSchedulerProxy yöntemini çağırma::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) parametresi `doSubscribeCurrentThread` ile değer **doğru** ayarlanmış bir donanım iş parçacığının abonelik düzeyini bir artar. Ayrıca aboneliği `IExecutionResource` temsil eden bir arabirim de döndürerler. IExecutionResource'a karşılık gelen bir [çağrı::Kaldırma](#remove) donanım iş parçacığının abonelik düzeyini birer bir erler.

IVirtualProcessorRoot yöntemini kullanarak sanal işlemci kökünü etkinleştirme [eylemi::Etkinleştirme,](ivirtualprocessorroot-structure.md#activate) bir donanım iş parçacığının abonelik düzeyini birer birer yükseltir. [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate)veya [IExecutionResource::Etkinleştirilen](#remove) sanal işlemci kökünde çağrıldığında abonelik düzeyini bir erle silme yöntemini kaldırın.

Kaynak Yöneticisi, kaynakları zamanlayıcılar arasında ne zaman taşıyarak belirleyecek yollardan biri olarak abonelik düzeyi bilgilerini kullanır.

## <a name="iexecutionresourcegetexecutionresourceid-method"></a><a name="getexecutionresourceid"></a>iExecutionResource::GetExecutionResourceid Yöntemi

Bu yürütme kaynağının temsil ettiği donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yürütme kaynağının altında yatan donanım iş parçacığı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Her donanım iş parçacığı, Eşzamanlılık Çalışma Zamanı tarafından benzersiz bir tanımlayıcı atanır. Birden çok yürütme kaynakları ilişkili donanım iş parçacığı ise, hepsi aynı yürütme kaynak tanımlayıcısı olacaktır.

## <a name="iexecutionresourcegetnodeid-method"></a><a name="getnodeid"></a>IExecutionResource::GetNodeId Yöntemi

Bu yürütme kaynağının ait olduğu işlemci düğümü için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İşlemci düğümü için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Süresi, işlemci düğümleri gruplarında sistemdeki donanım iş parçacıklarını temsil eder. Düğümler genellikle sistemin donanım topolojisinden türetilir. Örneğin, belirli bir soketveya belirli bir NUMA düğümündeki tüm işlemciler aynı işlemci düğümüne ait olabilir. Kaynak Yöneticisi, sistemdeki toplam işlemci düğümü sayısını temsil eden `0` `nodeCount - 1` `nodeCount` ve dahil olmak üzere bu düğümlere benzersiz tanımlayıcılar atar.

Düğüm sayısı [GetProcessorNodeCount](concurrency-namespace-functions.md)işlevinden elde edilebilir.

## <a name="iexecutionresourceremove-method"></a><a name="remove"></a>IExecutionResource::Kaldırma Yöntemi

Bu yürütme kaynağını Kaynak Yöneticisi'ne verir.

```cpp
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>Parametreler

*pScheduler*<br/>
Bu yürütme kaynağını kaldırmak için istekte bulunmayı yapan zamanlayıcıya bir arabirim.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, sanal işlemci kökleriyle ilişkili yürütme kaynaklarının yanı sıra bağımsız yürütme kaynaklarını da Kaynak Yöneticisi'ne döndürmek için kullanın.

Bu, [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) veya [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)yöntemlerinden aldığınız bağımsız bir yürütme kaynağıysa, yöntemi `Remove` arayarak kaynağın temsil etmek için oluşturulduğu iş parçacığı aboneliğini sona erdirecektir. Bir zamanlayıcı proxy'sini kapatmadan önce tüm iş parçacığı `Remove` aboneliklerini sonlamalısınız ve aboneliği oluşturan iş parçacığından aramanız gerekir.

Arabirim `IVirtualProcessorRoot` `IExecutionResource` arabirimden devraldığı için, sanal işlemci kökleri `Remove` de yöntemi çağırarak Kaynak Yöneticisi'ne döndürülebilir. IScheduler'a yapılan bir çağrıya yanıt olarak sanal işlemci kökünü döndürmeniz [gerekebilir::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) yöntemi veya ISchedulerProxy'den aldığınız aşırı aboneleştirilmiş bir sanal işlemci köküyle [yaptığınızda::CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) yöntemi. Sanal işlemci kökleri için, iş parçacığının `Remove` yöntemi çağırabileceği herhangi bir kısıtlama yoktur.

`invalid_argument`parametre `pScheduler` ' ye `NULL`ayarlanırsa atılır.

`invalid_operation`parametre, `pScheduler` bu yürütme kaynağının oluşturulduğu zamanlayıcıdan farklıysa veya geçerli iş parçacığı iş parçacığı aboneliğini oluşturan iş parçacığından farklıysa, bağımsız bir yürütme kaynağıyla atılırsa.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)
