---
title: CThreadPool Sınıfı
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
ms.openlocfilehash: 5e52868f23883836919b96be9aec1815bc1c17b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747453"
---
# <a name="cthreadpool-class"></a>CThreadPool Sınıfı

Bu sınıf, çalışma öğeleri kuyruğuni işleyen bir alt iş parçacığı havuzu sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>Parametreler

*Işçi*<br/>
İş parçacığı havuzunda sıraya girilen iş öğelerini işlemek için kullanılan kodu sağlayan [alt arketipe](../../atl/reference/worker-archetype.md) uyan sınıf.

*Konu Özellikleri*<br/>
Havuzdaki iş parçacıklarını oluşturmak için kullanılan işlevi sağlayan sınıf.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CThreadPool::CThreadPool](#cthreadpool)|İş parçacığı havuzunun oluşturucusu.|
|[CThreadPool::~CThreadPool](#dtor)|İş parçacığı havuzu için yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CThreadPool::Addref](#addref)|Uygulama `IUnknown::AddRef`.|
|[CThreadPool::GetNumThreads](#getnumthreads)|Havuzdaki iş parçacığı sayısını almak için bu yöntemi arayın.|
|[CThreadPool::GetQueueHandle](#getqueuehandle)|İş öğelerini sıraya almak için kullanılan IO tamamlama bağlantı noktasının tutamacını almak için bu yöntemi arayın.|
|[CThreadPool::GetSize](#getsize)|Havuzdaki iş parçacığı sayısını almak için bu yöntemi arayın.|
|[CThreadPool::GetTimeout](#gettimeout)|İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniyecinsinden en fazla zamanı almak için bu yöntemi arayın.|
|[CThreadPool::Initialize](#initialize)|İş parçacığı havuzunu başlatmaya çalışmak için bu yöntemi arayın.|
|[CThreadPool::QueryInterface](#queryinterface)|Uygulama `IUnknown::QueryInterface`.|
|[CThreadPool::QueueRequest](#queuerequest)|Bir iş parçacığı tarafından işlenecek bir iş öğesi sıraya bu yöntemi çağırın.|
|[CThreadPool::Sürüm](#release)|Uygulama `IUnknown::Release`.|
|[CThreadPool::SetSize](#setsize)|Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi arayın.|
|[CThreadPool::SetTimeout](#settimeout)|İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden maksimum süreyi ayarlamak için bu yöntemi arayın.|
|[CThreadPool::Kapatma](#shutdown)|İş parçacığı havuzunu kapatmak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Havuzdaki iş parçacıkları, havuz başharfe düşürüldüğünde, yeniden boyutlandırıldığında veya kapatıldığında oluşturulur ve yok edilir. Sınıf *İşçibir* örnek havuzda her işçi iş parçacığı yığını üzerinde oluşturulur. Her örnek iş parçacığının ömrü boyunca yaşayacaktır.

Bir iş parçacığı oluşturulduktan hemen`Initialize` sonra, *İşçi*:: bu iş parçacığı ile ilişkili nesne üzerinde çağrılacaktır. Bir iş parçacığı nın *Worker*imha`Terminate` hemen önce, İşçi :: çağrılacaktır. Her iki yöntem de **geçersiz** <strong>\*</strong> bir bağımsız değişkeni kabul etmelidir. Bu bağımsız değişkenin değeri CThreadPool *pvWorkerParam* parametresi üzerinden iş parçacığı havuzuna [geçirilir::Initialize](#initialize).

Kuyrukta iş öğeleri ve iş için kullanılabilir alt iş parçacıkları olduğunda, bir alt iş `Execute` parçacığı bir öğeyi kuyruktan çeker ve bu iş parçacığı için *İşçi* nesnesinin yöntemini çağırır. Üç öğe daha sonra yönteme geçirilir: kuyruktan `pvWorkerParam` öğe, *Aynı İşçi*geçti `Initialize` :: ve *İşçi*:: `Terminate`, IO tamamlama bağlantı noktası kuyruğu için kullanılan [Overlapped](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) yapısına bir işaretçi.

*İşçi* sınıfı bir typedef sağlayarak iş parçacığı havuzunda sıralanacak öğelerin türünü bildirir, `RequestType` *İşçi*:: . Bu tür ve bir ULONG_PTR döküm yeteneğine sahip olmalıdır.

*Bir İşçi* sınıfının bir örneği [CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)Sınıfı'dır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUnknown`

[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="cthreadpooladdref"></a><a name="addref"></a>CThreadPool::Addref

Uygulama `IUnknown::AddRef`.

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf, başvuru sayımı nı kullanarak yaşam boyu denetimi uygulamaz.

## <a name="cthreadpoolcthreadpool"></a><a name="cthreadpool"></a>CThreadPool::CThreadPool

İş parçacığı havuzunun oluşturucusu.

```
CThreadPool() throw();
```

### <a name="remarks"></a>Açıklamalar

zaman açıkçılığını ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT açıklamak. Varsayılan süre 36 saniyedir. Gerekirse, atlutil.h dahil etmeden önce bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

## <a name="cthreadpoolcthreadpool"></a><a name="dtor"></a>CThreadPool::~CThreadPool

İş parçacığı havuzu için yıkıcı.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>Açıklamalar

[Aramalar CThreadPool::Shutdown](#shutdown).

## <a name="cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a>CThreadPool::GetNumThreads

Havuzdaki iş parçacığı sayısını almak için bu yöntemi arayın.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Havuzdaki iş parçacığı sayısını verir.

## <a name="cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a>CThreadPool::GetQueueHandle

İş öğelerini sıraya almak için kullanılan IO tamamlama bağlantı noktasının tutamacını almak için bu yöntemi arayın.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı havuzu başharflere geçirilmişdeğilse, sıra tutamacını veya NULL'u döndürür.

## <a name="cthreadpoolgetsize"></a><a name="getsize"></a>CThreadPool::GetSize

Havuzdaki iş parçacığı sayısını almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>Parametreler

*pnNumThreads*<br/>
[çıkış] Başarı üzerine, havuzdaki iş parçacığı sayısını alan değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cthreadpoolgettimeout"></a><a name="gettimeout"></a>CThreadPool::GetTimeout

İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniyecinsinden en fazla zamanı almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>Parametreler

*pdwMaxWait*<br/>
[çıkış] Başarı da, iş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden en fazla süreyi alan değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu zaman aşım değeri [CThreadPool tarafından kullanılır::Bu](#shutdown) yönteme başka bir değer sağlanmışsa kapatma.

## <a name="cthreadpoolinitialize"></a><a name="initialize"></a>CThreadPool::Initialize

İş parçacığı havuzunu başlatmaya çalışmak için bu yöntemi arayın.

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>Parametreler

*pvWorkerParam*<br/>
Alt iş parçacığı nesnesine `Initialize` `Execute`ve `Terminate` yöntemlerine geçirilecek alt parametre.

*nNumThreads*<br/>
Havuzda istenen iş parçacığı sayısı.

*NNumThreads* negatif ise, mutlak değeri makinedeki işlemci sayısı ile çarpımır ve toplam iş parçacığı sayısını elde eder.

*nNumThreads* sıfır ise, ATLS_DEFAULT_THREADSPERPROC makinedeki işlemci sayısı ile çarpımır ve toplam iş parçacığı sayısını elde edecektir.  Varsayılan işlemci başına 2 iş parçacığıdır. Gerekirse, atlutil.h dahil etmeden önce bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

*dwStackSize*<br/>
Havuzdaki her iş parçacığı için yığın boyutu.

*hCompletion*<br/>
Tamamlama bağlantı noktası ile ilişkilendirmek için bir nesnenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cthreadpoolqueryinterface"></a><a name="queryinterface"></a>CThreadPool::QueryInterface

Uygulama `IUnknown::QueryInterface`.

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu sınıfın nesneleri başarıyla `IUnknown` ve [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) arabirimleri için sorgulanabilir.

## <a name="cthreadpoolqueuerequest"></a><a name="queuerequest"></a>CThreadPool::QueueRequest

Bir iş parçacığı tarafından işlenecek bir iş öğesi sıraya bu yöntemi çağırın.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>Parametreler

*Istek*<br/>
Sıraya alınma isteği.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sıraya bir iş öğesi ekler. Havuzdaki iş parçacıkları, alındıkları sırada sıradaki öğeleri sırayla alır.

## <a name="cthreadpoolrelease"></a><a name="release"></a>CThreadPool::Sürüm

Uygulama `IUnknown::Release`.

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sınıf, başvuru sayımı nı kullanarak yaşam boyu denetimi uygulamaz.

## <a name="cthreadpoolsetsize"></a><a name="setsize"></a>CThreadPool::SetSize

Havuzdaki iş parçacığı sayısını ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>Parametreler

*nNumThreads*<br/>
Havuzda istenen iş parçacığı sayısı.

*NNumThreads* negatif ise, mutlak değeri makinedeki işlemci sayısı ile çarpımır ve toplam iş parçacığı sayısını elde eder.

*nNumThreads* sıfır ise, ATLS_DEFAULT_THREADSPERPROC makinedeki işlemci sayısı ile çarpımır ve toplam iş parçacığı sayısını elde edecektir. Varsayılan işlemci başına 2 iş parçacığıdır. Gerekirse, atlutil.h dahil etmeden önce bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Belirtilen iş parçacığı sayısı havuzda bulunan iş parçacığı sayısından azsa, nesne bekleyen bir iş parçacığı tarafından alınmak üzere sıraya kapatma iletisi koyar. Bekleyen bir iş parçacığı iletiyi kuyruktan çektiğinde, iş parçacığı havuzunu haberverirken iş parçacığı yordamından çıkar. Bu işlem, havuzdaki iş parçacığı sayısı belirtilen sayıya ulaşıncaya veya [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)tarafından belirtilen süre içinde iş parçacığı çıkana kadar yinelenir. Bu durumda yöntem, WAIT_TIMEOUT karşılık gelen bir HRESULT döndürecek ve bekleyen kapatma iletisi iptal edilir.

## <a name="cthreadpoolsettimeout"></a><a name="settimeout"></a>CThreadPool::SetTimeout

İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden maksimum süreyi ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>Parametreler

*dwMaxWait*<br/>
İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden istenen maksimum süre.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Zaman açısından ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT. Varsayılan süre 36 saniyedir. Gerekirse, atlutil.h dahil etmeden önce bu sembol için kendi pozitif tamsayı değeri tanımlayabilirsiniz.

*DwMaxWait* havuzun tek bir iş parçacığının kapanmasını bekleyeceği zamandır olduğunu unutmayın. Havuzdan birden fazla iş parçacığı kaldırmak için alınabilir maksimum süre biraz *dwMaxWait* iş parçacığı sayısı ile çarpılır daha az olabilir.

## <a name="cthreadpoolshutdown"></a><a name="shutdown"></a>CThreadPool::Kapatma

İş parçacığı havuzunu kapatmak için bu yöntemi arayın.

```cpp
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>Parametreler

*dwMaxWait*<br/>
İş parçacığı havuzunun iş parçacığının kapanmasını bekleyeceği milisaniye cinsinden istenen maksimum süre. 0 veya hiç değer sağlanıyorsa, bu yöntem CThreadPool tarafından ayarlanan zaman aşama [kullanır::SetTimeout](#settimeout).

### <a name="remarks"></a>Açıklamalar

Bu yöntem, havuzdaki tüm iş parçacıklarına kapatma isteği gönderir. Zaman aşımı süresi dolduğunda, bu yöntem, çıkmayan herhangi bir iş parçacığı üzerinde [TerminateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-terminatethread) çağırır. Bu yöntem sınıfın yıkıcısından otomatik olarak çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[IThreadPoolConfig Arabirimi](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[Varsayılan ThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Sınıflar](../../atl/reference/atl-classes.md)
