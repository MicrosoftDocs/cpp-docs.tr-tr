---
title: ISchedulerProxy Yapısı
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: 0dddd43a5b3e68992e41f0b95893303e57e7c7ff
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268856"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy Yapısı

Tarafından zamanlayıcılar kaynak ayırma anlaşmak için eşzamanlılık çalışma zamanının Resource Manager ile iletişim kurmak arabirim.

## <a name="syntax"></a>Sözdizimi

```
struct ISchedulerProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ischedulerproxy::bindcontext](#bindcontext)|Zaten bir ile ilişkili değilse, bir yürütme bağlamı bir iş parçacığı proxy ile ilişkilendirir.|
|[Ischedulerproxy::createoversubscriber](#createoversubscriber)|Yeni bir sanal işlemci kökü var olan bir yürütme kaynakla ilişkili donanım iş parçacığı oluşturur.|
|[Ischedulerproxy::requestınitialvirtualprocessors](#requestinitialvirtualprocessors)|Sanal işlemci kökü ilk ayırma ister. Her sanal işlemci kökü İş Zamanlayıcısı gerçekleştirebileceği bir iş parçacığı yürütme yeteneği temsil eder.|
|[Ischedulerproxy::Shutdown](#shutdown)|Kaynak Yöneticisi scheduler kapatılıyor bildirir. Bu zamanlayıcı verilen tüm kaynaklar hemen geri kazanmak için Resource Manager neden olur.|
|[Ischedulerproxy::subscribecurrentthread](#subscribecurrentthread)|Geçerli iş parçacığı kaynak bu Zamanlayıcı ile ilişkilendirme Yöneticisi ile kaydeder.|
|[Ischedulerproxy::unbindcontext](#unbindcontext)|Bir iş parçacığı proxy'sini tarafından belirtilen yürütme bağlamı ayırır `pContext` parametre ve boş iş parçacığı proxy fabrikasının havuzuna döndürür. Bu yöntem yalnızca aracılığıyla bağlanan bir yürütme bağlamında çağrılabilir [Ischedulerproxy::bindcontext](#bindcontext) yöntemi ve henüz olan aracılığıyla başlatılmadı `pContext` parametresinin bir [Ithreadproxy::switchto ](ithreadproxy-structure.md#switchto) yöntem çağrısı.|

## <a name="remarks"></a>Açıklamalar

Resource Manager uygulamalı bir `ISchedulerProxy` kullanarak kendisiyle kaydeder her Zamanlayıcı arabirimi [Iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler) yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISchedulerProxy`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="bindcontext"></a>  Ischedulerproxy::bindcontext yöntemi

Zaten bir ile ilişkili değilse, bir yürütme bağlamı bir iş parçacığı proxy ile ilişkilendirir.

```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
İş parçacığı Ara sunucu ile ilişkilendirilecek yürütme bağlamı için bir arabirim.

### <a name="remarks"></a>Açıklamalar

Normalde, [Ithreadproxy::switchto](ithreadproxy-structure.md#switchto) yöntemi bağlanma bir iş parçacığı proxy'sini isteğe bağlı bir yürütme bağlamı. Vardır, ancak önceden emin olmak için bir bağlam bağlamak gerekli olduğu durumlarda `SwitchTo` yöntemi için zaten ilişkili bir bağlam geçer. Bu durumda bellek ayırma yöntemlerini çağıramazsınız gibi zamanlama bağlamı bir UMS üzerinde ve bir iş parçacığı proxy'sini iş parçacığı proxy Factory ücretsiz Havuzda kullanılabilir değilse, bir iş parçacığı proxy'sini bağlama bellek ayırma gerektirebilir.

`invalid_argument` varsa durum parametresi `pContext` değerine sahip `NULL`.

##  <a name="createoversubscriber"></a>  Ischedulerproxy::createoversubscriber yöntemi

Yeni bir sanal işlemci kökü var olan bir yürütme kaynakla ilişkili donanım iş parçacığı oluşturur.

```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Parametreler

*pExecutionResource*<br/>
Bir `IExecutionResource` oversubscribe istediğiniz donanım iş parçacığı temsil eden arabirim.

### <a name="return-value"></a>Dönüş Değeri

Bir `IVirtualProcessorRoot` arabirimi.

### <a name="remarks"></a>Açıklamalar

Scheduler sınırlı bir süre için belirli donanım iş parçacığı oversubscribe istediğinde bu yöntemi kullanın. Sanal işlemci kökü ile işiniz bittiğinde, resource Manager'a çağırarak döndürmelidir [Kaldır](iexecutionresource-structure.md#remove) metodunda `IVirtualProcessorRoot` arabirimi.

Bile var olan bir sanal işlemci kökü için fazladan abone atayabilir `IVirtualProcessorRoot` arabirimi devralır `IExecutionResource` arabirimi.

##  <a name="requestinitialvirtualprocessors"></a>  Ischedulerproxy::requestınitialvirtualprocessors yöntemi

Sanal işlemci kökü ilk ayırma ister. Her sanal işlemci kökü İş Zamanlayıcısı gerçekleştirebileceği bir iş parçacığı yürütme yeteneği temsil eder.

