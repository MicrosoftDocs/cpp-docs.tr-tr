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
ms.openlocfilehash: f642a29d0a80568f7a5f2a5e89f6951d4819243e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364255"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot Yapısı

İş parçacığı proxy'si yürütülebileceği bir donanım iş parçacığı için soyutlama.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[iVirtualProcessorRoot::Etkinleştir](#activate)|Yürütme bağlamı arabirimiyle `pContext` ilişkili iş parçacığı proxy'sinin bu sanal işlemci kökünde yürütmeye başlamasına neden olur.|
|[IVirtualProcessorRoot::Deactivate](#deactivate)|Yürütme bağlamını göndermeyi durdurmak için şu anda bu sanal işlemci köküüzerinde çalıştırıyorum iş parçacığı proxy neden olur. İş parçacığı proxy `Activate` yöntemiiçin bir çağrı yürütme devam edecektir.|
|[iVirtualProcessorRoot::Tüm Görevlerin Görünür Olmasını Sağlar](#ensurealltasksvisible)|Tek tek işlemcilerin bellek hiyerarşisinde depolanan verilerin sistemdeki tüm işlemciler tarafından görülebilmesine neden olur. Yöntem dönmeden önce tüm işlemcilerde tam bellek çitinin yürütülmesini sağlar.|
|[IVirtualProcessorRoot::Getid](#getid)|Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

Her sanal işlemci kökilişkili bir yürütme kaynağı vardır. `IVirtualProcessorRoot` [Arabirim, IExecutionResource](iexecutionresource-structure.md) arabiriminden devralır. Birden çok sanal işlemci kökü aynı temel donanım iş parçacığına karşılık gelebilir.

Kaynak Yöneticisi, kaynak isteklerine yanıt olarak zamanlayıcılara sanal işlemci kökleri verir. Zamanlayıcı, yürütme bağlamıyla etkinleştirerek işi gerçekleştirmek için sanal işlemci kökünü kullanabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="ivirtualprocessorrootactivate-method"></a><a name="activate"></a>iVirtualProcessorRoot::Etkinleştirme Yöntemi

Yürütme bağlamı arabirimiyle `pContext` ilişkili iş parçacığı proxy'sinin bu sanal işlemci kökünde yürütmeye başlamasına neden olur.

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
Bu sanal işlemci kökünde gönderilecek yürütme bağlamına bir arabirim.

### <a name="remarks"></a>Açıklamalar

Bir yürütme bağlamı arabirimi ile ilişkili değilse Kaynak Yöneticisi bir iş parçacığı proxy sağlar`pContext`

Yöntem, `Activate` Kaynak Yöneticisi tarafından döndürülen yeni bir sanal işlemci kökü üzerinde çalışmayı yürütmeye başlamak veya devre dışı bırakılmış veya devre dışı bırakmak üzere olan sanal işlemci kökündeki iş parçacığı proxy'sini devam ettirmek için kullanılabilir. Bkz. [IVirtualProcessorRoot::Ddevre](#deactivate) dışı bırakma hakkında daha fazla bilgi için etkinleştirin. Devre dışı bırakılmış bir sanal işlemci kökünü devam `pContext` ettirirken, parametre sanal işlemci kökünü devre dışı bırakmak için kullanılan parametreyle aynı olmalıdır.

Sanal işlemci kökü ilk kez etkinleştirildikten sonra, sonraki `Deactivate` çift `Activate` çağrılar birbiriyle yarışabilir ve diğerleriyle yarışabilir. Bu, Kaynak Yöneticisi'nin, amaçlandığını niçin aradığı `Activate` `Deactivate` aramayı almadan önce bir çağrı almasının kabul edilebilir olduğu anlamına gelir.

Sanal işlemci kökünü etkinleştirdiğinizde, Kaynak Yöneticisi'ne bu sanal işlemci kökünün şu anda işle meşgul olduğunu bildiren bir işaret verirsiniz. Zamanlayıcınız bu köküzerinde yürütülecek herhangi bir iş bulamıyorsa, Kaynak Yöneticisi'ne sanal işlemci kökünü boşta olduğunu bildiren `Deactivate` yöntemi çağırması beklenir. Kaynak Yöneticisi, sistemi yüklemek için bu verileri kullanır.

`invalid_argument`bağımsız değişken `pContext` in değeri `NULL`varsa atılır.

`invalid_operation`bağımsız değişken, `pContext` bu sanal işlemci kökü tarafından en son gönderilen yürütme bağlamını temsil etmiyorsa atılır.

Sanal işlemci kökünü etkinleştirme eylemi, temel donanım iş parçacığının abonelik düzeyini bir artırır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>IVirtualProcessorRoot::Deactivate Yöntemi

Yürütme bağlamını göndermeyi durdurmak için şu anda bu sanal işlemci köküüzerinde çalıştırıyorum iş parçacığı proxy neden olur. İş parçacığı proxy `Activate` yöntemiiçin bir çağrı yürütme devam edecektir.

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
Şu anda bu kök tarafından gönderilen bağlam.

### <a name="return-value"></a>Dönüş Değeri

Boole değeri. **True** değeri, iş parçacığı `Deactivate` `Activate` proxy'sinin yönteme yapılan çağrıya yanıt olarak yöntemden döndüğünü gösterir. Bir değer, kaynak yöneticisindeki bir bildirim olayına yanıt olarak iş parçacığı proxy'sinin yöntemden geri döndüğünü `false` gösterir. Kullanıcı modu zamanlanabilir (UMS) iş parçacığı zamanlayıcısında, bu, maddelerin zamanlayıcının tamamlanma listesinde göründüğünü ve zamanlayıcının bunları işlemek için gerekli olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcınızda herhangi bir iş bulamadığınızda sanal işlemci kökünü yürütmeyi geçici olarak durdurmak için bu yöntemi kullanın. Yönteme `Deactivate` yapılan bir çağrı, sanal `Dispatch` işlemci kökünün en son etkinleştirilen yürütme bağlamı yöntemi nin içinden kaynaklanmalıdır. Başka bir deyişle, `Deactivate` yöntemi çağıran iş parçacığı proxy şu anda sanal işlemci köküüzerinde yürütülen biri olmalıdır. Yöntemin yürütülmediğiniz sanal işlemci kökünde çağrılması tanımlanmamış davranışlara neden olabilir.

Devre dışı bırakılmış bir sanal işlemci kökü, `Activate` `Deactivate` yönteme geçirilen aynı bağımsız değişkenle yönteme yapılan bir çağrıyla uyandırılabilir. Zamanlayıcı, çağrıların ve `Activate` `Deactivate` yöntemlerin eşleştirilmesini sağlamaktan sorumludur, ancak belirli bir sırada alınması gerekmez. Kaynak Yöneticisi, metnin `Activate` amacı nın geldiği `Deactivate` yönteme çağrı almadan önce yönteme çağrı almayı işleyebilir.

Sanal işlemci kökü uyanır ve `Deactivate` yöntemden gelen geri dönüş değeri **yanlış**ise, zamanlayıcı `IUMSCompletionList::GetUnblockNotifications` yöntem aracılığıyla UMS tamamlama listesini sorgulamalı, `Deactivate` bu bilgilere göre hareket etmeli ve daha sonra yöntemi yeniden aramalıdır. Bu yöntem değeri `Deactivate` `true`döndürür gibi bir zaman akadar tekrarlanmalıdır.

`invalid_argument`bağımsız değişken `pContext` NULL değerine sahipse atılır.

`invalid_operation`sanal işlemci kökü hiç etkinleştirilmemişse veya `pContext` bağımsız değişken bu sanal işlemci kökü tarafından en son gönderilen yürütme bağlamını temsil etmiyorsa atılır.

Sanal işlemci kökünü devre dışı düşürme eylemi, temel donanım iş parçacığının abonelik düzeyini bir azaltır. Abonelik düzeyleri hakkında daha fazla bilgi için [bkz: IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>iVirtualProcessorRoot::EnsureAllTasksVisible Yöntemi

Tek tek işlemcilerin bellek hiyerarşisinde depolanan verilerin sistemdeki tüm işlemciler tarafından görülebilmesine neden olur. Yöntem dönmeden önce tüm işlemcilerde tam bellek çitinin yürütülmesini sağlar.

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
Şu anda bu sanal işlemci kökü tarafından gönderilen bağlam.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcıya yeni çalışma eklenmesiyle sanal işlemci kökünün devre dışı bırakılmasını eşitlemek istediğinizde bu yöntem yararlı olabilir. Performans nedenleriyle, bellek engelini yürütmeden zamanlayıcınıza iş öğeleri eklemeye karar verebilirsiniz, bu da bir işlemcide çalıştırılan bir iş parçacığı tarafından eklenen iş öğelerinin diğer tüm işlemciler tarafından hemen görülememesi anlamına gelir. Yöntemle `Deactivate` birlikte bu yöntemi kullanarak zamanlayıcınızın tüm sanal işlemci köklerini devre dışı bırakmadığından emin olabilirsiniz.

Yönteme `EnsureAllTasksVisibleThe` yapılan bir çağrı, sanal `Dispatch` işlemci kökünün en son etkinleştirilen yürütme bağlamı yöntemi nin içinden kaynaklanmalıdır. Başka bir deyişle, `EnsureAllTasksVisible` yöntemi çağıran iş parçacığı proxy şu anda sanal işlemci köküüzerinde yürütülen biri olmalıdır. Yöntemin yürütülmediğiniz sanal işlemci kökünde çağrılması tanımlanmamış davranışlara neden olabilir.

`invalid_argument`bağımsız değişken `pContext` in değeri `NULL`varsa atılır.

`invalid_operation`sanal işlemci kökü hiç etkinleştirilmemişse veya `pContext` bağımsız değişken bu sanal işlemci kökü tarafından en son gönderilen yürütme bağlamını temsil etmiyorsa atılır.

## <a name="ivirtualprocessorrootgetid-method"></a><a name="getid"></a>iVirtualProcessorRoot::Getid Yöntemi

Sanal işlemci kökü için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonda tanımlayıcısı.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
