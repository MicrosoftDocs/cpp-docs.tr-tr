---
title: task_group Sınıfı
ms.date: 07/20/2018
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
helpviewer_keywords:
- task_group class
ms.openlocfilehash: 4d11a7fc25d95884418a3062721df75cc11be520
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224961"
---
# <a name="task_group-class"></a>task_group Sınıfı

`task_group`Sınıfı, beklemiş veya iptal edilebilir bir paralel çalışma koleksiyonunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class task_group;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_group](#ctor)|Fazla Yüklendi. Yeni bir `task_group` nesne oluşturur.|
|[~ task_group yok edici](#dtor)|Bir nesneyi yok eder `task_group` . Yıkıcı `wait` `run_and_wait` yürütme işlemi, bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesnedeki ya da yöntemini çağırmanız beklenir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[İptal](#cancel)|Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.|
|[is_canceling](#is_canceling)|Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yöntemin nesne üzerinde çağrıldığı `task_group` (Bu tür kesinlikle bu yöntemi döndürecek şekilde niteleyen) anlamına gelmez **`true`** . `task_group`Nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Bu şekilde, çalışma zamanının, İptalin bu nesne üzerinden akacağı zamandan önce belirleyebildiği durumlar gibi durumlarda da `task_group` **`true`** döndürülür.|
|[çalışmaz](#run)|Fazla Yüklendi. Nesnesinde bir görevi zamanlar `task_group` . Bir `task_handle` nesne öğesine parametresi olarak geçirilirse `run` , çağıran nesnenin ömrünü yönetmekten sorumludur `task_handle` . Bir parametre olarak işlev nesnesine başvuru alan yöntemin sürümü, çalışma zamanının içinde bir nesneye başvuru alan sürümü kullanmaktan daha az bir yığın ayırma işlemi içerir `task_handle` . Parametresini alan sürüm, `_Placement` görevin, bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.|
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Bir görevi, `task_group` tam iptal desteği için nesnenin yardımı ile çağırma bağlamında, satır içi olarak çalışacak şekilde zamanlar. İşlev daha sonra nesne üzerindeki tüm işler tamamlanana ya `task_group` da iptal edilene kadar bekler. Bir `task_handle` nesne öğesine parametresi olarak geçirilirse `run_and_wait` , çağıran nesnenin ömrünü yönetmekten sorumludur `task_handle` .|
|[bekleneceğini](#wait)|Nesne üzerindeki tüm işler tamamlanana `task_group` ya da iptal edilene kadar bekler.|

## <a name="remarks"></a>Açıklamalar

Yoğun olarak kısıtlanmış sınıftan farklı olarak `structured_task_group` , `task_group` sınıfı çok daha genel yapısıdır. [Structured_task_group](structured-task-group-class.md)tarafından tanımlanan herhangi bir kısıtlama yoktur. `task_group`nesneler, iş parçacıkları genelinde güvenli bir şekilde kullanılabilir ve serbest biçimli yollarla kullanılır. Yapının olumsuz yanı, `task_group` `structured_task_group` az miktarda iş gerçekleştiren görevler için yapıyı da gerçekleştiremeyebilir.

Daha fazla bilgi için bkz. [Görev Paralelliği](../task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_group`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="cancel"></a><a name="cancel"></a>İptal

Bu görev grubunda kök olarak çalışan çalışmanın alt ağacını iptal etmeye yönelik en iyi çabayı sağlar. Görev grubunda zamanlanan her görev, mümkünse geçişli olarak iptal edilir.

```cpp
void cancel();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../cancellation-in-the-ppl.md).

## <a name="is_canceling"></a><a name="is_canceling"></a>is_canceling

Görev grubunun şu anda bir iptal etme ortatına bağlı olup olmadığına bakılmaksızın çağrıyı bilgilendirir. Bu, `cancel` yöntemin nesne üzerinde çağrıldığı `task_group` (Bu tür kesinlikle bu yöntemi döndürecek şekilde niteleyen) anlamına gelmez **`true`** . `task_group`Nesnenin satır içi yürütülmesi ve iş ağacında daha fazla görev grubunun iptal edilmesi durumunda olabilir. Bu şekilde, çalışma zamanının, İptalin bu nesne üzerinden akacağı zamandan önce belirleyebildiği durumlar gibi durumlarda da `task_group` **`true`** döndürülür.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Dönüş Değeri

`task_group`Nesnenin bir iptal etme ortalığının (veya kısa bir süre içinde olup olmadığı) bir göstergesi.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [iptal](../cancellation-in-the-ppl.md).

## <a name="run"></a><a name="run"></a>çalışmaz

Nesnesinde bir görevi zamanlar `task_group` . Bir `task_handle` nesne öğesine parametresi olarak geçirilirse `run` , çağıran nesnenin ömrünü yönetmekten sorumludur `task_handle` . Bir parametre olarak işlev nesnesine başvuru alan yöntemin sürümü, çalışma zamanının içinde bir nesneye başvuru alan sürümü kullanmaktan daha az bir yığın ayırma işlemi içerir `task_handle` . Parametresini alan sürüm, `_Placement` görevin, bu parametre tarafından belirtilen konumda yürütülmeye yaklaşmasına neden olur.

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
Görevin gövdesini çağırmak için çağrılacak bir işlev. Bu bir lambda ifadesi veya imza ile işlev çağrısı işlecinin bir sürümünü destekleyen başka bir nesne olabilir `void operator()()` .

*_Placement*<br/>
Parametresi tarafından temsil edilen görevin yürütmesi gereken konuma bir başvuru `_Func` .

*_Task_handle*<br/>
Zamanlanmakta olan iş için bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı, `wait` ya da `run_and_wait` yöntemi bu nesnede çağrılana kadar canlı olmaya devam edecektir `task_group` .

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, belirtilen çalışma işlevini daha sonraki bir zamanda çalışacak şekilde zamanlar ve bu, çağırma işlevi geri döndüğünde olabilir. Bu yöntem, belirtilen çalışma işlevinin bir kopyasını tutmak için bir [task_handle](task-handle-class.md) nesnesi kullanır. Bu nedenle, bu yönteme geçirdiğiniz bir işlev nesnesinde oluşan tüm durum değişiklikleri, bu işlev nesnesinin kopyasında görünmez. Ayrıca, işaretçi veya iş işlevine başvuru ile geçirdiğiniz nesnelerin kullanım ömrünün, iş işlevi görünene kadar geçerli kalmasını sağlayın.

`task_group`Serbest yapılar, yığın bir özel durumdan geriye doğru izleme sonucu olarak varsa, ya da yöntemine bir çağrının yapıldığını garanti etmeniz gerekmez `wait` `run_and_wait` . Bu durumda, yıkıcı uygun şekilde iptal edilir ve parametresi tarafından temsil edilen görevin tamamlanmasını bekler `_Task_handle` .

Parametresi tarafından verilen görev [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) tanıtıcısı, `_Task_handle` yöntemi aracılığıyla bir görev grubu nesnesi üzerinde zamanlanmışsa `run` ve `wait` `run_and_wait` Bu görev grubundaki veya yöntemine hiçbir aradaki çağrı yoksa, yöntemi invalid_multiple_scheduling bir özel durum oluşturur.

## <a name="run_and_wait"></a><a name="run_and_wait"></a>run_and_wait

Bir görevi, `task_group` tam iptal desteği için nesnenin yardımı ile çağırma bağlamında, satır içi olarak çalışacak şekilde zamanlar. İşlev daha sonra nesne üzerindeki tüm işler tamamlanana ya `task_group` da iptal edilene kadar bekler. Bir `task_handle` nesne öğesine parametresi olarak geçirilirse `run_and_wait` , çağıran nesnenin ömrünü yönetmekten sorumludur `task_handle` .

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
Bir görev için, çağıran bağlamda satır içi çalıştırılacak bir tanıtıcı. Çağıranın bu nesnenin kullanım ömrü için sorumluluğa sahip olduğunu unutmayın. Çalışma zamanı, yöntem yürütmeyi bitirene kadar canlı olmaya devam edecektir `run_and_wait` .

*_Func*<br/>
İşin gövdesini çağırmak için çağrılacak bir işlev. Bu bir lambda ifadesi veya imza ile işlev çağrısı işlecinin bir sürümünü destekleyen başka bir nesne olabilir `void operator()()` .

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Açıklamalar

Bu nesne için zamanlanmış bir veya daha fazla görevin, `task_group` çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu nesneye zamanlanan görevlerden bir veya daha fazlası `task_group` bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve yönteme çağrı dışına yayılır `run_and_wait` .

`run_and_wait`Bir nesne üzerindeki yönteminden geri döndüğünüzde `task_group` , çalışma zamanı nesneyi yeniden kullanılabilen temiz bir duruma sıfırlar. Bu, nesnenin iptal edildiği durumu içerir `task_group` .

Yürütmenin olağanüstü olmayan yolunda, bu yöntemi veya yürütme `wait` yıkıcıdan önce yöntemini çağırmak için bir mantarih vardır `task_group` .

## <a name="task_group"></a><a name="ctor"></a>task_group

Yeni bir `task_group` nesne oluşturur.

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

İptal belirteci alan Oluşturucu, `task_group` belirteç ile ilişkili kaynak iptal edildiğinde iptal edilecek bir oluşturur. Açık bir iptal belirteci sağlamak, bu görev grubunu bir üst gruptan farklı bir belirteç veya belirteç olmadan örtük bir iptal etme işleminden de yalıtır.

## <a name="task_group"></a><a name="dtor"></a>~ task_group

Bir nesneyi yok eder `task_group` . Yıkıcı `wait` `run_and_wait` yürütme işlemi, bir özel durum nedeniyle yığın geri sarma sonucu olarak yürütülemediği sürece, yıkıcı yürütmeden önce nesnedeki ya da yöntemini çağırmanız beklenir.

```cpp
~task_group();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı normal yürütmenin sonucu olarak çalışırsa (örneğin, bir özel durum nedeniyle yığın geriye doğru değil) ve `wait` ne de `run_and_wait` Yöntem çağrılmadıysa, yıkıcı [missing_wait](missing-wait-class.md) bir özel durum oluşturabilir.

## <a name="wait"></a><a name="wait"></a>bekleneceğini

Nesne üzerindeki tüm işler tamamlanana `task_group` ya da iptal edilene kadar bekler.

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Dönüş Değeri

Açık bir iptal işlemi veya görevlerinin birinden bir özel durum oluştuğundan, bekleme işleminin karşılanıp karşılanmadığını veya görev grubunun iptal edildiğini belirten bir gösterge. Daha fazla bilgi için bkz. [task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Açıklamalar

Bu nesne için zamanlanmış bir veya daha fazla görevin, `task_group` çağıran bağlamda satır içi yürütebileceğini unutmayın.

Bu nesneye zamanlanan görevlerden bir veya daha fazlası `task_group` bir özel durum oluşturursa, çalışma zamanı bu tür bir özel durum seçer ve yönteme çağrı dışına yayılır `wait` .

`wait`Bir nesne üzerinde çağırmak `task_group` , yeniden kullanılabilen bir temiz duruma sıfırlar. Bu, nesnenin iptal edildiği durumu içerir `task_group` .

Yürütmenin olağanüstü olmayan yolunda, bu yöntemi veya yürütme `run_and_wait` yıkıcıdan önce yöntemini çağırmak için bir mantarih vardır `task_group` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[structured_task_group sınıfı](structured-task-group-class.md)<br/>
[task_handle Sınıfı](task-handle-class.md)
