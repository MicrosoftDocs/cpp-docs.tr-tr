---
title: IExecutionContext Yapısı
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 45d65a5e16121d39233c3ceb801933aa1f5a5f8e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138908"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext Yapısı

Belirli bir sanal işlemci üzerinde çalışabilen ve birlikte çalışan içerik anahtarlamalı bir yürütme bağlamına yönelik arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IExecutionContext;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IExecutionContext::D ispatch](#dispatch)|Bir iş parçacığı proxy 'si belirli bir yürütme bağlamını yürütmeye başladığında çağrılan yöntem. Bu, Scheduler için ana çalışan yordamı olmalıdır.|
|[IExecutionContext:: GetId](#getid)|Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionContext:: GetProxy](#getproxy)|Bu bağlamı yürüten iş parçacığı proxy 'sine bir arabirim döndürür.|
|[IExecutionContext:: GetScheduler](#getscheduler)|Bu yürütme bağlamının ait olduğu Scheduler 'a bir arabirim döndürür.|
|[IExecutionContext:: SetProxy](#setproxy)|Bir iş parçacığı proxy 'sini bu yürütme bağlamıyla ilişkilendirir. İlişkili iş parçacığı proxy 'si, bağlamın `Dispatch` metodunu yürütmeye başlamadan önce bu yöntemi hemen çağırır.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi ile arabirimleri olan özel bir Zamanlayıcı uygularsanız `IExecutionContext` arabirimini uygulamanız gerekir. Kaynak Yöneticisi tarafından oluşturulan iş parçacıkları `IExecutionContext::Dispatch` yöntemini yürüterek Scheduler adına iş yapar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionContext`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="dispatch"></a>IExecutionContext::D ispatch yöntemi

Bir iş parçacığı proxy 'si belirli bir yürütme bağlamını yürütmeye başladığında çağrılan yöntem. Bu, Scheduler için ana çalışan yordamı olmalıdır.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatchState*<br/>
Bu yürütme bağlamının dağıtıldığı duruma yönelik bir işaretçi. Dağıtım durumu hakkında daha fazla bilgi için bkz. [DispatchState](dispatchstate-structure.md).

## <a name="getid"></a>IExecutionContext:: GetID Yöntemi

Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Arabirimi, Kaynak Yöneticisi tarafından sağlanan yöntemlere parametre olarak kullanmadan önce `IExecutionContext` arabirimini uygulayan nesne için benzersiz bir tanımlayıcı elde etmek üzere `GetExecutionContextId` yöntemini kullanmanız gerekir. `GetId` işlevi çağrıldığında aynı tanımlayıcıyı döndürmeli.

Farklı bir kaynaktan alınan bir tanımlayıcı, tanımsız davranışa neden olabilir.

## <a name="getproxy"></a>IExecutionContext:: GetProxy yöntemi

Bu bağlamı yürüten iş parçacığı proxy 'sine bir arabirim döndürür.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IThreadProxy` arabirimi. Yürütme bağlamının iş parçacığı proxy 'si `SetProxy`çağrısıyla başlatılmamışsa, işlevin `NULL`döndürmesi gerekir.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, `SetProxy` yöntemini bir yürütme bağlamında, `Dispatch` yöntemine bir parametre olarak girmeden önce bir `IThreadProxy` arabirimi ile çağırır. Bu bağımsız değişkeni depolamanız ve `GetProxy()`çağrılarında geri döndürülmesi beklenmektedir.

## <a name="getscheduler"></a>IExecutionContext:: GetScheduler yöntemi

Bu yürütme bağlamının ait olduğu Scheduler 'a bir arabirim döndürür.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IScheduler` arabirimi.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi tarafından sağlanan yöntemlere bir parametre olarak kullanmadan önce, geçerli bir `IScheduler` arabirimiyle Yürütme bağlamını başlatmak gerekir.

## <a name="setproxy"></a>IExecutionContext:: SetProxy yöntemi

Bir iş parçacığı proxy 'sini bu yürütme bağlamıyla ilişkilendirir. İlişkili iş parçacığı proxy 'si, bağlamın `Dispatch` metodunu yürütmeye başlamadan önce bu yöntemi hemen çağırır.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parametreler

*pThreadProxy*<br/>
Bu yürütme bağlamına `Dispatch` yöntemi girmek üzere iş parçacığı proxy 'sine yönelik bir arabirim.

### <a name="remarks"></a>Açıklamalar

`pThreadProxy` parametresini kaydetmeniz ve `GetProxy` yöntemine yapılan bir çağrıda döndürülmesi beklenmektedir. Kaynak Yöneticisi, iş parçacığı proxy 'si `Dispatch` yöntemini yürütürken yürütme bağlamıyla ilişkili iş parçacığı proxy 'sinin değişmeyecek olmasını güvence altına alır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)
