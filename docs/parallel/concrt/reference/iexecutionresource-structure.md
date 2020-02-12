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
ms.openlocfilehash: 40799d1ed6e21e6932f1adfbad117c436918b792
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141285"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource Yapısı

Donanım iş parçacığı için bir soyutlama.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IExecutionResource:: CurrentSubscriptionLevel](#currentsubscriptionlevel)|Etkinleştirilen sanal işlemci köklerinin ve bu yürütme kaynağının gösterdiği temel alınan donanım iş parçacığı ile ilişkili olan abone olunan dış iş parçacıklarının sayısını döndürür.|
|[IExecutionResource:: GetExecutionResourceId](#getexecutionresourceid)|Bu yürütme kaynağının temsil ettiği donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionResource:: GetNodeId](#getnodeid)|Bu yürütme kaynağının ait olduğu işlemci düğümü için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionResource:: Remove](#remove)|Bu yürütme kaynağını Kaynak Yöneticisi döndürür.|

## <a name="remarks"></a>Açıklamalar

Yürütme kaynakları tek başına veya sanal işlemci köklerinin ilişkili olabilir. Uygulamanızdaki bir iş parçacığı iş parçacığı aboneliği oluşturduğunda tek başına yürütme kaynağı oluşturulur. Yöntemler [ISchedulerProxy:: SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) ve [ISchedulerProxy:: Requestınitialvirtualiþlemcileri](ischedulerproxy-structure.md#requestinitialvirtualprocessors) , iş parçacığı abonelikleri oluşturur ve aboneliği temsil eden bir `IExecutionResource` arabirimi döndürür. İş parçacığı aboneliği oluşturma, belirli bir iş parçacığının bir Scheduler 'a sıraya alınan iş 'e katılmasını Kaynak Yöneticisi, Scheduler 'a atayan Kaynak Yöneticisi sanal işlemci kökleriyle birlikte bilgilendirmek için bir yoldur. Kaynak Yöneticisi, bu bilgileri kullanarak, donanım iş parçacıklarının mümkün olduğu yerde aşırı abone olmasını önler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionResource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="currentsubscriptionlevel"></a>IExecutionResource:: CurrentSubscriptionLevel yöntemi

Etkinleştirilen sanal işlemci köklerinin ve bu yürütme kaynağının gösterdiği temel alınan donanım iş parçacığı ile ilişkili olan abone olunan dış iş parçacıklarının sayısını döndürür.

```cpp
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli abonelik düzeyi.

### <a name="remarks"></a>Açıklamalar

Abonelik düzeyi, kaç çalışan iş parçacığının donanım iş parçacığıyla ilişkili olduğunu söyler. Bu yalnızca Kaynak Yöneticisi, abone olunan iş parçacıkları biçiminde ve iş parçacığı proxy 'lerini etkin bir şekilde yürüten sanal işlemci köklerine sahip iş parçacıklarını içerir.

[ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread)yöntemini çağırma ya da [ıbıchedulerproxy:: Requestınitialvirtualiþlemcileri](ischedulerproxy-structure.md#requestinitialvirtualprocessors) value değeri **true** olarak ayarlanmış `doSubscribeCurrentThread`, bir donanım iş parçacığının abonelik düzeyini bir ile artırır. Ayrıca, aboneliği temsil eden bir `IExecutionResource` arabirimi de döndürür. [IExecutionResource:: Remove](#remove) öğesine karşılık gelen bir çağrı, donanım iş parçacığının abonelik düzeyini bir azaltır.

[IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate) yöntemi kullanılarak sanal işlemci kökünü etkinleştirme eylemi, bir donanım iş parçacığının abonelik düzeyini bir tane artırır. [IVirtualProcessorRoot::D eactivate](ivirtualprocessorroot-structure.md#deactivate)veya [IExecutionResource:: Remove](#remove) yöntemleri, etkinleştirilen bir sanal işlemci kökünde çağrıldığında abonelik düzeyini tek bir azaltır.

Kaynak Yöneticisi, kaynakların zamanlayıcılar arasında ne zaman taşınacağını belirleme yöntemlerinden biri olarak abonelik düzeyi bilgilerini kullanır.

## <a name="getexecutionresourceid"></a>IExecutionResource:: GetExecutionResourceId yöntemi

Bu yürütme kaynağının temsil ettiği donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yürütme kaynağını temel alan donanım iş parçacığı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Her donanım iş parçacığına Eşzamanlılık Çalışma Zamanı tarafından benzersiz bir tanımlayıcı atanır. Birden çok yürütme kaynağı ilişkili donanım iş parçacığı ise, hepsi aynı yürütme kaynak tanımlayıcısına sahip olur.

## <a name="getnodeid"></a>IExecutionResource:: GetNodeId yöntemi

Bu yürütme kaynağının ait olduğu işlemci düğümü için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İşlemci düğümü için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı, işlemci düğümleri gruplarındaki sistemdeki donanım iş parçacıklarını temsil eder. Düğümler genellikle sistemin donanım topolojisinden türetilir. Örneğin, belirli bir yuvada veya belirli bir NUMA düğümündeki tüm işlemciler aynı işlemci düğümüne ait olabilir. Kaynak Yöneticisi, bu düğümlere `0` başlayarak `nodeCount - 1`dahil olmak üzere benzersiz tanımlayıcılar atar; burada `nodeCount`, sistemdeki toplam işlemci düğümü sayısını temsil eder.

Düğüm sayısı [GetProcessorNodeCount](concurrency-namespace-functions.md)işlevinden elde edilebilir.

## <a name="remove"></a>IExecutionResource:: Remove yöntemi

Bu yürütme kaynağını Kaynak Yöneticisi döndürür.

```cpp
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>Parametreler

*pScheduler*<br/>
Zamanlayıcı için bu yürütme kaynağını kaldırma isteğini yapan bir arabirim.

### <a name="remarks"></a>Açıklamalar

Tek başına yürütme kaynaklarını ve Kaynak Yöneticisi sanal işlemci köklerle ilişkili yürütme kaynaklarını döndürmek için bu yöntemi kullanın.

Bu, [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) veya [ıchedulerproxy:: Requestınitialvirtualiþlemcileri](ischedulerproxy-structure.md#requestinitialvirtualprocessors)yöntemlerinden herhangi birinden aldığınız tek başına bir yürütme kaynağıdır. `Remove` yöntemini çağırmak, kaynağın oluşturulduğu iş parçacığı aboneliğini sona ercektir. Bir Zamanlayıcı proxy 'sini kapatmadan önce tüm iş parçacığı aboneliklerini sonlandırmalısınız ve aboneliği oluşturan iş parçacığından `Remove` çağırmalıdır.

Arabirim `IVirtualProcessorRoot` `IExecutionResource` arabiriminden devraldığı için, `Remove` yöntemi çağrılarak sanal işlemci kökleri de Kaynak Yöneticisi döndürülür. [IComparer:: Removevirtualprocessor](ischeduler-structure.md#removevirtualprocessors) yöntemine yapılan çağrıya yanıt olarak veya [IComparer Ulerproxy:: CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) yönteminden edindiğiniz çok aboneli bir sanal işlemci kökü ile işiniz bittiğinde bir sanal işlemci kökünü geri almanız gerekebilir. Sanal işlemci kökleri için, hangi iş parçacığının `Remove` yöntemi çağırabileceği konusunda bir kısıtlama yoktur.

`invalid_argument`, `pScheduler` parametresi `NULL`olarak ayarlandıysa oluşturulur.

`invalid_operation`, geçerli iş parçacığı iş parçacığı aboneliğini oluşturan iş parçacığından farklıysa, `pScheduler` parametresi için bu yürütme kaynağının oluşturulduğu zamanlayıcının veya tek başına yürütme kaynağıyla farklıysa oluşur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)
