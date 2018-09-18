---
title: Ischeduler yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31623b7315d05ac2a40ee9fae7d9103ca6b0e6c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017891"
---
# <a name="ischeduler-structure"></a>IScheduler Yapısı
Bir arabirim için bir iş Zamanlayıcı bir soyutlamasıdır. Eşzamanlılık çalışma zamanının Resource Manager, bu arabirim iş zamanlayıcılar ile iletişim kurmak için kullanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ischeduler::addvirtualprocessors](#addvirtualprocessors)|Bir zamanlayıcı bir sanal işlemci kökü ile kullanımına sunmaktadır. Her `IVirtualProcessorRoot` arabirimi iş Zamanlayıcı adına gerçekleştiren tek bir iş parçacığı yürütme hakkı temsil eder.|  
|[Ischeduler::GetID](#getid)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|  
|[Ischeduler::getpolicy](#getpolicy)|Scheduler'ın ilke bir kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).|  
|[Ischeduler::notifyresourcesexternallybusy](#notifyresourcesexternallybusy)|Donanım iş parçacıklarının dizideki sanal işlemci kök kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` artık diğer zamanlayıcılar tarafından kullanılıyor.|  
|[Ischeduler::notifyresourcesexternallyıdle](#notifyresourcesexternallyidle)|Donanım iş parçacıklarının dizideki sanal işlemci kök kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` diğer zamanlayıcılar tarafından kullanılmıyor.|  
|[Ischeduler::removevirtualprocessors](#removevirtualprocessors)|Daha önce bu Zamanlayıcı için ayrılan sanal işlemci kökü kaldırılmasını başlatır.|  
|[Ischeduler::Statistics](#statistics)|Görev alma ve tamamlanma hızları ve kuyruk uzunluğu değişikliği bir zamanlayıcı için ilgili bilgiler sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Resource Manager ile iletişim kuran özel bir zamanlayıcı uyguluyorsanız, bir uygulamasını sağlamalıdır `IScheduler` arabirimi. Bu arabirim bir Zamanlayıcı ve Resource Manager arasındaki iletişim çift yönlü bir kanalı sonudur. Diğer uç tarafından temsil edilen `IResourceManager` ve `ISchedulerProxy` kaynak yöneticisi tarafından uygulanan arabirimler.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IScheduler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="addvirtualprocessors"></a>  Ischeduler::addvirtualprocessors yöntemi  
 Bir zamanlayıcı bir sanal işlemci kökü ile kullanımına sunmaktadır. Her `IVirtualProcessorRoot` arabirimi iş Zamanlayıcı adına gerçekleştiren tek bir iş parçacığı yürütme hakkı temsil eder.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*ppVirtualProcessorRoots*<br/>
Bir dizi `IVirtualProcessorRoot` arabirimleri temsil eden sanal işlemci kökleri Zamanlayıcı eklenen.  
  
*Sayısı*<br/>
Sayısını `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak Yöneticisi çağırır `AddVirtualProcessor` sanal işlemci kökü başlangıç kümesi için bir zamanlayıcı vermek için yöntemi. Ayrıca, bu kaynakları zamanlayıcılar arasında yeniden dengeler sırasında sanal işlemci kökü Zamanlayıcı eklemek için yöntemi de çağırabilirsiniz.  
  
##  <a name="getid"></a>  Ischeduler::GetID metodu  
 Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı benzersiz tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmanız gereken [Getschedulerıd](concurrency-namespace-functions.md) uygulayan nesne için benzersiz bir tanımlayıcı elde etmek için işlevi `IScheduler` arabirimi arabirim yöntemleri için parametre olarak kullanmadan önce kaynak yöneticisi tarafından sağlanan. Aynı tanımlayıcıyı döndürmek için beklenen zaman `GetId` işlevi çağrılır.  
  
 Farklı bir kaynaktan gelen bir tanımlayıcının tanımsız davranışlara neden.  
  
##  <a name="getpolicy"></a>  Ischeduler::getpolicy metodu  
 Scheduler'ın ilke bir kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Scheduler'ın ilke bir kopyası.  
  
##  <a name="notifyresourcesexternallybusy"></a>  Ischeduler::notifyresourcesexternallybusy yöntemi  
 Donanım iş parçacıklarının dizideki sanal işlemci kök kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` artık diğer zamanlayıcılar tarafından kullanılıyor.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*ppVirtualProcessorRoots*<br/>
Bir dizi `IVirtualProcessorRoot` donanım iş parçacığı üzerinde diğer zamanlayıcılar hale meşgul ilişkili arabirimi.  
  
*Sayısı*<br/>
Sayısını `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli donanım iş parçacığı aynı anda birden çok zamanlayıcılarına atanması mümkündür. Bunun bir nedeni, yok, yeterli donanım iş parçacıklarının kaynakları paylaşma olmadan tüm zamanlayıcılar için en düşük eşzamanlılık karşılamak için sistem üzerindeki olabilir. Sahip olan bir zamanlayıcı bunları devre dışı bırakılan bu donanım iş parçacığı üzerinde tüm sanal işlemci kökü ile kullanmadığında kaynakları geçici olarak diğer zamanlayıcılarına atanan başka bir olasılıktır.  
  
 Abonelik düzeyinde donanım iş parçacığı tarafından abone olunmuş iş parçacığı sayısı gösterilir ve bu donanım iş parçacığıyla ilişkilendirilmiş sanal işlemci kökü etkinleştirildi. Belirli bir Zamanlayıcının açısından bakıldığında, donanım iş parçacığı dış abonelik düzeyinde başka zamanlayıcılar katkıda abonelik bölümüdür. Donanım iş parçacığı için dış abonelik düzeyinde sıfırdan pozitif bölge içinde hareket ettiğinde kaynakların dışarıdan meşgul olduğunu bildirimler için bir zamanlayıcı gönderilir.  
  
 Bu yöntem yoluyla bildirim yalnızca bir ilkeye sahip zamanlayıcılarına gönderilen burada değeri `MinConcurrency` ilke anahtarı değerine eşit `MaxConcurrency` ilke anahtarı. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Oluşturulduğunda, bildirimler için uygun bir zamanlayıcı yalnızca atanan kaynakları harici meşgul ya da boş olup olmadığını bildiren ilk bildirimleri kümesini alır.  
  
##  <a name="notifyresourcesexternallyidle"></a>  Ischeduler::notifyresourcesexternallyıdle yöntemi  
 Donanım iş parçacıklarının dizideki sanal işlemci kök kümesi tarafından temsil edilen Bu zamanlayıcı bildirir `ppVirtualProcessorRoots` diğer zamanlayıcılar tarafından kullanılmıyor.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*ppVirtualProcessorRoots*<br/>
Bir dizi `IVirtualProcessorRoot` donanım iş parçacığı üzerinde diğer zamanlayıcılar hale boşta ilişkili arabirimi.  
  
*Sayısı*<br/>
Sayısını `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli donanım iş parçacığı aynı anda birden çok zamanlayıcılarına atanması mümkündür. Bunun bir nedeni, yok, yeterli donanım iş parçacıklarının kaynakları paylaşma olmadan tüm zamanlayıcılar için en düşük eşzamanlılık karşılamak için sistem üzerindeki olabilir. Sahip olan bir zamanlayıcı bunları devre dışı bırakılan bu donanım iş parçacığı üzerinde tüm sanal işlemci kökü ile kullanmadığında kaynakları geçici olarak diğer zamanlayıcılarına atanan başka bir olasılıktır.  
  
 Abonelik düzeyinde donanım iş parçacığı tarafından abone olunmuş iş parçacığı sayısı gösterilir ve bu donanım iş parçacığıyla ilişkilendirilmiş sanal işlemci kökü etkinleştirildi. Belirli bir Zamanlayıcının açısından bakıldığında, donanım iş parçacığı dış abonelik düzeyinde başka zamanlayıcılar katkıda abonelik bölümüdür. Dış abonelik düzeyinde bir donanım iş parçacığı için önceki bir pozitif değer sıfırdan düştüğünde kaynakların dışarıdan meşgul olduğunu bildirimler için bir zamanlayıcı gönderilir.  
  
 Bu yöntem yoluyla bildirim yalnızca bir ilkeye sahip zamanlayıcılarına gönderilen burada değeri `MinConcurrency` ilke anahtarı değerine eşit `MaxConcurrency` ilke anahtarı. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Oluşturulduğunda, bildirimler için uygun bir zamanlayıcı yalnızca atanan kaynakları harici meşgul ya da boş olup olmadığını bildiren ilk bildirimleri kümesini alır.  
  
##  <a name="removevirtualprocessors"></a>  Ischeduler::removevirtualprocessors yöntemi  
 Daha önce bu Zamanlayıcı için ayrılan sanal işlemci kökü kaldırılmasını başlatır.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*ppVirtualProcessorRoots*<br/>
Bir dizi `IVirtualProcessorRoot` kaldırılacak sanal işlemci kökü temsil eden arabirim.  
  
*Sayısı*<br/>
Sayısını `IVirtualProcessorRoot` dizideki arabirimleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak Yöneticisi çağırır `RemoveVirtualProcessors` bir sanal işlemci kök kümesine bir Zamanlayıcıdan geri almak için yöntemi. Zamanlayıcı çağırmak için beklenen [Kaldır](iexecutionresource-structure.md#remove) sanal işlemci kökü ile bittiğinde her arabirimde yöntemi. Kullanmak istemediğiniz bir `IVirtualProcessorRoot` , çağırdığınız sonra arabirim `Remove` yöntemini.  
  
 Parametre `ppVirtualProcessorRoots` işaret arabirimleri dizisi. Kaldırılacak sanal işlemci kökü kümesi arasında kökleri hiçbir etkinleştirilmiş hemen kullanarak döndürülebilir `Remove` yöntemi. Etkinleştirilmiş ve yürütme ya da iş veya devre dışı bırakıldı ve ulaşması, iş için bekleyen kökleri zaman uyumsuz olarak döndürülmelidir. Zamanlayıcı, tüm çabayı sanal işlemci kökü mümkün olan en kısa sürede kaldırmak için gerekir. Sanal işlemci kökü kaldırılmasını geciktirme Zamanlayıcı içindeki yanlışlıkla gecikmeyi neden olabilir.  
  
##  <a name="statistics"></a>  Ischeduler::Statistics yöntemi  
 Görev alma ve tamamlanma hızları ve kuyruk uzunluğu değişikliği bir zamanlayıcı için ilgili bilgiler sağlar.  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*pTaskCompletionRate*<br/>
Bu yöntem son çağrısından sonra Zamanlayıcı tarafından tamamlanan görev sayısı.  
  
*pTaskArrivalRate*<br/>
Bu yöntem son çağrısından sonra Zamanlayıcı'da gelmiş görev sayısı.  
  
*pNumberOfTasksEnqueued*<br/>
Görevler Zamanlayıcı tüm sıralardaki toplam sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından kaynak yöneticisi için bir zamanlayıcı istatistikleri toplamak için çağrılır. Burada toplanan istatistikleri Zamanlayıcı için diğer kaynakları atamak uygun olduğu zaman ve ne zaman kaynakları çıkardığınız belirlemek için dinamik geri bildirim algoritmaları desteklemek üzere kullanılır. Zamanlayıcı tarafından sağlanan değerleri iyimser olabilir ve mutlaka geçerli sayısını doğru şekilde yansıtmak izniniz yok.  
  
 Kaynak Yöneticisi scheduler ve Resource Manager ile kayıtlı diğer zamanlayıcılar arasında kaynak dengelemeye yönelik belirlemek için görev varış gibi şeyler hakkında geri bildirim kullanılacak istiyorsanız bu yöntemi uygulamalıdır. İstatistikleri toplamak isterseniz, ilke anahtarı ayarlayabilirsiniz `DynamicProgressFeedback` değerine `DynamicProgressFeedbackDisabled` İlkesi, scheduler'ın ve Kaynak Yöneticisi scheduler üzerinde bu yöntem çağırmayacaktır.  
  
 İstatistiksel bilgileri olmaması durumunda, Resource Manager kaynak ayırma ve geçiş kararları almak için donanım iş parçacığı abonelik düzeylerini kullanır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy sınıfı](schedulerpolicy-class.md)   
 [Iexecutioncontext yapısı](iexecutioncontext-structure.md)   
 [Ithreadproxy yapısı](ithreadproxy-structure.md)   
 [Ivirtualprocessorroot yapısı](ivirtualprocessorroot-structure.md)   
 [IResourceManager Yapısı](iresourcemanager-structure.md)
