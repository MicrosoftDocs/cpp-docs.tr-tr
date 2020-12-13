---
description: 'Daha fazla bilgi edinin: ISchedulerProxy yapısı'
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
ms.openlocfilehash: 4c3c488136c2b41a76b3080b2162fbf95dcb5ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334453"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy Yapısı

Zamanlayıcılar tarafından kaynak ayırmayı anlaşmak için Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi iletişim kuran arabirim.

## <a name="syntax"></a>Syntax

```cpp
struct ISchedulerProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ibıchedulerproxy:: BindContext](#bindcontext)|Zaten bir ilişkili değilse, bir yürütme bağlamını bir iş parçacığı proxy 'si ile ilişkilendirir.|
|[Ibıchedulerproxy:: CreateOversubscriber](#createoversubscriber)|Mevcut bir yürütme kaynağıyla ilişkili donanım iş parçacığında yeni bir sanal işlemci kökü oluşturur.|
|[Ibıchedulerproxy:: Requestınitialvirtualiþlemcileri](#requestinitialvirtualprocessors)|Sanal işlemci köklerinin ilk ayırmasını ister. Her sanal işlemci kökü Zamanlayıcı için iş gerçekleştirebilen bir iş parçacığını yürütme yeteneğini temsil eder.|
|[Ibıchedulerproxy:: kapanıyor](#shutdown)|Kaynak Yöneticisi Scheduler 'ın kapandığını bildirir. Bu, Kaynak Yöneticisi Scheduler 'a verilen tüm kaynakları hemen geri kazanmasına neden olur.|
|[ISchedulerProxy:: SubscribeCurrentThread](#subscribecurrentthread)|Geçerli iş parçacığını Bu Zamanlayıcı ile ilişkilendirerek Kaynak Yöneticisi kaydeder.|
|[Ibıchedulerproxy:: UnbindContext](#unbindcontext)|Bir iş parçacığı proxy 'sini parametresi tarafından belirtilen yürütme bağlamından ilişkilendirir `pContext` ve iş parçacığı proxy fabrikasının boş havuzuna döndürür. Bu yöntem yalnızca [ıbıchedulerproxy:: BindContext](#bindcontext) yöntemi aracılığıyla bağlı bir yürütme bağlamı üzerinde çağrılabilir ve henüz `pContext` bir [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) yöntem çağrısının parametresi ile başlatılmamış olabilir.|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, `ISchedulerProxy` [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) yöntemi kullanılarak kaydeden her Scheduler 'a bir arabirim sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISchedulerProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="ischedulerproxybindcontext-method"></a><a name="bindcontext"></a> Ibıchedulerproxy:: BindContext yöntemi

Zaten bir ilişkili değilse, bir yürütme bağlamını bir iş parçacığı proxy 'si ile ilişkilendirir.

```cpp
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bir iş parçacığı proxy 'si ile ilişkilendirilecek yürütme bağlamına yönelik arabirim.

### <a name="remarks"></a>Açıklamalar

Normalde, [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) yöntemi bir iş parçacığı proxy 'sini isteğe bağlı bir yürütme bağlamına bağlar. Ancak, `SwitchTo` metodun zaten bağlı bir içeriğe geçiş yapıldığından emin olmak için bir bağlamı önceden bağlamak gerekli olduğu durumlar vardır. Bu durum, bellek ayıran yöntemleri arayamamakta olduğu ve bir iş parçacığı proxy 'sinin serbest bırakılmadığı iş parçacığı proxy 'si fabrikası için bir iş parçacığı proxy 'si kullanılabilir değilse bellek ayırmayı içerebilen bir UMS zamanlama bağlamıdır.

`invalid_argument` parametrenin değeri varsa oluşturulur `pContext` `NULL` .

## <a name="ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a> Ibıchedulerproxy:: CreateOversubscriber yöntemi

Mevcut bir yürütme kaynağıyla ilişkili donanım iş parçacığında yeni bir sanal işlemci kökü oluşturur.

```cpp
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Parametreler

*pExecutionResource*<br/>
`IExecutionResource`Fazla abone olmak istediğiniz donanım iş parçacığını temsil eden bir arabirim.

### <a name="return-value"></a>Dönüş Değeri

Bir `IVirtualProcessorRoot` arabirim.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı, belirli bir donanım iş parçacığını sınırlı bir süre için fazla sayıda abone olmak istediğinde bu yöntemi kullanın. Sanal işlemci kökünü tamamladıktan sonra, arabirimdeki [Remove](iexecutionresource-structure.md#remove) metodunu çağırarak Kaynak Yöneticisi 'ne dönmeniz gerekir `IVirtualProcessorRoot` .

Arabirim arabirimden devraldığı için, var olan bir sanal işlemci köküne da fazla abone olabilirsiniz `IVirtualProcessorRoot` `IExecutionResource` .

## <a name="ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a> Ibıchedulerproxy:: Requestınitialvirtualişlemcilerle yöntemi

Sanal işlemci köklerinin ilk ayırmasını ister. Her sanal işlemci kökü Zamanlayıcı için iş gerçekleştirebilen bir iş parçacığını yürütme yeteneğini temsil eder.

```cpp
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Parametreler

*Dosubkaralama Becurrentthread*<br/>
Kaynak ayırma sırasında geçerli iş parçacığının ve hesabın abone yapılıp yapılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

