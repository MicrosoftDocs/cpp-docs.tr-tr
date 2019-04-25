---
title: CWorkerThread sınıfı
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
ms.openlocfilehash: d4645f4a57ce70c3683972c22e0f99cbce87ca6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276665"
---
# <a name="cworkerthread-class"></a>CWorkerThread sınıfı

Bu sınıf bir çalışan iş parçacığı oluşturur veya mevcut bir kullanır, bir veya daha fazla çekirdek nesne tutamaçları bekler ve tutamaçlarından birinin sinyal, belirtilen istemci işlevi yürütür.

> [!IMPORTANT]
> Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>Parametreler

*ThreadTraits*<br/>
İş parçacığı oluşturma işlevi gibi sağlama sınıfı [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) veya [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).

## <a name="members"></a>Üyeler

### <a name="protected-structures"></a>Korunan yapılar

|Ad|Açıklama|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWorkerThread::CWorkerThread](#cworkerthread)|Çalışan iş parçacığı için oluşturucu.|
|[CWorkerThread:: ~ CWorkerThread](#dtor)|Çalışan iş parçacığı yok Edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWorkerThread::AddHandle](#addhandle)|Beklenebilir nesne tanıtıcısı iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.|
|[CWorkerThread::AddTimer](#addtimer)|Düzenli bir beklenebilir Zamanlayıcı iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.|
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Çalışan iş parçacığının iş parçacığı tanıtıcısını almak için bu yöntemi çağırın.|
|[CWorkerThread::GetThreadId](#getthreadid)|Çalışan iş parçacığının iş parçacığı Kimliğini almak için bu yöntemi çağırın.|
|[CWorkerThread::Initialize](#initialize)|Çalışan iş parçacığı başlatmak için bu yöntemi çağırın.|
|[CWorkerThread::RemoveHandle](#removehandle)|Bir tanıtıcı beklenebilir nesne listeden kaldırmak için bu yöntemi çağırın.|
|[CWorkerThread::Shutdown](#shutdown)|Çalışan iş parçacığı kapatmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

### <a name="to-use-cworkerthread"></a>CWorkerThread kullanmak için

1. Bu sınıfın bir örneğini oluşturun.

1. Çağrı [CWorkerThread::Initialize](#initialize).

1. Çağrı [CWorkerThread::AddHandle](#addhandle) Çekirdek nesnesi ve uygulaması için bir işaretçi, tanıtıcı ile [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).

   \- veya -

   Çağrı [CWorkerThread::AddTimer](#addtimer) uygulanmasına yönelik bir işaretçi ile [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).

1. Uygulama [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) tanıtıcı veya Zamanlayıcı sinyal olduğunda bazı işlemler yapması için.

1. Bir nesne beklenebilir nesne listesinden kaldırmak için çağrı [CWorkerThread::RemoveHandle](#removehandle).

1. İş parçacığını sonlandırmak için çağrı [CWorkerThread::Shutdown](#shutdown).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

##  <a name="addhandle"></a>  CWorkerThread::AddHandle

Beklenebilir nesne tanıtıcısı iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Beklenebilir nesne için tanıtıcı.

*pClient*<br/>
İşaretçi [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) arabirimi nesne tanıtıcısını sinyal çağırılır.

*dwParam*<br/>
Geçirilecek parametreyi [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) tanıtıcı sinyal zaman.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) aracılığıyla adlı *pClient* olduğunda tanıtıcı *hObject*, işareti verilen.

##  <a name="addtimer"></a>  CWorkerThread::AddTimer

Düzenli bir beklenebilir Zamanlayıcı iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>Parametreler

*dwInterval*<br/>
Zamanlayıcının milisaniye cinsinden belirler.

*pClient*<br/>
İşaretçi [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) arabirimi nesne tanıtıcısını sinyal çağırılır.

*dwParam*<br/>
Geçirilecek parametreyi [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) tanıtıcı sinyal zaman.

*phTimer*<br/>
[out] Başarı durumunda, yeni oluşturulan Zamanlayıcı tanıtıcısını alır, tanıtıcı değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) aracılığıyla adlı *pClient* Zamanlayıcı sinyal zaman.

Zamanlayıcı tanıtıcıdan geçirmek *phTimer* için [CWorkerThread::RemoveHandle](#removehandle) Zamanlayıcı kapatın.

##  <a name="cworkerthread"></a>  CWorkerThread::CWorkerThread

Oluşturucu.

```
CWorkerThread() throw();
```

##  <a name="dtor"></a>  CWorkerThread:: ~ CWorkerThread

Yıkıcı.

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>Açıklamalar

Çağrıları [CWorkerThread::Shutdown](#shutdown).

##  <a name="getthreadhandle"></a>  CWorkerThread::GetThreadHandle

Çalışan iş parçacığının iş parçacığı tanıtıcısını almak için bu yöntemi çağırın.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışan iş parçacığı başlatılmadı iş parçacığı tanıtıcısı veya NULL döndürür.

##  <a name="getthreadid"></a>  CWorkerThread::GetThreadId

Çalışan iş parçacığının iş parçacığı Kimliğini almak için bu yöntemi çağırın.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışan iş parçacığı başlatılmadı iş parçacığı kimliği veya NULL döndürür.

##  <a name="initialize"></a>  CWorkerThread::Initialize

Çalışan iş parçacığı başlatmak için bu yöntemi çağırın.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>Parametreler

*pThread*<br/>
Mevcut bir iş parçacığı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Oluşturulduktan sonra veya çağrısı yapıldıktan sonra nesneyi başlatmak için bu yöntem çağrılmalıdır [CWorkerThread::Shutdown](#shutdown).

İki veya daha fazla `CWorkerThread` nesneleri aynı çalışan iş parçacığı kullanma, bir tanesi herhangi bir bağımsız değişken ardından geçirmek işaretçi için bu nesneye geçirme olmadan başlatmak `Initialize` diğer yöntemleri. İşaretçi kullanılarak başlatılan nesneler bunları başlatmak için kullanılan nesne önce kapatılması.

Bkz: [CWorkerThread::Shutdown](#shutdown) bilgi var olan bir nesneye bir işaretçi kullanılarak başlatılır, bu yöntemin davranışını nasıl değiştirir.

##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle

Bir tanıtıcı beklenebilir nesne listeden kaldırmak için bu yöntemi çağırın.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Kaldırılacak işleyici.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı kaldırıldığında [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) geçildi ilişkili nesne üzerinde çağrılacak [AddHandle](#addhandle). Bu çağrı başarısız olursa `CWorkerThread` Windows'ın arayacağı [CloseHandle](/windows/desktop/api/handleapi/nf-handleapi-closehandle) tutamacı işlevi.

##  <a name="shutdown"></a>  CWorkerThread::Shutdown

Çalışan iş parçacığı kapatmak için bu yöntemi çağırın.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>Parametreler

*dwWait*<br/>
Çalışan iş parçacığı kapatmak beklenecek milisaniye cinsinden süre. Varsayılan olarak 10 saniye ATL_WORKER_THREAD_WAIT. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi değeri tanımlayabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya hata durumunda, IF gibi bir hata HRESULT S_OK döndürür zaman aşımı değeri *dwWait*, aşıldı.

### <a name="remarks"></a>Açıklamalar

Nesnesini yeniden kullanmak için çağrı [CWorkerThread::Initialize](#initialize) bu yöntemi çağrıldıktan sonra.

Çağırmanın Not `Shutdown` başka bir işaretçi ile başlatılan bir nesne üzerinde `CWorkerThread` nesne hiçbir etkisi yoktur ve her zaman S_OK döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[Çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](../../parallel/multithreading-creating-worker-threads.md)<br/>
[IWorkerThreadClient Sınıfı](../../atl/reference/iworkerthreadclient-interface.md)
