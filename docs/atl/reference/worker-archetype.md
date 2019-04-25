---
title: Çalışan modeli
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 790cf064fcffe1f0cd3c191c28ed0a0614062406
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274505"
---
# <a name="worker-archetype"></a>Çalışan modeli

Uygun sınıfları *çalışan* archetype işlem iş öğeleri koda sıraya alınmış bir iş parçacığı havuzunda sağlayın.

**Uygulama**

Sınıfı, bu archetype için uygun bir sınıf uygulamak için aşağıdaki özellikleri sağlamanız gerekir:

|Yöntem|Açıklama|
|------------|-----------------|
|[Initialize](#initialize)|Tüm istekler için geçirilmeden önce alt nesne başlatmak için çağırılır [yürütme](#execute).|
|[Execute](#execute)|Bir iş öğesini işlemek için çağrılır.|
|[Terminate](#terminate)|Alt nesne için tüm istekleri geçildi; sonra kapatmak için çağrılan [yürütme](#execute).|

|tür tanımı|Açıklama|
|-------------|-----------------|
|[RequestType](#requesttype)|Çalışan sınıfı tarafından işlenen iş öğesi türü için bir typedef.|

Tipik bir *çalışan* sınıfı aşağıdaki gibi görünür:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Mevcut uygulamaları**

Bu sınıflar için bu archetype uyar:

|örneği|Açıklama|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|İş parçacığı havuzu isteklerini alır ve bunları oluşturulur ve imha her istek için bir alt nesnesi açın geçirir.|

**Kullanma**

Bu şablon parametreleri için bu archetype uymak için sınıf bekler:

|Parametre adı|Kullanan|
|--------------------|-------------|
|*Çalışan*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Çalışan*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="execute"></a>WorkerArchetype::Execute

Bir iş öğesini işlemek için çağrılır.

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parametreler

*İstek*<br/>
İşlenmek üzere çalışma öğesi. İş öğesi aynı türde olan `RequestType`.

*pvWorkerParam*<br/>
Çalışan sınıfı tarafından anlaşılan bir özel parametre. Ayrıca geçirilen `WorkerArchetype::Initialize` ve `Terminate`.

*pOverlapped*<br/>
Bir işaretçi [ÇAKIŞAN](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) yapısı üzerinde hangi iş öğelerini kuyruğa alındı sırayı oluşturmak için kullanılır.

## <a name="initialize"></a> WorkerArchetype::Initialize

Tüm istekler için geçirilmeden önce alt nesne başlatmak için çağırılır `WorkerArchetype::Execute`.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
Çalışan sınıfı tarafından anlaşılan bir özel parametre. Ayrıca geçirilen `WorkerArchetype::Terminate` ve `WorkerArchetype::Execute`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa TRUE döndürün başarısız olduğunda FALSE.

## <a name="requesttype"></a> WorkerArchetype::RequestType

Çalışan sınıfı tarafından işlenen iş öğesi türü için bir typedef.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu tür, ilk parametresi olarak kullanılmalıdır `WorkerArchetype::Execute` ve bir iç ULONG_PTR gelen ve giden cast uyumlu olması gerekir.

## <a name="terminate"></a> WorkerArchetype::Terminate

Alt nesne için tüm istekleri geçildi; sonra kapatmak için çağrılan `WorkerArchetype::Execute`).

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
Çalışan sınıfı tarafından anlaşılan bir özel parametre. Ayrıca geçirilen `WorkerArchetype::Initialize` ve `WorkerArchetype::Execute`.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
