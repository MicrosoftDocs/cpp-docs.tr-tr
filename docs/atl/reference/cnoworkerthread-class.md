---
description: 'Daha fazla bilgi edinin: CNoWorkerThread sınıfı'
title: CNoWorkerThread sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: 5159c04a8390f8933291f697faccedb7353fb48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141420"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread sınıfı

`MonitorClass`Dinamik önbellek bakımını devre dışı bırakmak istiyorsanız bu sınıfı önbelleğe almak için şablon parametresinin bağımsız değişkeni olarak kullanın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CNoWorkerThread
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CNoWorkerThread:: AddHandle](#addhandle)|[CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)'ın işlevsel olmayan eşdeğeri.|
|[CNoWorkerThread:: AddTimer](#addtimer)|[CWorkerThread:: AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)öğesinin işlevsel olmayan eşdeğeri.|
|[CNoWorkerThread:: GetThreadHandle](#getthreadhandle)|[CWorkerThread:: GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)'ın işlevsel olmayan eşdeğeri.|
|[CNoWorkerThread:: GetThreadId](#getthreadid)|[CWorkerThread:: GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)ile işlevsel olmayan eşdeğeri.|
|[CNoWorkerThread:: Initialize](#initialize)|[CWorkerThread:: Initialize](../../atl/reference/cworkerthread-class.md#initialize)' ın işlevsel olmayan eşdeğeri.|
|[CNoWorkerThread:: RemoveHandle](#removehandle)|[CWorkerThread:: RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)'ın işlevsel olmayan eşdeğeri.|
|[CNoWorkerThread:: kapanıyor](#shutdown)|[CWorkerThread:: kapanıyor](../../atl/reference/cworkerthread-class.md#shutdown)değerinin işlevsel olmayan eşdeğeri.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf [CWorkerThread](../../atl/reference/cworkerthread-class.md)ile aynı ortak arabirimi sağlar. Bu arabirimin, `MonitorClass` Cache sınıfları için şablon parametresi tarafından sağlanması beklenmektedir.

Bu sınıftaki Yöntemler hiçbir şey yapmak için uygulanır. HRESULT döndüren yöntemler her zaman S_OK döndürür ve bir tanıtıcı veya iş parçacığı KIMLIĞI döndüren yöntemler her zaman 0 döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a> CNoWorkerThread:: AddHandle

[CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)'ın işlevsel olmayan eşdeğeri.

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a> CNoWorkerThread:: AddTimer

[CWorkerThread:: AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)öğesinin işlevsel olmayan eşdeğeri.

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a> CNoWorkerThread:: GetThreadHandle

[CWorkerThread:: GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)'ın işlevsel olmayan eşdeğeri.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a> CNoWorkerThread:: GetThreadId

[CWorkerThread:: GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)ile işlevsel olmayan eşdeğeri.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a> CNoWorkerThread:: Initialize

[CWorkerThread:: Initialize](../../atl/reference/cworkerthread-class.md#initialize)' ın işlevsel olmayan eşdeğeri.

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a> CNoWorkerThread:: RemoveHandle

[CWorkerThread:: RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)'ın işlevsel olmayan eşdeğeri.

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a> CNoWorkerThread:: kapanıyor

[CWorkerThread:: kapanıyor](../../atl/reference/cworkerthread-class.md#shutdown)değerinin işlevsel olmayan eşdeğeri.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sunulan uygulama hiçbir şey yapmaz.
