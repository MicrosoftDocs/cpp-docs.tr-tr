---
title: "Ischedulerproxy yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
dev_langs: C++
helpviewer_keywords: ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d650df9c77b6a99c7ee9982caa88e8eb7c1b8d9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy Yapısı
Tarafından zamanlayıcılar kaynak ayırma anlaşmak üzere eşzamanlılık çalışma zamanı Resource Manager ile iletişim kurmak arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ischedulerproxy::bindcontext](#bindcontext)|Zaten bir ile ilişkili değilse yürütme bağlamı bir iş parçacığı proxy ile ilişkilendirir.|  
|[Ischedulerproxy::createoversubscriber](#createoversubscriber)|Varolan bir yürütme kaynakla ilişkili donanım iş parçacığı üzerinde yeni bir sanal işlemcinin kökü oluşturur.|  
|[Ischedulerproxy::requestınitialvirtualprocessors](#requestinitialvirtualprocessors)|Sanal işlemci kökleri ilk ayırma ister. Her sanal işlemci kök için Zamanlayıcı İş gerçekleştiren bir iş parçacığını yürütmek için özelliğini temsil eder.|  
|[Ischedulerproxy::Shutdown](#shutdown)|Resource Manager Zamanlayıcısı kapatılıyor bildirir. Bu zamanlayıcı için verilen tüm kaynaklar hemen geri kazanmak için Kaynak Yöneticisi'ni neden olur.|  
|[Ischedulerproxy::subscribecurrentthread](#subscribecurrentthread)|Geçerli iş parçacığının kaynak bu Zamanlayıcı ile ilişkilendirme Yöneticisi ile kaydeder.|  
|[Ischedulerproxy::unbindcontext](#unbindcontext)|Bir iş parçacığı Proxy'den tarafından belirtilen Yürütme bağlamını keser `pContext` parametre ve iş parçacığı proxy fabrikasının boş havuza geri döner. Bu yöntem yalnızca aracılığıyla bağlı bir yürütme bağlamı üzerinde çağrılabilir [Ischedulerproxy::bindcontext](#bindcontext) yöntemi ve henüz olan aracılığıyla başlatılmadı `pContext` parametresinin bir [Ithreadproxy::switchto ](ithreadproxy-structure.md#switchto) yöntem çağrısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Resource Manager aktarır bir `ISchedulerProxy` arabirimi kullanarak kendisiyle kaydeder her Zamanlayıcısına [Iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler) yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="bindcontext"></a>Ischedulerproxy::bindcontext yöntemi  
 Zaten bir ile ilişkili değilse yürütme bağlamı bir iş parçacığı proxy ile ilişkilendirir.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 Bir iş parçacığı proxy ile ilişkilendirmek için yürütme bağlamı için bir arabirim.  
  
### <a name="remarks"></a>Açıklamalar  
 Normalde, [Ithreadproxy::switchto](ithreadproxy-structure.md#switchto) bağlama yöntemini bir iş parçacığı proxy için isteğe bağlı bir yürütme bağlamı. Vardır, ancak, önceden emin olmak için bir bağlam bağlamak gerekli olduğu durumlarda `SwitchTo` yöntemi zaten ilişkili bir bağlamına geçer. Bu bellek yöntemleri çağrılamaz gibi zamanlama bağlamı UMS kasasındaki ve bir iş parçacığı proxy iş parçacığı proxy Fabrika boş havuzundaki kullanıma hazır değilse, bir iş parçacığı proxy bağlama bellek ayırma gerektirebilir.  
  
 `invalid_argument`varsa durum parametresi `pContext` değerine sahip `NULL`.  
  
##  <a name="createoversubscriber"></a>Ischedulerproxy::createoversubscriber yöntemi  
 Varolan bir yürütme kaynakla ilişkili donanım iş parçacığı üzerinde yeni bir sanal işlemcinin kökü oluşturur.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pExecutionResource`  
 Bir `IExecutionResource` oversubscribe istediğiniz donanım iş parçacığı temsil eden arabirim.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `IVirtualProcessorRoot` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı sınırlı bir süre için belirli donanım iş parçacığı oversubscribe istediğinde bu yöntemi kullanın. Sanal işlemci kök ile tamamladıktan sonra bu kaynak yöneticisi çağırarak döndürmelidir [kaldırmak](iexecutionresource-structure.md#remove) yöntemi `IVirtualProcessorRoot` arabirimi.  
  
 Hatta var olan bir sanal işlemcinin kökü çünkü fazlasına abone olabilirsiniz `IVirtualProcessorRoot` arabirimi devraldığı `IExecutionResource` arabirimi.  
  
##  <a name="requestinitialvirtualprocessors"></a>Ischedulerproxy::requestınitialvirtualprocessors yöntemi  
 Sanal işlemci kökleri ilk ayırma ister. Her sanal işlemci kök için Zamanlayıcı İş gerçekleştiren bir iş parçacığını yürütmek için özelliğini temsil eder.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `doSubscribeCurrentThread`  
 Geçerli iş parçacığının abone alıp almayacağını için kaynak ayırma sırasında hesap.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `IExecutionResource` Geçerli iş parçacığı için arabirim parametresi `doSubscribeCurrentThread` değerine sahip `true`. Değer ise `false`, yöntem `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir zamanlayıcı herhangi bir iş yürütülmeden önce Kaynak Yöneticisi'nden sanal işlemci kökleri istemek için bu yöntem kullanmanız gerekir. Resource Manager scheduler'ın ilke erişecek kullanarak [Ischeduler::getpolicy](ischeduler-structure.md#getpolicy) ve ilke tuşlarını değerleri `MinConcurrency`, `MaxConcurrency` ve `TargetOversubscriptionFactor` atamak için kaç tane donanım iş parçacığı belirlemek için Zamanlayıcı başlangıçta ve kaç tane sanal işlemci kökleri için her donanım iş parçacığı oluşturulamıyor. Zamanlayıcı ilkeleri scheduler'ın ilk ayırma belirlemek için nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [PolicyElementKey](concurrency-namespace-enums.md).  
  
 Resource Manager kaynakları yöntemini çağırarak bir zamanlayıcı verir [Ischeduler::addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors) sanal işlemci köklerin listesi ile. Bu yöntem döndürmeden önce yöntemi Zamanlayıcı geri arama olarak çağrılır.  
  
 Zamanlayıcı parametresi ayarlanarak abonelik geçerli iş parçacığı için istenen `doSubscribeCurrentThread` için `true`, yöntem bir `IExecutionResource` arabirimi. Abonelik sonraki bir noktada kullanarak bitmelidir [Iexecutionresource::Remove](iexecutionresource-structure.md#remove) yöntemi.  
  
 Hangi donanım iş parçacığı seçili belirlerken, Resource Manager işlemci düğümü benzeşimini için en iyi duruma getirme girişiminde bulunur. Abonelik için geçerli iş parçacığının istenen, geçerli iş parçacığının Bu zamanlayıcı için atanan iş katılan amaçlayan bir gösterge olur. Böyle bir durumda ayrılmış sanal işlemci kökleri geçerli iş parçacığı, mümkünse yürütüyor işlemci düğümünde bulunur.  
  
 Bir iş parçacığı abone eylemi bir temel alınan donanım iş parçacığı abonelik düzeyini artırır. Abonelik sonlandırıldığında abonelik düzeyinde bir azalır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="shutdown"></a>Ischedulerproxy::Shutdown yöntemi  
 Resource Manager Zamanlayıcısı kapatılıyor bildirir. Bu zamanlayıcı için verilen tüm kaynaklar hemen geri kazanmak için Kaynak Yöneticisi'ni neden olur.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm `IExecutionContext` yöntemleri kullanarak harici bir iş parçacığı abone sonucunda alınan Zamanlayıcı arabirimleri `ISchedulerProxy::RequestInitialVirtualProcessors` veya `ISchedulerProxy::SubscribeCurrentThread` Resource Manager döndürülmelidir kullanarak `IExecutionResource::Remove` kendisini bir zamanlayıcı kapatılmadan önce.  
  
 Zamanlayıcı sahipse, herhangi bir sanal işlemcinin kökleri devre dışı bırakıldı, bunları etkinleştirmeniz gerekir kullanarak [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate)ve bırakın üzerlerinde yürütme iş parçacığı proxy'leri `Dispatch` yürütme yöntemi Bunlar göndermeyi çağırmayı önce bağlamları `Shutdown` Zamanlayıcı proxy.  
  
 Tek tek tüm sanal işlemci kökleri kendisine çağrıları aracılığıyla verilen Resource Manager döndürmek Zamanlayıcı için gerekli değildir `Remove` yöntemi için kaynak yöneticisi kapatma sırasında tüm sanal işlemciler kökleri döndürülecek olduğundan.  
  
##  <a name="subscribecurrentthread"></a>Ischedulerproxy::subscribecurrentthread yöntemi  
 Geçerli iş parçacığının kaynak bu Zamanlayıcı ile ilişkilendirme Yöneticisi ile kaydeder.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `IExecutionResource` Çalışma zamanında geçerli iş parçacığının temsil eden arabirim.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli iş parçacığı için kaynakları, Zamanlayıcı ve diğer zamanlayıcılar ayrılırken hesap için Kaynak Yöneticisi'ni istiyorsanız bu yöntemi kullanın. İş katılmak için iş parçacığı planları Zamanlayıcı Kaynak Yöneticisi'nden alır sanal işlemci kökleri yanı sıra, Zamanlayıcı kuyruğa atılmış özellikle yararlı olur. Kaynak Yöneticisi sistem üzerindeki donanım iş parçacığı gereksiz aşırı abonelik önlemek için bilgileri kullanır.  
  
 Bu yöntem alınan yürütme kaynak Resource Manager döndürülmelidir kullanarak [Iexecutionresource::Remove](iexecutionresource-structure.md#remove) yöntemi. Çağıran iş parçacığı `Remove` yöntemi, daha önce adı aynı iş parçacığı olmalıdır `SubscribeCurrentThread` yöntemi.  
  
 Bir iş parçacığı abone eylemi bir temel alınan donanım iş parçacığı abonelik düzeyini artırır. Abonelik sonlandırıldığında abonelik düzeyinde bir azalır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="unbindcontext"></a>Ischedulerproxy::unbindcontext yöntemi  
 Bir iş parçacığı Proxy'den tarafından belirtilen Yürütme bağlamını keser `pContext` parametre ve iş parçacığı proxy fabrikasının boş havuza geri döner. Bu yöntem yalnızca aracılığıyla bağlı bir yürütme bağlamı üzerinde çağrılabilir [Ischedulerproxy::bindcontext](#bindcontext) yöntemi ve henüz olan aracılığıyla başlatılmadı `pContext` parametresinin bir [Ithreadproxy::switchto ](ithreadproxy-structure.md#switchto) yöntem çağrısı.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 Kendi iş parçacığı proxy sunucudan ilişkisini kaldırmak için yürütme bağlamı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Ischeduler yapısı](ischeduler-structure.md)   
 [Ithreadproxy yapısı](ithreadproxy-structure.md)   
 [Ivirtualprocessorroot yapısı](ivirtualprocessorroot-structure.md)   
 [Iresourcemanager yapısı](iresourcemanager-structure.md)
