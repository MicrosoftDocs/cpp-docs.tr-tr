---
title: task_group Sınıfı
ms.date: 07/20/2018
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
helpviewer_keywords:
- task_group class
ms.openlocfilehash: 60c147f38ddc3936f47aea0cfd1ab1548b382441
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142560"
---
# <a name="task_group-class"></a>task_group Sınıfı

`task_group` sınıfı, beklemiş veya iptal edilebilir bir paralel çalışma koleksiyonunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class task_group;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_group](#ctor)|Fazla Yüklendi. Yeni bir `task_group` nesnesi oluşturur.|
|[~ task_group yok edici](#dtor)|`task_group` nesnesini yok eder. Bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesnedeki `wait` veya `run_and_wait` yöntemini çağırmanız beklenmektedir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[İptal](#cancel)|Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.|
|[is_canceling](#is_canceling)|Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yönteminin `task_group` nesnesi üzerinde çağrıldığı anlamına gelmez (Bu nedenle, bu yöntem `true`döndürmek için bu yöntemi nitelendirir). `task_group` nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Çalışma zamanının, İptalin bu `task_group` nesne üzerinden akacağı zamandan önce belirleyebildiği durumlar gibi durumlarda, `true` de döndürülür.|
|[çalışmaz](#run)|Fazla Yüklendi. `task_group` nesnesinde bir görevi zamanlar. Bir `task_handle` nesnesi `run`bir parametre olarak geçirilirse, çağıran `task_handle` nesnesinin kullanım ömrünü yönetmekten sorumludur. Bir parametre olarak bir işlev nesnesine başvuru alan yöntemin sürümü, bir `task_handle` nesnesine başvuru alan sürümü kullanmaktan daha az iyi bir şekilde gerçekleştirilebilen çalışma zamanının içindeki yığın ayırmayı içerir. `_Placement` parametresini alan sürüm, görevin, bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.|
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Tam iptal desteği için `task_group` nesnenin yardımı ile, çağıran bağlamda satır içi çalışacak şekilde bir görev zamanlar. İşlev daha sonra, `task_group` nesnesi üzerindeki tüm işler tamamlanana ya da iptal edilene kadar bekler. Bir `task_handle` nesnesi `run_and_wait`bir parametre olarak geçirilirse, çağıran `task_handle` nesnesinin kullanım ömrünü yönetmekten sorumludur.|
|[bekleneceğini](#wait)|`task_group` nesnesi üzerindeki tüm işler tamamlanana ya da iptal edilene kadar bekler.|

## <a name="remarks"></a>Açıklamalar

Yoğun olarak kısıtlanmış `structured_task_group` sınıftan farklı olarak, `task_group` sınıfı çok daha genel bir yapıdır. [Structured_task_group](structured-task-group-class.md)tarafından tanımlanan herhangi bir kısıtlama yoktur. `task_group` nesneler, iş parçacıkları genelinde güvenli bir şekilde kullanılabilir ve serbest biçimli yollarla kullanılır. `task_group` yapısının dezavantajı, küçük miktarlarda iş gerçekleştiren görevler için `structured_task_group` yapısını da gerçekleştiremeyebilir.

Daha fazla bilgi için bkz. [Görev Paralelliği](../task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_group`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="cancel"></a>İptal

Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.

```cpp
void cancel();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../cancellation-in-the-ppl.md).

## <a name="is_canceling"></a>is_canceling

Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yönteminin `task_group` nesnesi üzerinde çağrıldığı anlamına gelmez (Bu nedenle, bu yöntem `true`döndürmek için bu yöntemi nitelendirir). `task_group` nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Çalışma zamanının, İptalin bu `task_group` nesne üzerinden akacağı zamandan önce belirleyebildiği durumlar gibi durumlarda, `true` de döndürülür.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

`task_group` nesnesinin bir iptal etme ortalığının (veya kısa bir süre içinde olup olmadığı) bir göstergesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../cancellation-in-the-ppl.md).

## <a name="run"></a>çalışmaz

`task_group` nesnesinde bir görevi zamanlar. Bir `task_handle` nesnesi `run`bir parametre olarak geçirilirse, çağıran `task_handle` nesnesinin kullanım ömrünü yönetmekten sorumludur. Bir parametre olarak bir işlev nesnesine başvuru alan yöntemin sürümü, bir `task_handle` nesnesine başvuru alan sürümü kullanmaktan daha az iyi bir şekilde gerçekleştirilebilen çalışma zamanının içindeki yığın ayırmayı içerir. `_Placement` parametresini alan sürüm, görevin, bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.

```cpp
template<
   typename _Function
>
void run(
   const _Function& _Func
);

template<
   typename _Function
>
void run(
   const _Function& _Func,
   location& _Placement
);

template<
   typename _Function
>
void run(
   task_handle<_Function>& _Task_handle
);

template<
   typename _Function
>
void run(
   task_handle<_Function>& _Task_handle,
   location& _Placement
);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Görev tanıtıcısının gövdesini yürütmek için çağrılacak işlev nesnesinin türü.

*_Func*<br/>
Görevin gövdesini çağırmak için çağrılacak bir işlev. Bu bir lambda ifadesi veya imza `void operator()()`işlev çağrısı işlecinin bir sürümünü destekleyen başka bir nesne olabilir.

*_Placement*<br/>
`_Func` parametresi tarafından temsil edilen görevin yürütüleceği konuma bir başvuru.

*_Task_handle*<br/>
Zamanlanmakta olan iş için bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı, bu `task_group` nesnesinde `wait` veya `run_and_wait` yöntemi çağrılana kadar canlı olmaya devam edecektir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, belirtilen çalışma işlevini daha sonraki bir zamanda çalışacak şekilde zamanlar ve bu, çağırma işlevi geri döndüğünde olabilir. Bu yöntem, belirtilen çalışma işlevinin bir kopyasını tutmak için bir [task_handle](task-handle-class.md) nesnesi kullanır. Bu nedenle, bu yönteme geçirdiğiniz bir işlev nesnesinde oluşan tüm durum değişiklikleri, bu işlev nesnesinin kopyasında görünmez. Ayrıca, işaretçi veya iş işlevine başvuru ile geçirdiğiniz nesnelerin kullanım ömrünün, iş işlevi görünene kadar geçerli kalmasını sağlayın.

Yığın bir özel durumdan geri sarma sonucu olarak `task_group`, `wait` veya `run_and_wait` yöntemine bir çağrının yapıldığını garanti etmeniz gerekmez. Bu durumda, yıkıcı uygun şekilde iptal eder ve `_Task_handle` parametresi tarafından temsil edilen görevin tamamlanmasını bekler.

`_Task_handle` parametresi tarafından verilen görev tanıtıcısı, `run` yöntemi aracılığıyla bir görev grubu nesnesi üzerinde zaten zamanlanmışsa ve bu görev grubunda `wait` veya `run_and_wait` yöntemine aradaki bir çağrı yoksa, yöntemi [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) bir özel durum oluşturur.

## <a name="run_and_wait"></a>run_and_wait

Tam iptal desteği için `task_group` nesnenin yardımı ile, çağıran bağlamda satır içi çalışacak şekilde bir görev zamanlar. İşlev daha sonra, `task_group` nesnesi üzerindeki tüm işler tamamlanana ya da iptal edilene kadar bekler. Bir `task_handle` nesnesi `run_and_wait`bir parametre olarak geçirilirse, çağıran `task_handle` nesnesinin kullanım ömrünü yönetmekten sorumludur.

```cpp
template<
   class _Function
>
task_group_status run_and_wait(
   task_handle<_Function>& _Task_handle
);

template<
   class _Function
>
task_group_status run_and_wait(
   const _Function& _Func
);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Görevin gövdesini yürütmek için çağrılacak işlev nesnesinin türü.

*_Task_handle*<br/>
Bir görev için, çağıran bağlamda satır içi çalıştırılacak bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı `run_and_wait` yöntemi yürütmeyi bitirene kadar canlı olmaya devam edecektir.

*_Func*<br/>
İşin gövdesini çağırmak için çağrılacak bir işlev. Bu bir lambda ifadesi veya imza `void operator()()`işlev çağrısı işlecinin bir sürümünü destekleyen başka bir nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Açıklamalar

Bu `task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası, çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu `task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve `run_and_wait` yöntemine yapılan çağrıdan yayılır.

Bir `task_group` nesnesindeki `run_and_wait` yönteminden geri dönene sonra, çalışma zamanı nesneyi yeniden kullanılabilen temiz bir duruma sıfırlar. Bu, `task_group` nesnesinin iptal edildiği durumu içerir.

Yürütmenin özel olmayan yolunda, bu yöntemi çağırmak için bir mantarih veya `task_group` yıkıcıdan önce `wait` yöntemi gerekir.

## <a name="ctor"></a>task_group

Yeni bir `task_group` nesnesi oluşturur.

```cpp
task_group();

task_group(
   cancellation_token _CancellationToken
);
```

### <a name="parameters"></a>Parametreler

*_CancellationToken*<br/>
Bu görev grubuyla ilişkilendirilecek iptal belirteci. Belirteç iptal edildiğinde görev grubu iptal edilir.

### <a name="remarks"></a>Açıklamalar

İptal belirteci alan Oluşturucu, belirteç ile ilişkili kaynak iptal edildiğinde iptal edilecek bir `task_group` oluşturur. Açık bir iptal belirteci sağlamak, bu görev grubunu bir üst gruptan farklı bir belirteç veya belirteç olmadan örtük bir iptal etme işleminden de yalıtır.

## <a name="dtor"></a>~ task_group

`task_group` nesnesini yok eder. Bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesnedeki `wait` veya `run_and_wait` yöntemini çağırmanız beklenmektedir.

```cpp
~task_group();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı normal yürütmenin sonucu olarak çalışırsa (örneğin, bir özel durum nedeniyle yığın geri sarma değil) ve `wait` ya da `run_and_wait` yöntemleri çağrılmadıysa, yıkıcı bir [missing_wait](missing-wait-class.md) özel durumu oluşturabilir.

## <a name="wait"></a>bekleneceğini

`task_group` nesnesi üzerindeki tüm işler tamamlanana ya da iptal edilene kadar bekler.

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Açıklamalar

Bu `task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası, çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu `task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve `wait` yöntemine yapılan çağrıdan yayılır.

Bir `task_group` nesnesi üzerinde `wait` çağırmak, onu yeniden kullanılabilen temiz bir duruma sıfırlar. Bu, `task_group` nesnesinin iptal edildiği durumu içerir.

Yürütmenin özel olmayan yolunda, bu yöntemi çağırmak için bir mantarih veya `task_group` yıkıcıdan önce `run_and_wait` yöntemi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)<br/>
[task_handle Sınıfı](task-handle-class.md)
