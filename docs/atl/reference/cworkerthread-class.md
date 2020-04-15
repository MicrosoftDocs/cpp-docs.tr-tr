---
title: CWorkerThread Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: 05e6b432d44927fa7e276792643e29c80c42d822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330217"
---
# <a name="cworkerthread-class"></a>CWorkerThread Sınıfı

Bu sınıf bir alt iş parçacığı oluşturur veya varolan bir iş parçacığı kullanır, bir veya daha fazla çekirdek nesne si tutamaçları bekler ve tutamaçlarından biri sinyal verildiğinde belirli bir istemci işlevini yürütür.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>Parametreler

*Konu Özellikleri*<br/>
[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) veya [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)gibi iş parçacığı oluşturma işlevini sağlayan sınıf.

## <a name="members"></a>Üyeler

### <a name="protected-structures"></a>Korumalı Yapılar

|Adı|Açıklama|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWorkerThread::CworkerThread](#cworkerthread)|İşçi iş parçacığı için oluşturucu.|
|[CWorkerThread::~CWorkerThread](#dtor)|İşçi iş parçacığı için yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWorkerThread::AddHandle](#addhandle)|İşçi iş parçacığı tarafından tutulan listeye beklenebilir bir nesnenin tanıtıcısını eklemek için bu yöntemi arayın.|
|[CWorkerThread::AddTimer](#addtimer)|Alt iş parçacığı tarafından tutulan listeye periyodik olarak bekletilebilir zamanlayıcı eklemek için bu yöntemi arayın.|
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Alt iş parçacığının iş parçacığı tutamacını almak için bu yöntemi arayın.|
|[CWorkerThread::GetThreadId](#getthreadid)|Alt iş parçacığının iş parçacığı kimliğini almak için bu yöntemi arayın.|
|[CWorkerThread::Initialize](#initialize)|Alt iş parçacığının başlatılması için bu yöntemi çağırın.|
|[CWorkerThread::RemoveHandle](#removehandle)|Bekletilebilir nesneler listesinden bir tanıtıcıyı kaldırmak için bu yöntemi arayın.|
|[CWorkerThread::Kapatma](#shutdown)|Alt iş parçacığı kapatmak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

### <a name="to-use-cworkerthread"></a>CWorkerThread kullanmak için

1. Bu sınıfın bir örneğini oluşturun.

1. [CWorkerThread'i Arayın::Initialize.](#initialize)

1. [CWorkerThread'i Arayın::Bir](#addhandle) çekirdek nesnesinin tutamacı ve [IWorkerThreadClient'ın](../../atl/reference/iworkerthreadclient-interface.md)uygulanmasına işaretçi ile AddHandle.

   \-veya -

   [Çağrı CWorkerThread::AddTimer](#addtimer) [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)bir uygulama için bir işaretçi ile .

1. [IWorkerThreadClient uygulayın::Tanıtıcı](../../atl/reference/iworkerthreadclient-interface.md#execute) veya zamanlayıcı sinyal verildiğinde bazı eylem de yürütmek.

1. Bir nesneyi beklenebilir nesneler listesinden kaldırmak için [CWorkerThread'i arayın:RemoveHandle.](#removehandle)

1. İş parçacığı sonlandırmak [için, CWorkerThread arayın::Kapatma](#shutdown).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="cworkerthreadaddhandle"></a><a name="addhandle"></a>CWorkerThread::AddHandle

İşçi iş parçacığı tarafından tutulan listeye beklenebilir bir nesnenin tanıtıcısını eklemek için bu yöntemi arayın.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Beklenebilir bir nesnenin tutamacı.

*pİsteSİ*<br/>
Tanıtıcı sinyal verildiğinde çağrılacak nesnedeki [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) arabiriminin işaretçisi.

*dwParam*<br/>
[IWorkerThreadClient'a](../../atl/reference/iworkerthreadclient-interface.md#execute) geçirilecek parametre::Tutamaç sinyal verildiğinde çalıştırın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) *pClient* üzerinden zaman kolu, *hObject*, sinyal olarak çağrılacak.

## <a name="cworkerthreadaddtimer"></a><a name="addtimer"></a>CWorkerThread::AddTimer

Alt iş parçacığı tarafından tutulan listeye periyodik olarak bekletilebilir zamanlayıcı eklemek için bu yöntemi arayın.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>Parametreler

*dwInterval*<br/>
Zamanlayıcının periyodu milisaniye cinsinden belirtir.

*pİsteSİ*<br/>
Tanıtıcı sinyal verildiğinde çağrılacak nesnedeki [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) arabiriminin işaretçisi.

*dwParam*<br/>
[IWorkerThreadClient'a](../../atl/reference/iworkerthreadclient-interface.md#execute) geçirilecek parametre::Tutamaç sinyal verildiğinde çalıştırın.

*phTimer*<br/>
[çıkış] Handle değişkeninin adresi, başarı üzerine, yeni oluşturulan zamanlayıcı için tutamacı alır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) zamanlayıcı sinyal verildiğinde *pClient* üzerinden çağrılacaktır.

Zamanlayıcıyı kapatmak için *phTimer'dan* CWorkerThread'e zamanlayıcı tutamacını [geçirin::Zamanlayıcıyı kapatmak için Kaldırıla'yı kaldırın.](#removehandle)

## <a name="cworkerthreadcworkerthread"></a><a name="cworkerthread"></a>CWorkerThread::CworkerThread

Oluşturucu.

```
CWorkerThread() throw();
```

## <a name="cworkerthreadcworkerthread"></a><a name="dtor"></a>CWorkerThread::~CWorkerThread

Yıkıcı.

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>Açıklamalar

[CWorkerThread'i Arar::Kapatma.](#shutdown)

## <a name="cworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle

Alt iş parçacığının iş parçacığı tutamacını almak için bu yöntemi arayın.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Alt iş parçacığı başharfe edilmemişse iş parçacığı tutamacını veya NULL'u döndürür.

## <a name="cworkerthreadgetthreadid"></a><a name="getthreadid"></a>CWorkerThread::GetThreadId

Alt iş parçacığının iş parçacığı kimliğini almak için bu yöntemi arayın.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Alt iş parçacığı başharfe edilmemişse iş parçacığı kimliğini veya NULL'u döndürür.

## <a name="cworkerthreadinitialize"></a><a name="initialize"></a>CWorkerThread::Initialize

Alt iş parçacığının başlatılması için bu yöntemi çağırın.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>Parametreler

*pThread*<br/>
Varolan bir alt iş parçacığı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, oluşturmadan sonra veya [CWorkerThread](#shutdown)için bir çağrı dan sonra nesneyi başlatmaya çağrılmalıdır::Kapatma .

İki veya daha `CWorkerThread` fazla nesnenin aynı alt iş parçacığı kullanmasını sağlamak için, herhangi bir bağımsız `Initialize` değişken ihdamadan bunlardan birini baş harfe getirin ve sonra bu nesneye diğerlerinin yöntemlerine bir işaretçi geçirin. İşaretçi kullanılarak başlatılan nesneler, bunları başlatmada kullanılan nesneden önce kapatılmalıdır.

Bkz. [CWorkerThread::Varolan](#shutdown) bir nesneye işaretçi kullanarak baş harfe geldiğinde bu yöntemin davranışının nasıl değiştiği hakkında bilgi için kapatma.

## <a name="cworkerthreadremovehandle"></a><a name="removehandle"></a>CWorkerThread::RemoveHandle

Bekletilebilir nesneler listesinden bir tanıtıcıyı kaldırmak için bu yöntemi arayın.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Kaldırılacak tutamaç.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı [kaldırıldığında IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) [AddHandle'a](#addhandle)geçirilen ilişkili nesneüzerinde çağrılacak. Bu çağrı başarısız `CWorkerThread` olursa, tanıtıcıdaki Windows [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) işlevini arayacaktır.

## <a name="cworkerthreadshutdown"></a><a name="shutdown"></a>CWorkerThread::Kapatma

Alt iş parçacığı kapatmak için bu yöntemi arayın.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>Parametreler

*dwWait*<br/>
Alt iş parçacığının kapanmasını beklemek için milisaniye cinsinden süre. ATL_WORKER_THREAD_WAIT varsayılan olarak 10 saniyedir. Gerekirse, atlutil.h dahil etmeden önce bu sembol için kendi değeri nizi tanımlayabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya zaman aşımı değeri *dwWait*aşıldığında gibi hata da bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Nesneyi yeniden kullanmak için [CWorkerThread'i arayın::Bu](#initialize) yöntemi aradıktan sonra başlatma.

İşaretçiyle `Shutdown` baş harfe dönen bir `CWorkerThread` nesneyi başka bir nesneye çağırmanın hiçbir etkisi olmadığını ve her zaman S_OK döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Varsayılan ThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[Çoklu İş Parçacığı Kullanımı: Çalışan İş Parçacıkları Oluşturma](../../parallel/multithreading-creating-worker-threads.md)<br/>
[IWorkerThreadClient Sınıfı](../../atl/reference/iworkerthreadclient-interface.md)
