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
ms.openlocfilehash: 60757b0edea6b60d080c2175d4df4830ffec0cc3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139890"
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
|[IVirtualProcessorRoot:: Activate](#activate)|`pContext` yürütme bağlamı arabirimiyle ilişkili iş parçacığı proxy 'sinin bu sanal işlemci kökünde yürütülmeye başlamasını sağlar.|
|[IVirtualProcessorRoot::D eactivate](#deactivate)|Şu anda bu sanal işlemci kökünde çalışan iş parçacığı proxy 'sinin Yürütme bağlamını gönderme durmasına neden olur. İş parçacığı proxy 'si, `Activate` metoduna yapılan bir çağrıda yürütmeyi sürdürecek.|
|[IVirtualProcessorRoot:: EnsureAllTasksVisible](#ensurealltasksvisible)|Tek tek işlemcilerin bellek hiyerarşisinde depolanan verilerin sistemdeki tüm işlemcilere görünür hale gelmesine neden olur. Yöntemin döndürdüğü tüm işlemcilerde tam bir bellek diliminin yürütülmesini sağlar.|
|[IVirtualProcessorRoot:: GetId](#getid)|Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

Her sanal işlemci kökünün ilişkili bir yürütme kaynağı vardır. `IVirtualProcessorRoot` arabirimi [IExecutionResource](iexecutionresource-structure.md) arabiriminden devralır. Birden çok sanal işlemci kökü, aynı temel alınan donanım iş parçacığına karşılık gelebilir.

Kaynak Yöneticisi, kaynak isteklerine yanıt olarak zamanlayıcılar 'e sanal işlemci kökleri verir. Bir zamanlayıcı, bir yürütme bağlamı ile etkinleştirerek çalışmayı gerçekleştirmek için bir sanal işlemci kökü kullanabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="activate"></a>IVirtualProcessorRoot:: Activate yöntemi

`pContext` yürütme bağlamı arabirimiyle ilişkili iş parçacığı proxy 'sinin bu sanal işlemci kökünde yürütülmeye başlamasını sağlar.

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu sanal işlemci kökünde dağıtılacak yürütme bağlamına yönelik bir arabirim.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, yürütme bağlamı arabirimiyle ilişkilendirilmediği bir iş parçacığı proxy 'si sağlar `pContext`

`Activate` yöntemi, Kaynak Yöneticisi tarafından döndürülen yeni bir sanal işlemci kökünde iş yürütmeye veya devre dışı bırakılmış veya devre dışı bırakmak üzere olan bir sanal işlemci kökünde iş parçacığı proxy 'sini sürdürmeye başlamak için kullanılabilir. Devre dışı bırakma hakkında daha fazla bilgi için bkz. [IVirtualProcessorRoot::D eactivate](#deactivate) . Devre dışı bırakılmış bir sanal işlemci kökünü sürdürülürken, `pContext` parametresi, sanal işlemci kökünü devre dışı bırakmak için kullanılan parametreyle aynı olmalıdır.

Bir sanal işlemci kökü ilk kez etkinleştirildikten sonra, `Deactivate` ve `Activate` yapılan çağrıların sonraki çiftleri birbirleriyle yarış olabilir. Bu, Kaynak Yöneticisi `Activate` bir çağrı almak için, onun amaçlanan `Deactivate` çağrısını almadan önce kabul edilebilir olduğu anlamına gelir.

Bir sanal işlemci kökünü etkinleştirdiğinizde, bu sanal işlemci kökünün Şu anda çalışmaya meşgul olduğunu Kaynak Yöneticisi sinyaliniz. Scheduler bu kökte yürütülecek bir iş bulamazsa, sanal işlemci kökünün boşta olduğunu Kaynak Yöneticisi bildiren `Deactivate` yöntemi çağırmak beklenir. Kaynak Yöneticisi, sistemin yükünü dengelemek için bu verileri kullanır.

`invalid_argument`, `pContext` bağımsız değişken `NULL`değere sahipse oluşturulur.

`invalid_operation`, `pContext` bağımsız değişkeni bu sanal işlemci kökü tarafından en son dağıtılan Yürütme bağlamını temsil etmediği zaman oluşturulur.

Bir sanal işlemci kökünü etkinleştirme eylemi, temel alınan donanım iş parçacığının abonelik düzeyini bir tane artırır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="deactivate"></a>IVirtualProcessorRoot::D eactivate yöntemi

Şu anda bu sanal işlemci kökünde çalışan iş parçacığı proxy 'sinin Yürütme bağlamını gönderme durmasına neden olur. İş parçacığı proxy 'si, `Activate` metoduna yapılan bir çağrıda yürütmeyi sürdürecek.

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu kök tarafından şu anda gönderilen bağlam.

### <a name="return-value"></a>Dönüş Değeri

Boole değeri. **True** değeri, iş parçacığı proxy 'sinin `Activate` yöntemine yapılan çağrıya yanıt olarak `Deactivate` yönteminden döndürüldüğünü gösterir. `false` değeri, iş parçacığı proxy 'sinin, Kaynak Yöneticisi bir bildirim olayına yanıt olarak yönteminden döndürüldüğünü gösterir. Bir Kullanıcı modu zamanlanabilen (UMS) iş parçacığı Scheduler 'da, bu öğelerin Scheduler 'ın tamamlanma listesinde göründü olduğunu ve Scheduler 'ın bunları işlemek için gerekli olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcıda herhangi bir iş bulamadığınızda bir sanal işlemci kökünü yürütmeyi geçici olarak durdurmak için bu yöntemi kullanın. `Deactivate` yöntemine yapılan bir çağrı, sanal işlemci kökünün en son etkinleştirildiği yürütme bağlamının `Dispatch` yönteminin içinden kaynaklanmalıdır. Diğer bir deyişle, `Deactivate` yöntemini çağıran iş parçacığı proxy 'si, şu anda sanal işlemci kökünde yürütülmekte olan bir değer olmalıdır. Üzerinde yürütmekte olduğunuz bir sanal işlemci kökünde yöntemi çağırmak tanımsız davranışa neden olabilir.

Devre dışı bırakılmış bir sanal işlemci kökü, `Deactivate` yöntemine geçirilmiş aynı bağımsız değişkenle `Activate` yöntemine yapılan bir çağrıyla kesilebilir. Zamanlayıcı, `Activate` ve `Deactivate` yöntemlerine yapılan çağrıların eşlenmesinin ve belirli bir sırada alınmaları gerekmeyeceğinden sorumludur. Kaynak Yöneticisi, `Activate` yöntemine bir çağrı almayı, onun amaçlanan `Deactivate` yöntemine bir çağrı almadan önce işleyebilir.

Bir sanal işlemci kök Awakens ve dönüş değeri `Deactivate` yönteminden değeri **false**ise zamanlayıcı, `IUMSCompletionList::GetUnblockNotifications` YÖNTEMI aracılığıyla UMS tamamlama listesini sorgulayıp, daha sonra `Deactivate` yöntemini yeniden çağırmalıdır. `Deactivate` yöntemi `true`değerini döndürdüğünden Bu zaman yinelenmelidir.

bağımsız değişken `pContext` NULL değeri içeriyorsa `invalid_argument` oluşturulur.

sanal işlemci kökü hiç etkinleştirilmemişse veya `pContext` bağımsız değişkeni bu sanal işlemci kökü tarafından en son dağıtılan Yürütme bağlamını temsil etmediği `invalid_operation` oluşturulur.

Sanal işlemci kökünü devre dışı bırakma eylemi, temel alınan donanım iş parçacığının abonelik düzeyini bir azaltır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ensurealltasksvisible"></a>IVirtualProcessorRoot:: EnsureAllTasksVisible yöntemi

Tek tek işlemcilerin bellek hiyerarşisinde depolanan verilerin sistemdeki tüm işlemcilere görünür hale gelmesine neden olur. Yöntemin döndürdüğü tüm işlemcilerde tam bir bellek diliminin yürütülmesini sağlar.

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu sanal işlemci kökü tarafından şu anda gönderilen bağlam.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, bir sanal işlemci kökünü devre dışı bırakmak istediğinizde, yeni çalışmanın Scheduler 'a eklenmesini istediğiniz durumlarda yararlı olabilir. Performans nedenleriyle, bir bellek engeli yürütmeden iş öğelerini zamanlayıcıya eklemeyi seçebilirsiniz. Bu, bir işlemci üzerinde çalışan iş öğelerinin, tüm diğer işlemcilere hemen görünmeyeceği anlamına gelir. `Deactivate` yöntemiyle birlikte bu yöntemi kullanarak, Scheduler 'ın, iş öğeleri Zamanlayıcınızın koleksiyonlarında bulunan tüm sanal işlemci köklerinin devre dışı olmamasını sağlayabilirsiniz.

`EnsureAllTasksVisibleThe` yöntemine yapılan bir çağrı, sanal işlemci kökünün en son etkinleştirildiği yürütme bağlamının `Dispatch` yönteminin içinden kaynaklanmalıdır. Diğer bir deyişle, `EnsureAllTasksVisible` yöntemini çağıran iş parçacığı proxy 'si, şu anda sanal işlemci kökünde yürütülmekte olan bir değer olmalıdır. Üzerinde yürütmekte olduğunuz bir sanal işlemci kökünde yöntemi çağırmak tanımsız davranışa neden olabilir.

`invalid_argument`, `pContext` bağımsız değişken `NULL`değere sahipse oluşturulur.

sanal işlemci kökü hiç etkinleştirilmemişse veya `pContext` bağımsız değişkeni bu sanal işlemci kökü tarafından en son dağıtılan Yürütme bağlamını temsil etmediği `invalid_operation` oluşturulur.

## <a name="getid"></a>IVirtualProcessorRoot:: GetID Yöntemi

Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tamsayı tanımlayıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
