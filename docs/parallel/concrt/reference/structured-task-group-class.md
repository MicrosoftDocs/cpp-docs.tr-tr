---
title: structured_task_group sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs:
- C++
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9e87ebd4523b5211c94955b5bec7905ed848946
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161690"
---
# <a name="structuredtaskgroup-class"></a>structured_task_group Sınıfı

`structured_task_group` Sınıfı, yüksek düzeyde yapılandırılmış bir paralel iş koleksiyonunu temsil eder. Tek tek Paralel Görevler sıraya alabilirsiniz bir `structured_task_group` kullanarak `task_handle` yürütme başlamadığınız herhangi bir görevi iptal edilecek yürütme bitirmeden önce görev grubunu iptal nesneleri veya tamamlanmalarını bekleyin.

## <a name="syntax"></a>Sözdizimi

```
class structured_task_group;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[structured_task_group](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `structured_task_group` nesne.|
|[~ structured_task_group yok Edicisi](#dtor)|Yok eder bir `structured_task_group` nesne. Çağırın ya da beklenir `wait` veya `run_and_wait` yok Edicisi yürütmeden önce nesnesi üzerinde yöntemi yok Edicisi yürütme sürece sonucu olarak yığın bir özel durum nedeniyle geriye doğru izleme.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[İptal](#cancel)|Alt ağaç bu görev grubu kökü çalışmanın iptal edilmesi girişimi bir en iyi hale getirir. Her görev, görev grubuna zamanlanmış geçişli mümkünse iptal.|
|[is_canceling](#is_canceling)|Çağıranın olup olmadığını görev grubunu iptal ortasında şu anda olduğunu bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `structured_task_group` nesne (kesinlikle niteleyen gibi döndürmek için bu yöntem olsa da **true**). Bu durum olabilir, `structured_task_group` nesne satır içi yürütme ve başka bir görev grubu oluşturan iş ağacında iptal edildi. Bu nerede gibi durumlarda çalışma zamanı iptal bu akar vaktinden belirleyebilirsiniz `structured_task_group` nesnesi **true** da döndürülür.|
|[Çalıştırma](#run)|Fazla Yüklendi. Üzerinde bir görevi zamanlar `structured_task_group` nesne. Çağıranın ömrünü yönetir `task_handle` geçirilen nesne `_Task_handle` parametresi. Parametre sürüm `_Placement` görevi bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.|
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Satır içi arama bağlamda Yardımı ile çalışması için bir görevi zamanlar `structured_task_group` tam iptal desteği için nesne. Varsa bir `task_handle` nesnesi bir parametre olarak geçirilir `run_and_wait`, ömrünü yönetmek için çağıran sorumludur `task_handle` nesne. İşlevi, ardından tüm çalıştığı bekler `structured_task_group` nesne tamamlandı veya iptal edildi.|
|[bekleme](#wait)|Tüm çalıştığı bekler `structured_task_group` tamamlandıktan veya iptal edildi.|

## <a name="remarks"></a>Açıklamalar

Bir dizi kullanıma ciddi kısıtlamalardır vardır bir `structured_task_group` performans kazanmak için nesne:

- Tek bir `structured_task_group` nesne birden çok iş parçacığı tarafından kullanılamaz. Tüm işlemler bir `structured_task_group` nesne nesneyi oluşturan iş parçacığı tarafından gerçekleştirilmesi gerekir. Bu kural için iki özel üye işlevleri olan `cancel` ve `is_canceling`. Nesne bir lambda ifadesinin yakalama listesinde olmayabilir ve görev iptal işlemlerden biri, kullanmadığınız sürece bir görev içinde kullanılabilir.

- Zamanlanan tüm görevlerin bir `structured_task_group` nesne kullanımının zamanlanır `task_handle` nesneleri, açıkça ömrünü yönetmeniz gerekir.

- Birden çok grup yalnızca kesinlikle iç içe geçmiş bir sırada kullanılabilir. İki `structured_task_group` nesneleri bildirildiğinde, önce dışında herhangi bir yöntem (iç bir) bildirilen ikincisi yok etmek gerekir `cancel` veya `is_canceling` Birincisi çağrılır (dış bir). Bu durum, yalnızca birden çok bildirme her iki durumda da korumadıkça `structured_task_group` nesneleri için sıraya alındı bir görevin durum yanı sıra, aynı veya işlevsel olarak iç içe kapsam içinde `structured_task_group` aracılığıyla `run` veya `run_and_wait` yöntemleri.

- Genel aksine `task_group` sınıfı, tüm durumlarda `structured_task_group` son sınıfı bulunur. Sıraya alınan görevler grubuna ve bunları tamamlamak beklenen sonra aynı grup yeniden kullanamazsınız.

Daha fazla bilgi için [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`structured_task_group`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="cancel"></a> İptal

Alt ağaç bu görev grubu kökü çalışmanın iptal edilmesi girişimi bir en iyi hale getirir. Her görev, görev grubuna zamanlanmış geçişli mümkünse iptal.

```
void cancel();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="is_canceling"></a> is_canceling

