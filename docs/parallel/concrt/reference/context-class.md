---
title: Bağlam Sınıfı
ms.date: 11/04/2016
f1_keywords:
- Context
- CONCRT/concurrency::Context
- CONCRT/concurrency::Context::Block
- CONCRT/concurrency::Context::CurrentContext
- CONCRT/concurrency::Context::GetId
- CONCRT/concurrency::Context::GetScheduleGroupId
- CONCRT/concurrency::Context::GetVirtualProcessorId
- CONCRT/concurrency::Context::Id
- CONCRT/concurrency::Context::IsCurrentTaskCollectionCanceling
- CONCRT/concurrency::Context::IsSynchronouslyBlocked
- CONCRT/concurrency::Context::Oversubscribe
- CONCRT/concurrency::Context::ScheduleGroupId
- CONCRT/concurrency::Context::Unblock
- CONCRT/concurrency::Context::VirtualProcessorId
- CONCRT/concurrency::Context::Yield
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
ms.openlocfilehash: 7c47d9db64b0af7d5413abed3f85e9d41a591fa2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143125"
---
# <a name="context-class"></a>Bağlam Sınıfı

Yürütme bağlamı için bir soyutlama temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Context;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ Bağlam yok edici](#dtor)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Block](#block)|Geçerli bağlamı engeller.|
|[LicenseManager 'ın CurrentContext](#currentcontext)|Geçerli bağlam için bir işaretçi döndürür.|
|[GetId](#getid)|Bağlamın ait olduğu Scheduler 'da benzersiz olan bağlam için bir tanımlayıcı döndürür.|
|[Getschedulegroupıd](#getschedulegroupid)|Bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı döndürür.|
|[Getvirtualprocessorıd](#getvirtualprocessorid)|Bağlamın Şu anda yürütüldüğü sanal işlemci için bir tanımlayıcı döndürür.|
|[Kimlik](#id)|Geçerli bağlamın ait olduğu Zamanlayıcı içinde benzersiz olan geçerli bağlam için bir tanımlayıcı döndürür.|
|[Iscurrenttaskcollectioncanceling](#iscurrenttaskcollectioncanceling)|Geçerli bağlamda şu anda yürütülmekte olan görev koleksiyonunun etkin bir iptal etme ortamın (veya kısa bir süre) üzerinde olup olmadığına ilişkin bir gösterge döndürür.|
|[Issynchronouslyblocked](#issynchronouslyblocked)|Bağlamın zaman uyumlu olarak engellenip engellenmeyeceğini belirler. Bir bağlam, açıkça engellemeye işaret eden bir eylemi gerçekleştirirse zaman uyumlu olarak engellenmiştir.|
|[Oversubscribe](#oversubscribe)|Bu Scheduler 'daki sanal işlemcilerin birinde çalıştırılan bir bağlamda çağrıldığında, bir kod bloğunun süresi boyunca ek bir sanal işlemciyi zamanlayıcıya çıkartır.|
|[Schedulegroupıd](#schedulegroupid)|Geçerli bağlamın üzerinde çalıştığı zamanlama grubu için bir tanımlayıcı döndürür.|
|[Kaldırabilir](#unblock)|Bağlamını kaldırır ve çalıştırılabilir duruma gelmesine neden olur.|
|[Virtualprocessorıd](#virtualprocessorid)|Geçerli bağlamın üzerinde yürütüldüğü sanal işlemci için bir tanımlayıcı döndürür.|
|[Yield](#yield)|Başka bir bağlamın yürütebilmesi için yürütmeyi verir. Üzerinde işlem yapmak için başka bir bağlam yoksa, Zamanlayıcı başka bir işletim sistemi iş parçacığı için ödeme yapabilir.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı Zamanlayıcı (bkz. [Scheduler](scheduler-class.md)), uygulamanız tarafından kuyruğa alınan işleri yürütmek için yürütme bağlamlarını kullanır. Win32 iş parçacığı, bir Windows işletim sisteminde yürütme bağlamına bir örnektir.

Her zaman, bir Scheduler 'ın eşzamanlılık düzeyi, Kaynak Yöneticisi tarafından verilen sanal işlemci sayısına eşittir. Sanal işlemci bir işleme kaynağı için soyutlamadır ve temel alınan sistemdeki bir donanım iş parçacığına eşlenir. Belirli bir zamanda sanal işlemcide yalnızca tek bir Zamanlayıcı bağlamı çalıştırılabilir.

Zamanlayıcı, doğası halinde birlikte çalışır ve bir yürütme bağlamı, bir bekleme durumu girmek isterse, sanal işlemciyi herhangi bir zamanda farklı bir içeriğe getirebilir. Bunun yerine geldiğinde, Scheduler 'ın kullanılabilir bir sanal işlemci tarafından yürütülmeye başlaması bitinceye kadar sürdürülemez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Context`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="block"></a>Engelleyin

Geçerli bağlamı engeller.

```cpp
static void __cdecl Block();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

Çağıran bağlam sanal bir işlemcide çalışıyorsa, sanal işlemci yürütmek için başka bir çalıştırılabilir bağlam bulur veya yeni bir tane oluşturabilir.

`Block` yöntemi çağrıldıktan veya çağrdıktan sonra, yeniden çalışması için başka bir yürütme bağlamından [engellemeyi kaldırma](#unblock) yönteminin bir çağrısıyla eşleştirmelidir. Kodunuzun, `Unblock` yöntemini çağırabilmesi için başka bir iş parçacığının bağlamını yayımlayıp `Block` gerçek yöntem çağrısının yapıldığı nokta arasında kritik bir süre olduğunu unutmayın. Bu süre boyunca, kendi nedenleri (örneğin, bir kilit almak) için sırasıyla blok ve engellemeyi kaldırma işleminde olabilecek herhangi bir yöntemi çağırmamalıdır. `Block` ve `Unblock` yöntemine yapılan çağrılar, engelleme ve engellemeyi kaldırma nedenini izlemez. Yalnızca bir nesne `Block`- `Unblock` çiftinin sahipliğini içermelidir.

Bu yöntem [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)dahil olmak üzere çeşitli özel durumlar oluşturabilir.

## <a name="dtor"></a>~ Bağlam

```cpp
virtual ~Context();
```

## <a name="currentcontext"></a>LicenseManager 'ın CurrentContext

Geçerli bağlam için bir işaretçi döndürür.

```cpp
static Context* __cdecl CurrentContext();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bağlam işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

## <a name="getid"></a>GetId

Bağlamın ait olduğu Scheduler 'da benzersiz olan bağlam için bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlamın ait olduğu zamanlayıcıda benzersiz olan bağlamı için bir tanımlayıcı.

## <a name="getschedulegroupid"></a>Getschedulegroupıd

Bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetScheduleGroupId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin dönüş değeri, bağlamın üzerinde yürütüldüğü Zamanlama grubunun anlık örneklemesi olur. Bu yöntem, geçerli bağlam dışında bir bağlamda çağrılırsa, değer döndürüldüğünden ve bundan dolayı güvenlenemez. Genellikle, bu yöntem yalnızca hata ayıklama veya izleme amacıyla kullanılır.

## <a name="getvirtualprocessorid"></a>Getvirtualprocessorıd

Bağlamın Şu anda yürütüldüğü sanal işlemci için bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetVirtualProcessorId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlam Şu anda sanal bir işlemcide yürütüleçalışıyorsa, sanal işlemci için bağlamın Şu anda yürütüldüğü bir tanımlayıcı; Aksi takdirde değer `-1`.

### <a name="remarks"></a>Açıklamalar

Bu yöntemden döndürülen değer, içeriğin üzerinde yürütüldüğü Sanal işlemcinin anlık örneklemesi olur. Bu değer, daha eski bir süre sonra geri alınamaz ve bundan dolayı güvenlenemez. Genellikle, bu yöntem yalnızca hata ayıklama veya izleme amacıyla kullanılır.

## <a name="id"></a>Numarasını

Geçerli bağlamın ait olduğu Zamanlayıcı içinde benzersiz olan geçerli bağlam için bir tanımlayıcı döndürür.

```cpp
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bağlam bir Scheduler 'a iliştirilmişse geçerli bağlam için geçerli bağlamın ait olduğu Zamanlayıcı dahilinde benzersiz olan bir tanımlayıcı; Aksi takdirde değer `-1`.

## <a name="iscurrenttaskcollectioncanceling"></a>Iscurrenttaskcollectioncanceling

Geçerli bağlamda şu anda yürütülmekte olan görev koleksiyonunun etkin bir iptal etme ortamın (veya kısa bir süre) üzerinde olup olmadığına ilişkin bir gösterge döndürür.

```cpp
static bool __cdecl IsCurrentTaskCollectionCanceling();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Zamanlayıcı çağıran içeriğe bağlıysa ve bir görev grubu bu bağlamda satır içi bir görevi yürütülerek, görev grubunun etkin bir iptal etme ortasitesinde olup olmadığı (veya kısa süre içinde) bir göstergesi. Aksi takdirde değer `false`.

## <a name="issynchronouslyblocked"></a>Issynchronouslyblocked

Bağlamın zaman uyumlu olarak engellenip engellenmeyeceğini belirler. Bir bağlam, açıkça engellemeye işaret eden bir eylemi gerçekleştirirse zaman uyumlu olarak engellenmiştir.

```cpp
virtual bool IsSynchronouslyBlocked() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlamın zaman uyumlu olarak engellenip engellenmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bir bağlam, açıkça engellemeye işaret eden bir eylemi gerçekleştirirse zaman uyumlu olarak engellenmiştir. İş parçacığı zamanlayıcıda bu, `Context::Block` yöntemine doğrudan çağrı veya `Context::Block` yöntemi kullanılarak oluşturulan bir eşitleme nesnesi olduğunu gösterir.

Bu yöntemin dönüş değeri, bağlamın zaman uyumlu olarak engellenip engellenmeyeceğini anlık bir örnektir. Bu değer, eski ve yalnızca çok özel koşullarda kullanılabilecek bir süre içinde olabilir.

## <a name="operator_delete"></a>delete işleci

`Context` bir nesne, çalışma zamanı tarafından dahili olarak yok edilir. Bu, açıkça silinemez.

```cpp
void operator delete(void* _PObject);
```

### <a name="parameters"></a>Parametreler

*_PObject*<br/>
Silinecek nesneye yönelik bir işaretçi.

## <a name="oversubscribe"></a>Oversubscribe

Bu Scheduler 'daki sanal işlemcilerin birinde çalıştırılan bir bağlamda çağrıldığında, bir kod bloğunun süresi boyunca ek bir sanal işlemciyi zamanlayıcıya çıkartır.

```cpp
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```

### <a name="parameters"></a>Parametreler

*_BeginOversubscription*<br/>
**True**ise, fazla abonelik süresi boyunca fazladan bir sanal işlemcinin eklenmesi gerektiğini belirten bir gösterge. **Yanlış**ise, fazla aboneliğin bitmesi ve önceden eklenmiş Sanal işlemcinin kaldırılması gerektiğini belirten bir gösterge kaldırılmalıdır.

## <a name="schedulegroupid"></a>Schedulegroupıd

Geçerli bağlamın üzerinde çalıştığı zamanlama grubu için bir tanımlayıcı döndürür.

```cpp
static unsigned int __cdecl ScheduleGroupId();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bağlam bir Scheduler 'a iliştirilmişse ve bir zamanlama grubu üzerinde çalışıyorsa, geçerli bağlamın üzerinde çalıştığı Zamanlayıcı grubu için bir tanımlayıcı; Aksi takdirde değer `-1`.

## <a name="unblock"></a>Kaldırabilir

Bağlamını kaldırır ve çalıştırılabilir duruma gelmesine neden olur.

```cpp
virtual void Unblock() = 0;
```

### <a name="remarks"></a>Açıklamalar

`Unblock` yöntemine yapılan bir çağrı, [blok](#block) yöntemine karşılık gelen bir çağrıdan önce gelmesi için mükemmel bir şekilde geçerlidir. `Block` ve `Unblock` yöntemlerine yapılan çağrılar doğru şekilde eşleştirildiği sürece, çalışma zamanı her iki sıralamayı da doğal olarak işler. Bir `Block` çağrısından önce gelen `Unblock` çağrısı, `Block` çağrısının etkisini geçersiz kılar.

Bu yöntemden oluşturulabilecek birkaç özel durum vardır. Bir bağlam kendi başına `Unblock` yöntemini çağırmayı denerse, bir [context_self_unblock](context-self-unblock-class.md) özel durumu oluşturulur. `Block` ve `Unblock` çağrıları düzgün şekilde eşlenmiyorsa (örneğin, şu anda çalışan bir bağlam için `Unblock` için iki çağrı yapılırsa), bir [context_unblock_unbalanced](context-unblock-unbalanced-class.md) özel durumu oluşturulur.

Kodunuzun, `Unblock` yöntemini çağırabilmesi için başka bir iş parçacığının bağlamını yayımlayıp `Block` gerçek yöntem çağrısının yapıldığı nokta arasında kritik bir süre olduğunu unutmayın. Bu süre boyunca, kendi nedenleri (örneğin, bir kilit almak) için sırasıyla blok ve engellemeyi kaldırma işleminde olabilecek herhangi bir yöntemi çağırmamalıdır. `Block` ve `Unblock` yöntemine yapılan çağrılar, engelleme ve engellemeyi kaldırma nedenini izlemez. Yalnızca bir nesne `Block` ve `Unblock` çiftinin sahipliğini içermelidir.

## <a name="virtualprocessorid"></a>Virtualprocessorıd

Geçerli bağlamın üzerinde yürütüldüğü sanal işlemci için bir tanımlayıcı döndürür.

```cpp
static unsigned int __cdecl VirtualProcessorId();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bağlam bir Scheduler 'a iliştirilmişse, geçerli bağlamın üzerinde yürütüldüğü sanal işlemci için bir tanımlayıcı; Aksi takdirde değer `-1`.

### <a name="remarks"></a>Açıklamalar

Bu yöntemden döndürülen değer, geçerli bağlamın üzerinde yürütüldüğü Sanal işlemcinin anlık örneklemesi olur. Bu değer, daha eski bir süre sonra geri alınamaz ve bundan dolayı güvenlenemez. Genellikle, bu yöntem yalnızca hata ayıklama veya izleme amacıyla kullanılır.

## <a name="yield"></a>Yield

Başka bir bağlamın yürütebilmesi için yürütmeyi verir. Üzerinde işlem yapmak için başka bir bağlam yoksa, Zamanlayıcı başka bir işletim sistemi iş parçacığı için ödeme yapabilir.

```cpp
static void __cdecl Yield();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

## <a name="yieldexecution"></a>Ödemedexecution

Başka bir bağlamın yürütebilmesi için yürütmeyi verir. Üzerinde işlem yapmak için başka bir bağlam yoksa, Zamanlayıcı başka bir işletim sistemi iş parçacığı için ödeme yapabilir.

```cpp
static void __cdecl YieldExecution();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda çağıran bağlamla ilişkili bir Zamanlayıcı yoksa, işlemin varsayılan Zamanlayıcı oluşturulması ve/veya çağırma bağlamına iliştirilmesi ile sonuçlanır.

Bu işlev, Visual Studio 2015 ' de yenidir ve [yield](#yield) işleviyle aynıdır, ancak Windows. h 'deki yield makrosu ile çakışmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
