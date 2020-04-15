---
title: CNonStatelessWorker Sınıfı
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
ms.openlocfilehash: f3604f95c8217c7407c100671265140bbadbab78
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326726"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker Sınıfı

İş parçacığı havuzundan istekler alır ve bunları her istekte oluşturulan ve yok edilen bir alt nesneye aktarın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Parametreler

*Işçi*<br/>
[CThreadPool'da](../../atl/reference/cthreadpool-class.md)sıraya konan istekleri işlemeye uygun [işçi arketipine](../../atl/reference/worker-archetype.md) uygun bir işçi iş parçacığı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|İşçi [Archetype Uygulanması::RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CNonStatelessWorker::Execute](#execute)|İşçi [Arketipinin Uygulanması::Yürüt .](worker-archetype.md#execute)|
|[CNonStatelessWorker::Initialize](#initialize)|İşçi [Archetype Uygulanması::Initialize](worker-archetype.md#initialize).|
|[CNonStatelessWorker::Sonlandırma](#terminate)|İşçi [Archetype Uygulanması::Sonlandırmak](worker-archetype.md#terminate).|

## <a name="remarks"></a>Açıklamalar

Bu sınıf [CThreadPool](../../atl/reference/cthreadpool-class.md)ile kullanılmak üzere basit bir işçi iş parçacığıdır. Bu sınıf kendi istek işleme yeteneklerini sağlamaz. Bunun yerine, istek başına *İşçi'nin* bir örneğini anında verir ve yöntemlerinin uygulanmasını o örneğe devreden.

Bu sınıfın yararı, varolan alt iş parçacığı sınıfları için durum modelini değiştirmek için uygun bir yol sağlamasıdır. `CThreadPool`iş parçacığının ömrü boyunca tek bir alt lık oluşturur, bu nedenle işçi sınıfı durumu tutarsa, birden çok istek arasında tutar. Yalnızca bu sınıfı kullanmadan `CNonStatelessWorker` önce şablona sararak , işçinin ömrü ve sahip olduğu durum tek bir istekle `CThreadPool`sınırlıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a>CNonStatelessWorker::Execute

İşçi [Arketipinin Uygulanması::Yürüt .](worker-archetype.md#execute)

```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem yığında *İşçi* sınıfının bir örneğini oluşturur ve bu nesnede [Initialize](worker-archetype.md#initialize) çağırır. Başlatma başarılı olursa, bu yöntem aynı nesne üzerinde [Yürüt](worker-archetype.md#execute) ve [Sonlandırma](worker-archetype.md#terminate) çağırır.

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a>CNonStatelessWorker::Initialize

İşçi [Archetype Uygulanması::Initialize](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf' ta `Initialize`herhangi bir başlatma yapmaz.

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a>CNonStatelessWorker::RequestType

İşçi [Archetype Uygulanması::RequestType](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf, *İşçi* şablonu parametresi için kullanılan sınıfla aynı çalışma öğesi türünü işler. Ayrıntılar için [CNonStatelessWorker Genel Bakış'a](../../atl/reference/cnonstatelessworker-class.md) bakın.

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a>CNonStatelessWorker::Sonlandırma

İşçi [Archetype Uygulanması::Sonlandırmak](worker-archetype.md#terminate).

```
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf herhangi bir temizlik `Terminate`yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[CThreadPool Sınıfı](../../atl/reference/cthreadpool-class.md)<br/>
[İşçi Arketipi](../../atl/reference/worker-archetype.md)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)