Çağıranın olup olmadığını görev grubunu iptal ortasında şu anda olduğunu bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `structured_task_group` nesne (kesinlikle niteleyen gibi döndürmek için bu yöntem olsa da **true**). Bu durum olabilir, `structured_task_group` nesne satır içi yürütme ve başka bir görev grubu oluşturan iş ağacında iptal edildi. Bu nerede gibi durumlarda çalışma zamanı iptal bu akar vaktinden belirleyebilirsiniz `structured_task_group` nesnesi **true** da döndürülür.

```
bool is_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

Bir gösterge olup `structured_task_group` nesne ortasında iptal (veya kısa süre içinde olması sağlanır).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="run"></a> Çalıştırma

Üzerinde bir görevi zamanlar `structured_task_group` nesne. Çağıranın ömrünü yönetir `task_handle` geçirilen nesne `_Task_handle` parametresi. Parametre sürüm `_Placement` görevi bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.

```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Görev tanıtıcısını gövdesi yürütme için çağrılacak işlev nesnesinin türü.

*_Task_handle*<br/>
Zamanlanmış iş için bir tanıtıcı. Çağıranın bu nesnenin ömrünü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `wait` veya `run_and_wait` bu yöntemi çağrıldıktan `structured_task_group` nesne.

*Y_erleştirme*<br/>
Görevi nerede temsil ettiği konumuna yönelik bir başvuru `_Task_handle` parametre yürütün.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, bu yönteme geçirin iş işlevi bir kopyasını oluşturur. Bu yönteme geçirin bir işlev nesnesi içinde gerçekleşen durumu değişiklikleri, bu işlev nesnesi kopyanızda görünmez.

Varsa `structured_task_group` destructs yığını bir özel durumdan geriye doğru izleme sonucu olarak, gerekmez çağrı olarak yapıldığını garanti `wait` veya `run_and_wait` yöntemi. Bu durumda, yok edici uygun şekilde iptal edip tarafından temsil edilen bir görevi beklerken `_Task_handle` tamamlamak için parametre.

Oluşturur bir [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) görev işleme özel durum tarafından verilen `_Task_handle` parametresi zaten zamanlandı bir görev grubu nesnesi üzerine `run` yöntemi ve hiçbir çağrı göndermelisiniz meydana geldi ya da `wait` veya `run_and_wait` bu görev grubunda yöntemi.

##  <a name="run_and_wait"></a> run_and_wait

Satır içi arama bağlamda Yardımı ile çalışması için bir görevi zamanlar `structured_task_group` tam iptal desteği için nesne. Varsa bir `task_handle` nesnesi bir parametre olarak geçirilir `run_and_wait`, ömrünü yönetmek için çağıran sorumludur `task_handle` nesne. İşlevi, ardından tüm çalıştığı bekler `structured_task_group` nesne tamamlandı veya iptal edildi.

