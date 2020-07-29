---
title: IVirtualProcessorRoot Yapısı
ms.date: 11/04/2016
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
ms.openlocfilehash: 869d51144b686dd684f62b337bb90eff8a9a5589
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193958"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot Yapısı

İş parçacığı proxy 'sinin yürütebileceği donanım iş parçacığı için bir soyutlama.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IVirtualProcessorRoot:: Activate](#activate)|Yürütme bağlamı arabirimiyle ilişkili iş parçacığı proxy 'sinin `pContext` Bu sanal işlemci kökünde yürütülmeye başlamasını sağlar.|
|[IVirtualProcessorRoot::D eactivate](#deactivate)|Şu anda bu sanal işlemci kökünde çalışan iş parçacığı proxy 'sinin Yürütme bağlamını gönderme durmasına neden olur. İş parçacığı proxy 'si, yönteme yapılan bir çağrıda yürütülmeye sürdürülecek `Activate` .|
|[IVirtualProcessorRoot:: EnsureAllTasksVisible](#ensurealltasksvisible)|Tek tek işlemcilerin bellek hiyerarşisinde depolanan verilerin sistemdeki tüm işlemcilere görünür hale gelmesine neden olur. Yöntemin döndürdüğü tüm işlemcilerde tam bir bellek diliminin yürütülmesini sağlar.|
|[IVirtualProcessorRoot:: GetId](#getid)|Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

Her sanal işlemci kökünün ilişkili bir yürütme kaynağı vardır. `IVirtualProcessorRoot`Arabirim [IExecutionResource](iexecutionresource-structure.md) arabiriminden devralır. Birden çok sanal işlemci kökü, aynı temel alınan donanım iş parçacığına karşılık gelebilir.

Kaynak Yöneticisi, kaynak isteklerine yanıt olarak zamanlayıcılar 'e sanal işlemci kökleri verir. Bir zamanlayıcı, bir yürütme bağlamı ile etkinleştirerek çalışmayı gerçekleştirmek için bir sanal işlemci kökü kullanabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="ivirtualprocessorrootactivate-method"></a><a name="activate"></a>IVirtualProcessorRoot:: Activate yöntemi

Yürütme bağlamı arabirimiyle ilişkili iş parçacığı proxy 'sinin `pContext` Bu sanal işlemci kökünde yürütülmeye başlamasını sağlar.

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu sanal işlemci kökünde dağıtılacak yürütme bağlamına yönelik bir arabirim.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, yürütme bağlamı arabirimiyle ilişkilendirilmediği bir iş parçacığı proxy 'si sağlar`pContext`

`Activate`Yöntemi, kaynak yöneticisi tarafından döndürülen yeni bir sanal işlemci kökünde iş yürütmeye başlamak veya devre dışı bırakılan veya devre dışı bırakmak üzere olan bir sanal işlemci kökünde iş parçacığı proxy 'sini sürdürmek için kullanılabilir. Devre dışı bırakma hakkında daha fazla bilgi için bkz. [IVirtualProcessorRoot::D eactivate](#deactivate) . Devre dışı bırakılan bir sanal işlemci kökünü sürdürülürken, parametre `pContext` sanal işlemci kökünü devre dışı bırakmak için kullanılan parametreyle aynı olmalıdır.

Bir sanal işlemci kökü ilk kez etkinleştirildikten sonra, ve ' a yapılan çağrı çiftleri birbirini `Deactivate` `Activate` verebilir. Bu, Kaynak Yöneticisi için, kendisine `Activate` ait olan çağrıyı almadan önce bir çağrı alması için kabul edilebilir olduğu anlamına gelir `Deactivate` .

Bir sanal işlemci kökünü etkinleştirdiğinizde, bu sanal işlemci kökünün Şu anda çalışmaya meşgul olduğunu Kaynak Yöneticisi sinyaliniz. Scheduler bu kökte yürütülecek bir iş bulamazsa, `Deactivate` sanal işlemci kökünün boşta olduğunu Kaynak Yöneticisi bildiren yöntemi çağırmak beklenir. Kaynak Yöneticisi, sistemin yükünü dengelemek için bu verileri kullanır.

`invalid_argument`bağımsız değişkenin değeri varsa oluşturulur `pContext` `NULL` .

`invalid_operation`bağımsız değişken, `pContext` Bu sanal işlemci kökü tarafından en son dağıtılan Yürütme bağlamını temsil etmediği zaman oluşturulur.

Bir sanal işlemci kökünü etkinleştirme eylemi, temel alınan donanım iş parçacığının abonelik düzeyini bir tane artırır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>IVirtualProcessorRoot::D eactivate yöntemi

Şu anda bu sanal işlemci kökünde çalışan iş parçacığı proxy 'sinin Yürütme bağlamını gönderme durmasına neden olur. İş parçacığı proxy 'si, yönteme yapılan bir çağrıda yürütülmeye sürdürülecek `Activate` .

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu kök tarafından şu anda gönderilen bağlam.

### <a name="return-value"></a>Dönüş Değeri

Boole değeri. Değeri, **`true`** iş parçacığı proxy 'sinin yöntemine yapılan `Deactivate` çağrıya yanıt olarak yönteminden döndürüldüğünü gösterir `Activate` . Değeri, **`false`** iş parçacığı proxy 'sinin Kaynak Yöneticisi bir bildirim olayına yanıt olarak yönteminden döndürüldüğünü gösterir. Bir Kullanıcı modu zamanlanabilen (UMS) iş parçacığı Scheduler 'da, bu öğelerin Scheduler 'ın tamamlanma listesinde göründü olduğunu ve Scheduler 'ın bunları işlemek için gerekli olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcıda herhangi bir iş bulamadığınızda bir sanal işlemci kökünü yürütmeyi geçici olarak durdurmak için bu yöntemi kullanın. Yöntemine yapılan bir çağrı, `Deactivate` `Dispatch` sanal işlemci kökünün en son etkinleştirildiği yürütme bağlamı yönteminin içinden kaynaklanmalıdır. Diğer bir deyişle, yöntemi çağıran iş parçacığı proxy 'si, `Deactivate` Şu anda sanal işlemci kökünde yürütülmekte olan bir olmalıdır. Üzerinde yürütmekte olduğunuz bir sanal işlemci kökünde yöntemi çağırmak tanımsız davranışa neden olabilir.

Devre dışı bırakılmış bir sanal işlemci kökü, yönteme `Activate` geçirilmiş aynı bağımsız değişkenle birlikte yöntemi çağrısıyla birlikte woolabilir `Deactivate` . Zamanlayıcı, `Activate` ve yöntemlerine yapılan çağrıların `Deactivate` eşlenmesinin ve belirli bir sırada alınmaları gerekmeyeceğinden sorumludur. Kaynak Yöneticisi, `Activate` yöntemi için amaçlanan yönteme çağrı almadan önce bir çağrı almayı işleyebilir `Deactivate` .

Bir sanal işlemci kök Awakens ve döndürülen değer `Deactivate` değer ise **`false`** , Scheduler YÖNTEMI aracılığıyla UMS tamamlama listesini sorgulayıp, daha `IUMSCompletionList::GetUnblockNotifications` sonra `Deactivate` yöntemi yeniden çağırmalıdır. Bu, yöntem değeri döndürdüğünden Bu süre kadar tekrarlanmalıdır `Deactivate` **`true`** .

`invalid_argument`bağımsız değişkenin `pContext` DEĞERI null ise oluşturulur.

`invalid_operation`sanal işlemci kökü hiç etkinleştirilmemişse veya bağımsız değişken `pContext` Bu sanal işlemci kökü tarafından en son dağıtılan Yürütme bağlamını temsil etmediği zaman oluşturulur.

Sanal işlemci kökünü devre dışı bırakma eylemi, temel alınan donanım iş parçacığının abonelik düzeyini bir azaltır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>IVirtualProcessorRoot:: EnsureAllTasksVisible yöntemi

Tek tek işlemcilerin bellek hiyerarşisinde depolanan verilerin sistemdeki tüm işlemcilere görünür hale gelmesine neden olur. Yöntemin döndürdüğü tüm işlemcilerde tam bir bellek diliminin yürütülmesini sağlar.

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu sanal işlemci kökü tarafından şu anda gönderilen bağlam.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, bir sanal işlemci kökünü devre dışı bırakmak istediğinizde, yeni çalışmanın Scheduler 'a eklenmesini istediğiniz durumlarda yararlı olabilir. Performans nedenleriyle, bir bellek engeli yürütmeden iş öğelerini zamanlayıcıya eklemeyi seçebilirsiniz. Bu, bir işlemci üzerinde çalışan iş öğelerinin, tüm diğer işlemcilere hemen görünmeyeceği anlamına gelir. Bu yöntemi yöntemiyle birlikte kullanarak, Scheduler `Deactivate` 'nizin, iş öğeleri Zamanlayıcınızın koleksiyonlarında bulunan tüm sanal işlemci köklerinin devre dışı olmamasını sağlayabilirsiniz.

Yöntemine yapılan bir çağrı, `EnsureAllTasksVisibleThe` `Dispatch` sanal işlemci kökünün en son etkinleştirildiği yürütme bağlamı yönteminin içinden kaynaklanmalıdır. Diğer bir deyişle, yöntemi çağıran iş parçacığı proxy 'si, `EnsureAllTasksVisible` Şu anda sanal işlemci kökünde yürütülmekte olan bir olmalıdır. Üzerinde yürütmekte olduğunuz bir sanal işlemci kökünde yöntemi çağırmak tanımsız davranışa neden olabilir.

`invalid_argument`bağımsız değişkenin değeri varsa oluşturulur `pContext` `NULL` .

`invalid_operation`sanal işlemci kökü hiç etkinleştirilmemişse veya bağımsız değişken `pContext` Bu sanal işlemci kökü tarafından en son dağıtılan Yürütme bağlamını temsil etmediği zaman oluşturulur.

## <a name="ivirtualprocessorrootgetid-method"></a><a name="getid"></a>IVirtualProcessorRoot:: GetID Yöntemi

Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tamsayı tanımlayıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
