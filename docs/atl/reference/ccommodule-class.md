---
title: "CComModule sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
dev_langs: C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b86e1f082b7be844afe3b1a84d182d1c722f500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommodule-class"></a>CComModule sınıfı
ATL 7. 0'dan sonra `CComModule` kullanım dışıdır: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|Belirtilen CLSID bir nesne oluşturur. Yalnızca DLL'ler için.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Döndürür `m_hInst`.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Döndürür `m_hInstResource`.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Döndürür `m_hInstTypeLib`.|  
|[CComModule::Init](#init)|Veri üyeleri başlatır.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Bir nesnenin standart sınıf kaydı sistem kayıt defterinde girer.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Sınıf nesnesi kaydeder. Yalnızca exe için.|  
|[CComModule::RegisterServer](#registerserver)|Nesne eşlemesindeki her nesne için sistem kayıt defterini güncelleştirir.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Tür kitaplığını kaydeder.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesi iptal eder. Yalnızca exe için.|  
|[CComModule::Term](#term)|Veri üyeleri serbest bırakır.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Bir nesnenin standart sınıf kaydı sistem kayıt defterinden kaldırır.|  
|[CComModule::UnregisterServer](#unregisterserver)|Her nesne eşlemesi nesnesinde kaydını siler.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Kaydeder veya nesnenin standart sınıf kaydı kaydını siler.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Kaydetmek veya kaydı bir nesne için belirtilen bir kaynak içinde yer alan komut dosyasını çalıştırır.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Statik olarak bağlantılar ATL kayıt defteri bileşeni. Kaydetmek veya kaydı bir nesne için belirtilen bir kaynak içinde yer alan komut dosyasını çalıştırır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Eşitlenen nesne eşleme bilgilerine erişim sağlar.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Tür kitaplığı bilgileri eşitlenmiş erişim sağlar.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Pencere sınıfı bilgileri ve pencere oluşturma sırasında kullanılan statik verileri eşitlenmiş erişim sağlar.|  
|[CComModule::m_hInst](#m_hinst)|Modül örneğinin tanıtıcısını içerir.|  
|[CComModule::m_hInstResource](#m_hinstresource)|Varsayılan olarak, modül örneğinin tanıtıcısını içerir.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|Varsayılan olarak, modül örneğinin tanıtıcısını içerir.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Modül örneği tarafından tutulan nesne eşlemesi noktalarına.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu sınıf kullanım dışıdır ve ATL kodu oluşturma sihirbazları artık kullanmak [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıfları. Bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla bilgi için. Aşağıdaki bilgiler, ATL eski sürümleriyle oluşturulan uygulamalarla kullanım içindir. `CComModule`hala ATL için geriye doğru yetenek parçasıdır.  
  
 `CComModule`Modülün bileşenlerine erişmek bir istemci sağlayan bir COM sunucusu modül uygular. `CComModule`DLL (işlemdeki) ve EXE (yerel) modülleri destekler.  
  
 A `CComModule` örneği sınıf nesne tanımları kümesini korumak için bir nesne eşlemesi kullanır. Bu nesne eşlemesi bir dizisi olarak uygulanan `_ATL_OBJMAP_ENTRY` yapıları ve ilgili bilgiler içerir:  
  
-   Girme ve sistem kayıt defterinde nesnesi açıklamaları kaldırma.  
  
-   Bir sınıf fabrikası nesnelerde örnekleme.  
  
-   Bir istemci kök nesnesi arasındaki iletişimi bileşeni oluşturma.  
  
-   Sınıf nesnelerine gerçekleştirme ömrü yönetimi.  
  
 ATL COM AppWizard çalıştırdığınızda, sihirbaz otomatik olarak oluşturur `_Module`, genel bir örneğini `CComModule` veya ondan türetilmiş bir sınıf. ATL Proje Sihirbazı hakkında daha fazla bilgi için bkz: [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
 Ek olarak `CComModule`, ATL sağlar [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), exe ve Windows Hizmetleri için bir modeli modülü uygular. Modülünden türetilen `CComAutoThreadModule` içinde birden çok grupların nesneleri oluşturmak istediğinizde.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="getclassobject"></a>CComModule::GetClassObject  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rclsid`  
 [in] Oluşturulacak nesnenin CLSID'si.  
  
 `riid`  
 [in] İstenen arabirim IID.  
  
 `ppv`  
 [out] Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppv` ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen CLSID bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.  
  
 `GetClassObject`yalnızca DLL'ler için kullanılabilir.  
  
##  <a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `HINSTANCE` Bu modül tanımlama.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [m_hInst](#m_hinst) veri üyesi.  
  
##  <a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HINSTANCE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [m_hInstResource](#m_hinstresource) veri üyesi.  
  
##  <a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HINSTANCE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [m_hInstTypeLib](#m_hinsttypelib) veri üyesi.  
  
##  <a name="init"></a>CComModule::Init  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] Nesne eşleme girişleri dizisi için bir işaretçi.  
  
 `h`  
 [in] `HINSTANCE` Geçirilen **DLLMain** veya `WinMain`.  
  
 `plibid`  
 [in] Projeyle ilişkili tür kitaplığı kimliği için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri başlatır.  
  
##  <a name="m_csobjmap"></a>CComModule::m_csObjMap  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne eşlemesi eşitlenmiş erişim sağlar.  
  
##  <a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür kitaplığı eşitlenmiş erişim sağlar.  
  
##  <a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere sınıfı bilgileri ve pencere oluşturma sırasında kullanılan statik verileri eşitlenmiş erişim sağlar.  
  
##  <a name="m_hinst"></a>CComModule::m_hInst  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Modül örneğinin tanıtıcısını içerir.  
  
 [Init](#init) yöntemi kümeleri `m_hInst` geçirilen işlenecek **DLLMain** veya `WinMain`.  
  
##  <a name="m_hinstresource"></a>CComModule::m_hInstResource  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, modül örneğinin tanıtıcısını içerir.  
  
 [Init](#init) yöntemi kümeleri `m_hInstResource` geçirilen işlenecek **DLLMain** veya `WinMain`. Açık olarak ayarlanıp `m_hInstResource` bir kaynağa işlenecek.  
  
 [GetResourceInstance](#getresourceinstance) yöntemi döndürür depolanan tanıtıcı `m_hInstResource`.  
  
##  <a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, modül örneğinin tanıtıcısını içerir.  
  
 [Init](#init) yöntemi kümeleri `m_hInstTypeLib` geçirilen işlenecek **DLLMain** veya `WinMain`. Açık olarak ayarlanıp `m_hInstTypeLib` tür kitaplığının işlenecek.  
  
 [GetTypeLibInstance](#gettypelibinstance) yöntemi döndürür depolanan tanıtıcı `m_hInstTypeLib`.  
  
##  <a name="m_pobjmap"></a>CComModule::m_pObjMap  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Modül örneği tarafından tutulan nesne eşlemesi noktalarına.  
  
##  <a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 [in] Kaydedilecek nesne CLSID'si.  
  
 `lpszProgID`  
 [in] Nesneyle ilişkili ProgID.  
  
 `lpszVerIndProgID`  
 [in] Sürüm bağımsız bir nesneyle ilişkili ProgID.  
  
 `nDescID`  
 [in] Nesnenin açıklaması için bir dize kaynak tanımlayıcısı.  
  
 `dwFlags`  
 [in] Kayıt defterinde girmek için iş parçacığı modelini belirtir. Olası değerler şunlardır: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, veya **AUTPRXFLAG**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir nesnenin standart sınıf kaydı sistem kayıt defterinde girer.  
  
 [UpdateRegistryClass](#updateregistryclass) yöntem çağrılarını `RegisterClassHelper`.  
  
##  <a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwClsContext`  
 [in] Sınıf nesnesi çalıştırılsın mı bağlam belirtir. Olası değerler şunlardır: **CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, veya **CLSCTX_LOCAL_SERVER**. Bu değerleri açıklaması için bkz: [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) Windows SDK'sındaki.  
  
 `dwFlags`  
 [in] Bağlantı türleri sınıf nesnesine belirler. Olası değerler şunlardır: **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, veya **REGCLS_MULTI_SEPARATE**. Bu değerleri açıklaması için bkz: [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Diğer uygulamalar için bağlanabilmesi için bir EXE sınıf nesnesi ile OLE kaydeder. Bu yöntem yalnızca exe için kullanılabilir.  
  
##  <a name="registerserver"></a>CComModule::RegisterServer  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bRegTypeLib`  
 [in] Tür kitaplığı kayıtlı olup olmadığını belirtir. Varsayılan değer **FALSE**.  
  
 `pCLSID`  
 [in] CLSID noktalarına nesnenin kayıtlı olması gerekir. Varsa **NULL** (varsayılan değer) nesne eşlemesi içindeki tüm nesneler kaydedilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlı olarak `pCLSID` parametresi, tek sınıf nesnesi veya nesne eşlemesi içindeki tüm nesneler için sistem kayıt defterini güncelleştirir.  
  
 Varsa `bRegTypeLib` olan **doğru**, tür kitaplığı bilgileri de güncelleştirilir.  
  
 Bkz: [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) bir giriş için nesne eşleme ekleme hakkında bilgi için.  
  
 `RegisterServer`tarafından otomatik olarak çağrılacak **DLLRegisterServer** DLL ya da `WinMain` bir EXE dosyasını çalıştırmak için **/regserver** komut satırı seçeneği.  
  
##  <a name="registertypelib"></a>CComModule::RegisterTypeLib  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszIndex`  
 [in] Dize biçimindeki `"\\N"`, burada `N` TYPELIB kaynak tamsayı dizinidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Tür Kitaplığı hakkında bilgi için sistem kayıt defteri ekler.  
  
 Modül örneğinin birden çok tür kitaplıklarının içeriyorsa, hangi tür kitaplığı kullanılması gerektiğini belirtmek için bu yöntem ikinci sürümü kullanın.  
  
##  <a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf nesnesi kaldırır. Bu yöntem yalnızca exe için kullanılabilir.  
  
##  <a name="term"></a>CComModule::Term  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri serbest bırakır.  
  
##  <a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 [in] Kaydı nesnesinin CLSID.  
  
 `lpszProgID`  
 [in] Nesneyle ilişkili ProgID.  
  
 `lpszVerIndProgID`  
 [in] Sürüm bağımsız bir nesneyle ilişkili ProgID.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir nesnenin standart sınıf kaydı sistem kayıt defterinden kaldırır.  
  
 [UpdateRegistryClass](#updateregistryclass) yöntem çağrılarını `UnregisterClassHelper`.  
  
##  <a name="unregisterserver"></a>CComModule::UnregisterServer  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 `bUnRegTypeLib`  
 Varsa **doğru**, tür kitaplığı da kaydettirilmemiş.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin sona erdirilecek. Varsa **NULL** (varsayılan değer) tüm nesneleri nesneyi eşlemesindeki kaydı kaldırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlı olarak `pCLSID` parametresi, tek sınıf nesnesi veya tüm nesneleri nesneyi eşlemesindeki kaydını siler.  
  
 `UnregisterServer`tarafından otomatik olarak çağrılacak **DLLUnregisterServer** DLL ya da `WinMain` bir EXE dosyasını çalıştırmak için **/Unregserver** komut satırı seçeneği.  
  
 Bkz: [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) bir giriş için nesne eşleme ekleme hakkında bilgi için.  
  
##  <a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Kayıtlı veya kaydı için CLSID nesnesinin.  
  
 `lpszProgID`  
 Nesneyle ilişkili ProgID.  
  
 `lpszVerIndProgID`  
 Sürüm bağımsız bir nesneyle ilişkili ProgID.  
  
 `nDescID`  
 Nesnenin açıklama dizesi kaynak tanımlayıcısı.  
  
 `szDesc`  
 Nesnenin açıklamasını içeren bir dize.  
  
 `dwFlags`  
 Kayıt defterinde girmek için iş parçacığı modelini belirtir. Olası değerler şunlardır: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, veya **AUTPRXFLAG**.  
  
 `bRegister`  
 Nesne kayıtlı olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bRegister` olan **doğru**, bu yöntem nesnenin standart sınıf kaydı sistem kayıt defterinde girer.  
  
 Varsa `bRegister` olan **yanlış**, nesnenin kaydını kaldırır.  
  
 Değerine bağlı olarak `bRegister`, `UpdateRegistryClass` ya da çağıran [RegisterClassHelper](#registerclasshelper) veya [UnregisterClassHelper](#unregisterclasshelper).  
  
 Belirterek [DECLARE_REGISTRY](registry-macros.md#declare_registry) makrosu, `UpdateRegistryClass` nesne haritanızı işlendiğinde otomatik olarak çağrılır.  
  
##  <a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
virtual HRESULT UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszRes`  
 [in] Bir kaynak adı.  
  
 `nResID`  
 [in] Bir kaynak kimliği  
  
 `bRegister`  
 [in] Nesne kayıtlı olup olmadığını belirtir.  
  
 `pMapEntries`  
 [in] Komut dosyanızın değiştirilebilir parametreler ile ilişkili değerlerini depolama değiştirme eşlemesi için bir işaretçi. ATL otomatik olarak kullanan `%MODULE%`. Ek değiştirilebilir parametreler kullanmak için açıklamalar Ayrıntılar için bkz. Aksi takdirde kullanın **NULL** varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen kaynak içinde yer alan komut dosyasını çalıştırır `lpszRes` veya `nResID`.  
  
 Varsa `bRegister` olan **doğru**, bu yöntem nesne sistem kayıt defterinde kaydeder; Aksi halde, nesne kaydını siler.  
  
 Belirterek [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makrosu, `UpdateRegistryFromResourceD` nesne haritanızı işlendiğinde otomatik olarak çağrılır.  
  
> [!NOTE]
>  Çalışma zamanında değiştirme değeri değiştirmek için belirtmeyin `DECLARE_REGISTRY_RESOURCE` veya `DECLARE_REGISTRY_RESOURCEID` makrosu. Bunun yerine, bir dizi oluşturmak **_ATL_REGMAP_ENTRIES** , her giriş içerdiği değişken yer tutucu yapıları eşleştirilmiş yer tutucu çalışma zamanında değiştirmek için bir değere sahip. ' I çağırın `UpdateRegistryFromResourceD`, dizi geçirmesi `pMapEntries` parametresi. Bu işlem tüm değiştirme değerleri ekler **_ATL_REGMAP_ENTRIES** kayıt şirketinin değiştirme eşlemesine yapıları.  
  
> [!NOTE]
>  ATL kayıt defteri bileşeni (Kaydedici) statik olarak bağlamak için bkz: [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi için bkz: [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 ATL 7. 0'dan sonra `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
virtual HRESULT UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszRes`  
 [in] Bir kaynak adı.  
  
 `nResID`  
 [in] Bir kaynak kimliği  
  
 `bRegister`  
 [in] Kaynak betik kayıtlı olup olmadığını belirtir.  
  
 `pMapEntries`  
 [in] Komut dosyanızın değiştirilebilir parametreler ile ilişkili değerlerini depolama değiştirme eşlemesi için bir işaretçi. ATL otomatik olarak kullanan `%MODULE%`. Ek değiştirilebilir parametreler kullanmak için açıklamalar Ayrıntılar için bkz. Aksi takdirde kullanın **NULL** varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde [UpdateRegistryFromResourceD](#updateregistryfromresourced) dışında `UpdateRegistryFromResourceS` ATL kayıt defteri bileşeni (Kaydedici) statik bir bağlantı oluşturur.  
  
 `UpdateRegistryFromResourceS`Nesne haritanızı işlendiğinde, eklediğiniz sağlanan otomatik olarak çağrılacak `#define _ATL_STATIC_REGISTRY` , Stdafx.H'ye.  
  
> [!NOTE]
>  Çalışma zamanında değiştirme değeri değiştirmek için belirtmeyin [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makrosu. Bunun yerine, bir dizi oluşturmak **_ATL_REGMAP_ENTRIES** , her giriş içerdiği değişken yer tutucu yapıları eşleştirilmiş yer tutucu çalışma zamanında değiştirmek için bir değere sahip. ' I çağırın `UpdateRegistryFromResourceS`, dizi geçirmesi `pMapEntries` parametresi. Bu işlem tüm değiştirme değerleri ekler **_ATL_REGMAP_ENTRIES** kayıt şirketinin değiştirme eşlemesine yapıları.  
  
 Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi için bkz: [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
