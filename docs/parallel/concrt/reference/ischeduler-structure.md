---
description: 'Daha fazla bilgi edinin: IScheduler Yapısı'
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
ms.openlocfilehash: 3a99ea5041c9d1146bb2247c1dcac54ff2fb7cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334467"
---
# <a name="ischeduler-structure"></a>IScheduler Yapısı

Bir iş Scheduler soyutlaması için arabirim. Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, iş zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır.

## <a name="syntax"></a>Syntax

```cpp
struct IScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Isecheduler:: Addvirtualiþlemcileri](#addvirtualprocessors)|Kullanımı için bir sanal işlemci kökleri kümesi içeren bir Zamanlayıcı sağlar. Her `IVirtualProcessorRoot` arabirim Zamanlayıcı adına iş gerçekleştirebilen tek bir iş parçacığını yürütme hakkını temsil eder.|
|[IScheduler:: GetId](#getid)|Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.|
|[IComparer:: GetPolicy](#getpolicy)|Zamanlayıcı ilkesinin bir kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).|
|[IScheduler:: Notifyresourcesexüçlü Allybusy](#notifyresourcesexternallybusy)|Bu Scheduler 'da dizideki sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının `ppVirtualProcessorRoots` artık diğer zamanlayıcılar tarafından kullanılmakta olduğunu bildirir.|
|[IScheduler:: Notifyresourcesexüçlü Allyıdle](#notifyresourcesexternallyidle)|Bu zamanlayıcıya dizideki sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının `ppVirtualProcessorRoots` diğer zamanlayıcılar tarafından kullanılmadığını bildirir.|
|[IScheduler:: Removevirtualişlemcilerle](#removevirtualprocessors)|Daha önce Bu Scheduler 'a ayrılmış olan sanal işlemci köklerinin kaldırılmasını başlatır.|
|[IScheduler:: STATISTICS](#statistics)|Görev varışı ve tamamlanma ücretleri ile ilgili bilgiler ve Zamanlayıcı için sıra uzunluğu değişikliği sağlar.|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi ile iletişim kuran özel bir Zamanlayıcı uygulamadıysanız, arabirimin bir uygulamasını sağlamanız gerekir `IScheduler` . Bu arabirim, bir Zamanlayıcı ve Kaynak Yöneticisi arasındaki iki yönlü bir kanalın bir bitişidir. Diğer son, `IResourceManager` `ISchedulerProxy` Kaynak Yöneticisi tarafından uygulanan ve arabirimleri tarafından temsil edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IScheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="ischeduleraddvirtualprocessors-method"></a><a name="addvirtualprocessors"></a> Isecheduler:: Addvirtualiþlemciler yöntemi

Kullanımı için bir sanal işlemci kökleri kümesi içeren bir Zamanlayıcı sağlar. Her `IVirtualProcessorRoot` arabirim Zamanlayıcı adına iş gerçekleştirebilen tek bir iş parçacığını yürütme hakkını temsil eder.

```cpp
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*Ppvirtualprocessorkökleri*<br/>
`IVirtualProcessorRoot`Scheduler 'a eklenmekte olan sanal işlemci köklerini temsil eden bir arabirim dizisi.

*biriktirme*<br/>
`IVirtualProcessorRoot`Dizideki arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, `AddVirtualProcessor` bir Scheduler 'a ilk sanal işlemci kökleri kümesi vermek için yöntemini çağırır. Ayrıca, zamanlayıcılar arasında kaynakları yeniden dengeleyip Scheduler 'a sanal işlemci kökleri eklemek için yöntemini çağırabilir.

## <a name="ischedulergetid-method"></a><a name="getid"></a> IComparer:: GetID Yöntemi

Zamanlayıcı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[](concurrency-namespace-functions.md) `IScheduler` Arabirimi, kaynak yöneticisi tarafından sağlanan yöntemlere parametre olarak kullanmadan önce, arabirimi uygulayan nesne için benzersiz bir tanımlayıcı elde etmek üzere GetSchedulerId işlevini kullanmanız gerekir. İşlev çağrıldığında aynı tanımlayıcıyı döndürmeli `GetId` .

Farklı bir kaynaktan alınan bir tanımlayıcı, tanımsız davranışa neden olabilir.

## <a name="ischedulergetpolicy-method"></a><a name="getpolicy"></a> IComparer:: GetPolicy yöntemi

Zamanlayıcı ilkesinin bir kopyasını döndürür. Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı ilkesinin bir kopyası.

