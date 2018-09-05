---
title: CNoWorkerThread sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e602b3493269924e7b80b52b70b34397fcc7dd71
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753933"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread sınıfı

Bu sınıf için bağımsız değişken olarak kullanmak `MonitorClass` şablon parametresi için dinamik önbellek bakım devre dışı bırakmak isterseniz önbellek sınıfları.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CNoWorkerThread
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CNoWorkerThread::AddHandle](#addhandle)|İşlevsel olmayan denk [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|
|[CNoWorkerThread::AddTimer](#addtimer)|İşlevsel olmayan denk [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|İşlevsel olmayan denk [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|
|[CNoWorkerThread::GetThreadId](#getthreadid)|İşlevsel olmayan denk [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|
|[CNoWorkerThread::Initialize](#initialize)|İşlevsel olmayan denk [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|
|[CNoWorkerThread::RemoveHandle](#removehandle)|İşlevsel olmayan denk [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|
|[CNoWorkerThread::Shutdown](#shutdown)|İşlevsel olmayan denk [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|

## <a name="remarks"></a>Açıklamalar

Aynı genel arabirimi olarak bu sınıfın sağladığı [CWorkerThread](../../atl/reference/cworkerthread-class.md). Bu arabirim tarafından sağlanan beklenir `MonitorClass` önbellek sınıfları için şablon parametresi.

Bu sınıftaki yöntemlerin yapmamak için uygulanır. Her zaman bir HRESULT döndüren yöntemler S_OK döndürür ve her zaman bir tanıtıcı veya iş parçacığı kimliği döndüren yöntemler 0 değerini döndürür.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle

İşlevsel olmayan denk [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer

İşlevsel olmayan denk [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle

İşlevsel olmayan denk [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId

İşlevsel olmayan denk [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

##  <a name="initialize"></a>  CNoWorkerThread::Initialize

İşlevsel olmayan denk [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle

İşlevsel olmayan denk [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown

İşlevsel olmayan denk [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.
