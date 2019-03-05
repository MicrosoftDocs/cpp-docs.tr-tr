---
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
ms.openlocfilehash: abfd3e585c843fcc4ed4ad273c8ed217eaaccb7d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283163"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker sınıfı

Bir iş parçacığı havuzundan isteklerini alır ve bunları her istekte oluşturulur ve imha bir alt nesnesi açın geçirir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Parametreler

*Çalışan*<br/>
Bir çalışan iş parçacığı sınıfı uyumludur [çalışan modeli](../../atl/reference/worker-archetype.md) üzerinde sıraya isteklerini işlemek için uygun [CThreadPool](../../atl/reference/cthreadpool-class.md).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|Uygulamasını [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CNonStatelessWorker::Execute](#execute)|Uygulamasını [WorkerArchetype::Execute](worker-archetype.md#execute).|
|[CNonStatelessWorker::Initialize](#initialize)|Uygulamasını [WorkerArchetype::Initialize](worker-archetype.md#initialize).|
|[CNonStatelessWorker::Terminate](#terminate)|Uygulamasını [WorkerArchetype::Terminate](worker-archetype.md#terminate).|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir basit çalışan iş parçacığı ile kullanılmak üzere [CThreadPool](../../atl/reference/cthreadpool-class.md). Bu sınıf, herhangi bir istek işleme yetenek kendi sağlamaz. Bunun yerine, bir örneğinin örneğini oluşturur *çalışan* istek başına ve bu örneğe yöntemlerinin uygulaması atar.

Bu sınıfın avantajı var olan çalışan iş parçacığı sınıfları için durum modeli değiştirmek için kullanışlı bir yol sağlamasıdır. `CThreadPool` tek bir çalışan iş parçacığının ömrü boyunca oluşturacak şekilde çalışan sınıfı durumu barındırıyorsa, birden çok istekler genelinde aktarabilecek. Yalnızca bu sınıfta sarmalama tarafından `CNonStatelessWorker` ile kullanmadan önce şablonu `CThreadPool`, alt ve içeren tek bir istek için sınırlı durumu ömrü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

##  <a name="execute"></a>  CNonStatelessWorker::Execute

Uygulamasını [WorkerArchetype::Execute](worker-archetype.md#execute).

```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir örneğini oluşturur *çalışan* sınıfı çağrılar ve yığın [başlatmak](worker-archetype.md#initialize) bu nesne üzerinde. Başlatma başarılı olursa, bu yöntem ayrıca çağırır [yürütme](worker-archetype.md#execute) ve [sonlandırma](worker-archetype.md#terminate) aynı nesne üzerinde.

##  <a name="initialize"></a>  CNonStatelessWorker::Initialize

Uygulamasını [WorkerArchetype::Initialize](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf sıfırlamaları yapmaz `Initialize`.

##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType

Uygulamasını [WorkerArchetype::RequestType](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf, aynı iş öğesi türü için kullanılan sınıf olarak işleme *çalışan* şablon parametresi. Bkz: [CNonStatelessWorker genel bakış](../../atl/reference/cnonstatelessworker-class.md) Ayrıntılar için.

##  <a name="terminate"></a>  CNonStatelessWorker::Terminate

Uygulamasını [WorkerArchetype::Terminate](worker-archetype.md#terminate).

```
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu sınıfın tüm temizleme işlemlerini yapmaz `Terminate`.

## <a name="see-also"></a>Ayrıca bkz.

[CThreadPool Sınıfı](../../atl/reference/cthreadpool-class.md)<br/>
[Çalışan Modeli](../../atl/reference/worker-archetype.md)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)
