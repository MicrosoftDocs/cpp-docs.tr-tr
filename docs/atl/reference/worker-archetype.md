---
title: İşçi Arketipi
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: c9ed9b30b94a8debe133bc213c12063750bfb15a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747351"
---
# <a name="worker-archetype"></a>İşçi Arketipi

*Alt* arketipe uygun sınıflar, iş parçacığı havuzunda sıralanmış iş öğelerini işlemek için kodu sağlar.

**Uygulama**

Bu arketipe uygun bir sınıf uygulamak için sınıfın aşağıdaki özellikleri sağlaması gerekir:

|Yöntem|Açıklama|
|------------|-----------------|
|[Initialize](#initialize)|Herhangi bir istek [Yürüt tümevarıma](#execute)geçirilmeden önce alt nesneyi başlatmaya çağrıldı.|
|[Yürütmek](#execute)|Bir çalışma öğesini işlemek için çağrıldı.|
|[Terminate](#terminate)|Tüm istekler [Yürüt tüm'e](#execute)geçtikten sonra işçi nesnesinin başlatılması için çağrıldı.|

|Typedef|Açıklama|
|-------------|-----------------|
|[Requesttype](#requesttype)|İşçi sınıfı tarafından işlenebilen iş öğesi türü için bir typedef.|

Tipik bir *işçi* sınıfı şuna benzer:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Mevcut Uygulamalar**

Bu sınıflar bu arketipe uygundur:

|Sınıf|Açıklama|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|İş parçacığı havuzundan istekler alır ve bunları her istek için oluşturulan ve yok edilen bir alt nesneye aktarın.|

**Kullanma**

Bu şablon parametreleri sınıfın bu arketipe uymasını bekler:

|Parametre adı|Kullanan|
|--------------------|-------------|
|*Işçi*|[Cthreadpool](../../atl/reference/cthreadpool-class.md)|
|*Işçi*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="workerarchetypeexecute"></a><a name="execute"></a>İşçiArchetype::Yürüt

Bir çalışma öğesini işlemek için çağrıldı.

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parametreler

*Istek*<br/>
İşlenecek iş öğesi. Çalışma öğesi `RequestType`aynı türdedir.

*pvWorkerParam*<br/>
İşçi sınıfı tarafından anlaşılan özel bir parametre. Ayrıca geçti `WorkerArchetype::Initialize` `Terminate`ve .

*pOverlapped*<br/>
İş öğelerinin sıralandığı sırayı oluşturmak için kullanılan [OverLAPPED](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) yapısına işaretçi.

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a>İşçiArchetype::Initialize

Herhangi bir istek. `WorkerArchetype::Execute`

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
İşçi sınıfı tarafından anlaşılan özel bir parametre. Ayrıca geçti `WorkerArchetype::Terminate` `WorkerArchetype::Execute`ve .

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru, başarısızlık false dön.

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a>İşçiArchetype::RequestType

İşçi sınıfı tarafından işlenebilen iş öğesi türü için bir typedef.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu tür ilk parametre olarak `WorkerArchetype::Execute` kullanılmalı ve bir ULONG_PTR döküm ve sahip olmalıdır.

## <a name="workerarchetypeterminate"></a><a name="terminate"></a>İşçiArchetype::Sonlandırma

Tüm istekler geçtikten sonra işçi nesnesinin `WorkerArchetype::Execute`başlatılması için çağrıldı).

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
İşçi sınıfı tarafından anlaşılan özel bir parametre. Ayrıca geçti `WorkerArchetype::Initialize` `WorkerArchetype::Execute`ve .

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