```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Görev yürütme için çağrılacak işlev nesnesinin türü.

*_Task_handle*<br/>
Satır içi arama bağlamda çalıştırılacak görev için bir tanıtıcı. Çağıranın bu nesnenin ömrünü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `run_and_wait` yöntemi yürütme biter.

*_Func*<br/>
İş gövdesi çağırmak için çağrılacak işlev. Bu bir lambda veya işlev çağrısı işleci imzalı sürümünü destekleyen başka bir nesne olabilir `void operator()()`.

### <a name="return-value"></a>Dönüş Değeri

Bir gösterge olup bekleme memnun ettiyse veya görev grubu, bir açık İptal işlemi veya görevleri birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazlası için zamanlanmış görevleri Not `structured_task_group` nesne satır içi arama bağlamda yürütme.

Bir veya daha fazlası için zamanlanmış görevlerin `structured_task_group` nesnesi, bir özel durum oluşturursa, çalışma zamanı kendi seçtiğiniz bir tür özel durumu seçin ve çağrı dışına yayan `run_and_wait` yöntemi.

Bu işlev döndürdükten sonra `structured_task_group` nesne son bir durumu olarak kabul edilir ve kullanılmamalıdır. Bu kullanımı sonra Not `run_and_wait` yöntemi döndürür tanımsız davranışlara neden olur.

Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için olan uyumluluğunu doğrulamıştır olması veya `wait` yöntemi yok edicisinde önce `structured_task_group` yürütür.

##  <a name="ctor"></a> structured_task_group

Yeni bir oluşturur `structured_task_group` nesne.

```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>Parametreler

*_CancellationToken*<br/>
Bu yapılandırılmış görev grubu ile ilişkilendirilecek iptal belirteci. Belirteç iptal edildiğinde, yapılandırılmış görev grubunu iptal edilir.

### <a name="remarks"></a>Açıklamalar

İptali belirteci alan oluşturucu bir `structured_task_group` , iptal edilemez belirteçle ilişkili kaynak iptal edildiğinde. Bir açık bir iptal belirteci sağlayan örtük bir iptal belirteci yok ya da farklı bir belirteç ile bir üst gruptan katılan bu yapılandırılmış görev grubunun yalıtır.

##  <a name="dtor"></a> ~ structured_task_group

Yok eder bir `structured_task_group` nesne. Çağırın ya da beklenir `wait` veya `run_and_wait` yok Edicisi yürütmeden önce nesnesi üzerinde yöntemi yok Edicisi yürütme sürece sonucu olarak yığın bir özel durum nedeniyle geriye doğru izleme.

```
~structured_task_group();
```

### <a name="remarks"></a>Açıklamalar

Yok edici normal yürütmenin (bir özel durum nedeniyle yığını geriye doğru izleme gibi değil) ve birinin diğerinden sonucu olarak çalışıyorsa `wait` ya da `run_and_wait` yöntemi çağrılır, yok edici oluşturabilecek bir [missing_wait](missing-wait-class.md) özel durum.

##  <a name="wait"></a> bekleme

Tüm çalıştığı bekler `structured_task_group` tamamlandıktan veya iptal edildi.

```
task_group_status wait();
```

### <a name="return-value"></a>Dönüş Değeri

Bir gösterge olup bekleme memnun ettiyse veya görev grubu, bir açık İptal işlemi veya görevleri birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazlası için zamanlanmış görevleri Not `structured_task_group` nesne satır içi arama bağlamda yürütme.

Bir veya daha fazlası için zamanlanmış görevlerin `structured_task_group` nesnesi, bir özel durum oluşturursa, çalışma zamanı kendi seçtiğiniz bir tür özel durumu seçin ve çağrı dışına yayan `wait` yöntemi.

Bu işlev döndürdükten sonra `structured_task_group` nesne son bir durumu olarak kabul edilir ve kullanılmamalıdır. Bu kullanımı sonra Not `wait` yöntemi döndürür tanımsız davranışlara neden olur.

Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için olan uyumluluğunu doğrulamıştır olması veya `run_and_wait` yöntemi yok edicisinde önce `structured_task_group` yürütür.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_group sınıfı](task-group-class.md)<br/>
[task_handle Sınıfı](task-handle-class.md)
