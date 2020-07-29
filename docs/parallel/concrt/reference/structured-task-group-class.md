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
ms.openlocfilehash: 44fd2a42f4c98a569e985449f0c55102a9cbc3a6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231682"
---
# <a name="structured_task_group-class"></a>structured_task_group Sınıfı

`structured_task_group`Sınıfı, paralel çalışmanın yüksek yapılandırılmış bir koleksiyonunu temsil eder. Tek tek paralel görevleri bir `structured_task_group` using nesnelerine sıraya alabilir `task_handle` ve bunların tamamlanmasını bekleyebilir ya da yürütmeyi bitirmeden önce görev grubunu iptal edebilirsiniz. Bu, yürütmeye başlamış olmayan tüm görevleri iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class structured_task_group;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[structured_task_group](#ctor)|Fazla Yüklendi. Yeni bir `structured_task_group` nesne oluşturur.|
|[~ structured_task_group yok edici](#dtor)|Bir nesneyi yok eder `structured_task_group` . `wait` `run_and_wait` Bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesne üzerinde ya da yöntemini çağırmanız beklenmektedir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[İptal](#cancel)|Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.|
|[is_canceling](#is_canceling)|Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yöntemin nesne üzerinde çağrıldığı `structured_task_group` (Bu tür kesinlikle bu yöntemi döndürecek şekilde niteleyen) anlamına gelmez **`true`** . `structured_task_group`Nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Bu şekilde, çalışma zamanının, İptalin bu nesne üzerinden akacağı zamandan önce belirleyebildiği durumlar gibi durumlarda da `structured_task_group` **`true`** döndürülür.|
|[çalışmaz](#run)|Fazla Yüklendi. Nesnesinde bir görevi zamanlar `structured_task_group` . Çağıran, `task_handle` parametre içinde geçirilen nesnenin ömrünü yönetir `_Task_handle` . Parametresini alan sürüm, `_Placement` görevin bu parametre tarafından belirtilen konumda yürütülmeye kaydırılmasına neden olur.|
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Bir görevi, `structured_task_group` tam iptal desteği için nesnenin yardımı ile çağırma bağlamında, satır içi olarak çalışacak şekilde zamanlar. Bir `task_handle` nesne öğesine parametresi olarak geçirilirse `run_and_wait` , çağıran nesnenin ömrünü yönetmekten sorumludur `task_handle` . İşlev daha sonra nesne üzerindeki tüm işler tamamlanana ya `structured_task_group` da iptal edilene kadar bekler.|
|[bekleneceğini](#wait)|Üzerindeki tüm işler tamamlanana veya iptal edilene kadar bekler `structured_task_group` .|

## <a name="remarks"></a>Açıklamalar

Performans kazanmak için bir nesne kullanımına yerleştirilmiş çok sayıda ciddi kısıtlama vardır `structured_task_group` :

- Tek bir `structured_task_group` nesne birden çok iş parçacığı tarafından kullanılamaz. Bir nesne üzerindeki tüm işlemlerin `structured_task_group` , nesneyi oluşturan iş parçacığı tarafından gerçekleştirilmesi gerekir. Bu kuralın iki özel durumu, üye işlevleridir `cancel` `is_canceling` . Nesne, bir lambda ifadesinin yakalama listesinde bulunmayabilir ve görev, iptal işlemlerinden birini kullanmadığı takdirde bir görev içinde kullanılabilir.

- Bir nesneye zamanlanan tüm görevler `structured_task_group` `task_handle` , süresini açıkça yönetmeniz gereken nesneler kullanılarak zamanlanır.

- Birden çok grup yalnızca kesinlikle iç içe geçmiş sırada kullanılabilir. İki `structured_task_group` nesne bildirilirse, belirtilen ikinci bir Yöntem (iç bir), `cancel` ilki haricinde veya `is_canceling` çağırılmadığında (dıştaki bir) önce yapı birimi olmalıdır. Bu durum, yalnızca `structured_task_group` aynı veya işlevsel iç içe geçmiş kapsamlar içinde birden fazla nesnenin bildirilmesinin yanı sıra `structured_task_group` veya yöntemleri aracılığıyla sıraya alınmış bir görevin durumunu da içerir `run` `run_and_wait` .

- Genel sınıftan farklı olarak `task_group` , sınıfındaki tüm durumlar `structured_task_group` son ' dur. Görevleri gruba sıraya aldıktan ve bunların tamamlanmasını bekledikten sonra, aynı grubu yeniden kullanamazsınız.

Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`structured_task_group`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="cancel"></a><a name="cancel"></a>İptal

Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.

```cpp
void cancel();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="is_canceling"></a><a name="is_canceling"></a>is_canceling

Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yöntemin nesne üzerinde çağrıldığı `structured_task_group` (Bu tür kesinlikle bu yöntemi döndürecek şekilde niteleyen) anlamına gelmez **`true`** . `structured_task_group`Nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Bu şekilde, çalışma zamanının, İptalin bu nesne üzerinden akacağı zamandan önce belirleyebildiği durumlar gibi durumlarda da `structured_task_group` **`true`** döndürülür.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

`structured_task_group`Nesnenin bir iptal etme ortalığının (veya kısa bir süre içinde olup olmadığı) bir göstergesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="run"></a><a name="run"></a>çalışmaz

Nesnesinde bir görevi zamanlar `structured_task_group` . Çağıran, `task_handle` parametre içinde geçirilen nesnenin ömrünü yönetir `_Task_handle` . Parametresini alan sürüm, `_Placement` görevin bu parametre tarafından belirtilen konumda yürütülmeye kaydırılmasına neden olur.

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
Zamanlanmakta olan iş için bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı, `wait` ya da `run_and_wait` yöntemi bu nesnede çağrılana kadar canlı olmaya devam edecektir `structured_task_group` .

*_Placement*<br/>
Parametresi tarafından temsil edilen görevin yürütmesi gereken konuma bir başvuru `_Task_handle` .

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, bu yönteme geçirdiğiniz çalışma işlevinin bir kopyasını oluşturur. Bu yönteme geçirdiğiniz bir işlev nesnesinde oluşan herhangi bir durum değişikliği, bu işlev nesnesinin kopyasında görünmez.

`structured_task_group`Serbest yapılar, yığın bir özel durumdan geriye doğru izleme sonucu olarak varsa, ya da yöntemine bir çağrının yapıldığını garanti etmeniz gerekmez `wait` `run_and_wait` . Bu durumda, yıkıcı uygun şekilde iptal edilir ve parametresi tarafından temsil edilen görevin tamamlanmasını bekler `_Task_handle` .

Parametresi tarafından [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) verilen görev tanıtıcısı, `_Task_handle` yöntemi aracılığıyla bir görev grubu nesnesi üzerinde zamanlanmışsa `run` ve `wait` `run_and_wait` Bu görev grubundaki veya yöntemine hiçbir eklenmemiş çağrı yoksa invalid_multiple_scheduling bir özel durum oluşturur.

## <a name="run_and_wait"></a><a name="run_and_wait"></a>run_and_wait

Bir görevi, `structured_task_group` tam iptal desteği için nesnenin yardımı ile çağırma bağlamında, satır içi olarak çalışacak şekilde zamanlar. Bir `task_handle` nesne öğesine parametresi olarak geçirilirse `run_and_wait` , çağıran nesnenin ömrünü yönetmekten sorumludur `task_handle` . İşlev daha sonra nesne üzerindeki tüm işler tamamlanana ya `structured_task_group` da iptal edilene kadar bekler.

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
Bir görev için, çağıran bağlamda satır içi çalıştırılacak bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı, yöntem yürütmeyi bitirene kadar canlı olmaya devam edecektir `run_and_wait` .

*_Func*<br/>
İşin gövdesini çağırmak için çağrılacak bir işlev. Bu, imzaya sahip işlev çağrısı işlecinin bir sürümünü destekleyen bir lambda veya diğer nesne olabilir `void operator()()` .

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Açıklamalar

Bu nesne için zamanlanmış bir veya daha fazla görevin, `structured_task_group` çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu nesneye zamanlanan görevlerden bir veya daha fazlası `structured_task_group` bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve yönteme çağrı dışına yayılır `run_and_wait` .

Bu işlev çağrıldıktan sonra, `structured_task_group` nesnesi son durumda değerlendirilir ve kullanılmamalıdır. `run_and_wait`Yöntem dönüşün ardından kullanım tanımsız davranışa neden olur.

Yürütmenin olağanüstü olmayan yolunda, bu yöntemi veya yürütme `wait` yıkıcıdan önce yöntemini çağırmak için bir mantarih vardır `structured_task_group` .

## <a name="structured_task_group"></a><a name="ctor"></a>structured_task_group

Yeni bir `structured_task_group` nesne oluşturur.

```cpp
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>Parametreler

*_CancellationToken*<br/>
Bu yapılandırılmış görev grubuyla ilişkilendirilecek iptal belirteci. Yapılandırılmış görev grubu, belirteç iptal edildiğinde iptal edilir.

### <a name="remarks"></a>Açıklamalar

İptal belirteci alan Oluşturucu, `structured_task_group` belirteç ile ilişkili kaynak iptal edildiğinde iptal edilecek bir oluşturur. Açık bir iptal belirteci sağlamak, bu yapılandırılmış görev grubunu, farklı bir belirteç olan veya belirteci olmayan bir üst gruptan örtük bir iptal 'e katılmasını de yalıtır.

## <a name="structured_task_group"></a><a name="dtor"></a>~ structured_task_group

Bir nesneyi yok eder `structured_task_group` . `wait` `run_and_wait` Bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesne üzerinde ya da yöntemini çağırmanız beklenmektedir.

```cpp
~structured_task_group();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı normal yürütmenin sonucu olarak çalışırsa (örneğin, bir özel durum nedeniyle yığın geriye doğru değil) ve `wait` ne de `run_and_wait` Yöntem çağrılmadıysa, yıkıcı [missing_wait](missing-wait-class.md) bir özel durum oluşturabilir.

## <a name="wait"></a><a name="wait"></a>bekleneceğini

Üzerindeki tüm işler tamamlanana veya iptal edilene kadar bekler `structured_task_group` .

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Açıklamalar

Bu nesne için zamanlanmış bir veya daha fazla görevin, `structured_task_group` çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu nesneye zamanlanan görevlerden bir veya daha fazlası `structured_task_group` bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve yönteme çağrı dışına yayılır `wait` .

Bu işlev çağrıldıktan sonra, `structured_task_group` nesnesi son durumda değerlendirilir ve kullanılmamalıdır. `wait`Yöntem dönüşün ardından kullanım tanımsız davranışa neden olur.

Yürütmenin olağanüstü olmayan yolunda, bu yöntemi veya yürütme `run_and_wait` yıkıcıdan önce yöntemini çağırmak için bir mantarih vardır `structured_task_group` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[task_group sınıfı](task-group-class.md)<br/>
[task_handle Sınıfı](task-handle-class.md)
