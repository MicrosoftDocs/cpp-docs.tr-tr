---
title: "CThreadPool sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6739e179843864c952a5e864de1389b466d7ca7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cthreadpool-class"></a>CThreadPool sınıfı
Bu sınıf, iş öğelerinin sırasını işlemek çalışan iş parçacığı havuzu sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>Parametreler  
 *Çalışan*  
 Uyumludur sınıfı [çalışan archetype](../../atl/reference/worker-archetype.md) iş öğeleri iş parçacığı havuzunun sıraya işlemek için kullanılan kod sağlama.  
  
 `ThreadTraits`  
 İş parçacığı havuzu oluşturmak için kullanılan işlevi sağlayan sınıf.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|İş parçacığı havuzu Oluşturucusu.|  
|[CThreadPool:: ~ CThreadPool](#dtor)|İş parçacığı havuzu yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|Uygulaması `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|İş parçacığı sayısını havuzda almak için bu yöntemi çağırın.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|İş öğelerini sıraya almak için kullanılan g/ç tamamlama bağlantı noktasını tanıtıcısı almak için bu yöntemi çağırın.|  
|[CThreadPool::GetSize](#getsize)|İş parçacığı sayısını havuzda almak için bu yöntemi çağırın.|  
|[CThreadPool::GetTimeout](#gettimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.|  
|[CThreadPool::Initialize](#initialize)|İş parçacığı havuzu başlatmak için bu yöntemi çağırın.|  
|[CThreadPool::QueryInterface](#queryinterface)|Uygulaması **IUnknown::QueryInterface**.|  
|[CThreadPool::QueueRequest](#queuerequest)|Bir iş parçacığı havuzu tarafından işlenecek bir çalışma öğesini sıraya almak için bu yöntemi çağırın.|  
|[CThreadPool::Release](#release)|Uygulaması `IUnknown::Release`.|  
|[CThreadPool::SetSize](#setsize)|Havuzundaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.|  
|[CThreadPool::SetTimeout](#settimeout)|İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.|  
|[CThreadPool::Shutdown](#shutdown)|İş parçacığı havuzu kapatmak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı havuzundaki oluşturulur ve havuzu başlatılmadı, yeniden boyutlandırılmış veya kapatma yok. Sınıfının bir örneği *çalışan* her çalışan iş parçacığı havuzundaki yığınını oluşturulur. Her bir örnek, iş parçacığı ömrü boyunca dinamik.  
  
 Bir iş parçacığı oluşturma hemen sonra *çalışan*:: `Initialize` o iş parçacığı ile ilişkili nesne üzerinde çağrılır. Bir iş parçacığı yok etme hemen önce *çalışan*:: `Terminate` çağrılır. Her iki yöntem de kabul etmeniz gerekir bir **void\***  bağımsız değişkeni. Bu bağımsız değişkenin değeri iş parçacığı havuzu geçirilir `pvWorkerParam` parametresinin [CThreadPool::Initialize](#initialize).  
  
 Olduğunda iş öğeleri içindeki sırası ve çalışan iş parçacığı için iş kullanılabilir, bir çalışan iş parçacığı arama ve sıra dışı bir öğe çeker **yürütme** yöntemi *çalışan* o iş parçacığı için nesnesi. Üç öğe sonra yönteme geçirilen: sıra aynı öğesinden `pvWorkerParam` geçirilen *çalışan*:: `Initialize` ve *çalışan*:: `Terminate`, gösterenbirişaretçi[ÇAKIŞAN](http://msdn.microsoft.com/library/windows/desktop/ms684342) g/ç tamamlama bağlantı noktasını sırası için kullanılan yapısı.  
  
 *Çalışan* sınıfı bildiren bir typedef sağlayarak iş parçacığı havuzunun Sıraya alınacak öğe türü *çalışan*:: `RequestType`. Bu tür kitaplıklarından cast özellikli bir **iç ULONG_PTR**.  
  
 Örnek olarak bir *çalışan* sınıf [CNonStatelessWorker sınıfı](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="addref"></a>CThreadPool::AddRef  
 Uygulaması `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf, başvuru sayımı kullanarak ömrü denetimi uygulamıyor.  
  
##  <a name="cthreadpool"></a>CThreadPool::CThreadPool  
 İş parçacığı havuzu Oluşturucusu.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman aşımı değerine başlatır `ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT`. Varsayılan süre 36 saniyedir. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz.  
  
##  <a name="dtor"></a>CThreadPool:: ~ CThreadPool  
 İş parçacığı havuzu yıkıcı.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="getnumthreads"></a>CThreadPool::GetNumThreads  
 İş parçacığı sayısını havuzda almak için bu yöntemi çağırın.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı sayısını havuzda döndürür.  
  
##  <a name="getqueuehandle"></a>CThreadPool::GetQueueHandle  
 İş öğelerini sıraya almak için kullanılan g/ç tamamlama bağlantı noktasını tanıtıcısı almak için bu yöntemi çağırın.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı havuzu başlatılmadı varsa sıra işleyici ya da NULL değerini döndürür.  
  
##  <a name="getsize"></a>CThreadPool::GetSize  
 İş parçacığı sayısını havuzda almak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pnNumThreads`  
 [out] Adresi değişkenin, başarı, havuzda iş parçacığı sayısını alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="gettimeout"></a>CThreadPool::GetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi almak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pdwMaxWait`  
 [out] Adresi değişkenin, başarı, iş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu zaman aşımı değeri tarafından kullanılan [CThreadPool::Shutdown](#shutdown) bu yöntem için başka bir değer belirtilirse.  
  
##  <a name="initialize"></a>CThreadPool::Initialize  
 İş parçacığı havuzu başlatmak için bu yöntemi çağırın.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pvWorkerParam`  
 Çalışan iş parçacığı nesnenin için geçirilecek çalışan parametresi `Initialize`, **yürütme**, ve `Terminate` yöntemleri.  
  
 `nNumThreads`  
 İş parçacığı havuzundaki istenen sayısı.  
  
 Varsa `nNumThreads` olan negatif mutlak değerini toplam iş parçacığı sayısını almak üzere makine işlemci sayısı çarpılacağı.  
  
 Varsa `nNumThreads` sıfır `ATLS_DEFAULT_THREADSPERPROC` toplam iş parçacığı sayısını almak üzere makine işlemci sayısı çarpılacağı.  İşlemci başına 2 iş parçacığı varsayılandır. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz.
  
 `dwStackSize`  
 Havuzdaki her bir iş parçacığı için yığın boyutu.  
  
 *hCompletion*  
 Tamamlama bağlantı noktasını ile ilişkilendirilecek bir nesne işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="queryinterface"></a>CThreadPool::QueryInterface  
 Uygulaması **IUnknown::QueryInterface**.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıfın nesneleri için başarıyla sorgulandı **IUnknown** ve [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) arabirimleri.  
  
##  <a name="queuerequest"></a>CThreadPool::QueueRequest  
 Bir iş parçacığı havuzu tarafından işlenecek bir çalışma öğesini sıraya almak için bu yöntemi çağırın.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `request`  
 Sıraya alınabilecek isteği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir iş öğesini kuyruğa ekler. İş parçacığı havuzundaki bunlar alındığı sırada sıranın öğeleri seçin.  
  
##  <a name="release"></a>CThreadPool::Release  
 Uygulaması `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf, başvuru sayımı kullanarak ömrü denetimi uygulamıyor.  
  
##  <a name="setsize"></a>CThreadPool::SetSize  
 Havuzundaki iş parçacığı sayısını ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nNumThreads`  
 İş parçacığı havuzundaki istenen sayısı.  
  
 Varsa `nNumThreads` olan negatif mutlak değerini toplam iş parçacığı sayısını almak üzere makine işlemci sayısı çarpılacağı.  
  
 Varsa `nNumThreads` sıfır `ATLS_DEFAULT_THREADSPERPROC` toplam iş parçacığı sayısını almak üzere makine işlemci sayısı çarpılacağı. İşlemci başına 2 iş parçacığı varsayılandır. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz.
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen iş parçacığı sayısı şu anda havuzu iş parçacıkları sayısından daha az ise, nesne kapatma iletiyi bekleyen iş parçacığı tarafından çekilmesi için sıraya koyar. İletinin sıra dışı bir bekleyen iş parçacığı çeker, iş parçacığı havuzu bildirir ve iş parçacığı yordamdan çıkar. Bu işlem havuzundaki iş parçacığı sayısı belirtilen sayıyla ulaşana kadar veya hiçbir iş parçacığı tarafından belirtilen süre içinde yaptı kadar yinelenir [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). Bu durumda, HRESULT için karşılık gelen bir yöntem döndürülecek **WAIT_TIMEOUT** ve bekleyen kapatma iletisini iptal edilir.  
  
##  <a name="settimeout"></a>CThreadPool::SetTimeout  
 İş parçacığı havuzu kapatmak bir iş parçacığı için bekleyeceği milisaniye cinsinden en uzun süreyi ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwMaxWait`  
 İstenen en uzun süre kapatmak bir iş parçacığı için iş parçacığı havuzu bekleyeceği milisaniye cinsinden.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman aşımı başlatılıp başlatılmadığı `ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT`. Varsayılan süre 36 saniyedir. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi pozitif bir tamsayı değeri tanımlayabilirsiniz. 
  
 Unutmayın `dwMaxWait` kapatmak tek bir iş parçacığı havuzu bekleyecek saattir. Birden çok iş parçacığı havuzundan kaldırmak üzere yapılması en uzun süreyi olabilir biraz değerinden `dwMaxWait` iş parçacığı sayısı ile çarpılmasıyla hesaplanır.  
  
##  <a name="shutdown"></a>CThreadPool::Shutdown  
 İş parçacığı havuzu kapatmak için bu yöntemi çağırın.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwMaxWait`  
 İstenen en uzun süre kapatmak bir iş parçacığı için iş parçacığı havuzu bekleyeceği milisaniye cinsinden. 0 veya herhangi bir değer belirtilirse, bu yöntem tarafından belirlenen zaman aşımı kullanacağı [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, havuzdaki tüm iş parçacıklarını bir kapatma isteği gönderir. Zaman aşımı süresi dolarsa, bu yöntemi çağırır [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) değil çıkmak herhangi bir iş parçacığı üzerinde. Bu yöntem, sınıf yıkıcı otomatik olarak çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IThreadPoolConfig arabirimi](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Sınıflar](../../atl/reference/atl-classes.md)
