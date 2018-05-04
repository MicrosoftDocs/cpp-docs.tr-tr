---
title: CWorkerThread sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e87001ca341ae27cb173357f74e06e543f5eb262
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cworkerthread-class"></a>CWorkerThread sınıfı
Bu sınıf bir çalışan iş parçacığı oluşturur veya mevcut bir kullanır, bir veya daha fazla çekirdek nesne işleyicilerinin bekler ve tanıtıcıları birini işaret, belirtilen istemci işlevi yürütür.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>Parametreler  
 `ThreadTraits`  
 İş parçacığı oluşturma işlevi gibi sağlayan sınıf [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) veya [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-structures"></a>Korumalı yapıları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|Çalışan iş parçacığı Oluşturucusu.|  
|[CWorkerThread:: ~ CWorkerThread](#dtor)|Çalışan iş parçacığı için yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|Bir waitable nesnesinin tanıtıcı çalışan iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.|  
|[CWorkerThread::AddTimer](#addtimer)|Bir dönemsel waitable süreölçer çalışan iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Çalışan iş parçacığı iş parçacığı tanıtıcısı almak için bu yöntemi çağırın.|  
|[CWorkerThread::GetThreadId](#getthreadid)|Çalışan iş parçacığı iş parçacığı Kimliğini almak için bu yöntemi çağırın.|  
|[CWorkerThread::Initialize](#initialize)|Çalışan iş parçacığı başlatmak için bu yöntemi çağırın.|  
|[CWorkerThread::RemoveHandle](#removehandle)|Bir tanıtıcı waitable nesneleri listesinden kaldırmak için bu yöntemi çağırın.|  
|[CWorkerThread::Shutdown](#shutdown)|Çalışan iş parçacığı kapatmak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
  
### <a name="to-use-cworkerthread"></a>CWorkerThread kullanmak için  
  
1.  Bu sınıfın bir örneğini oluşturun.  
  
2.  Çağrı [CWorkerThread::Initialize](#initialize).  
  
3.  Çağrı [CWorkerThread::AddHandle](#addhandle) bir çekirdek nesnesi ve uygulaması için bir işaretçi tanıtıcısı ile [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     - veya -  
  
     Çağrı [CWorkerThread::AddTimer](#addtimer) uygulaması için bir işaretçi ile [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Uygulama [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) tanıtıcısı veya Zamanlayıcı işaret olduğunda bazı işlemler yapması için.  
  
5.  Bir nesne waitable nesneleri listesinden kaldırmak için arama [CWorkerThread::RemoveHandle](#removehandle).  
  
6.  İş parçacığı sonlandırmak için çağrı [CWorkerThread::Shutdown](#shutdown).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="addhandle"></a>  CWorkerThread::AddHandle  
 Bir waitable nesnesinin tanıtıcı çalışan iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hObject`  
 Waitable nesnesi için tanıtıcı.  
  
 `pClient`  
 İşaretçi [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) tanıtıcı işaret olduğunda çağrılacak nesnesindeki arabirim.  
  
 `dwParam`  
 Geçirilecek parametresi [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) tanıtıcı durdurulma zaman.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) aracılığıyla adlı `pClient` zaman tanıtıcı `hObject`, verdi.  
  
##  <a name="addtimer"></a>  CWorkerThread::AddTimer  
 Bir dönemsel waitable süreölçer çalışan iş parçacığı tarafından tutulan listesine eklemek için bu yöntemi çağırın.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwInterval*  
 Zamanlayıcı süreyi milisaniye cinsinden belirtir.  
  
 `pClient`  
 İşaretçi [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) tanıtıcı işaret olduğunda çağrılacak nesnesindeki arabirim.  
  
 `dwParam`  
 Geçirilecek parametresi [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) tanıtıcı durdurulma zaman.  
  
 `phTimer`  
 [out] Başarı, yeni oluşturulan Zamanlayıcı tanıtıcısını alır, tanıtıcı değişken adresidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) aracılığıyla adlı `pClient` Zamanlayıcı durdurulma zaman.  
  
 Gelen zamanlayıcı tanıtıcı geçirmek `phTimer` için [CWorkerThread::RemoveHandle](#removehandle) Zamanlayıcı kapatın.  
  
##  <a name="cworkerthread"></a>  CWorkerThread::CWorkerThread  
 Oluşturucu.  
  
```
CWorkerThread() throw();
```  
  
##  <a name="dtor"></a>  CWorkerThread:: ~ CWorkerThread  
 Yok Edicisi.  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CWorkerThread::Shutdown](#shutdown).  
  
##  <a name="getthreadhandle"></a>  CWorkerThread::GetThreadHandle  
 Çalışan iş parçacığı iş parçacığı tanıtıcısı almak için bu yöntemi çağırın.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çalışan iş parçacığı başlatılmadı varsa iş parçacığı tutamacı ya da NULL değerini döndürür.  
  
##  <a name="getthreadid"></a>  CWorkerThread::GetThreadId  
 Çalışan iş parçacığı iş parçacığı Kimliğini almak için bu yöntemi çağırın.  
  
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
 `pThread`  
 Var olan bir iş parçacığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, nesne oluşturulduktan sonra veya bir çağrı sonra başlatmak için çağrılmalıdır [CWorkerThread::Shutdown](#shutdown).  
  
 İki veya daha fazla bilgi için `CWorkerThread` nesneleri çalışan iş parçacığı kullanın, bunlardan birini herhangi bir bağımsız değişken sonra geçirin bir işaretçi için bu nesneye geçirme olmadan başlatma `Initialize` diğer yöntemleri. İşaretçinin başlatıldı nesneleri bunları başlatmak için kullanılan nesne önce kapatılmalıdır.  
  
 Bkz: [CWorkerThread::Shutdown](#shutdown) nasıl varolan bir nesne için bir işaretçi kullanarak hazırlarken bu yöntemin davranışını değiştiren hakkında bilgi için.  
  
##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle  
 Bir tanıtıcı waitable nesneleri listesinden kaldırmak için bu yöntemi çağırın.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hObject`  
 Kaldırmak için işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tanıtıcı kaldırıldığında [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) geçirilmedi ilişkili nesne üzerinde adlı [AddHandle](#addhandle). Bu çağrı başarısız olursa, `CWorkerThread` Windows'ın arayacağı [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) tutamacı işlevi.  
  
##  <a name="shutdown"></a>  CWorkerThread::Shutdown  
 Çalışan iş parçacığı kapatmak için bu yöntemi çağırın.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwWait`  
 Çalışan iş parçacığının kapatmak için beklenecek süreyi milisaniye olarak süre. 10 saniye ATL_WORKER_THREAD_WAIT varsayılan değeri. Gerekirse, atlutil.h eklemeden önce bu simgenin kendi değeri tanımlayabilirsiniz. 
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı veya başarısız olduğunda, eğer gibi HRESULT hata S_OK döndürür zaman aşımı değeri `dwWait`, aşıldı.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne yeniden kullanmak için arama [CWorkerThread::Initialize](#initialize) bu yöntemi çağrıldıktan sonra.  
  
 Bu arama Not **kapatma** diğerine işaretçiyle başlatılan bir nesne üzerinde `CWorkerThread` nesne herhangi bir etkisi olmaz ve her zaman S_OK döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Sınıfları](../../atl/reference/atl-classes.md)   
 [Çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient Sınıfı](../../atl/reference/iworkerthreadclient-interface.md)
