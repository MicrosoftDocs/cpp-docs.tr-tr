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
ms.openlocfilehash: 8c49df5a8c7f214b574b4f6118d182b63fec5dca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264969"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext Yapısı

Belirli bir sanal işlemci üzerinde çalıştırabilir ve olması bir yürütme bağlamı için bir arabirim işbirliği içerisinde devamlılığı bağlam değiştirdi.

## <a name="syntax"></a>Sözdizimi

```
struct IExecutionContext;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iexecutioncontext::Dispatch](#dispatch)|Bir iş parçacığı proxy'sini belirli yürütme bağlamı yürütme başlatıldığında çağrılan yöntem. Bu ana çalışan rutin scheduler için olmalıdır.|
|[IExecutionContext::GetId](#getid)|Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.|
|[Iexecutioncontext::getproxy](#getproxy)|Bu bağlam yürüten iş parçacığı proxy için bir arabirim döndürür.|
|[Iexecutioncontext::getscheduler](#getscheduler)|Bu yürütme bağlamı ait olduğu Zamanlayıcı bir arabirim döndürür.|
|[Iexecutioncontext::setproxy](#setproxy)|Bir iş parçacığı proxy'sini bu yürütme bağlamı ile ilişkilendirir. Yürütme bağlamı'nın başlamadan önce ilişkili iş parçacığı proxy bu yöntem hak çağırır `Dispatch` yöntemi.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlılık çalışma zamanının Resource Manager ile arabirimleri özel bir zamanlayıcı uyguluyorsanız uygulamak ihtiyacınız olacak `IExecutionContext` arabirimi. Resource Manager tarafından oluşturulan iş parçacığı adına, Zamanlayıcı İş yürüterek gerçekleştirmek `IExecutionContext::Dispatch` yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionContext`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="dispatch"></a>  Iexecutioncontext::Dispatch yöntemi

Bir iş parçacığı proxy'sini belirli yürütme bağlamı yürütme başlatıldığında çağrılan yöntem. Bu ana çalışan rutin scheduler için olmalıdır.

```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatchState*<br/>
Bu yürütme bağlamı altında dağıtıldığı durumuna yönelik bir işaretçi. Dağıtım durumu hakkında daha fazla bilgi için bkz. [DispatchState](dispatchstate-structure.md).

##  <a name="getid"></a>  Iexecutioncontext::GetID metodu

Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir tamsayı benzersiz tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Yöntem `GetExecutionContextId` uygulayan nesne için benzersiz bir tanımlayıcı elde etmek için `IExecutionContext` arabirimi arabirim yöntemleri için parametre olarak kullanmadan önce kaynak yöneticisi tarafından sağlanan. Aynı tanımlayıcıyı döndürmek için beklenen zaman `GetId` işlevi çağrılır.

Farklı bir kaynaktan gelen bir tanımlayıcının tanımsız davranışlara neden.

##  <a name="getproxy"></a>  Iexecutioncontext::getproxy metodu

Bu bağlam yürüten iş parçacığı proxy için bir arabirim döndürür.

```
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IThreadProxy` arabirimi. Yürütme bağlamı'nın iş parçacığı proxy'sini çağrısıyla başlatılmadı ise `SetProxy`, işlev döndürmelidir `NULL`.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi çağırır `SetProxy` bir yürütme bağlamı yöntemi ile bir `IThreadProxy` girme önce bir parametre olarak arabirimi `Dispatch` metodunda bağlam üzerinde. Bu bağımsız değişken depolayıp için çağrılar üzerinde döndürmek için beklenen `GetProxy()`.

##  <a name="getscheduler"></a>  Iexecutioncontext::getscheduler metodu

Bu yürütme bağlamı ait olduğu Zamanlayıcı bir arabirim döndürür.

```
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IScheduler` arabirimi.

### <a name="remarks"></a>Açıklamalar

Geçerli bir yürütme bağlamıyla başlatmak için gerekli `IScheduler` arabirim yöntemleri için parametre olarak kullanmadan önce kaynak yöneticisi tarafından sağlanan.

##  <a name="setproxy"></a>  Iexecutioncontext::setproxy yöntemi

Bir iş parçacığı proxy'sini bu yürütme bağlamı ile ilişkilendirir. Yürütme bağlamı'nın başlamadan önce ilişkili iş parçacığı proxy bu yöntem hak çağırır `Dispatch` yöntemi.

```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parametreler

*pThreadProxy*<br/>
Arabirim hakkında girmektir iş parçacığı proxy'sini `Dispatch` yöntemi bu yürütme bağlamı.

### <a name="remarks"></a>Açıklamalar

Parametre kaydetmek için beklenen `pThreadProxy` ve çağırması döndürün `GetProxy` yöntemi. Kaynak Yöneticisi iş parçacığı proxy'sini yürütülürken yürütme bağlamı ile ilişkili iş parçacığı proxy'sini değiştirmeyeceğini garanti eder `Dispatch` yöntemi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)
