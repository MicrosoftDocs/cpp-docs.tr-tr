---
description: 'Daha fazla bilgi edinin: Worker arşiv Etype'
title: Çalışan arşiv Etype
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 8cb8c2b281bbdc074bb700b77a856f4d26c26cf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157574"
---
# <a name="worker-archetype"></a>Çalışan arşiv Etype

*Çalışan* arşiv ETYPE ile uyumlu sınıflar, bir iş parçacığı havuzunda sıraya alınan iş öğelerini işlemek için kod sağlar.

**Uygulama**

Bu bir arşiv ETYPE ile uyumlu bir sınıf uygulamak için, sınıf aşağıdaki özellikleri sağlamalıdır:

|Yöntem|Açıklama|
|------------|-----------------|
|[Başlatma](#initialize)|Herhangi bir istek [yürütülmeye](#execute)geçirilmeden önce çalışan nesnesini başlatmak için çağırılır.|
|[Yürütme](#execute)|Bir iş öğesini işlemek için çağırılır.|
|[Terminate](#terminate)|Tüm istekler [yürütülmeye](#execute)geçirilmeden sonra çalışan nesnesine Uninitialize için çağırılır.|

|Genişletiyor|Açıklama|
|-------------|-----------------|
|[RequestType](#requesttype)|Çalışan sınıfının işlenebilmesi için iş öğesi türü için bir typedef.|

Tipik bir *çalışan* sınıfı şöyle görünür:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Mevcut uygulamalar**

Bu sınıflar bu arşiv ETYPE ile uyumlu:

|Sınıf|Açıklama|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|İş parçacığı havuzundan gelen istekleri alır ve her istek için oluşturulan ve yok edilen bir çalışan nesnesine geçirir.|

**Kullanım**

Bu şablon parametreleri, sınıfın bu arşiv ETYPE ile uyumlu olmasını bekler:

|Parametre adı|Kullanan|
|--------------------|-------------|
|*Indan*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Indan*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="workerarchetypeexecute"></a><a name="execute"></a> WorkerArchetype:: Execute

Bir iş öğesini işlemek için çağırılır.

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parametreler

*isteyen*<br/>
İşlenecek iş öğesi. İş öğesi ile aynı türde `RequestType` .

*pvWorkerParam*<br/>
Çalışan sınıfının anladığı özel parametre. Ayrıca `WorkerArchetype::Initialize` , ve ' a geçirilir `Terminate` .

*Polatik*<br/>
[Çakışan](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) yapının iş öğelerinin sıraya alındığı kuyruğu oluşturmak için kullanılan bir işaretçisi.

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a> WorkerArchetype:: Initialize

Herhangi bir istek geçirilmeden çalışan nesnesini başlatmak için çağırılır `WorkerArchetype::Execute` .

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
Çalışan sınıfının anladığı özel parametre. Ayrıca `WorkerArchetype::Terminate` , ve ' a geçirilir `WorkerArchetype::Execute` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürün.

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a> WorkerArchetype:: RequestType

Çalışan sınıfının işlenebilmesi için iş öğesi türü için bir typedef.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Açıklamalar

Bu tür, ilk parametresi olarak kullanılmalıdır `WorkerArchetype::Execute` ve bir ulong_ptr ' a ve ' a dönüştürme yeteneğine sahip olmalıdır.

## <a name="workerarchetypeterminate"></a><a name="terminate"></a> WorkerArchetype:: Terminate

Tüm istekler iletildikten sonra çalışan nesnesine Uninitialize için çağırılır `WorkerArchetype::Execute` ).

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametreler

*pvParam*<br/>
Çalışan sınıfının anladığı özel parametre. Ayrıca `WorkerArchetype::Initialize` , ve ' a geçirilir `WorkerArchetype::Execute` .

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
