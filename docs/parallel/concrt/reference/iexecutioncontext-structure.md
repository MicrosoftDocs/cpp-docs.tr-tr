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
ms.openlocfilehash: 532247ca1776452ad32476d2bcdfafcee3481058
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358799"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext Yapısı

Belirli bir sanal işlemcide çalıştırılabilen ve işbirliği içinde bağlam değiştirilebilen bir yürütme bağlamına arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IExecutionContext;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IExecutionContext::Dispatch](#dispatch)|Bir iş parçacığı proxy belirli bir yürütme bağlamı yürütme başladığında çağrılan yöntem. Bu zamanlayıcı için ana işçi rutin olmalıdır.|
|[IExecutionContext::Getid](#getid)|Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.|
|[IExecutionContext::GetProxy](#getproxy)|Bu bağlamı yürüten iş parçacığı proxy'sine bir arabirim döndürür.|
|[IExecutionContext::GetScheduler](#getscheduler)|Bu yürütme bağlamına ait olan zamanlayıcıya bir arabirim verir.|
|[IExecutionContext::SetProxy](#setproxy)|İş parçacığı proxy'yi bu yürütme bağlamıyla ilişkilendirin. İlişkili iş parçacığı proxy bağlamın `Dispatch` yöntemini yürütmeye başlamadan hemen önce bu yöntemi çağırır.|

## <a name="remarks"></a>Açıklamalar

Eşzamanlı Çalışma Zamanı Kaynak Yöneticisi ile arabirim yapan özel bir zamanlayıcı uyguluyorsanız, `IExecutionContext` arabirimi uygulamanız gerekir. Kaynak Yöneticisi tarafından oluşturulan iş `IExecutionContext::Dispatch` parçacıkları, yöntemi çalıştırarak zamanlayıcınız adına çalışma gerçekleştirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IExecutionContext`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a>IExecutionContext::Dispatch Yöntemi

Bir iş parçacığı proxy belirli bir yürütme bağlamı yürütme başladığında çağrılan yöntem. Bu zamanlayıcı için ana işçi rutin olmalıdır.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatchState*<br/>
Bu yürütme bağlamı altında gönderilen durumuna bir işaretçi. Gönderi durumu hakkında daha fazla bilgi için [DispatchState'e](dispatchstate-structure.md)bakın.

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a>IExecutionContext::Getid Yöntemi

Yürütme bağlamı için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Arabirimi Kaynak `GetExecutionContextId` Yöneticisi tarafından sağlanan yöntemlere parametre olarak kullanmadan `IExecutionContext` önce, arabirimi uygulayan nesne için benzersiz bir tanımlayıcı elde etmek için yöntemi kullanmanız gerekir. İşlev çağrıldığında aynı tanımlayıcıyı `GetId` döndürmeniz beklenir.

Farklı bir kaynaktan elde edilen bir tanımlayıcı tanımlanmamış davranışa neden olabilir.

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>IExecutionContext::GetProxy Yöntemi

Bu bağlamı yürüten iş parçacığı proxy'sine bir arabirim döndürür.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IThreadProxy` arayüz. Yürütme bağlamı iş parçacığı proxy için bir çağrı `SetProxy`ile baş harfe getirilmiş değilse, işlev in döndürülmesi `NULL`gerekir.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, bağlam `SetProxy` üzerindeki `Dispatch` yöntemi girmeden `IThreadProxy` önce, parametre olarak arabirim içeren bir yürütme bağlamında yöntemi çağırır. Bu bağımsız değişkeni depolamanız ve aramalarda iade etmeniz `GetProxy()`beklenir.

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>IExecutionContext::GetScheduler Yöntemi

Bu yürütme bağlamına ait olan zamanlayıcıya bir arabirim verir.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IScheduler` arayüz.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi tarafından sağlanan yöntemlere parametre olarak kullanmadan önce yürütme bağlamını geçerli `IScheduler` bir arabirimle başlatmanız gerekir.

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>IExecutionContext::SetProxy Yöntemi

İş parçacığı proxy'yi bu yürütme bağlamıyla ilişkilendirin. İlişkili iş parçacığı proxy bağlamın `Dispatch` yöntemini yürütmeye başlamadan hemen önce bu yöntemi çağırır.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parametreler

*pThreadProxy*<br/>
Bu yürütme bağlamında yöntem girmek üzere `Dispatch` olan iş parçacığı proxy'sine bir arabirim.

### <a name="remarks"></a>Açıklamalar

Parametreyi `pThreadProxy` kaydetmeniz ve yönteme bir çağrıda `GetProxy` döndürmeniz beklenir. Kaynak Yöneticisi, iş parçacığı proxy `Dispatch` yöntemi ni uygularken yürütme bağlamı ile ilişkili iş parçacığı proxy değişmez garanti eder.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IThreadProxy Yapısı](ithreadproxy-structure.md)
