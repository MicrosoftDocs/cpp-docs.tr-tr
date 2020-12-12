---
description: ': IExecutionContext yapısı hakkında daha fazla bilgi'
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
ms.openlocfilehash: 90802229e878546383f683bc99ffedc9cb5411af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122193"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext Yapısı

Belirli bir sanal işlemci üzerinde çalışabilen ve birlikte çalışan içerik anahtarlamalı bir yürütme bağlamına yönelik arabirim.

## <a name="syntax"></a>Syntax

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
|[IExecutionContext:: SetProxy](#setproxy)|Bir iş parçacığı proxy 'sini bu yürütme bağlamıyla ilişkilendirir. İlişkili iş parçacığı proxy 'si, bağlamın metodunu yürütmeye başlamadan önce bu yöntemi hemen çağırır `Dispatch` .|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi ile arabirimleri olan özel bir Zamanlayıcı uygularsanız, arabirimini uygulamanız gerekir `IExecutionContext` . Kaynak Yöneticisi tarafından oluşturulan iş parçacıkları, yöntemi yürüterek Zamanlayıcı adına iş yapar `IExecutionContext::Dispatch` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionContext`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a> IExecutionContext::D ispatch yöntemi

Bir iş parçacığı proxy 'si belirli bir yürütme bağlamını yürütmeye başladığında çağrılan yöntem. Bu, Scheduler için ana çalışan yordamı olmalıdır.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatchState*<br/>
Bu yürütme bağlamının dağıtıldığı duruma yönelik bir işaretçi. Dağıtım durumu hakkında daha fazla bilgi için bkz. [DispatchState](dispatchstate-structure.md).

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a> IExecutionContext:: GetID Yöntemi

Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

`GetExecutionContextId` `IExecutionContext` Arabirimini, kaynak yöneticisi tarafından sağlanan yöntemlere parametre olarak kullanmadan önce, arabirimini uygulayan nesne için benzersiz bir tanımlayıcı elde etmek üzere yöntemini kullanmanız gerekir. İşlev çağrıldığında aynı tanımlayıcıyı döndürmeli `GetId` .

Farklı bir kaynaktan alınan bir tanımlayıcı, tanımsız davranışa neden olabilir.

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a> IExecutionContext:: GetProxy yöntemi

Bu bağlamı yürüten iş parçacığı proxy 'sine bir arabirim döndürür.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IThreadProxy` arabirim. Yürütme bağlamının iş parçacığı proxy 'si ' a çağrısıyla başlatılmamışsa `SetProxy` , işlev döndürmelidir `NULL` .

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, yöntemi bağlam üzerine `SetProxy` girmeden önce, bir arabirim olan bir yürütme bağlamında yöntemi çağıracaktır `IThreadProxy` `Dispatch` . Bu bağımsız değişkeni depolamanız ve çağrılarına geri dönebilmeniz beklenmektedir `GetProxy()` .

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a> IExecutionContext:: GetScheduler yöntemi

Bu yürütme bağlamının ait olduğu Scheduler 'a bir arabirim döndürür.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IScheduler` arabirim.

### <a name="remarks"></a>Açıklamalar

`IScheduler`Kaynak Yöneticisi tarafından sağlanan yöntemlere bir parametre olarak kullanmadan önce, yürütme bağlamını geçerli bir arabirimle başlatmak gerekir.

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a> IExecutionContext:: SetProxy yöntemi

Bir iş parçacığı proxy 'sini bu yürütme bağlamıyla ilişkilendirir. İlişkili iş parçacığı proxy 'si, bağlamın metodunu yürütmeye başlamadan önce bu yöntemi hemen çağırır `Dispatch` .

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parametreler

*pThreadProxy*<br/>
Bu yürütme bağlamına metodu girmek üzere olan iş parçacığı proxy 'sine yönelik bir arabirim `Dispatch` .

### <a name="remarks"></a>Açıklamalar

Parametreyi kaydetmeniz `pThreadProxy` ve yöntemine yapılan bir çağrıda döndürülmesi beklenmektedir `GetProxy` . Kaynak Yöneticisi, iş parçacığı proxy 'si yöntemini yürütürken yürütme bağlamıyla ilişkili iş parçacığı proxy 'sinin değişmeyecek olmasını güvence altına alır `Dispatch` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)
