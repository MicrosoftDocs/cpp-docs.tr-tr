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
ms.openlocfilehash: f4a9e79c2da56406610ad6da08fb438e2f92923d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368157"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy Yapısı

Zamanlayıcıların kaynak ayırma konusunda anlaşmak için Eşzamanlı Çalışma Zamanı Kaynak Yöneticisi ile iletişim kurduğu arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
struct ISchedulerProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ISchedulerProxy::BindContext](#bindcontext)|Yürütme bağlamını, zaten bir iş parçacığı yla ilişkilendirmiyorsa, iş parçacığı proxy'si ile ilişkilendirin.|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Varolan bir yürütme kaynağıyla ilişkili donanım iş parçacığında yeni bir sanal işlemci kökü oluşturur.|
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Sanal işlemci köklerinin ilk tahsisini ister. Her sanal işlemci kökü, zamanlayıcı için iş gerçekleştirebilecek bir iş parçacığı yürütme yeteneğini temsil eder.|
|[ISchedulerProxy::Kapatma](#shutdown)|Kaynak Yöneticisi'ne zamanlayıcının kapatılıyor olduğunu belirtir. Bu, Kaynak Yöneticisi'nin zamanlayıcıya verilen tüm kaynakları hemen geri almasına neden olur.|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Geçerli iş parçacığıkaynak yöneticisine kaydeder ve bu zamanlayıcıyla ilişkilendirerek.|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|Bir iş parçacığı proxy'sini `pContext` parametre tarafından belirtilen yürütme bağlamından uzaklaştırın ve iş parçacığı proxy fabrikasının boş havuzuna döndürür. Bu yöntem yalnızca ISchedulerProxy üzerinden bağlanan bir yürütme bağlamında çağrılabilir::BindContext yöntemi ve `pContext` henüz bir IThreadProxy parametresi olarak başlatılmış [değil::SwitchTo](ithreadproxy-structure.md#switchto) yöntemi çağrısı. [ISchedulerProxy::BindContext](#bindcontext)|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, `ISchedulerProxy` [IResourceManager:RegisterScheduler](iresourcemanager-structure.md#registerscheduler) yöntemini kullanarak birlikte kaydeden her zamanlayıcıya bir arabirim verir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISchedulerProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>ISchedulerProxy::BindContext Yöntemi

Yürütme bağlamını, zaten bir iş parçacığı yla ilişkilendirmiyorsa, iş parçacığı proxy'si ile ilişkilendirin.

```cpp
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
Bir iş parçacığı proxy ile ilişkilendirmek için yürütme bağlamına bir arayüz.

### <a name="remarks"></a>Açıklamalar

Normalde, [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) yöntemi isteğe bağlı bir yürütme bağlamına bir iş parçacığı proxy bağlar. Ancak, yöntemin zaten bağlı bir içeriğe geçişini sağlamak `SwitchTo` için bir bağlamı önceden bağlamanın gerekli olduğu durumlar vardır. Bu, bellek ayıran yöntemleri arayamaz ve iş parçacığı proxy iş parçacığı proxy serbest havuzda hazır değilse bir iş parçacığı proxy bağlama bellek ayırma içerebilir gibi bir UMS zamanlama bağlamında durumdur.

`invalid_argument`parametre `pContext` değerine `NULL`sahipse atılır.

## <a name="ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>ISchedulerProxy::CreateOversubscriber Yöntemi

Varolan bir yürütme kaynağıyla ilişkili donanım iş parçacığında yeni bir sanal işlemci kökü oluşturur.

```cpp
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Parametreler

*pExecutionResource*<br/>
Aşırı `IExecutionResource` abone olmak istediğiniz donanım iş parçacığı temsil eden bir arabirim.

### <a name="return-value"></a>Dönüş Değeri

Bir `IVirtualProcessorRoot` arayüz.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcınız belirli bir donanım iş parçacığına sınırlı bir süre için aşırı abone olmak istediğinde bu yöntemi kullanın. Sanal işlemci köküyle iş bittiğinde, arabirimdeki [Kaldır](iexecutionresource-structure.md#remove) yöntemini çağırarak bu `IVirtualProcessorRoot` yöntemi kaynak yöneticisine döndürmelisiniz.

`IVirtualProcessorRoot` Arabirim `IExecutionResource` arabirimden devraldığı için varolan sanal işlemci köküne bile fazla abone olabilirsiniz.

## <a name="ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>ISchedulerProxy::RequestInitialVirtualProcessors Yöntemi

Sanal işlemci köklerinin ilk tahsisini ister. Her sanal işlemci kökü, zamanlayıcı için iş gerçekleştirebilecek bir iş parçacığı yürütme yeteneğini temsil eder.

```cpp
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Parametreler

*doSubscribeCurrentThread*<br/>
Kaynak ayırma sırasında geçerli iş parçacığına abone olunup hesaba katılmamak.

### <a name="return-value"></a>Dönüş Değeri

Parametre `IExecutionResource` `doSubscribeCurrentThread` **değeri gerçekse,** geçerli iş parçacığının arabirimi. Değer **yanlışsa,** yöntem NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bir zamanlayıcı herhangi bir çalışmayı yürütmeden önce, Kaynak Yöneticisi'nden sanal işlemci kökleri istemek için bu yöntemi kullanmalıdır. Kaynak [Yöneticisi, IScheduler::GetPolicy'yi](ischeduler-structure.md#getpolicy) kullanarak zamanlayıcının ilkesine erişecek `MinConcurrency`ve `MaxConcurrency` `TargetOversubscriptionFactor` ilke anahtarlarıiçin değerleri kullanacak ve başlangıçta zamanlayıcıya kaç donanım iş parçacığı atayacak ve her donanım iş parçacığı için kaç sanal işlemci kökü oluşturulacağını belirleyecek. Zamanlayıcı ilkelerinin bir zamanlayıcının ilk tahsisatLarını belirlemek için nasıl kullanıldığı hakkında daha fazla bilgi için [Bkz.](concurrency-namespace-enums.md)

Kaynak Yöneticisi, iScheduler yöntemini arayarak bir zamanlayıcıya kaynak verir::Sanal işlemci köklerinin bir listesini içeren [VirtualProcessors ekler.](ischeduler-structure.md#addvirtualprocessors) Yöntem, bu yöntem dönmeden önce zamanlayıcıya geri çağrılolarak çağrılır.

Zamanlayıcı, parametreyi `doSubscribeCurrentThread` **doğru**olarak ayarlayarak geçerli iş parçacığı için `IExecutionResource` abonelik istediyse, yöntem bir arabirim döndürür. Abonelik [iExecutionResource::Remove](iexecutionresource-structure.md#remove) yöntemi kullanılarak daha sonraki bir noktada sonlandırılmalıdır.

Hangi donanım iş parçacığının seçili olduğunu belirlerken, Kaynak Yöneticisi işlemci düğümü afiyeti için en iyi duruma getirmeye çalışır. Geçerli iş parçacığı için abonelik isteniyorsa, geçerli iş parçacığının bu zamanlayıcıya atanan çalışmaya katılmak niyetinde olduğunun bir göstergesidir. Böyle bir durumda, ayrılan sanal işlemci kökleri, varsa geçerli iş parçacığının yürütüldettiği işlemci düğümünde bulunur.

Bir iş parçacığıabone olma eylemi, temel donanım iş parçacığının abonelik düzeyini bir artırır. Abonelik sonlandırıldığında abonelik düzeyi bir azaltılır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyshutdown-method"></a><a name="shutdown"></a>ISchedulerProxy::Kapatma Yöntemi

Kaynak Yöneticisi'ne zamanlayıcının kapatılıyor olduğunu belirtir. Bu, Kaynak Yöneticisi'nin zamanlayıcıya verilen tüm kaynakları hemen geri almasına neden olur.

```cpp
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Açıklamalar

Zamanlamacının `IExecutionContext` yöntemleri `ISchedulerProxy::RequestInitialVirtualProcessors` kullanarak harici bir iş parçacığına abone olması sonucunda `ISchedulerProxy::SubscribeCurrentThread` aldığı tüm arabirimler `IExecutionResource::Remove` veya zamanlayıcı kendini kapatmadan önce kaynak yöneticisine döndürülmelidir.

Zamanlayıcınız devre dışı bırakılmış sanal işlemci köklerine sahipse, bunları IVirtualProcessorRoot kullanarak etkinleştirmeniz [gerekir::Etkinleştirin](ivirtualprocessorroot-structure.md#activate)ve iş parçacığı proxy'lerinin, `Shutdown` bir zamanlayıcı proxy'ye çağırmadan önce gönderdikleri yürütme bağlamlarının `Dispatch` yöntemini bırakmasını sağlar.

Tüm sanal işlemci kökleri kapatma sırasında Kaynak Yöneticisi'nin kendisine çağrılar `Remove` yoluyla verdiği tüm sanal işlemci köklerini tek tek döndürmesi gerekli değildir.

## <a name="ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>ISchedulerProxy::SubscribeCurrentThread Yöntemi

Geçerli iş parçacığıkaynak yöneticisine kaydeder ve bu zamanlayıcıyla ilişkilendirerek.

```cpp
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma `IExecutionResource` zamanında geçerli iş parçacığı temsil eden ara yüz.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi'nin zamanlayıcınıza ve diğer zamanlayıcılarınıza kaynak ayırırken geçerli iş parçacığının hesabını kullanmasını istiyorsanız bu yöntemi kullanın. İş parçacığı, zamanlayıcınızın Kaynak Yöneticisi'nden aldığı sanal işlemci kökleriyle birlikte programlayıcınıza sıralanmış çalışmaya katılmayı planladığında özellikle yararlıdır. Kaynak Yöneticisi, sistemdeki donanım iş parçacığının gereksiz aşırı aboneliğini önlemek için bilgileri kullanır.

Bu yöntemle alınan yürütme [kaynağı, IExecutionResource::Remove](iexecutionresource-structure.md#remove) yöntemi kullanılarak Kaynak Yöneticisi'ne döndürülmelidir. `Remove` Yöntemi çağıran iş parçacığı, daha önce `SubscribeCurrentThread` yöntem olarak adlandırılan aynı iş parçacığı olmalıdır.

Bir iş parçacığıabone olma eylemi, temel donanım iş parçacığının abonelik düzeyini bir artırır. Abonelik sonlandırıldığında abonelik düzeyi bir azaltılır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>ISchedulerProxy::UnbindContext Yöntemi

Bir iş parçacığı proxy'sini `pContext` parametre tarafından belirtilen yürütme bağlamından uzaklaştırın ve iş parçacığı proxy fabrikasının boş havuzuna döndürür. Bu yöntem yalnızca ISchedulerProxy üzerinden bağlanan bir yürütme bağlamında çağrılabilir::BindContext yöntemi ve `pContext` henüz bir IThreadProxy parametresi olarak başlatılmış [değil::SwitchTo](ithreadproxy-structure.md#switchto) yöntemi çağrısı. [ISchedulerProxy::BindContext](#bindcontext)

```cpp
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
İş parçacığı proxy'sinden ayırmak için yürütme bağlamı.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