## <a name="ischedulernotifyresourcesexternallybusy-method"></a><a name="notifyresourcesexternallybusy"></a> IScheduler:: Notifyresourcesexüçlü Allybusy yöntemi

Bu Scheduler 'da dizideki sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının `ppVirtualProcessorRoots` artık diğer zamanlayıcılar tarafından kullanılmakta olduğunu bildirir.

```cpp
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*Ppvirtualprocessorkökleri*<br/>
`IVirtualProcessorRoot`Diğer zamanlayıcılar meşgul hale geldiği donanım iş parçacıklarıyla ilişkili bir arabirim dizisi.

*biriktirme*<br/>
`IVirtualProcessorRoot`Dizideki arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Belirli bir donanım iş parçacığının aynı anda birden çok zamanlayıcılar atanmak mümkündür. Bunun bir nedeni, kaynak paylaşmadan tüm zamanlayıcılar için en düşük eşzamanlılık gereksinimini karşılamak üzere sistemde yeterli donanım iş parçacığı olmaması olabilir. Diğer bir olasılık ise, sahip olan Scheduler tarafından kullanılmayan Zamanlayıcı, bu donanım iş parçacığında devre dışı bırakılan tüm sanal işlemci köklerine göre geçici olarak diğer zamanlayıcılar atanmış olur.

Bir donanım iş parçacığının abonelik düzeyi, abone olunan iş parçacıklarının sayısıyla ve bu donanım iş parçacığıyla ilişkili etkinleştirilmiş sanal işlemci köklerine göre gösterilir. Belirli bir zamanlayıcının görünüm noktasından, bir donanım iş parçacığının dış abonelik düzeyi diğer zamanlayıcılar katkıda bulunan aboneliğin bölümüdür. Bir donanım iş parçacığı için dış abonelik düzeyi sıfırdan pozitif bölgeye geçerse, kaynakların dışarıdan meşgul olduğu bildirimler bir Scheduler 'a gönderilir.

Bu yöntem aracılığıyla yapılan bildirimler yalnızca ilke anahtarı değerinin ilke anahtarı için değere eşit olduğu bir ilkeye sahip zamanlayıcılar 'e gönderilir `MinConcurrency` `MaxConcurrency` . Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).

Bildirimleri niteleyen bir zamanlayıcı, oluşturulduğunda ilk bildirim kümesini alır, bu, yeni atanan kaynakların dışarıdan meşgul veya boşta olduğunu bilgilendirdi.

## <a name="ischedulernotifyresourcesexternallyidle-method"></a><a name="notifyresourcesexternallyidle"></a> IComparer:: Notifyresourcesexdeallyıdle yöntemi

Bu zamanlayıcıya dizideki sanal işlemci kökleri kümesi tarafından temsil edilen donanım iş parçacıklarının `ppVirtualProcessorRoots` diğer zamanlayıcılar tarafından kullanılmadığını bildirir.

```cpp
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*Ppvirtualprocessorkökleri*<br/>
`IVirtualProcessorRoot`Diğer zamanlayıcılar boşta hale geldiği donanım iş parçacıklarıyla ilişkili bir arabirim dizisi.

*biriktirme*<br/>
`IVirtualProcessorRoot`Dizideki arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Belirli bir donanım iş parçacığının aynı anda birden çok zamanlayıcılar atanmak mümkündür. Bunun bir nedeni, kaynak paylaşmadan tüm zamanlayıcılar için en düşük eşzamanlılık gereksinimini karşılamak üzere sistemde yeterli donanım iş parçacığı olmaması olabilir. Diğer bir olasılık ise, sahip olan Scheduler tarafından kullanılmayan Zamanlayıcı, bu donanım iş parçacığında devre dışı bırakılan tüm sanal işlemci köklerine göre geçici olarak diğer zamanlayıcılar atanmış olur.

Bir donanım iş parçacığının abonelik düzeyi, abone olunan iş parçacıklarının sayısıyla ve bu donanım iş parçacığıyla ilişkili etkinleştirilmiş sanal işlemci köklerine göre gösterilir. Belirli bir zamanlayıcının görünüm noktasından, bir donanım iş parçacığının dış abonelik düzeyi diğer zamanlayıcılar katkıda bulunan aboneliğin bölümüdür. Bir donanım iş parçacığı için dış abonelik düzeyi önceki bir pozitif değerden sıfıra düşerse, kaynakların dışarıdan meşgul olduğu bildirimler bir Scheduler 'a gönderilir.

