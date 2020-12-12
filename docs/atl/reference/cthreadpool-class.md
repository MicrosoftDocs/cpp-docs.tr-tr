---
description: 'Daha fazla bilgi edinin: CThreadPool sınıfı'
title: CThreadPool sınıfı
ms.date: 11/04/2016
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
ms.openlocfilehash: 445b32ccff2df2456687e9b9ae34950c91c00613
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140367"
---
# <a name="cthreadpool-class"></a>CThreadPool sınıfı

Bu sınıf iş öğelerinin bir kuyruğunu işleyen çalışan iş parçacıklarının havuzunu sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>Parametreler

*Indan*<br/>
İş parçacığı havuzunda sıraya alınan iş öğelerini işlemek için kullanılan kodu sağlayan [çalışan arşiv ETYPE](../../atl/reference/worker-archetype.md) 'e uyan sınıf.

*Threadnitelikler*<br/>
Havuzdaki iş parçacıklarını oluşturmak için kullanılan işlevi sağlayan sınıf.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CThreadPool:: CThreadPool](#cthreadpool)|İş parçacığı havuzu için Oluşturucu.|
|[CThreadPool:: ~ CThreadPool](#dtor)|İş parçacığı havuzu için yok edici.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CThreadPool:: AddRef](#addref)|Uygulamasının uygulamasıdır `IUnknown::AddRef` .|
|[CThreadPool:: GetNumThreads](#getnumthreads)|Havuzdaki iş parçacığı sayısını almak için bu yöntemi çağırın.|
|[CThreadPool:: GetQueueHandle](#getqueuehandle)|İş öğelerini kuyruğa almak için kullanılan GÇ tamamlama bağlantı noktasının tanıtıcısını almak için bu yöntemi çağırın.|
|[CThreadPool:: GetSize](#getsize)|Havuzdaki iş parçacığı sayısını almak için bu yöntemi çağırın.|
|[CThreadPool:: GetTimeout](#gettimeout)|İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye olarak almak için bu yöntemi çağırın.|
|[CThreadPool:: Initialize](#initialize)|İş parçacığı havuzunu başlatmak için bu yöntemi çağırın.|
|[CThreadPool:: QueryInterface](#queryinterface)|Uygulamasının uygulamasıdır `IUnknown::QueryInterface` .|
|[CThreadPool:: QueueRequest](#queuerequest)|Havuzdaki iş parçacığı tarafından işlenecek bir iş öğesini sıraya almak için bu yöntemi çağırın.|
|[CThreadPool:: Release](#release)|Uygulamasının uygulamasıdır `IUnknown::Release` .|
|[CThreadPool:: SetSize](#setsize)|Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.|
|[CThreadPool:: SetTimeout](#settimeout)|İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye cinsinden ayarlamak için bu yöntemi çağırın.|
|[CThreadPool:: kapanıyor](#shutdown)|İş parçacığı havuzunu kapatmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Havuzun başlatılması, yeniden boyutlandırılması veya kapatılması durumunda havuzdaki iş parçacıkları oluşturulur ve yok edilir. Havuzdaki her çalışan iş parçacığının yığınında, *çalışan* sınıfının bir örneği oluşturulacaktır. Her örnek iş parçacığının ömrü boyunca etkin olacaktır.

İş parçacığı oluşturulduktan hemen sonra, iş  `Initialize` parçacığı ile Ilişkili nesne üzerinde çalışan:: çağırılır. Bir iş parçacığının yok edilmesiyle hemen önce, *Worker*:: `Terminate` çağrılır. Her iki yöntem de bir **`void`** <strong>\*</strong> bağımsız değişken kabul etmelidir. Bu bağımsız değişkenin değeri, [CThreadPool:: Initialize](#initialize)öğesinin *pvWorkerParam* parametresi aracılığıyla iş parçacığı havuzuna geçirilir.

Kuyrukta ve çalışan iş parçacıklarında iş öğeleri olduğunda, bir çalışan iş parçacığı kuyruktan bir öğe çeker ve `Execute` o iş parçacığı Için *çalışan* nesnesinin yöntemini çağırır. Daha sonra bu yönteme üç öğe geçirilir: kuyruktaki öğe, `pvWorkerParam` *Worker*:: `Initialize` ve *Worker*:: `Terminate` olarak ve g/ç tamamlama bağlantı noktası kuyruğu için kullanılan [örtüşen](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) yapıya yönelik bir işaretçi.

*Çalışan* sınıfı, bir typedef, *Worker*:: ile iş parçacığı havuzunda sıraya eklenecek öğelerin türünü bildirir `RequestType` . Bu tür, bir ULONG_PTR dönüştürme özelliğine sahip olmalıdır.

*Çalışan* sınıfının bir örneği, [CNonStatelessWorker sınıfıdır](../../atl/reference/cnonstatelessworker-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUnknown`

[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="cthreadpooladdref"></a><a name="addref"></a> CThreadPool:: AddRef

Uygulamasının uygulamasıdır `IUnknown::AddRef` .

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf, başvuru sayımı kullanılarak yaşam süresi denetimini uygulamaz.

## <a name="cthreadpoolcthreadpool"></a><a name="cthreadpool"></a> CThreadPool:: CThreadPool

İş parçacığı havuzu için Oluşturucu.

```
CThreadPool() throw();
```

### <a name="remarks"></a>Açıklamalar

ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT için zaman aşımı değerini başlatır. Varsayılan süre 36 saniyedir. Gerekirse, atlutil. h 'yi dahil etmeden önce Bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

## <a name="cthreadpoolcthreadpool"></a><a name="dtor"></a> CThreadPool:: ~ CThreadPool

İş parçacığı havuzu için yok edici.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>Açıklamalar

[CThreadPool:: kapatılmasını](#shutdown)çağırır.

## <a name="cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a> CThreadPool:: GetNumThreads

Havuzdaki iş parçacığı sayısını almak için bu yöntemi çağırın.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Havuzdaki iş parçacıklarının sayısını döndürür.

## <a name="cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a> CThreadPool:: GetQueueHandle

İş öğelerini kuyruğa almak için kullanılan GÇ tamamlama bağlantı noktasının tanıtıcısını almak için bu yöntemi çağırın.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı havuzu başlatılmamışsa kuyruk tanıtıcısını veya NULL değerini döndürür.

## <a name="cthreadpoolgetsize"></a><a name="getsize"></a> CThreadPool:: GetSize

Havuzdaki iş parçacığı sayısını almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>Parametreler

*pnNumThreads*<br/>
dışı Başarılı olan değişkenin, havuzdaki iş parçacığı sayısını aldığı değişken adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="cthreadpoolgettimeout"></a><a name="gettimeout"></a> CThreadPool:: GetTimeout

İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye olarak almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>Parametreler

*pdwMaxWait*<br/>
dışı Başarılı olan değişkenin, iş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye olarak alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu zaman aşımı değeri, bu yönteme başka bir değer sağlanmadığında [CThreadPool:: kapanıyor](#shutdown) tarafından kullanılır.

## <a name="cthreadpoolinitialize"></a><a name="initialize"></a> CThreadPool:: Initialize

İş parçacığı havuzunu başlatmak için bu yöntemi çağırın.

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>Parametreler

*pvWorkerParam*<br/>
Çalışan iş parçacığı nesnesinin `Initialize` , ve yöntemlerine geçirilecek çalışan parametresi `Execute` `Terminate` .

*nNumThreads*<br/>
Havuzdaki istenen iş parçacığı sayısı.

*NNumThreads* negatifse, toplam iş parçacığı sayısını almak için, mutlak değeri makinedeki işlemci sayısıyla çarpılacak.

*NNumThreads* sıfırsa, ATLS_DEFAULT_THREADSPERPROC toplam iş parçacığı sayısını almak için makinedeki işlemci sayısıyla çarpılacak.  İşlemci başına 2 iş parçacığı varsayılandır. Gerekirse, atlutil. h 'yi dahil etmeden önce Bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

*dwStackSize*<br/>
Havuzdaki her iş parçacığının yığın boyutu.

*hCompletion*<br/>
Tamamlama bağlantı noktasıyla ilişkilendirilecek nesnenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="cthreadpoolqueryinterface"></a><a name="queryinterface"></a> CThreadPool:: QueryInterface

Uygulamasının uygulamasıdır `IUnknown::QueryInterface` .

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu sınıfın nesneleri, `IUnknown` ve [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) arabirimleri için başarıyla sorgulanabilir.

## <a name="cthreadpoolqueuerequest"></a><a name="queuerequest"></a> CThreadPool:: QueueRequest

Havuzdaki iş parçacığı tarafından işlenecek bir iş öğesini sıraya almak için bu yöntemi çağırın.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>Parametreler

*isteyen*<br/>
Kuyruğa alma isteği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kuyruğa bir iş öğesi ekler. Havuzdaki iş parçacıkları, öğeleri alındıkları sırada bir kuyruk dışında seçer.

## <a name="cthreadpoolrelease"></a><a name="release"></a> CThreadPool:: Release

Uygulamasının uygulamasıdır `IUnknown::Release` .

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf, başvuru sayımı kullanılarak yaşam süresi denetimini uygulamaz.

## <a name="cthreadpoolsetsize"></a><a name="setsize"></a> CThreadPool:: SetSize

Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>Parametreler

*nNumThreads*<br/>
Havuzdaki istenen iş parçacığı sayısı.

*NNumThreads* negatifse, toplam iş parçacığı sayısını almak için, mutlak değeri makinedeki işlemci sayısıyla çarpılacak.

*NNumThreads* sıfırsa, ATLS_DEFAULT_THREADSPERPROC toplam iş parçacığı sayısını almak için makinedeki işlemci sayısıyla çarpılacak. İşlemci başına 2 iş parçacığı varsayılandır. Gerekirse, atlutil. h 'yi dahil etmeden önce Bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Belirtilen iş parçacığı sayısı, havuzdaki Şu anda iş parçacığı sayısından az ise, nesne bekleyen bir iş parçacığı tarafından çekilecek sıraya bir kapatılma iletisi koyar. Bekleyen bir iş parçacığı iletiyi kuyruktan çeker, iş parçacığı havuzuna bildirir ve iş parçacığı yordamından çıkar. Bu işlem, havuzdaki iş parçacığı sayısı belirtilen sayıya ulaşıncaya kadar veya [GetTimeout](#gettimeout)setTimeout tarafından belirtilen süre içinde çıkış yapana kadar yinelenir /  [](#settimeout). Bu durumda yöntem WAIT_TIMEOUT karşılık gelen bir HRESULT döndürür ve bekleyen kapatılma iletisi iptal edilir.

## <a name="cthreadpoolsettimeout"></a><a name="settimeout"></a> CThreadPool:: SetTimeout

İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleyeceği en uzun süreyi milisaniye cinsinden ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>Parametreler

*dwMaxWait*<br/>
İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleneceği milisaniye cinsinden istenen en uzun süre.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Zaman aşımı ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT olarak başlatılır. Varsayılan süre 36 saniyedir. Gerekirse, atlutil. h 'yi dahil etmeden önce Bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

*DwMaxWait* 'in, havuzun tek bir iş parçacığının kapatılmasını bekleyeceği zaman olduğunu unutmayın. Havuzdan birden çok iş parçacığını kaldırmak için alınabilecek en uzun süre, iş parçacığı sayısıyla itibaren *dwMaxWait* 'tan biraz daha az olabilir.

## <a name="cthreadpoolshutdown"></a><a name="shutdown"></a> CThreadPool:: kapanıyor

İş parçacığı havuzunu kapatmak için bu yöntemi çağırın.

```cpp
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>Parametreler

*dwMaxWait*<br/>
İş parçacığı havuzunun bir iş parçacığının kapatılmasını bekleneceği milisaniye cinsinden istenen en uzun süre. 0 veya hiçbir değer sağlanmazsa, bu yöntem [CThreadPool:: setTimeout](#settimeout)tarafından ayarlanan zaman aşımını kullanır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, havuzdaki tüm iş parçacıklarına bir kapalı isteği gönderir. Zaman aşımı süresi dolarsa, bu yöntem, çıkış olmayan herhangi bir iş parçacığında [TerminateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-terminatethread) öğesini çağırır. Bu yöntem, sınıfının yıkıcısında otomatik olarak çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[IThreadPoolConfig arabirimi](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[Defaultthreadnitelikler](atl-typedefs.md#defaultthreadtraits)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)
