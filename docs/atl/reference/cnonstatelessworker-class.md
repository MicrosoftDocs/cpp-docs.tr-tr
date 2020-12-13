---
description: 'Daha fazla bilgi edinin: CNonStatelessWorker sınıfı'
title: CNonStatelessWorker sınıfı
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: 68457c9594bfaf4d8dd53acd80d7997355c3a3f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141433"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker sınıfı

Bir iş parçacığı havuzundan istekleri alır ve her istekte oluşturulan ve yok edilen bir çalışan nesnesine geçirir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Parametreler

*Indan*<br/>
[CThreadPool](../../atl/reference/cthreadpool-class.md)üzerinde sıraya alınan isteklerin işlenmesine uygun [çalışan](../../atl/reference/worker-archetype.md) bir çalışan iş parçacığı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CNonStatelessWorker:: RequestType](#requesttype)|[Workerarchetype:: RequestType](worker-archetype.md#requesttype)uygulama.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CNonStatelessWorker:: Execute](#execute)|[Workerarchetype:: Execute](worker-archetype.md#execute)uygulama.|
|[CNonStatelessWorker:: Initialize](#initialize)|[Workerarchetype:: Initialize](worker-archetype.md#initialize)uygulamasının uygulanması.|
|[CNonStatelessWorker:: Terminate](#terminate)|[Workerarchetype:: Terminate](worker-archetype.md#terminate)uygulama.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [CThreadPool](../../atl/reference/cthreadpool-class.md)ile kullanılmak üzere basit bir çalışan iş parçacığıdır. Bu sınıf kendi istek işleme özelliklerini sağlamaz. Bunun yerine, her istek için *çalışan* bir örnek başlatır ve yöntemlerinin bu örneğe uygulanmasını devreder.

Bu sınıfın avantajı, mevcut çalışan iş parçacığı sınıflarının durum modelini değiştirmek için kullanışlı bir yol sağlar. `CThreadPool` iş parçacığının ömrü boyunca tek bir çalışan oluşturacak, bu nedenle çalışan sınıfı durum barındırıyorsa, bu işlem birden çok istekte tutulur. Yalnızca bu sınıfı `CNonStatelessWorker` ile kullanılmadan önce şablonda sarmalayarak `CThreadPool` , çalışanın ömrü ve tuttuğu durum tek bir istekle sınırlıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a> CNonStatelessWorker:: Execute

[Workerarchetype:: Execute](worker-archetype.md#execute)uygulama.

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yığında *çalışan* sınıfının bir örneğini oluşturur ve bu nesne üzerinde [Initialize](worker-archetype.md#initialize) öğesini çağırır. Başlatma başarılı olursa, bu yöntem aynı nesne üzerinde [Execute](worker-archetype.md#execute) ve [Terminate](worker-archetype.md#terminate) öğesini de çağırır.

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a> CNonStatelessWorker:: Initialize

[Workerarchetype:: Initialize](worker-archetype.md#initialize)uygulamasının uygulanması.

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf içinde herhangi bir başlatma yapmaz `Initialize` .

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a> CNonStatelessWorker:: RequestType

[Workerarchetype:: RequestType](worker-archetype.md#requesttype)uygulama.

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf, *çalışan* şablon parametresi için kullanılan sınıfla aynı iş öğesi türünü işler. Ayrıntılar için bkz. [CNonStatelessWorker 'A genel bakış](../../atl/reference/cnonstatelessworker-class.md) .

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a> CNonStatelessWorker:: Terminate

[Workerarchetype:: Terminate](worker-archetype.md#terminate)uygulama.

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf içinde herhangi bir temizlik yapmaz `Terminate` .

## <a name="see-also"></a>Ayrıca bkz.

[CThreadPool sınıfı](../../atl/reference/cthreadpool-class.md)<br/>
[Çalışan arşiv Etype](../../atl/reference/worker-archetype.md)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)
