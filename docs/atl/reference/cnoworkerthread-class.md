---
title: CNoWorkerThread Sınıfı
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
ms.openlocfilehash: 90056e648a53218ac06083d43ca34870e1ca72fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326704"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread Sınıfı

Dinamik önbellek bakımını `MonitorClass` devre dışı kıfsaytak etmek istiyorsanız, şablon parametresinin önbellek sınıflarını önbelleğe almak için bağımsız değişkenolarak bu sınıfı kullanın.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CNoWorkerThread
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CNoWorkerThread::AddHandle](#addhandle)|CWorkerThread'in işlevsel olmayan [eşdeğeri::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|
|[CNoWorkerThread::AddTimer](#addtimer)|CWorkerThread'in işlevsel olmayan [eşdeğeri::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|CWorkerThread fonksiyonel olmayan [eşdeğer::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|
|[CNoWorkerThread::GetThreadid](#getthreadid)|CWorkerThread fonksiyonel olmayan [eşdeğer::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|
|[CNoWorkerThread::Initialize](#initialize)|CWorkerThread'in işlevsel olmayan [eşdeğeri::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|
|[CNoWorkerThread::RemoveHandle](#removehandle)|CWorkerThread'in işlevsel olmayan [eşdeğeri::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|
|[CNoWorkerThread::Kapatma](#shutdown)|CWorkerThread'in işlevsel olmayan [eşdeğeri::Kapatma](../../atl/reference/cworkerthread-class.md#shutdown).|

## <a name="remarks"></a>Açıklamalar

Bu [sınıf, CWorkerThread](../../atl/reference/cworkerthread-class.md)ile aynı ortak arabirimi sağlar. Bu arabirimin `MonitorClass` önbellek sınıflarına şablon parametresi tarafından sağlanması beklenir.

Bu sınıftaki yöntemler hiçbir şey yapmamak için uygulanır. HRESULT'i döndüren yöntemler her zaman S_OK döndürer ve HANDLE veya iş parçacığı kimliğini döndüren yöntemler her zaman 0 döndürer.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a>CNoWorkerThread::AddHandle

CWorkerThread'in işlevsel olmayan [eşdeğeri::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a>CNoWorkerThread::AddTimer

CWorkerThread'in işlevsel olmayan [eşdeğeri::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).

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

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle

CWorkerThread fonksiyonel olmayan [eşdeğer::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>CNoWorkerThread::GetThreadid

CWorkerThread fonksiyonel olmayan [eşdeğer::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a>CNoWorkerThread::Initialize

CWorkerThread'in işlevsel olmayan [eşdeğeri::Initialize](../../atl/reference/cworkerthread-class.md#initialize).

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a>CNoWorkerThread::RemoveHandle

CWorkerThread'in işlevsel olmayan [eşdeğeri::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoWorkerThread::Kapatma

CWorkerThread'in işlevsel olmayan [eşdeğeri::Kapatma](../../atl/reference/cworkerthread-class.md#shutdown).

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf tarafından sağlanan uygulama hiçbir şey yapmaz.
