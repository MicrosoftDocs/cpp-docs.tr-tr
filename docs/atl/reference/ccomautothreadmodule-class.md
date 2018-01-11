---
title: "CComAutoThreadModule sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
dev_langs: C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 094d10069b854d122e835f7d12f9ef095775db2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule sınıfı
ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>Parametreler  
 `ThreadAllocator`  
 [in] İş parçacığı seçimi yönetme sınıfı. Varsayılan değer [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.|  
|[GetDefaultThreads](#getdefaultthreads)|(Statik) İşlemci sayısına göre modülü için iş parçacığı sayısını dinamik olarak hesaplar.|  
|[Init](#init)|Modülün iş parçacığı oluşturur.|  
|[Kilitleme](#lock)|Modül ve geçerli iş parçacığının kilit sayısını artırır.|  
|[Kilidini aç](#unlock)|Azaltır kilidi modülü ve geçerli iş parçacığı sayısı.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|Geçerli iş parçacığının tanımlayıcısını içerir.|  
|[m_Allocator](#m_allocator)|İş parçacığı seçimi yönetir.|  
|[m_nThreads](#m_nthreads)|Modül içindeki iş parçacığı sayısını içerir.|  
|[m_pApartments](#m_papartments)|Modülün grupların yönetir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu sınıf tarafından değiştirilmiş kullanımdan kalkmıştır [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıfları. Aşağıdaki bilgiler ATL eski sürümleriyle kullanılır  
  
 `CComAutoThreadModule`türetilen [CComModule](../../atl/reference/ccommodule-class.md) exe ve Windows Hizmetleri için bir iş parçacığı havuza, modeli COM sunucusu uygulamak için. `CComAutoThreadModule`kullanan [CComApartment](../../atl/reference/ccomapartment-class.md) modüldeki her bir iş parçacığı için bir grup yönetmek için.  
  
 Modülünden türetilen `CComAutoThreadModule` içinde birden çok grupların nesneleri oluşturmak istediğinizde. De dahil etmelisiniz [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) belirtmek için nesnenin sınıf tanımında makrosu [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) üreteci olarak.  
  
 Varsayılan olarak, ATL COM AppWizard (ATL Proje Sihirbazı Visual Studio .NET içinde), modülünden elde `CComModule`. Kullanılacak `CComAutoThreadModule`, sınıf tanımını değiştirin. Örneğin:  
  
 [!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Parametreler  
 *pfnCreateInstance*  
 [in] Oluşturucu işlevi için bir işaretçi.  
  
 `riid`  
 [in] İstenen arabirim IID.  
  
 `ppvObj`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppvObj` NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir iş parçacığı seçer ve ardından ilişkili grupta bir nesne oluşturur.  
  
##  <a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli iş parçacığının tanımlayıcısını içerir.  
  
##  <a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 EXE modülünde oluşturulacak iş parçacığı sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik işlev işlemci sayısına göre EXE modülü için iş parçacığı sayısını dinamik olarak hesaplar. Varsayılan olarak, bu dönüş değeri için geçirilen [Init](#init) yöntemi iş parçacığı oluşturabilir.  
  
##  <a name="init"></a>CComAutoThreadModule::Init  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] Nesne eşleme girişleri dizisi için bir işaretçi.  
  
 `h`  
 [in] `HINSTANCE` Geçirilen **DLLMain** veya `WinMain`.  
  
 `plibid`  
 [in] Projeyle ilişkili tür kitaplığı kimliği için bir işaretçi.  
  
 `nThreads`  
 [in] Oluşturulacak iş parçacığı sayısı. Varsayılan olarak, `nThreads` tarafından döndürülen değer [GetDefaultThreads](#getdefaultthreads).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri üyeleri başlatır ve tarafından belirtilen iş parçacığı sayısını oluşturur `nThreads`.  
  
##  <a name="lock"></a>CComAutoThreadModule::Lock  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli iş parçacığının ve modül için kilit sayısı atomik artışı gerçekleştirir. `CComAutoThreadModule`Modül kilit sayısı, tüm istemciler modülü erişme olup olmadığını belirlemek için kullanır. Geçerli iş parçacığı üzerinde kilit sayısı İstatistiksel amaçlar için kullanılır.  
  
##  <a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>Açıklamalar  
 İş parçacığı seçimi yönetme nesnesi. Varsayılan olarak, `ThreadAllocator` sınıfı şablon parametresi [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
##  <a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>Açıklamalar  
 EXE modülündeki iş parçacığı sayısını içerir. Zaman [Init](#init) olarak adlandırılır, `m_nThreads` ayarlanır `nThreads` parametre değeri. Her iş parçacığının ilişkili grup tarafından yönetilen bir [CComApartment](../../atl/reference/ccomapartment-class.md) nesnesi.  
  
##  <a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Noktaları için bir dizi [CComApartment](../../atl/reference/ccomapartment-class.md) nesneleri, her biri bir grupta modülü yönetir. Dizideki öğelerin sayısını temel alır [m_nThreads](#m_nthreads) üyesi.  
  
##  <a name="unlock"></a>CComAutoThreadModule::Unlock  
 ATL 7. 0'dan sonra `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanılama için kullanışlı veya test bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli iş parçacığının ve modül için kilit sayısı üzerinde bir atomik azaltma gerçekleştirir. `CComAutoThreadModule`Modül kilit sayısı, tüm istemciler modülü erişme olup olmadığını belirlemek için kullanır. Geçerli iş parçacığı üzerinde kilit sayısı İstatistiksel amaçlar için kullanılır.  
  
 Modül kilit sayısı sıfır ulaştığında modülü yüklenmemiş olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
