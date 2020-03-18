---
title: structured_task_group Sınıfı
ms.date: 11/04/2016
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
ms.openlocfilehash: 93dd79b755f79dcb4857c1b1c4856362b0bd45dd
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422131"
---
# <a name="structured_task_group-class"></a>structured_task_group Sınıfı

`structured_task_group` sınıfı, paralel çalışmanın yüksek yapılandırılmış bir koleksiyonunu temsil eder. Tek tek paralel görevleri `task_handle` nesneleri kullanarak bir `structured_task_group` kuyruğa alabilir ve bunların tamamlanmasını bekleyebilir veya yürütmeyi bitirmeden önce görev grubunu iptal edebilirsiniz. Bu, yürütmeyi başlamamış olan tüm görevleri iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class structured_task_group;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[structured_task_group](#ctor)|Aşırı yüklendi. Yeni bir `structured_task_group` nesnesi oluşturur.|
|[~ structured_task_group yok edici](#dtor)|`structured_task_group` nesnesini yok eder. Bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesnedeki `wait` veya `run_and_wait` yöntemini çağırmanız bekleniyor.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[İptal](#cancel)|Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.|
|[is_canceling](#is_canceling)|Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yönteminin `structured_task_group` nesnesi üzerinde çağrıldığı anlamına gelmez (Bu nedenle, bu yöntemi **true**döndürecek şekilde nitelendirir). `structured_task_group` nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Bu gibi durumlarda, İptalin bu `structured_task_group` nesne üzerinden akacağı zamanın önüne göre belirleyebildiği gibi durumlarda, **true değeri** de döndürülür.|
|[çalışmaz](#run)|Aşırı yüklendi. `structured_task_group` nesnesinde bir görevi zamanlar. Çağıran, `_Task_handle` parametresinde geçirilen `task_handle` nesnesinin ömrünü yönetir. `_Placement` parametresini alan sürüm, görevin, bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.|
|[run_and_wait](#run_and_wait)|Aşırı yüklendi. Tam iptal desteği için `structured_task_group` nesnenin yardımı ile, çağıran bağlamda satır içi çalışacak şekilde bir görev zamanlar. Bir `task_handle` nesnesi `run_and_wait`bir parametre olarak geçirilirse, çağıran `task_handle` nesnesinin kullanım ömrünü yönetmekten sorumludur. İşlev daha sonra, `structured_task_group` nesnesi üzerindeki tüm işler tamamlanana ya da iptal edilene kadar bekler.|
|[bekleneceğini](#wait)|`structured_task_group` tüm çalışmalar tamamlanana veya iptal edilene kadar bekler.|

## <a name="remarks"></a>Açıklamalar

Performans kazanmak için bir `structured_task_group` nesnesinin kullanımına yerleştirilmiş çok sayıda ciddi kısıtlama vardır:

- Tek bir `structured_task_group` nesnesi birden çok iş parçacığı tarafından kullanılamaz. Bir `structured_task_group` nesnesindeki tüm işlemler, nesneyi oluşturan iş parçacığı tarafından gerçekleştirilmelidir. Bu kuralın iki özel durumu `cancel` ve `is_canceling`üye işlevleridir. Nesne, bir lambda ifadesinin yakalama listesinde bulunmayabilir ve görev, iptal işlemlerinden birini kullanmadığı takdirde bir görev içinde kullanılabilir.

- Bir `structured_task_group` nesnesine zamanlanan tüm görevler, süresini açıkça yönetmeniz gereken `task_handle` nesneler kullanılarak zamanlanır.

- Birden çok grup yalnızca kesinlikle iç içe geçmiş sırada kullanılabilir. İki `structured_task_group` nesne bildirilirse, belirtilen ikinci bir yöntemin (iç bir), `cancel` veya `is_canceling` dışındaki herhangi bir yöntemden önce, birinci bir kez (dıştaki bir) çağırılmalıdır. Bu durum, yalnızca aynı veya işlevsel iç içe geçmiş kapsamlar içinde birden çok `structured_task_group` nesnesi bildirmek ve `run` ya da `run_and_wait` yöntemleri aracılığıyla `structured_task_group` sıraya alınmış bir görevin olması durumunda true değerini tutar.

- Genel `task_group` sınıfından farklı olarak, `structured_task_group` sınıfındaki tüm durumlar son ' dur. Görevleri gruba sıraya aldıktan ve bunların tamamlanmasını bekledikten sonra, aynı grubu yeniden kullanamazsınız.

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`structured_task_group`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="cancel"></a>İptal

Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.

```cpp
void cancel();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="is_canceling"></a>is_canceling

Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yönteminin `structured_task_group` nesnesi üzerinde çağrıldığı anlamına gelmez (Bu nedenle, bu yöntemi **true**döndürecek şekilde nitelendirir). `structured_task_group` nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Bu gibi durumlarda, İptalin bu `structured_task_group` nesne üzerinden akacağı zamanın önüne göre belirleyebildiği gibi durumlarda, **true değeri** de döndürülür.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

`structured_task_group` nesnesinin bir iptal etme ortalığının (veya kısa bir süre içinde olup olmadığı) bir göstergesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="run"></a>çalışmaz

`structured_task_group` nesnesinde bir görevi zamanlar. Çağıran, `_Task_handle` parametresinde geçirilen `task_handle` nesnesinin ömrünü yönetir. `_Placement` parametresini alan sürüm, görevin, bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.

```cpp
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
Görev tanıtıcısının gövdesini yürütmek için çağrılacak işlev nesnesinin türü.

*_Task_handle*<br/>
Zamanlanmakta olan iş için bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı, bu `structured_task_group` nesnesinde `wait` veya `run_and_wait` yöntemi çağrılana kadar canlı olmaya devam edecektir.

*_Placement*<br/>
`_Task_handle` parametresi tarafından temsil edilen görevin yürütüleceği konuma bir başvuru.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, bu yönteme geçirdiğiniz çalışma işlevinin bir kopyasını oluşturur. Bu yönteme geçirdiğiniz bir işlev nesnesinde oluşan herhangi bir durum değişikliği, bu işlev nesnesinin kopyasında görünmez.

Yığın bir özel durumdan geri sarma sonucu olarak `structured_task_group`, `wait` veya `run_and_wait` yöntemine bir çağrının yapıldığını garanti etmeniz gerekmez. Bu durumda, yıkıcı uygun şekilde iptal eder ve `_Task_handle` parametresi tarafından temsil edilen görevin tamamlanmasını bekler.

`_Task_handle` parametresi tarafından verilen görev tanıtıcısı, `run` yöntemi aracılığıyla bir görev grubu nesnesi üzerinde zaten zamanlanmışsa ve bu görev grubunda `wait` veya `run_and_wait` yöntemine aradaki bir çağrı yoksa [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) bir özel durum oluşturur.

## <a name="run_and_wait"></a>run_and_wait

Tam iptal desteği için `structured_task_group` nesnenin yardımı ile, çağıran bağlamda satır içi çalışacak şekilde bir görev zamanlar. Bir `task_handle` nesnesi `run_and_wait`bir parametre olarak geçirilirse, çağıran `task_handle` nesnesinin kullanım ömrünü yönetmekten sorumludur. İşlev daha sonra, `structured_task_group` nesnesi üzerindeki tüm işler tamamlanana ya da iptal edilene kadar bekler.

```cpp
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Görevi yürütmek için çağrılacak işlev nesnesinin türü.

*_Task_handle*<br/>
Bir görev için, çağıran bağlamda satır içi çalıştırılacak bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı `run_and_wait` yöntemi yürütmeyi bitirene kadar canlı olmaya devam edecektir.

*_Func*<br/>
İşin gövdesini çağırmak için çağrılacak bir işlev. Bu, imza `void operator()()`işlev çağrısı işlecinin bir sürümünü destekleyen bir lambda veya diğer nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Açıklamalar

Bu `structured_task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası, çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu `structured_task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve `run_and_wait` yöntemine yapılan çağrıdan yayılır.

Bu işlev çağrıldıktan sonra, `structured_task_group` nesnesi son durumda değerlendirilir ve kullanılmamalıdır. `run_and_wait` yöntemi getirduktan sonra kullanılan kullanım tanımsız davranışa neden olur.

Yürütmenin özel olmayan yolunda, bu yöntemi çağırmak için bir mantarih veya `structured_task_group` yıkıcıdan önce `wait` yöntemi gerekir.

## <a name="ctor"></a>structured_task_group

Yeni bir `structured_task_group` nesnesi oluşturur.

```cpp
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>Parametreler

*_CancellationToken*<br/>
Bu yapılandırılmış görev grubuyla ilişkilendirilecek iptal belirteci. Yapılandırılmış görev grubu, belirteç iptal edildiğinde iptal edilir.

### <a name="remarks"></a>Açıklamalar

İptal belirteci alan Oluşturucu, belirteç ile ilişkili kaynak iptal edildiğinde iptal edilecek bir `structured_task_group` oluşturur. Açık bir iptal belirteci sağlamak, bu yapılandırılmış görev grubunu, farklı bir belirteç olan veya belirteci olmayan bir üst gruptan örtük bir iptal 'e katılmasını de yalıtır.

## <a name="dtor"></a>~ structured_task_group

`structured_task_group` nesnesini yok eder. Bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesnedeki `wait` veya `run_and_wait` yöntemini çağırmanız bekleniyor.

```cpp
~structured_task_group();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı normal yürütmenin sonucu olarak çalışırsa (örneğin, bir özel durum nedeniyle yığın geri sarma değil) ve `wait` ya da `run_and_wait` yöntemleri çağrılmadıysa, yıkıcı bir [missing_wait](missing-wait-class.md) özel durumu oluşturabilir.

## <a name="wait"></a>bekleneceğini

`structured_task_group` tüm çalışmalar tamamlanana veya iptal edilene kadar bekler.

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Açıklamalar

Bu `structured_task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası, çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu `structured_task_group` nesnesine zamanlanan görevlerden bir veya daha fazlası bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve `wait` yöntemine yapılan çağrıdan yayılır.

Bu işlev çağrıldıktan sonra, `structured_task_group` nesnesi son durumda değerlendirilir ve kullanılmamalıdır. `wait` yöntemi getirduktan sonra kullanılan kullanım tanımsız davranışa neden olur.

Yürütmenin özel olmayan yolunda, bu yöntemi çağırmak için bir mantarih veya `structured_task_group` yıkıcıdan önce `run_and_wait` yöntemi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[task_handle Sınıfı](task-handle-class.md)
