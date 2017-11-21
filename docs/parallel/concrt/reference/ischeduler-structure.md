---
title: "Ischeduler yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
dev_langs: C++
helpviewer_keywords: IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e38029e13bc342895922f4f3624076ab513f7a45
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ischeduler-structure"></a>IScheduler Yapısı
İş Zamanlayıcı bir soyutlamasını bir arabirim. Eşzamanlılık Çalışma zamanı Resource Manager, iş zamanlayıcılar ile iletişim kurmak için bu arabirimini kullanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ischeduler::addvirtualprocessors](#addvirtualprocessors)|Bir zamanlayıcı kullanımı için sanal işlemci kökleri bir dizi sağlar. Her `IVirtualProcessorRoot` arabirimi iş Zamanlayıcı adına gerçekleştirebileceğiniz tek bir iş parçacığını yürütmek için sağa temsil eder.|  
|[Ischeduler::GetID](#getid)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|  
|[Ischeduler::getpolicy](#getpolicy)|Scheduler'ın ilke kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [SchedulerPolicy](schedulerpolicy-class.md).|  
|[Ischeduler::notifyresourcesexternallybusy](#notifyresourcesexternallybusy)|Donanım iş parçacıkları sanal işlemci kökleri dizideki kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` şimdi diğer zamanlayıcılar tarafından kullanılıyor.|  
|[Ischeduler::notifyresourcesexternallyıdle](#notifyresourcesexternallyidle)|Donanım iş parçacıkları sanal işlemci kökleri dizideki kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` diğer zamanlayıcılar tarafından kullanılmıyor.|  
|[Ischeduler::removevirtualprocessors](#removevirtualprocessors)|Daha önce bu Zamanlayıcı için ayrılan sanal işlemci kökleri kaldırılmasını başlatır.|  
|[Ischeduler::Statistics](#statistics)|Görev varış ve tamamlama hızları ve kuyruk uzunluğu değişikliği bir zamanlayıcı için ilgili bilgiler sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Resource Manager ile iletişim kuran özel Zamanlayıcısı'nı uyguluyorsanız, uygulaması sağlamalıdır `IScheduler` arabirimi. Bu arabirim bir Zamanlayıcı ve kaynak yöneticisi arasındaki iletişim çift yönlü bir kanal sonudur. Diğer uçtaki tarafından temsil edilen `IResourceManager` ve `ISchedulerProxy` , kaynak yöneticisi tarafından uygulanan arabirimler.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IScheduler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="addvirtualprocessors"></a>Ischeduler::addvirtualprocessors yöntemi  
 Bir zamanlayıcı kullanımı için sanal işlemci kökleri bir dizi sağlar. Her `IVirtualProcessorRoot` arabirimi iş Zamanlayıcı adına gerçekleştirebileceğiniz tek bir iş parçacığını yürütmek için sağa temsil eder.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `ppVirtualProcessorRoots`  
 Bir dizi `IVirtualProcessorRoot` sanal işlemci temsil eden arabirimleri kökleri Zamanlayıcı eklenmekte olan.  
  
 `count`  
 Sayısı `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak Yöneticisi'ni çağırır `AddVirtualProcessor` sanal işlemci kökleri başlangıç kümesi için bir zamanlayıcı vermek için yöntem. Bu ayrıca kaynakları zamanlayıcılar arasında yeniden dengeler zaman sanal işlemci kökleri Zamanlayıcı eklemek için yöntemi çağıramadı.  
  
##  <a name="getid"></a>Ischeduler::GetID yöntemi  
 Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı benzersiz tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmanız gereken [Getschedulerıd](concurrency-namespace-functions.md) uygulayan nesnenin için benzersiz bir tanımlayıcı elde etmek için işlevi `IScheduler` arabirimi arabirim yöntemleri için bir parametre olarak kullanmadan önce kaynak yöneticisi tarafından sağlanan. Aynı tanımlayıcısı döndürmesi bekleniyor zaman `GetId` işlevi çağrılır.  
  
 Farklı bir kaynaktan alınan tanımlayıcı tanımsız davranışlara neden.  
  
##  <a name="getpolicy"></a>Ischeduler::getpolicy yöntemi  
 Scheduler'ın ilke kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [SchedulerPolicy](schedulerpolicy-class.md).  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Scheduler'ın ilke kopyası.  
  
##  <a name="notifyresourcesexternallybusy"></a>Ischeduler::notifyresourcesexternallybusy yöntemi  
 Donanım iş parçacıkları sanal işlemci kökleri dizideki kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` şimdi diğer zamanlayıcılar tarafından kullanılıyor.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `ppVirtualProcessorRoots`  
 Bir dizi `IVirtualProcessorRoot` donanım iş parçacığı üzerinde diğer zamanlayıcılar hale meşgul ilişkili arabirimleri.  
  
 `count`  
 Sayısı `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli donanım iş parçacığı aynı anda birden çok zamanlayıcılar atanması mümkündür. Bunun bir nedeni olmadığından, yeterli donanım iş parçacığı kaynakları paylaşma olmadan tüm zamanlayıcılar için minimum eşzamanlılık karşılamak için sistem üzerindeki olabilir. Başka bir olasılık sahibi olan Zamanlayıcı bunları devre dışı bırakılan bu donanım iş parçacığı üzerinde tüm sanal işlemci kökleri yapmamanız kullanmadığında kaynakları geçici olarak diğer zamanlayıcılar için atanmış olabilir.  
  
 Bir donanım iş parçacığı abonelik düzeyi abone iş parçacığı sayısı ile gösterilir ve bu donanım iş parçacığı ile ilişkili sanal işlemci kökleri etkinleştirilmelidir. Belirli bir Zamanlayıcının açısından bakıldığında, bir donanım iş parçacığı dış abonelik düzeyi diğer zamanlayıcılar katkıda abonelik bölümüdür. Bir donanım iş parçacığı için dış abonelik düzeyi pozitif bölge içine sıfırdan taşındığında bildirimleri kaynağı dışarıdan meşgul olduğundan bir zamanlayıcı gönderilir.  
  
 Bu yöntemle bildirimleri yalnızca bir ilkeye sahip zamanlayıcılar gönderilen burada değeri `MinConcurrency` ilke anahtarı değerine eşit `MaxConcurrency` ilke anahtarı. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Oluşturulduğunda, bildirimler için niteleyen bir zamanlayıcı yalnızca atanan kaynaklara dışarıdan meşgul ya da boş olup olmadığını bildiren bir ilk bildirimleri kümesini alır.  
  
##  <a name="notifyresourcesexternallyidle"></a>Ischeduler::notifyresourcesexternallyıdle yöntemi  
 Donanım iş parçacıkları sanal işlemci kökleri dizideki kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` diğer zamanlayıcılar tarafından kullanılmıyor.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `ppVirtualProcessorRoots`  
 Bir dizi `IVirtualProcessorRoot` arabirimleri üzerinde diğer zamanlayıcılar hale boşta donanım iş parçacığı ile ilişkilendirilmiş.  
  
 `count`  
 Sayısı `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli donanım iş parçacığı aynı anda birden çok zamanlayıcılar atanması mümkündür. Bunun bir nedeni olmadığından, yeterli donanım iş parçacığı kaynakları paylaşma olmadan tüm zamanlayıcılar için minimum eşzamanlılık karşılamak için sistem üzerindeki olabilir. Başka bir olasılık sahibi olan Zamanlayıcı bunları devre dışı bırakılan bu donanım iş parçacığı üzerinde tüm sanal işlemci kökleri yapmamanız kullanmadığında kaynakları geçici olarak diğer zamanlayıcılar için atanmış olabilir.  
  
 Bir donanım iş parçacığı abonelik düzeyi abone iş parçacığı sayısı ile gösterilir ve bu donanım iş parçacığı ile ilişkili sanal işlemci kökleri etkinleştirilmelidir. Belirli bir Zamanlayıcının açısından bakıldığında, bir donanım iş parçacığı dış abonelik düzeyi diğer zamanlayıcılar katkıda abonelik bölümüdür. Bir donanım iş parçacığı için dış abonelik düzeyi önceki pozitif bir değer sıfırdan düştüğünde bildirimleri kaynağı dışarıdan meşgul olduğundan bir zamanlayıcı gönderilir.  
  
 Bu yöntemle bildirimleri yalnızca bir ilkeye sahip zamanlayıcılar gönderilen burada değeri `MinConcurrency` ilke anahtarı değerine eşit `MaxConcurrency` ilke anahtarı. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz: [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Oluşturulduğunda, bildirimler için niteleyen bir zamanlayıcı yalnızca atanan kaynaklara dışarıdan meşgul ya da boş olup olmadığını bildiren bir ilk bildirimleri kümesini alır.  
  
##  <a name="removevirtualprocessors"></a>Ischeduler::removevirtualprocessors yöntemi  
 Daha önce bu Zamanlayıcı için ayrılan sanal işlemci kökleri kaldırılmasını başlatır.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `ppVirtualProcessorRoots`  
 Bir dizi `IVirtualProcessorRoot` kaldırılacak sanal işlemci kökleri temsil eden arabirim.  
  
 `count`  
 Sayısı `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak Yöneticisi'ni çağırır `RemoveVirtualProcessors` sanal işlemci kökleri bir dizi bir zamanlayıcı geri almak için yöntem. Zamanlayıcı çağırmak için beklenen [kaldırmak](iexecutionresource-structure.md#remove) sanal işlemci kökleri ile işiniz bittiğinde her arabirimde yöntemi. Kullanmayan bir `IVirtualProcessorRoot` çağrılan sonra arabirim `Remove` yöntemini.  
  
 Parametre `ppVirtualProcessorRoots` işaret arabirimleri bir dizi. Kaldırılacak sanal işlemci kökleri kümesi arasında kökleri hiçbir zaman etkinleştirilmiş kullanmaya hemen döndürülen `Remove` yöntemi. Etkinleştirilmiş ve yürütme ya da iş ya da devre dışı bırakıldı ve ulaşması, iş için bekleyen kökleri zaman uyumsuz olarak döndürülmelidir. Zamanlayıcı, tüm çabayı sanal işlemci kök mümkün olan en kısa sürede kaldırmak için gerekir. Sanal işlemci kökleri kaldırılmasını geciktirme Zamanlayıcı içinde istenmeyen aşırı abonelik neden olabilir.  
  
##  <a name="statistics"></a>Ischeduler::Statistics yöntemi  
 Görev varış ve tamamlama hızları ve kuyruk uzunluğu değişikliği bir zamanlayıcı için ilgili bilgiler sağlar.  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pTaskCompletionRate`  
 Bu yöntem son çağrısından itibaren Zamanlayıcı tarafından tamamlanmamış görevler sayısı.  
  
 `pTaskArrivalRate`  
 Bu yöntem son çağrısından itibaren zamanlayıcıda gelmedi görevleri sayısı.  
  
 `pNumberOfTasksEnqueued`  
 Görevleri tüm Zamanlayıcı sıralardaki toplam sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için bir zamanlayıcı istatistikleri toplamak için kaynak yöneticisi tarafından çağrılır. Burada toplanan istatistikleri Zamanlayıcı için daha fazla kaynak atama uygun olduğunda ve ne zaman kaynakları çıkardığınız belirlemek için dinamik geri bildirim algoritmaları sürücü için kullanılır. Zamanlayıcı tarafından sağlanan değerler iyimser olabilir ve mutlaka geçerli sayısı doğru bir şekilde yansıtmak gerekmez.  
  
 Gibi şeyler hakkında geri bildirim, Zamanlayıcı ve Resource Manager ile kayıtlı diğer zamanlayıcılar arasında kaynak dengelemeye yönelik belirlemek için görev varış kullanmak üzere Kaynak Yöneticisi'ni istiyorsanız bu yöntemi uygulaması gerekir. İstatistikleri toplamak değil seçerseniz, ilke anahtarı ayarlayabilirsiniz `DynamicProgressFeedback` değerine `DynamicProgressFeedbackDisabled` , scheduler'ın ilke ve kaynak yöneticisi bu yöntem, Zamanlayıcı üzerinde çağırmayacaktır.  
  
 İstatistiksel bilgileri olmaması durumunda, kaynak ayırma ve geçiş kararlar almak için donanım iş parçacığı abonelik düzeylerini Kaynak Yöneticisi'ni kullanır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy sınıfı](schedulerpolicy-class.md)   
 [Iexecutioncontext yapısı](iexecutioncontext-structure.md)   
 [Ithreadproxy yapısı](ithreadproxy-structure.md)   
 [Ivirtualprocessorroot yapısı](ivirtualprocessorroot-structure.md)   
 [Iresourcemanager yapısı](iresourcemanager-structure.md)
