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
ms.openlocfilehash: 642b73f81146fa8df68d36ee3b63b1902ed66619
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162405"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource Yapısı

Donanım iş parçacığı için bir Özet.

## <a name="syntax"></a>Sözdizimi

```
struct IExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iexecutionresource::currentsubscriptionlevel](#currentsubscriptionlevel)|Etkinleştirilmiş sanal işlemci sayısı kökleri ve dış iş parçacıkları şu anda bu yürütme kaynak temsil eder. temel alınan donanım iş parçacığı ile ilişkili abone döndürür.|
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Bu yürütme kaynak temsil eden donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionResource::GetNodeId](#getnodeid)|Bu yürütme kaynağın ait olduğu işlemci düğüm için benzersiz bir tanımlayıcı döndürür.|
|[Iexecutionresource::Remove](#remove)|Bu yürütme kaynak Resource Manager'a döndürür.|

## <a name="remarks"></a>Açıklamalar

Tek başına olabilir veya sanal işlemci kökü ile ilişkili yürütme kaynaklar. Uygulamanızı bir iş parçacığında bir iş parçacığı abonelik oluştururken bir tek başına yürütme kaynağı oluşturulur. Yöntemleri [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) ve [Ischedulerproxy::requestınitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) iş parçacığı abonelikler oluşturun ve dönüş bir `IExecutionResource` arabirimi temsil eden Abonelik. Bir iş parçacığı abonelik oluşturma, Resource Manager Zamanlayıcı atar sanal işlemci kökü ile birlikte bir zamanlayıcı için belirli bir iş parçacığı iş katılacak olan kaynak yöneticisi bilgilendirmek için bir yol sıraya bağlıdır. Resource Manager yapabileceğiniz, donanım iş parçacıklarının oversubscribing önlemek için bu bilgileri kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionResource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="currentsubscriptionlevel"></a>  Iexecutionresource::currentsubscriptionlevel yöntemi

Etkinleştirilmiş sanal işlemci sayısı kökleri ve dış iş parçacıkları şu anda bu yürütme kaynak temsil eder. temel alınan donanım iş parçacığı ile ilişkili abone döndürür.

```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli abonelik düzeyi.

### <a name="remarks"></a>Açıklamalar

Abonelik düzeyinde kaç çalışan iş parçacıkları donanım iş parçacığıyla ilişkilendirilmiş söyler. Bu, yalnızca Resource Manager abone iş parçacıkları ve iş parçacığı proxy etkin bir şekilde yürütülen sanal işlemci kökü biçiminde farkındadır iş parçacıklarını içerir.

Yöntemini çağırarak [Ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread), ya da yöntem [Ischedulerproxy::requestınitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) parametresiyle `doSubscribeCurrentThread` değerineayarlanırsa**true** bire bir donanım iş parçacığı abonelik düzeyini artırır. Aynı zamanda sonuç bir `IExecutionResource` aboneliği temsil eden arabirim. Karşılık gelen bir çağrı [Iexecutionresource::Remove](#remove) azaltır donanım iş parçacığının abonelik düzeyine göre bir.

Yöntemini kullanarak bir sanal işlemci kökünde etkinleştirme işlemi [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate) bire bir donanım iş parçacığı abonelik düzeyini artırır. Yöntemleri [Ivirtualprocessorroot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), veya [Iexecutionresource::Remove](#remove) tek bir etkin sanal işlemci kökünde çağrıldığında abonelik düzeyinde azaltma.

Resource Manager kaynakları zamanlayıcılar arasında taşımak ne zaman belirlemek yöntemler biri olarak abonelik düzeyi bilgileri kullanır.

##  <a name="getexecutionresourceid"></a>  Iexecutionresource::getexecutionresourceıd metodu

Bu yürütme kaynak temsil eden donanım iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yürütme kaynak temel alınan donanım iş parçacığı için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Benzersiz bir tanımlayıcı, her bir donanım iş parçacığı eşzamanlılık çalışma zamanı tarafından atanır. Birden çok yürütme kaynakları ilişkili donanım varsa, iş parçacığı tümü aynı yürütme kaynak tanımlayıcısına sahip olacaktır.

##  <a name="getnodeid"></a>  Iexecutionresource::getnodeıd metodu

Bu yürütme kaynağın ait olduğu işlemci düğüm için benzersiz bir tanımlayıcı döndürür.

```
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işlemci düğüm için benzersiz bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma zamanı işlemci düğümleri gruplar halinde sistemdeki donanım iş parçacıklarının temsil eder. Düğümleri genellikle sistem donanım topolojisinden türetilir. Örneğin, belirli bir yuva veya belirli bir NUMA düğümünde tüm işlemcilerin aynı işlemci düğüme ait olabilir. Resource Manager sürümünden itibaren bu düğümler benzersiz tanımlayıcı atar `0` dahil `nodeCount - 1`burada `nodeCount` işlemci düğüm sistemdeki toplam sayısını temsil eder.

Düğüm sayısı işlevden elde edilebilir [GetProcessorNodeCount](concurrency-namespace-functions.md).

##  <a name="remove"></a>  Iexecutionresource::Remove yöntemi

Bu yürütme kaynak Resource Manager'a döndürür.

```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>Parametreler

*pScheduler*<br/>
Bu yürütme kaynağı kaldırmak için istekte Zamanlayıcı için arabirim.

### <a name="remarks"></a>Açıklamalar

Tek başına yürütme kaynakların yanı sıra sanal işlemci kökü için Resource Manager ile ilişkili yürütme kaynakları döndürmek için bu yöntemi kullanın.

Bu bir tek başına yürütme kaynak ise yöntemlerden birini alınan [Ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread) veya [Ischedulerproxy::requestınitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), çağırma yöntemi `Remove` kaynak için oluşturulmuş iş parçacığı abonelik sona erer temsil eder. İş parçacığı abonelikler Zamanlayıcı proxy kapatmadan önce sonlandırmak için gereklidir ve çağırmalıdır `Remove` abonelik oluşturulan iş parçacığından.

Sanal işlemci kökü de döndürülmesi için kaynak yöneticisi çağırarak `Remove` yöntemi, çünkü arabirimi `IVirtualProcessorRoot` devraldığı `IExecutionResource` arabirimi. Bir sanal işlemci kökünde yanıt olarak bir çağrı döndürmesi gerekebilir [Ischeduler::removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors) yöntemi veya öğesinden alınan bir zamanlayıcınızın sanal işlemci kökü ile işiniz bittiğinde [ Ischedulerproxy::createoversubscriber](ischedulerproxy-structure.md#createoversubscriber) yöntemi. Sanal işlemci kökü için sınırlama yoktur hangi iş parçacığı üzerinde çağırabilirsiniz `Remove` yöntemi.

`invalid_argument` varsa durum parametresi `pScheduler` ayarlanır `NULL`.

`invalid_operation` varsa durum parametresi `pScheduler` geçerli iş parçacığının iş parçacığı abonelik oluşturulan iş parçacığından farklı olması durumunda bu yürütme kaynak için veya, bir tek başına yürütme kaynak ile oluşturulmuş Zamanlayıcı farklıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)
