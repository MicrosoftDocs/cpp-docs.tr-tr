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
ms.openlocfilehash: 6e3f874aa7c20494483172d7c7c3efee362cf6a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569877"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot Yapısı

Bir Özet donanım iş parçacığı üzerinde bir iş parçacığı proxy'sini yürütebilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ivirtualprocessorroot::Activate](#activate)|Yürütme bağlamı arabirimiyle ilişkilendirilen iş parçacığı proxy'sini neden `pContext` bu sanal işlemci kökünde Yürütülüyor başlatmak için.|
|[Ivirtualprocessorroot::Deactivate](#deactivate)|Geçerli yürütme bağlamı gönderme durdurmak için bu sanal işlemci kökünde Yürütülüyor iş parçacığı proxy'sini neden olur. Çağrı sırasında yürütme iş parçacığı proxy'sini devam edecek `Activate` yöntemi.|
|[Ivirtualprocessorroot::ensurealltasksvisible](#ensurealltasksvisible)|Sistemdeki tüm işlemcileri için görünür hale gelmiş bellek hiyerarşideki tek işlemci depolanan verilerin neden olur. Bu, tüm işlemcilerin yöntemi döndürmeden önce tam bellek sınırı yürütüldüğünü sağlar.|
|[Ivirtualprocessorroot::GetID](#getid)|Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

Her sanal işlemci kökünde bir yürütme ilişkili kaynak vardır. `IVirtualProcessorRoot` Arabirimi devralır [Iexecutionresource](iexecutionresource-structure.md) arabirimi. Birden çok sanal işlemci kökü için aynı temel alınan donanım iş parçacığı karşılık gelebilir.

Resource Manager sanal işlemci kökü kaynaklar için isteklere planlayıcılar için verir. Bir Zamanlayıcı, bir sanal işlemci kök, bir yürütme bağlamıyla etkinleştirerek çalışmayı gerçekleştirmek için kullanabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Iexecutionresource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="activate"></a>  Ivirtualprocessorroot::Activate yöntemi

Yürütme bağlamı arabirimiyle ilişkilendirilen iş parçacığı proxy'sini neden `pContext` bu sanal işlemci kökünde Yürütülüyor başlatmak için.

```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu sanal işlemci kökünde dağıtılacağı yürütme bağlamı için bir arabirim.

### <a name="remarks"></a>Açıklamalar

Bir yürütme bağlamı arabirimi ile ilişkili değilse, kaynak yöneticisi bir iş parçacığı proxy'sini sağlayacak `pContext`

`Activate` Yöntemi, kaynak yöneticisi tarafından döndürülen yeni bir sanal işlemci kökünde iş yürütmeye başlamak için ya da devre dışı bıraktı veya devre dışı bırakmak için bir sanal işlemci kökünde iş parçacığı proxy'sini devam etmek için kullanılabilir. Bkz: [Ivirtualprocessorroot::Deactivate](#deactivate) devre dışı bırakma hakkında daha fazla bilgi için. Ne zaman, sürdürme devre dışı bırakılan sanal işlemci kök parametresi `pContext` sanal işlemci kökü devre dışı bırakmak için kullanılan parametresi ile aynı olmalıdır.

Bir sanal işlemci kök, ilk kez, çağrıları izleyen çiftlerini etkinleştirildikten sonra `Deactivate` ve `Activate` birbiriyle yarışını. Bu kaynak için bir çağrı almak için Yöneticisi için kabul edilebilir olduğu anlamına gelir `Activate` aldığı önce `Deactivate` çağrı yöneliktir.

Bir sanal işlemci kökünde etkinleştirdiğinizde, bu sanal işlemci kökü ile iş şu anda meşgul Resource Manager'a sinyal. Bu kök yürütülecek herhangi bir iş, Zamanlayıcı bulamazsanız, çağrılacak beklenmektedir `Deactivate` Resource Manager sanal işlemci kökü boşta olduğunu bildiren yöntemi. Resource Manager, Yük Dengeleme sistemi için bu verileri kullanır.

`invalid_argument` oluşturulur bağımsız değişken `pContext` değerine sahip `NULL`.

`invalid_operation` oluşturulur bağımsız değişken `pContext` bu sanal işlemci kök tarafından en son postasıdan yürütme bağlamı temsil etmiyor.

Bir sanal işlemci kökü etkinleştirme işlemi temel alınan donanım iş parçacığı abonelik düzeyini artırır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="deactivate"></a>  Ivirtualprocessorroot::Deactivate yöntemi

Geçerli yürütme bağlamı gönderme durdurmak için bu sanal işlemci kökünde Yürütülüyor iş parçacığı proxy'sini neden olur. Çağrı sırasında yürütme iş parçacığı proxy'sini devam edecek `Activate` yöntemi.

```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu kök tarafından şu anda dağıtıldığı bağlamı.

### <a name="return-value"></a>Dönüş Değeri

Bir Boole değeri. Değerini **true** öğesinden döndürülen iş parçacığı proxy'sini gösterir `Deactivate` yanıt olarak bir çağrı yöntemi `Activate` yöntemi. Değerini `false` Kaynak Yöneticisi'nde bir bildirim olaya yanıt olarak yönteminden döndürülen iş parçacığı proxy'sini gösterir. Bir kullanıcı modunda zamanlanabilen (UMS) iş parçacığı Zamanlayıcısı, bu öğeleri scheduler'ın tamamlama listesinde görüntülenmektedir ve bunları işlemek için Zamanlayıcı gerekli gösterir.

### <a name="remarks"></a>Açıklamalar

Scheduler işlerinizi bulamadığında sanal işlemci kökünde yürütülürken geçici olarak durdurmak için bu yöntemi kullanın. Bir çağrı `Deactivate` yöntemi gerekir kaynaklanan içinden `Dispatch` yürütme bağlamı yöntemi sanal işlemci kökü ile son etkinleştirildi. Diğer bir deyişle, çağırma iş parçacığı proxy'sini `Deactivate` yöntemi sanal işlemci kökünde Yürütülüyor biri olması gerekir. Yöntemi, üzerinde yürütülen olmayan bir sanal işlemci kökünde çağırma tanımsız davranışlara neden.

Devre dışı bırakılan sanal işlemci kök çağrısı ile uyandırılabilir `Activate` yöntemiyle için geçirilen bağımsız değişken `Deactivate` yöntemi. Zamanlayıcı, çağrılar sağlamaktan sorumludur `Activate` ve `Deactivate` yöntemleri halindedir ancak belirli bir sırayla alınabilmesi için gerekli değildir. Kaynak Yöneticisi için bir çağrı alma işleyebilir `Activate` çağrısı almadan önce yöntem `Deactivate` yöntemi yöneliktir.

Bir sanal işlemci kökünde awakens varsa ve dönüş değeri `Deactivate` yöntemdir değeri **false**, Zamanlayıcı UMS tamamlanma listesi aracılığıyla sorgu `IUMSCompletionList::GetUnblockNotifications` yöntemi, bu bilgileri üzerinde işlem yapma ve ardından Daha sonra arama `Deactivate` yeniden yöntemi. Bu tür sürede kadar tekrarlanmalıdır `Deactivate` yöntemi değeri döndürür `true`.

`invalid_argument` oluşturulur bağımsız değişken `pContext` NULL değere sahip.

`invalid_operation` Sanal işlemci kökü etkinleştirmemiştir değilse, durum veya bağımsız değişken `pContext` bu sanal işlemci kök tarafından en son postasıdan yürütme bağlamı temsil etmiyor.

Sanal işlemci kökü devre dışı bırakma işlemi temel alınan donanım iş parçacığının abonelik düzeyinde birer birer azaltır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz. [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="ensurealltasksvisible"></a>  Ivirtualprocessorroot::ensurealltasksvisible yöntemi

Sistemdeki tüm işlemcileri için görünür hale gelmiş bellek hiyerarşideki tek işlemci depolanan verilerin neden olur. Bu, tüm işlemcilerin yöntemi döndürmeden önce tam bellek sınırı yürütüldüğünü sağlar.

```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Bu sanal işlemci kök tarafından şu anda dağıtıldığı bağlamı.

### <a name="remarks"></a>Açıklamalar

Bir sanal işlemci kökünde devre dışı bırakma Zamanlayıcı yeni işe eklenmesi ile eşitlemek istediğiniz zaman bu yöntem yararlı bulabilirsiniz. Performansla ilgili nedenlerden dolayı bir işlemci üzerinde yürütülen bir iş parçacığı tarafından eklenen iş öğeleri için tüm işlemcilerin hemen görünür olmadığı anlamına gelir bir bellek engel çalıştırmadan scheduler için iş öğelerini eklemeye karar verebilirsiniz. Bu yöntem ile birlikte kullanarak `Deactivate` kökleri iş öğeleri, scheduler'ın koleksiyonlarında varken yöntemi scheduler tüm sanal işlemci devre dışı değildir, sağlayabilirsiniz.

Bir çağrı `EnsureAllTasksVisibleThe` yöntemi gerekir kaynaklanan içinden `Dispatch` yürütme bağlamı yöntemi sanal işlemci kökü ile son etkinleştirildi. Diğer bir deyişle, çağırma iş parçacığı proxy'sini `EnsureAllTasksVisible` yöntemi sanal işlemci kökünde Yürütülüyor biri olması gerekir. Yöntemi, üzerinde yürütülen olmayan bir sanal işlemci kökünde çağırma tanımsız davranışlara neden.

`invalid_argument` oluşturulur bağımsız değişken `pContext` değerine sahip `NULL`.

`invalid_operation` Sanal işlemci kökü etkinleştirmemiştir değilse, durum veya bağımsız değişken `pContext` bu sanal işlemci kök tarafından en son postasıdan yürütme bağlamı temsil etmiyor.

##  <a name="getid"></a>  Ivirtualprocessorroot::GetID metodu

Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tamsayı tanımlayıcısı.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