Bu yöntem aracılığıyla yapılan bildirimler yalnızca ilke anahtarı değerinin ilke anahtarı için değere eşit olduğu bir ilkeye sahip zamanlayıcılar 'e gönderilir `MinConcurrency` `MaxConcurrency` . Zamanlayıcı ilkeleri hakkında daha fazla bilgi için bkz. [SchedulerPolicy](schedulerpolicy-class.md).

Bildirimleri niteleyen bir zamanlayıcı, oluşturulduğunda ilk bildirim kümesini alır, bu, yeni atanan kaynakların dışarıdan meşgul veya boşta olduğunu bilgilendirdi.

## <a name="ischedulerremovevirtualprocessors-method"></a><a name="removevirtualprocessors"></a> IComparer:: Removevirtualişlemcilerle yöntemi

Daha önce Bu Scheduler 'a ayrılmış olan sanal işlemci köklerinin kaldırılmasını başlatır.

```cpp
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parametreler

*Ppvirtualprocessorkökleri*<br/>
`IVirtualProcessorRoot`Kaldırılacak sanal işlemci köklerini temsil eden bir arabirim dizisi.

*biriktirme*<br/>
`IVirtualProcessorRoot`Dizideki arabirimlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, `RemoveVirtualProcessors` bir Scheduler 'dan bir dizi sanal işlemci kökü geri alma yöntemini çağırır. Zamanlayıcı, sanal işlemci köklerinde tamamlandığında her arabirimdeki [Remove](iexecutionresource-structure.md#remove) metodunu çağırmalıdır. `IVirtualProcessorRoot`Üzerinde yöntemini çağırdıktan sonra bir arabirim kullanmayın `Remove` .

Parametresi `ppVirtualProcessorRoots` bir arabirim dizisine işaret eder. Kaldırılacak sanal işlemci köklerinin kümesi arasında, köklerin hiçbir şekilde etkinleştirilmemesi, yöntemi kullanılarak hemen döndürülemez `Remove` . Etkinleştirilen ve işleri yürüten veya devre dışı bırakılan ve iş için bekleyen, zaman uyumsuz olarak döndürülmüş olan köklerdir. Zamanlayıcı, sanal işlemci kökünü mümkün olduğunca hızlı bir şekilde kaldırmayı denemelidir. Sanal işlemci köklerinin kaldırılması geciktirilmesi Zamanlayıcı içinde istenmeden fazla aboneliğe neden olabilir.

## <a name="ischedulerstatistics-method"></a><a name="statistics"></a> IComparer:: Statistics yöntemi

Görev varışı ve tamamlanma ücretleri ile ilgili bilgiler ve Zamanlayıcı için sıra uzunluğu değişikliği sağlar.

```cpp
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>Parametreler

*pTaskCompletionRate*<br/>
Bu yönteme son çağrıdan bu yana Zamanlayıcı tarafından tamamlanmış görevlerin sayısı.

*pTaskArrivalRate*<br/>
Bu yönteme son çağrıdan bu yana Scheduler 'da ulaşan görevlerin sayısı.

*Pnumberoftasksenkuyruğa alındı*<br/>
Tüm Zamanlayıcı sıralarındaki toplam görev sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Scheduler istatistiklerini toplamak için Kaynak Yöneticisi tarafından çağrılır. Burada toplanan istatistikler, Scheduler 'a daha fazla kaynak atamak için uygun olduğunda ve kaynakların ne zaman ele kullanılmayacağını öğrenmek için dinamik geri bildirim algoritmalarını yönlendirmek üzere kullanılacaktır. Zamanlayıcı tarafından belirtilen değerler iyimser olabilir ve geçerli sayıyı doğru bir şekilde yansıtması gerekmez.

Kaynak Yöneticisi, Scheduler ve Kaynak Yöneticisi kayıtlı diğer zamanlayıcılar arasında kaynağın nasıl dengelenmesi gerektiğini tespit etmek üzere görev varışı hakkında geri bildirim kullanmasını istiyorsanız bu yöntemi uygulamalısınız. İstatistik toplamamalıdır seçeneğini belirlerseniz, Zamanlayıcı ilkenizde ilke anahtarını bir değere ayarlayabilirsiniz `DynamicProgressFeedback` `DynamicProgressFeedbackDisabled` ve Kaynak Yöneticisi Scheduler 'da bu yöntemi çağırmaz.

İstatistiksel bilgiler yokluğunda Kaynak Yöneticisi, kaynak ayırma ve geçiş kararları almak için donanım iş parçacığı abonelik düzeylerini kullanacaktır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)<br/>
[IExecutionContext Yapısı](iexecutioncontext-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