```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Parametreler

*doSubscribeCurrentThread*<br/>
Geçerli iş parçacığı abone olmak ve bunun için kaynak ayırma sırasında hesap belirtir.

### <a name="return-value"></a>Dönüş Değeri

`IExecutionResource` Geçerli iş parçacığı için arabirim parametresi `doSubscribeCurrentThread` değerine sahip **true**. Değer ise **false**, bu yöntem NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bir zamanlayıcı herhangi bir iş yürütülmeden önce sanal işlemci kökü Kaynak Yöneticisi'nden istemek için bu yöntem kullanmalısınız. Kaynak Yöneticisi scheduler'ın ilke erişecek kullanarak [Ischeduler::getpolicy](ischeduler-structure.md#getpolicy) ve değerleri için ilke anahtarları kullanın `MinConcurrency`, `MaxConcurrency` ve `TargetOversubscriptionFactor` atamak için kaç donanım iş parçacıklarının belirlemek için Zamanlayıcı başlangıçta ve her donanım iş parçacığı için kaç sanal işlemci kökü. Zamanlayıcı ilkeleri scheduler'ın ilk ayırma belirlemek için nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md).

Resource Manager kaynakları için bir zamanlayıcı yöntemi çağırarak verir [Ischeduler::addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors) sanal işlemci kökü listesi ile. Bu yöntem döndürmeden önce yöntemin zamanlayıcıya bir geri arama olarak çağrılan.

Zamanlayıcı parametresini ayarlayarak aboneliği için geçerli iş parçacığının istenen `doSubscribeCurrentThread` için **true**, yöntem döndürür bir `IExecutionResource` arabirimi. Abonelik kullanarak sonraki bir noktada bitirilmelidir [Iexecutionresource::Remove](iexecutionresource-structure.md#remove) yöntemi.

Hangi donanım iş parçacıklarının seçili belirlerken, Resource Manager'ın işlemci düğüm benzeşim için en iyi duruma getirme dener. Aboneliği için geçerli iş parçacığının istenen geçerli iş parçacığı bu Zamanlayıcı için atanan çalışma katılmak amaçlayan bir gösterge yoktur. Böyle bir durumda ayrılmış sanal işlemci kökü, geçerli iş parçacığı, mümkünse yürütüldüğü işlemci düğümde yer alır.

Bir iş parçacığı abone olma işlemi bir temel alınan donanım iş parçacığı abonelik düzeyini artırır. Abonelik sonlandırıldığında abonelik düzeyinde bir azaltılır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="shutdown"></a>  Ischedulerproxy::Shutdown yöntemi

Kaynak Yöneticisi scheduler kapatılıyor bildirir. Bu zamanlayıcı verilen tüm kaynaklar hemen geri kazanmak için Resource Manager neden olur.

```
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Açıklamalar

Tüm `IExecutionContext` yöntemleri kullanarak harici bir iş parçacığı abone sonucunda alınan Zamanlayıcı arabirimleri `ISchedulerProxy::RequestInitialVirtualProcessors` veya `ISchedulerProxy::SubscribeCurrentThread` Resource Manager'a döndürülen kullanarak `IExecutionResource::Remove` kendisi bir zamanlayıcı kapatılmadan önce.

Scheduler varsa herhangi bir sanal işlemci kökü etkinliği, bunları etkinleştirmeniz gerekir kullanarak [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate)ve bırakın bunlar üzerinde yürütülen iş parçacığı proxy `Dispatch` yürütme yöntemi Bunlar gönderme çağırmayı önce bağlamları `Shutdown` Zamanlayıcı proxy.

Tek tek tüm sanal işlemci kökü çağrılar aracılığıyla kendisine verilen Resource Manager döndürecek şekilde Zamanlayıcı için gerekli değil `Remove` yöntemi olduğundan için Resource Manager kapatma içindeki tüm sanal işlemci kökü döndürülür.

##  <a name="subscribecurrentthread"></a>  Ischedulerproxy::subscribecurrentthread yöntemi

Geçerli iş parçacığı kaynak bu Zamanlayıcı ile ilişkilendirme Yöneticisi ile kaydeder.

```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IExecutionResource` Çalışma zamanı geçerli iş parçacığında temsil eden arabirim.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi scheduler ve diğer planlayıcılar için kaynak ayırma sırasında geçerli iş parçacığı için hesap istiyorsanız bu yöntemi kullanın. Zamanlayıcı Kaynak Yöneticisi'nden alır sanal işlemci kökü ile birlikte, Zamanlayıcı İş katılmak için iş parçacığı planları sıraya alınan olduğunda özellikle yararlıdır. Resource Manager bilgileri sistemdeki donanım iş parçacıklarının gereksiz gecikmeyi önlemek için kullanır.

Bu yöntem alınan yürütme kaynak Resource Manager'a döndürülmelidir kullanarak [Iexecutionresource::Remove](iexecutionresource-structure.md#remove) yöntemi. Çağıran iş parçacığının `Remove` yöntemi, daha önce çağıran iş parçacığının olmalıdır `SubscribeCurrentThread` yöntemi.

Bir iş parçacığı abone olma işlemi bir temel alınan donanım iş parçacığı abonelik düzeyini artırır. Abonelik sonlandırıldığında abonelik düzeyinde bir azaltılır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="unbindcontext"></a>  Ischedulerproxy::unbindcontext yöntemi

Bir iş parçacığı proxy'sini tarafından belirtilen yürütme bağlamı ayırır `pContext` parametre ve boş iş parçacığı proxy fabrikasının havuzuna döndürür. Bu yöntem yalnızca aracılığıyla bağlanan bir yürütme bağlamında çağrılabilir [Ischedulerproxy::bindcontext](#bindcontext) yöntemi ve henüz olan aracılığıyla başlatılmadı `pContext` parametresinin bir [Ithreadproxy::switchto ](ithreadproxy-structure.md#switchto) yöntem çağrısı.

```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
İş parçacığı proxy'sinin ilişkisini yürütme bağlamı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
