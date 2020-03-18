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
ms.openlocfilehash: f1aa76514b98bbf12f8e516d3d54f68e8ef4dd7d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417721"
---
# <a name="cworkerthread-class"></a>CWorkerThread sınıfı

Bu sınıf, bir çalışan iş parçacığı oluşturur veya var olanı kullanır, bir veya daha fazla çekirdek nesne tanıtıcılarını bekler ve tutamaçlardan biri sinyalde olduğunda belirtilen bir istemci işlevini yürütür.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>Parametreler

*Threadnitelikler*<br/>
[Crtthreadnitelikler](../../atl/reference/crtthreadtraits-class.md) veya [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)gibi iş parçacığı oluşturma işlevini sağlayan sınıf.

## <a name="members"></a>Üyeler

### <a name="protected-structures"></a>Korumalı yapılar

|Adı|Açıklama|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWorkerThread:: CWorkerThread](#cworkerthread)|Çalışan iş parçacığı için Oluşturucu.|
|[CWorkerThread:: ~ CWorkerThread](#dtor)|Çalışan iş parçacığının yıkıcısı.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWorkerThread:: AddHandle](#addhandle)|Çalışan iş parçacığı tarafından tutulan listeye bir wasever nesnesinin tanıtıcısını eklemek için bu yöntemi çağırın.|
|[CWorkerThread:: AddTimer](#addtimer)|Çalışan iş parçacığı tarafından tutulan listeye düzenli bir wasever süreölçeri eklemek için bu yöntemi çağırın.|
|[CWorkerThread:: GetThreadHandle](#getthreadhandle)|Çalışan iş parçacığının iş parçacığı tanıtıcısını almak için bu yöntemi çağırın.|
|[CWorkerThread:: GetThreadId](#getthreadid)|Çalışan iş parçacığının iş parçacığı KIMLIĞINI almak için bu yöntemi çağırın.|
|[CWorkerThread:: Initialize](#initialize)|Çalışan iş parçacığını başlatmak için bu yöntemi çağırın.|
|[CWorkerThread:: RemoveHandle](#removehandle)|Bir tanıtıcıyı wasever nesneleri listesinden kaldırmak için bu yöntemi çağırın.|
|[CWorkerThread:: kapanıyor](#shutdown)|Çalışan iş parçacığını kapatmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

### <a name="to-use-cworkerthread"></a>CWorkerThread kullanmak için

1. Bu sınıfın bir örneğini oluşturun.

1. [CWorkerThread:: Initialize](#initialize)öğesini çağırın.

1. Bir çekirdek nesnesinin tanıtıcısı ve [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)uygulamasının bir Işaretçisi Ile [CWorkerThread:: AddHandle](#addhandle) çağırın.

   \- veya-

   [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)uygulamasına yönelik bir Işaretçiyle [CWorkerThread:: AddTimer](#addtimer) çağrısı yapın.

1. Tanıtıcı veya zamanlayıcı sinyali geldiğinde bazı işlemleri yapmak için [IWorkerThreadClient:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) öğesini uygulayın.

1. Bir nesneyi wasever nesneleri listesinden kaldırmak için [CWorkerThread:: RemoveHandle](#removehandle)çağırın.

1. İş parçacığını sonlandırmak için [CWorkerThread:: kapatılmasını](#shutdown)çağırın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

##  <a name="addhandle"></a>CWorkerThread:: AddHandle

Çalışan iş parçacığı tarafından tutulan listeye bir wasever nesnesinin tanıtıcısını eklemek için bu yöntemi çağırın.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Bir wasever nesnesine olan tanıtıcı.

*pClient*<br/>
Tanıtıcı sinyalden çağrıldığında çağrılacak nesne üzerindeki [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) arabirimine yönelik işaretçi.

*dwParam*<br/>
Tanıtıcı sinyalden sonra [IWorkerThreadClient:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) öğesine geçirilecek parametre.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[IWorkerThreadClient:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) , *Hosbject*olduğunda *pClient* aracılığıyla çağrılacaktır.

##  <a name="addtimer"></a>CWorkerThread:: AddTimer

Çalışan iş parçacığı tarafından tutulan listeye düzenli bir wasever süreölçeri eklemek için bu yöntemi çağırın.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>Parametreler

*Dwınterval*<br/>
Süre ölçer süresini milisaniye olarak belirtir.

*pClient*<br/>
Tanıtıcı sinyalden çağrıldığında çağrılacak nesne üzerindeki [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) arabirimine yönelik işaretçi.

*dwParam*<br/>
Tanıtıcı sinyalden sonra [IWorkerThreadClient:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) öğesine geçirilecek parametre.

*Olağanüstü Zamanlayıcı*<br/>
dışı Başarı durumunda, yeni oluşturulan Zamanlayıcı için tanıtıcıyı alan tanıtıcı değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[IWorkerThreadClient:: Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) , zamanlayıcıya sinyal geldiğinde *pClient* aracılığıyla çağrılır.

Zamanlayıcıyı kapatmak için *olağanüstü zamanlayıcının* Zamanlayıcı tanıtıcısını [CWorkerThread:: RemoveHandle](#removehandle) 'a geçirin.

##  <a name="cworkerthread"></a>CWorkerThread:: CWorkerThread

Oluşturucu.

```
CWorkerThread() throw();
```

##  <a name="dtor"></a>CWorkerThread:: ~ CWorkerThread

Yok edicisi.

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>Açıklamalar

[CWorkerThread:: kapatılmasını](#shutdown)çağırır.

##  <a name="getthreadhandle"></a>CWorkerThread:: GetThreadHandle

Çalışan iş parçacığının iş parçacığı tanıtıcısını almak için bu yöntemi çağırın.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışan iş parçacığı başlatılmamışsa iş parçacığı tanıtıcısını veya NULL değerini döndürür.

##  <a name="getthreadid"></a>CWorkerThread:: GetThreadId

Çalışan iş parçacığının iş parçacığı KIMLIĞINI almak için bu yöntemi çağırın.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışan iş parçacığı başlatılmamışsa iş parçacığı KIMLIĞINI veya NULL değerini döndürür.

##  <a name="initialize"></a>CWorkerThread:: Initialize

Çalışan iş parçacığını başlatmak için bu yöntemi çağırın.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>Parametreler

*pThread*<br/>
Mevcut bir çalışan iş parçacığı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, oluşturulduktan sonra veya [CWorkerThread:: kapanmaya](#shutdown)yönelik bir çağrıdan sonra nesneyi başlatmak için çağrılmalıdır.

İki veya daha fazla `CWorkerThread` nesnenin aynı çalışan iş parçacığını kullanması için herhangi bir bağımsız değişkeni geçirmeden bunlardan birini başlatın ve ardından bu nesneye bir işaretçi geçirerek diğerlerinin `Initialize` yöntemlerine geçirin. İşaretçi kullanılarak başlatılan nesneler, nesneyi başlatmak için kullanılmadan önce kapatılmalıdır.

Bu yöntemin davranışının, var olan bir nesnenin işaretçisi kullanılarak başlatıldığında nasıl değiştiği hakkında bilgi için bkz. [CWorkerThread:: kapanıyor](#shutdown) .

##  <a name="removehandle"></a>CWorkerThread:: RemoveHandle

Bir tanıtıcıyı wasever nesneleri listesinden kaldırmak için bu yöntemi çağırın.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Kaldırılacak tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı kaldırıldığında [IWorkerThreadClient:: CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) , [AddHandle](#addhandle)'a geçirilen ilişkili nesne üzerinde çağrılır. Bu çağrı başarısız olursa, `CWorkerThread` tanıtıcıda Windows [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) işlevini çağırır.

##  <a name="shutdown"></a>CWorkerThread:: kapanıyor

Çalışan iş parçacığını kapatmak için bu yöntemi çağırın.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>Parametreler

*dwWait*<br/>
Çalışan iş parçacığının kapanması için beklenecek süre (milisaniye olarak). ATL_WORKER_THREAD_WAIT varsayılan değer 10 saniyedir. Gerekirse, atlutil. h dahil etmeden önce Bu sembol için kendi değerini tanımlayabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT, zaman aşımı değeri *dwWait*gibi döndürür.

### <a name="remarks"></a>Açıklamalar

Nesneyi yeniden kullanmak için, bu yöntemi çağırdıktan sonra [CWorkerThread:: Initialize](#initialize) öğesini çağırın.

Başka bir `CWorkerThread` nesnesinin işaretçisi ile başlatılan bir nesne üzerinde `Shutdown` çağırmanın etkin olmadığını ve her zaman S_OK döndürdüğünü unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Defaultthreadnitelikler](atl-typedefs.md#defaultthreadtraits)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[Çoklu İş Parçacığı Kullanımı: Çalışan İş Parçacıkları Oluşturma](../../parallel/multithreading-creating-worker-threads.md)<br/>
[IWorkerThreadClient Sınıfı](../../atl/reference/iworkerthreadclient-interface.md)
