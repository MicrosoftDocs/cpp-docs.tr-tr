---
title: Çalışan arşiv Etype
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 3efd77c38508df8302fa4e1dd5c9b51f66cd5e43
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915455"
---
# <a name="worker-archetype"></a>Çalışan arşiv Etype

*Çalışan* arşiv ETYPE ile uyumlu sınıflar, bir iş parçacığı havuzunda sıraya alınan iş öğelerini işlemek için kod sağlar.

**Uygulama**

Bu bir arşiv ETYPE ile uyumlu bir sınıf uygulamak için, sınıf aşağıdaki özellikleri sağlamalıdır:

|Yöntem|Açıklama|
|------------|-----------------|
|[Initialize](#initialize)|Herhangi bir istek [yürütülmeye](#execute)geçirilmeden önce çalışan nesnesini başlatmak için çağırılır.|
|[Execute](#execute)|Bir iş öğesini işlemek için çağırılır.|
|[Terminate](#terminate)|Tüm istekler [yürütülmeye](#execute)geçirilmeden sonra çalışan nesnesine Uninitialize için çağırılır.|

|Genişletiyor|Açıklama|
|-------------|-----------------|
|[RequestType](#requesttype)|Çalışan sınıfının işlenebilmesi için iş öğesi türü için bir typedef.|

Tipik bir *çalışan* sınıfı şöyle görünür:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Mevcut uygulamalar**

Bu sınıflar bu arşiv ETYPE ile uyumlu:

|örneği|Açıklama|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|İş parçacığı havuzundan gelen istekleri alır ve her istek için oluşturulan ve yok edilen bir çalışan nesnesine geçirir.|

**Kullanma**

Bu şablon parametreleri, sınıfın bu arşiv ETYPE ile uyumlu olmasını bekler:

|Parametre adı|Kullanan|
|--------------------|-------------|
|*Indan*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Indan*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="execute"></a>WorkerArchetype:: Execute

Bir iş öğesini işlemek için çağırılır.

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parametreler

*isteyen*<br/>
İşlenecek iş öğesi. İş öğesi ile `RequestType`aynı türde.

*pvWorkerParam*<br/>
Çalışan sınıfının anladığı özel parametre. Ayrıca `WorkerArchetype::Initialize` , ve ' `Terminate`a geçirilir.

*Polatik*<br/>
[Çakışan](/windows/desktop/api/minwinbase/ns-minwinbase-overlapped) yapının iş öğelerinin sıraya alındığı kuyruğu oluşturmak için kullanılan bir işaretçisi.

## <a name="initialize"></a>WorkerArchetype:: Initialize

Herhangi bir istek geçirilmeden `WorkerArchetype::Execute`çalışan nesnesini başlatmak için çağırılır.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
Çalışan sınıfının anladığı özel parametre. Ayrıca `WorkerArchetype::Terminate` , ve ' `WorkerArchetype::Execute`a geçirilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürün.

## <a name="requesttype"></a>WorkerArchetype:: RequestType

Çalışan sınıfının işlenebilmesi için iş öğesi türü için bir typedef.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu tür, öğesinin `WorkerArchetype::Execute` ilk parametresi olarak kullanılmalıdır ve bir ulong_ptr öğesine veya bir öğesine atama yeteneğine sahip olmalıdır.

## <a name="terminate"></a>WorkerArchetype:: Terminate

Tüm istekler iletildikten `WorkerArchetype::Execute`sonra çalışan nesnesine Uninitialize için çağırılır).

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
Çalışan sınıfının anladığı özel parametre. Ayrıca `WorkerArchetype::Initialize` , ve ' `WorkerArchetype::Execute`a geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
