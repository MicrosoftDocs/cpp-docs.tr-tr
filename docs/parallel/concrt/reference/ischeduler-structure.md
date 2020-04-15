---
title: IScheduler Yapısı
ms.date: 11/04/2016
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
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
ms.openlocfilehash: ccd82b5c5112bc322717f2b58d79d4c8f34f5bbd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368171"
---
# <a name="ischeduler-structure"></a>IScheduler Yapısı

Çalışma zamanlayıcısının soyutlama için bir arabirimi. Eşzamanlı Çalışma Zamanı Kaynak Yöneticisi, çalışma zamanlayıcılarıyla iletişim kurmak için bu arabirimi kullanır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|Kullanımı için sanal işlemci kökleri kümesi olan bir zamanlayıcı sağlar. Her `IVirtualProcessorRoot` arabirim, zamanlayıcı adına iş gerçekleştirebilecek tek bir iş parçacığı yürütme hakkını temsil eder.|
|[IScheduler::GetId](#getid)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[IScheduler::GetPolicy](#getpolicy)|Zamanlayıcının ilkesinin bir kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için [Bkz. SchedulerPolicy.](schedulerpolicy-class.md)|
|[IScheduler::NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Bu zamanlayıcıya, dizideki `ppVirtualProcessorRoots` sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının artık diğer zamanlayıcılar tarafından kullanıldığını belirtir.|
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Bu zamanlayıcıya, dizideki `ppVirtualProcessorRoots` sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının diğer zamanlayıcılar tarafından kullanılmadığını belirtir.|
|[IScheduler::VirtualProcessors kaldırma](#removevirtualprocessors)|Daha önce bu zamanlayıcıya ayrılmış olan sanal işlemci köklerinin kaldırılmasını başlatır.|
|[IScheduler::İstatistikler](#statistics)|Görev varış ve tamamlama oranları ve zamanlayıcı için sıra uzunluğu değişikliği ile ilgili bilgiler sağlar.|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi ile iletişim kuran özel bir zamanlayıcı uyguluyorsanız, `IScheduler` arabirimin uygulanmasını sağlamanız gerekir. Bu arabirim, zamanlayıcı ile Kaynak Yöneticisi arasındaki iki yönlü iletişim kanalının bir sonudur. Diğer uç, Kaynak Yöneticisi `IResourceManager` `ISchedulerProxy` tarafından uygulanan ve arayüzler tarafından temsil edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IScheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="ischeduleraddvirtualprocessors-method"></a><a name="addvirtualprocessors"></a>IScheduler::AddVirtualProcessors Yöntemi

Kullanımı için sanal işlemci kökleri kümesi olan bir zamanlayıcı sağlar. Her `IVirtualProcessorRoot` arabirim, zamanlayıcı adına iş gerçekleştirebilecek tek bir iş parçacığı yürütme hakkını temsil eder.

```cpp
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*ppVirtualProcessorRoots*<br/>
Zamanlayıcıya `IVirtualProcessorRoot` eklenen sanal işlemci köklerini temsil eden bir dizi arabirim.

*Sayısı*<br/>
Dizideki `IVirtualProcessorRoot` arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, bir `AddVirtualProcessor` zamanlayıcıya ilk sanal işlemci kökleri kümesini vermek için yöntemi çağırır. Ayrıca, zamanlayıcılar arasında kaynakları yeniden dengeler zamanlayıcıya sanal işlemci kökleri eklemek için yöntemi çağırabilir.

## <a name="ischedulergetid-method"></a><a name="getid"></a>IScheduler::GetId Yöntemi

Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi tarafından sağlanan yöntemlere parametre olarak arabirimi kullanmadan önce, `IScheduler` arabirimi uygulayan nesne için benzersiz bir tanımlayıcı elde etmek için [GetSchedulerId](concurrency-namespace-functions.md) işlevini kullanmanız gerekir. İşlev çağrıldığında aynı tanımlayıcıyı `GetId` döndürmeniz beklenir.

Farklı bir kaynaktan elde edilen bir tanımlayıcı tanımlanmamış davranışa neden olabilir.

## <a name="ischedulergetpolicy-method"></a><a name="getpolicy"></a>IScheduler::GetPolicy Yöntemi

Zamanlayıcının ilkesinin bir kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için [Bkz. SchedulerPolicy.](schedulerpolicy-class.md)

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcının politikasının bir kopyası.

## <a name="ischedulernotifyresourcesexternallybusy-method"></a><a name="notifyresourcesexternallybusy"></a>IScheduler::NotifyResourcesExternallyBusy Yöntemi

Bu zamanlayıcıya, dizideki `ppVirtualProcessorRoots` sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının artık diğer zamanlayıcılar tarafından kullanıldığını belirtir.

```cpp
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*ppVirtualProcessorRoots*<br/>
Diğer zamanlayıcıların meşgul olduğu donanım iş parçacıklarıyla ilişkili `IVirtualProcessorRoot` bir dizi arabirim.

*Sayısı*<br/>
Dizideki `IVirtualProcessorRoot` arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Belirli bir donanım iş parçacığının aynı anda birden çok zamanlayıcıya atanması mümkündür. Bunun bir nedeni, kaynakları paylaşmadan, tüm zamanlayıcılar için minimum eşzamanlılık karşılamak için sistemde yeterli donanım iş parçacığı olmaması olabilir. Başka bir olasılık, kaynakların, sahip olan zamanlayıcı bunları kullanmadığında, bu donanım iş parçacığı üzerindeki tüm sanal işlemci kökleri devre dışı bırakılarak geçici olarak diğer zamanlayıcılara atanmasıdır.

Bir donanım iş parçacığının abonelik düzeyi, abone olunan iş parçacığı sayısı ve bu donanım iş parçacığıyla ilişkili etkinleştirilen sanal işlemci kökleriyle gösterilir. Belirli bir zamanlayıcının bakış açısından, donanım iş parçacığının dış abonelik düzeyi, diğer zamanlayıcıların katkıda bulunan abonelik bölümüdür. Bir donanım iş parçacığının dış abonelik düzeyi sıfırdan pozitif bölgeye geçtiğinde, kaynakların dışarıdan meşgul olduğuna dair bildirimler zamanlayıcıya gönderilir.

Bu yöntem üzerinden yapılan bildirimler yalnızca `MinConcurrency` ilke anahtarının değerinin `MaxConcurrency` ilke anahtarının değerine eşit olduğu bir ilkesi olan zamanlayıcılara gönderilir. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için [Bkz. SchedulerPolicy.](schedulerpolicy-class.md)

Bildirimler için yeterli olan bir zamanlayıcı, oluşturulduğunda bir dizi ilk bildirim alır ve yalnızca atandığı kaynakların dışarıdan meşgul veya boşta olup olmadığını bildirir.

## <a name="ischedulernotifyresourcesexternallyidle-method"></a><a name="notifyresourcesexternallyidle"></a>IScheduler::NotifyResourcesExternallyIdle Yöntemi

Bu zamanlayıcıya, dizideki `ppVirtualProcessorRoots` sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının diğer zamanlayıcılar tarafından kullanılmadığını belirtir.

```cpp
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*ppVirtualProcessorRoots*<br/>
Diğer zamanlayıcıların boşta olduğu donanım iş parçacıklarıyla ilişkili `IVirtualProcessorRoot` arabirimler dizisi.

*Sayısı*<br/>
Dizideki `IVirtualProcessorRoot` arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Belirli bir donanım iş parçacığının aynı anda birden çok zamanlayıcıya atanması mümkündür. Bunun bir nedeni, kaynakları paylaşmadan, tüm zamanlayıcılar için minimum eşzamanlılık karşılamak için sistemde yeterli donanım iş parçacığı olmaması olabilir. Başka bir olasılık, kaynakların, sahip olan zamanlayıcı bunları kullanmadığında, bu donanım iş parçacığı üzerindeki tüm sanal işlemci kökleri devre dışı bırakılarak geçici olarak diğer zamanlayıcılara atanmasıdır.

Bir donanım iş parçacığının abonelik düzeyi, abone olunan iş parçacığı sayısı ve bu donanım iş parçacığıyla ilişkili etkinleştirilen sanal işlemci kökleriyle gösterilir. Belirli bir zamanlayıcının bakış açısından, donanım iş parçacığının dış abonelik düzeyi, diğer zamanlayıcıların katkıda bulunan abonelik bölümüdür. Bir donanım iş parçacığının dış abonelik düzeyi önceki pozitif değerden sıfıra düştüğünde, kaynakların dışarıdan meşgul olduğuna dair bildirimler zamanlayıcıya gönderilir.

Bu yöntem üzerinden yapılan bildirimler yalnızca `MinConcurrency` ilke anahtarının değerinin `MaxConcurrency` ilke anahtarının değerine eşit olduğu bir ilkesi olan zamanlayıcılara gönderilir. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için [Bkz. SchedulerPolicy.](schedulerpolicy-class.md)

Bildirimler için yeterli olan bir zamanlayıcı, oluşturulduğunda bir dizi ilk bildirim alır ve yalnızca atandığı kaynakların dışarıdan meşgul veya boşta olup olmadığını bildirir.

## <a name="ischedulerremovevirtualprocessors-method"></a><a name="removevirtualprocessors"></a>IScheduler::RemoveVirtualProcessors Yöntemi

Daha önce bu zamanlayıcıya ayrılmış olan sanal işlemci köklerinin kaldırılmasını başlatır.

```cpp
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*ppVirtualProcessorRoots*<br/>
Kaldırılacak `IVirtualProcessorRoot` sanal işlemci köklerini temsil eden arabirimler dizisi.

*Sayısı*<br/>
Dizideki `IVirtualProcessorRoot` arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, bir `RemoveVirtualProcessors` zamanlayıcıdan sanal işlemci kökleri kümesini geri almak için yöntemi çağırır. Zamanlayıcının, sanal işlemci kökleriyle yapıldığında her arabirimde [Kaldır](iexecutionresource-structure.md#remove) yöntemini çağırması beklenir. Yöntemi çağırdıktan `IVirtualProcessorRoot` `Remove` sonra arabirim kullanmayın.

Parametre `ppVirtualProcessorRoots` bir dizi arabirimi işaret eder. Kaldırılacak sanal işlemci kökleri kümesi arasında, kökler hiçbir zaman etkinleştirilmedi `Remove` yöntem kullanılarak hemen döndürülebilir. Etkinleştirilen ve çalışmayı yürüten veya devre dışı bırakılan ve çalışmanın gelmesini bekleyen kökler eşzamanlı olarak döndürülmelidir. Zamanlayıcı, sanal işlemci kökünü mümkün olan en kısa sürede kaldırmak için her türlü girişimi yapmalıdır. Sanal işlemci köklerinin kaldırılmasını geciktirmek zamanlayıcı içinde kasıtsız aşırı abonelik neden olabilir.

## <a name="ischedulerstatistics-method"></a><a name="statistics"></a>IScheduler::İstatistik Yöntemi

Görev varış ve tamamlama oranları ve zamanlayıcı için sıra uzunluğu değişikliği ile ilgili bilgiler sağlar.

```cpp
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>Parametreler

*pTaskCompletionRate*<br/>
Bu yönteme yapılan son çağrıdan bu yana zamanlayıcı tarafından tamamlanan görev sayısı.

*pTaskArrivalRate*<br/>
Bu yönteme yapılan son çağrıdan bu yana zamanlayıcıya gelen görev sayısı.

*pNumberOfTasksEnqueued*<br/>
Tüm zamanlayıcı kuyruklarında görev toplam sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir zamanlayıcı için istatistik toplamak için Kaynak Yöneticisi tarafından çağrılır. Burada toplanan istatistikler, zamanlayıcıya daha fazla kaynak atamanın ne zaman uygun olduğunu ve kaynakları ne zaman uzaklaştıracağını belirlemek için dinamik geri bildirim algoritmalarını kullanmak için kullanılır. Zamanlayıcı tarafından sağlanan değerler iyimser olabilir ve geçerli sayıyı doğru şekilde yansıtmak zorunda değildir.

Kaynak Yöneticisi'nin, kaynak zamanlamanız ile Kaynak Yöneticisi'ne kayıtlı diğer zamanlayıcılar arasında nasıl dengeleyiş olduğunu belirlemek için görev gelişi gibi şeylerle ilgili geri bildirimlerkullanmasını istiyorsanız, bu yöntemi uygulamanız gerekir. İstatistik toplamamayı seçerseniz, ilke anahtarını `DynamicProgressFeedback` zamanlayıcınızın ilkesindeki değere `DynamicProgressFeedbackDisabled` ayarlayabilirsiniz ve Kaynak Yöneticisi bu yöntemi zamanlayıcınızda çağırmaz.

İstatistiksel bilgi yokluğunda, Kaynak Yöneticisi kaynak ayırma ve geçiş kararları almak için donanım iş parçacığı abonelik düzeylerini kullanır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)<br/>
[IExecutionContext Yapısı](iexecutioncontext-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