`IExecutionResource`Parametrenin değeri varsa, geçerli iş parçacığı için arabirim `doSubscribeCurrentThread` **`true`** . Değer ise **`false`** , YÖNTEMI null değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı herhangi bir çalışmayı yürütmeden önce, Kaynak Yöneticisi sanal işlemci kökleri istemek için bu yöntemi kullanmalıdır. Kaynak Yöneticisi, [IScheduler:: GetPolicy](ischeduler-structure.md#getpolicy) kullanarak Scheduler ilkesine erişir ve ilke anahtarlarının değerlerini kullanır ve `MinConcurrency` `MaxConcurrency` her bir `TargetOversubscriptionFactor` donanım iş parçacığı için başlangıçta ve kaç tane sanal işlemci köklerine atanacağını belirleme ve bu Zamanlayıcı için kaç tane donanım iş parçacığının oluşturulacağını belirlemektir. Zamanlayıcı ilkelerinin bir Scheduler 'ın ilk ayırmasını belirlemede nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [PolicyElementKey](concurrency-namespace-enums.md).

Kaynak Yöneticisi, sanal işlemci köklerinin listesini içeren [IComparer:: AddVirtualProcessor](ischeduler-structure.md#addvirtualprocessors) metodunu çağırarak bir Scheduler 'a kaynak verir. Yöntemi, bu yöntemin döndürüldüğünden önce Scheduler 'a geri çağırma olarak çağrılır.

Zamanlayıcı, parametresi olarak ayarlanarak geçerli iş parçacığı için abonelik isteğinde bulunursa `doSubscribeCurrentThread` **`true`** , yöntem bir `IExecutionResource` arabirim döndürür. Aboneliğin [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) yöntemi kullanılarak sonraki bir noktada sonlandırılması gerekir.

Hangi donanım iş parçacıklarının seçili olduğunu belirlerken, Kaynak Yöneticisi işlemci düğümü benzeşimi için iyileştirmeye çalışacaktır. Geçerli iş parçacığı için abonelik isteniyorsa, bu, geçerli iş parçacığının Bu Scheduler 'a atanan işe katılmayı amaçladığı bir göstergesidir. Böyle bir durumda, ayrılan sanal işlemcilerin kökleri, mümkünse geçerli iş parçacığının yürütüldüğü işlemci düğümünde bulunur.

Bir iş parçacığını abone olma eylemi, temel alınan donanım iş parçacığının abonelik düzeyini bir tane artırır. Abonelik sonlandırıldığı zaman abonelik düzeyi bir şekilde azaltılır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyshutdown-method"></a><a name="shutdown"></a> Ibıchedulerproxy:: kapanıyor yöntemi

Kaynak Yöneticisi Scheduler 'ın kapandığını bildirir. Bu, Kaynak Yöneticisi Scheduler 'a verilen tüm kaynakları hemen geri kazanmasına neden olur.

```cpp
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Açıklamalar

Tüm `IExecutionContext` arabirimler, bir dış iş parçacığının yöntemlerini kullanarak abone olma sonucu olarak aldığı `ISchedulerProxy::RequestInitialVirtualProcessors` veya `ISchedulerProxy::SubscribeCurrentThread` Zamanlayıcı kendisini kapatmadan önce kullanılarak Kaynak Yöneticisi döndürülmelidir `IExecutionResource::Remove` .

Scheduler 'da devre dışı bırakılmış bir sanal işlemci kökü varsa, [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate)öğesini kullanarak bunları etkinleştirmeniz gerekir ve iş parçacığı proxy 'leri, `Dispatch` `Shutdown` bir Zamanlayıcı proxy üzerinde çağırmadan önce, gönderen yürütme bağlamlarının yöntemini bırakır.

Scheduler 'ın tüm sanal işlemci köklerinin, bu yönteme çağrı aracılığıyla Kaynak Yöneticisi, `Remove` tüm sanal işlemci köklerinin, kapatılırken Kaynak Yöneticisi döndürüldüğünden bağımsız olarak tek başına döndürülmesi gerekli değildir.

## <a name="ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a> Ibıchedulerproxy:: SubscribeCurrentThread yöntemi

Geçerli iş parçacığını Bu Zamanlayıcı ile ilişkilendirerek Kaynak Yöneticisi kaydeder.

```cpp
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IExecutionResource`Çalışma zamanındaki geçerli iş parçacığını temsil eden arabirim.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi Scheduler 'a ve diğer zamanlayıcılar kaynak atarken geçerli iş parçacığı için hesap kullanmasını istiyorsanız bu yöntemi kullanın. İş parçacığı, Scheduler 'ın Kaynak Yöneticisi aldığı sanal işlemci kökleriyle birlikte Zamanlayıcı 'ya sıraya alınan çalışmaya katılmayı planlıyorsa özellikle yararlıdır. Kaynak Yöneticisi sistemdeki donanım iş parçacıklarının gereksiz aşırı aboneliğini engellemek için bilgileri kullanır.

Bu yöntem aracılığıyla alınan yürütme kaynağı [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) yöntemi kullanılarak Kaynak Yöneticisi döndürülmelidir. Yöntemi çağıran iş parçacığının, `Remove` daha önce yöntemini çağıran aynı iş parçacığı olması gerekir `SubscribeCurrentThread` .

Bir iş parçacığını abone olma eylemi, temel alınan donanım iş parçacığının abonelik düzeyini bir tane artırır. Abonelik sonlandırıldığı zaman abonelik düzeyi bir şekilde azaltılır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a> Ibıchedulerproxy:: UnbindContext yöntemi

Bir iş parçacığı proxy 'sini parametresi tarafından belirtilen yürütme bağlamından ilişkilendirir `pContext` ve iş parçacığı proxy fabrikasının boş havuzuna döndürür. Bu yöntem yalnızca [ıbıchedulerproxy:: BindContext](#bindcontext) yöntemi aracılığıyla bağlı bir yürütme bağlamı üzerinde çağrılabilir ve henüz `pContext` bir [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) yöntem çağrısının parametresi ile başlatılmamış olabilir.

```cpp
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
İş parçacığı proxy 'sinden ilişkiyi kaldırmak için yürütme bağlamı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
