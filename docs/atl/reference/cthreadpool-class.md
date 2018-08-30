---
title: CThreadPool sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8371ec583bd8b9ee4962445e4c2b6f2fbfa6280
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196968"
---
# <a name="cthreadpool-class"></a>CThreadPool sınıfı
Bu sınıf, iş öğelerinin bir kuyruğu işleyen çalışan iş parçacığı havuzu sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>Parametreler  
 *Çalışan*  
 Uyumludur sınıfı [çalışan modeli](../../atl/reference/worker-archetype.md) iş iş parçacığı havuzu üzerinde sıraya alınan öğeleri işlemek için kullanılan kod sağlama.  
  
 *ThreadTraits*  
 İş parçacığı havuzu oluşturmak için kullanılan işlev sağlayan sınıf.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|İş parçacığı havuzu için oluşturucu.|  
|[CThreadPool:: ~ CThreadPool](#dtor)|İş parçacığı havuzu yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|Uygulamasını `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|Havuzda iş parçacığı sayısını almak için bu yöntemi çağırın.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|İş öğeleri sıralamak için kullandığınız IO tamamlama bağlantı tanıtıcısını almak için bu yöntemi çağırın.|  
|[CThreadPool::GetSize](#getsize)|Havuzda iş parçacığı sayısını almak için bu yöntemi çağırın.|  
|[CThreadPool::GetTimeout](#gettimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.|  
|[CThreadPool::Initialize](#initialize)|İş parçacığı havuzu başlatmak için bu yöntemi çağırın.|  
|[CThreadPool::QueryInterface](#queryinterface)|Uygulamasını `IUnknown::QueryInterface`.|  
|[CThreadPool::QueueRequest](#queuerequest)|Bir iş öğesi bir iş parçacığı havuzu tarafından işlenmek üzere sıraya almak için bu yöntemi çağırın.|  
|[CThreadPool::Release](#release)|Uygulamasını `IUnknown::Release`.|  
|[CThreadPool::SetSize](#setsize)|Havuzda iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.|  
|[CThreadPool::SetTimeout](#settimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.|  
|[CThreadPool::Shutdown](#shutdown)|İş parçacığı havuz ölçeğini küçültme kapatmak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı havuzunda oluşturulur ve Havuz başlatılmadı, yeniden boyutlandırılabilir veya kapatma yok. Sınıfının bir örneğini *çalışan* havuzdaki her bir çalışan iş parçacığı yığını üzerinde oluşturulur. Her örnek, iş parçacığının ömrü boyunca Canlı.  
  
 Bir iş parçacığı oluşturulduktan hemen sonra *çalışan*::`Initialize` bu iş parçacığıyla ilişkilendirilmiş nesne üzerinde çağrılır. Bir iş parçacığı yok edilmesini hemen önce *çalışan*::`Terminate` olarak adlandırılır. Her iki yöntem de kabul etmesi gereken bir **void** <strong>\*</strong> bağımsız değişken. Bu bağımsız değişkenin değeri iş parçacığı havuzu ile geçirilecek *pvWorkerParam* parametresinin [CThreadPool::Initialize](#initialize).  
  
 İş öğesi olmadığında kuyruk ve çalışan iş parçacıkları iş için kullanılabilir, iş parçacığı çağrı ve kuyruk devre dışı bir öğe çeker `Execute` yöntemi *çalışan* iş parçacığı için nesne. Üç öğe ardından yönteme geçirilen: kuyruk aynı öğesinden `pvWorkerParam` geçirilen *çalışan*:: `Initialize` ve *çalışan*:: `Terminate`, bir işaretçi [ÇAKIŞAN](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) IO tamamlama bağlantı noktası sırası için kullanılan yapısı.  
  
 *Çalışan* sınıfı bildirir iş parçacığı havuzunda bir typedef sağlayarak Sıraya alınacak öğelerin türünü *çalışan*:: `RequestType`. Bu tür bir iç ULONG_PTR gelen ve giden cast uyumlu olması gerekir.  
  
 Örneği bir *çalışan* sınıfı [CNonStatelessWorker sınıfı](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IUnknown`  
  
 [Ithreadpoolconfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="addref"></a>  CThreadPool::AddRef  
 Uygulamasını `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf, yaşam süresi denetimi kullanarak başvuru sayımı uygulamıyor.  
  
##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool  
 İş parçacığı havuzu için oluşturucu.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman aşımı değeri ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT başlatır. Varsayılan süre 36 saniyedir. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz.  
  
##  <a name="dtor"></a>  CThreadPool:: ~ CThreadPool  
 İş parçacığı havuzu yok Edicisi.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads  
 Havuzda iş parçacığı sayısını almak için bu yöntemi çağırın.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Havuzda iş parçacıklarının sayısını döndürür.  
  
##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle  
 İş öğeleri sıralamak için kullandığınız IO tamamlama bağlantı tanıtıcısını almak için bu yöntemi çağırın.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı havuzu henüz başlatılmamış sıra işleyici ya da NULL döndürür.  
  
##  <a name="getsize"></a>  CThreadPool::GetSize  
 Havuzda iş parçacığı sayısını almak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pnNumThreads*  
 [out] Değişkeninin adresi, başarı, havuzda iş parçacığı sayısını alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
##  <a name="gettimeout"></a>  CThreadPool::GetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pdwMaxWait*  
 [out] Başarı durumunda, iş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi alır. değişkenin adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu zaman aşımı değeri tarafından kullanılan [CThreadPool::Shutdown](#shutdown) yöntem için başka bir değer sağlanmazsa.  
  
##  <a name="initialize"></a>  CThreadPool::Initialize  
 İş parçacığı havuzu başlatmak için bu yöntemi çağırın.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pvWorkerParam*  
 Çalışan iş parçacığı nesnenin iletilecek alt parametre `Initialize`, `Execute`, ve `Terminate` yöntemleri.  
  
 *nNumThreads*  
 İstenen havuzundaki iş parçacığı sayısı.  
  
 Varsa *nNumThreads* olan negatif mutlak değerini toplam iş parçacığı sayısını almak için makinede işlemci sayısını çarpılacağı.  
  
 Varsa *nNumThreads* sıfır ATLS_DEFAULT_THREADSPERPROC çarpılarak toplam iş parçacığı sayısını almak için makinede işlemci sayısı.  İşlemci başına 2 iş parçacığı varsayılandır. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz.
  
 *dwStackSize*  
 Havuzdaki her bir iş parçacığı için yığın boyutu.  
  
 *hCompletion*  
 Tamamlama bağlantı ile ilişkilendirilecek bir nesne tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
##  <a name="queryinterface"></a>  CThreadPool::QueryInterface  
 Uygulamasını `IUnknown::QueryInterface`.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıfın nesneleri başarıyla sorgulanabilen için `IUnknown` ve [Ithreadpoolconfig](../../atl/reference/ithreadpoolconfig-interface.md) arabirimleri.  
  
##  <a name="queuerequest"></a>  CThreadPool::QueueRequest  
 Bir iş öğesi bir iş parçacığı havuzu tarafından işlenmek üzere sıraya almak için bu yöntemi çağırın.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *İstek*  
 Kuyruğa alınacak istek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir iş öğesini kuyruğa ekler. Havuzundaki iş parçacığı içinde alındıkları sırayla sıranın öğelerini seçin.  
  
##  <a name="release"></a>  CThreadPool::Release  
 Uygulamasını `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf, yaşam süresi denetimi kullanarak başvuru sayımı uygulamıyor.  
  
##  <a name="setsize"></a>  CThreadPool::SetSize  
 Havuzda iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *nNumThreads*  
 İstenen havuzundaki iş parçacığı sayısı.  
  
 Varsa *nNumThreads* olan negatif mutlak değerini toplam iş parçacığı sayısını almak için makinede işlemci sayısını çarpılacağı.  
  
 Varsa *nNumThreads* sıfır ATLS_DEFAULT_THREADSPERPROC çarpılarak toplam iş parçacığı sayısını almak için makinede işlemci sayısı. İşlemci başına 2 iş parçacığı varsayılandır. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz.
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen iş parçacığı sayısını şu anda havuzundaki iş parçacığı sayısından daha az ise, nesne bir kapatma ileti bir bekleyen iş parçacığı tarafından işlenmek üzere sıraya koyar. Bekleyen iş parçacığı kuyruk iletisini çeker, iş parçacığı havuzu bildirir ve iş parçacığı yordamdan çıkar. Bu işlem havuzundaki iş parçacığı sayısı belirtilen sayıyla ulaşana kadar veya iş parçacığı tarafından belirtilen süre içinde çıkıldı kadar yinelenir [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). Bu durumda yöntem WAIT_TIMEOUT için karşılık gelen bir HRESULT döndürür ve bekleyen kapatma iletisini iptal edilir.  
  
##  <a name="settimeout"></a>  CThreadPool::SetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwMaxWait*  
 İstenen en uzun süreyi milisaniye kapatmak bir iş parçacığı için iş parçacığı havuzu bekler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman aşımı için ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT başlatılır. Varsayılan süre 36 saniyedir. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz. 
  
 Unutmayın *dwMaxWait* kapatmak tek bir iş parçacığı havuzu bekler zamandır. Birden çok iş parçacığı havuzdan kaldırma geçen en uzun süreyi olabilir biraz daha küçüktür *dwMaxWait* tarafından iş parçacığı sayısı çarpılır.  
  
##  <a name="shutdown"></a>  CThreadPool::Shutdown  
 İş parçacığı havuz ölçeğini küçültme kapatmak için bu yöntemi çağırın.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwMaxWait*  
 İstenen en uzun süreyi milisaniye kapatmak bir iş parçacığı için iş parçacığı havuzu bekler. 0 veya herhangi bir değer sağlanmazsa, bu yöntem ayarlanan zaman aşımı kullanacağı [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, havuzdaki tüm iş parçacıkları bir kapatma isteği gönderir. Zaman aşımı süresi dolarsa, bu yöntemi çağıran [TerminateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-terminatethread) değil çıkmak herhangi bir iş parçacığı üzerinde. Bu yöntem, sınıf yok ediciden otomatik olarak çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ithreadpoolconfig arabirimi](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Sınıflar](../../atl/reference/atl-classes.md)
