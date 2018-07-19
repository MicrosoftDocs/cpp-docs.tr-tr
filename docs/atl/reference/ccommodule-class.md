---
title: CComModule sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eae4218d6c6446554d5fb45d680588127ec3e0ee
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883098"
---
# <a name="ccommodule-class"></a>CComModule sınıfı
ATL 7. 0'den itibaren `CComModule` kullanım dışı bırakılmıştır: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|Belirtilen CLSID'yi bir nesne oluşturur. Yalnızca DLL'leri için.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Döndürür `m_hInst`.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Döndürür `m_hInstResource`.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Döndürür `m_hInstTypeLib`.|  
|[Ccommodule::Init](#init)|Veri üyeleri başlatır.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Standart sınıf kaydı bir nesnenin sistem kayıt defterinde girer.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Sınıf nesnesini kaydeder. Exe dosyaları için yalnızca.|  
|[CComModule::RegisterServer](#registerserver)|Nesne eşlemesindeki her nesnenin sistem kayıt defterini güncelleştirir.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Tür kitaplığını kaydeder.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Sınıf nesnesi iptal eder. Exe dosyaları için yalnızca.|  
|[CComModule::Term](#term)|Veri üyeleri serbest bırakır.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Standart sınıf kaydı bir nesnenin sistem kayıt defterinden kaldırır.|  
|[CComModule::UnregisterServer](#unregisterserver)|Nesne eşlemesindeki her nesnenin kaydını siler.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Kaydeder veya bir nesnenin standart sınıf kaydı kaydını siler.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Belirtilen kaynak kaydetmek veya kaydını bir nesne için yer alan komut dosyasını çalıştırır.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Statik olarak bağlanan ATL kayıt defteri bileşeni. Belirtilen kaynak kaydetmek veya kaydını bir nesne için yer alan komut dosyasını çalıştırır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Eşitlenen nesne eşleme bilgilerine erişim sağlar.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Tür kitaplığı bilgisi eşitlenmiş erişim sağlar.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Pencere sınıfı bilgileri ve statik veri penceresi oluşturulurken kullanılan eşitlenmiş erişim sağlar.|  
|[CComModule::m_hInst](#m_hinst)|Modül örneğinin tanıtıcısını içerir.|  
|[CComModule::m_hInstResource](#m_hinstresource)|Varsayılan olarak, modül örneğinin tanıtıcısını içerir.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|Varsayılan olarak, modül örneğinin tanıtıcısını içerir.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Modül örneği tarafından tutulan nesne eşlemesine işaret eder.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu sınıf kullanım dışıdır ve ATL kodu oluşturma sihirbazları artık kullanabilir [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) ve [CAtlModule](../../atl/reference/catlmodule-class.md) türetilmiş sınıflar. Bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla bilgi için. Aşağıdaki bilgiler, ATL daha eski sürümleri ile oluşturulan uygulamalarla kullanım içindir. `CComModule` hala ATL için geriye dönük özelliği parçasıdır.  
  
 `CComModule` Modülün bileşenlerine erişmek bir istemci sağlayan bir COM sunucusu modülü uygular. `CComModule` DLL (işlem içi) hem de EXE (yerel) modülleri destekler.  
  
 A `CComModule` örneği sınıfı nesne tanımları kümesini korumak için bir nesne eşleme kullanır. Bu nesne eşlemesi bir dizi olarak uygulanan `_ATL_OBJMAP_ENTRY` yapıları ve bilgileri içerir:  
  
-   Girme ve sistem kayıt defterinde nesnesi açıklamaları kaldırılıyor.  
  
-   Bir sınıf üreteci nesnelerde örnekleme.  
  
-   Bir istemci kök nesnesi arasındaki iletişimi bileşen oluşturma.  
  
-   Sınıf nesnelerinin ömür Yönetimi gerçekleştiriliyor.  
  
 ATL COM AppWizard çalıştırdığınızda, sihirbaz otomatik olarak oluşturulur `_Module`, genel bir örneğini `CComModule` veya ondan türetilmiş bir sınıf. ATL projesi Sihirbazı hakkında daha fazla bilgi için bkz [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
 Ek olarak `CComModule`, ATL sağlar [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), sağlar ve exe ve Windows Hizmetleri için bir apartman modeli modülü uygular. Modülünüzün öğesinden türetilen `CComAutoThreadModule` içinde birden çok apartmanlar nesneleri oluşturmak istediğinizde.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="getclassobject"></a>  CComModule::GetClassObject  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *rclsid*  
 [in] Oluşturulacak nesnenin CLSID.  
  
 *riid*  
 [in] İstenen arabirim Laboratuvardaki.  
  
 *ppv*  
 [out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppv* NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen CLSID'yi bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.  
  
 `GetClassObject` yalnızca dll için kullanılabilir.  
  
##  <a name="getmoduleinstance"></a>  CComModule::GetModuleInstance  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu modül tanımlama HINSTANCE.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [m_hInst](#m_hinst) veri üyesi.  
  
##  <a name="getresourceinstance"></a>  CComModule::GetResourceInstance  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir HINSTANCE.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [m_hInstResource](#m_hinstresource) veri üyesi.  
  
##  <a name="gettypelibinstance"></a>  CComModule::GetTypeLibInstance  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir HINSTANCE.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [m_hInstTypeLib](#m_hinsttypelib) veri üyesi.  
  
##  <a name="init"></a>  Ccommodule::Init  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *p*  
 [in] Bir nesne eşleme girişleri dizisine bir işaretçi.  
  
 *h*  
 [in] Geçirilen HINSTANCE `DLLMain` veya `WinMain`.  
  
 *plibid*  
 [in] Projeyle ilişkili tür kitaplığının Kitaplık kimliği için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri başlatır.  
  
##  <a name="m_csobjmap"></a>  CComModule::m_csObjMap  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne eşlemesine eşitlenmiş erişim sağlar.  
  
##  <a name="m_cstypeinfoholder"></a>  CComModule::m_csTypeInfoHolder  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür kitaplığını eşitlenmiş erişim sağlar.  
  
##  <a name="m_cswindowcreate"></a>  CComModule::m_csWindowCreate  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere sınıfı bilgileri ve statik veri penceresi oluşturulurken kullanılan eşitlenmiş erişim sağlar.  
  
##  <a name="m_hinst"></a>  CComModule::m_hInst  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Modül örneğinin tanıtıcısını içerir.  
  
 [Init](#init) yöntemi kümeleri `m_hInst` geçirilen işlenecek `DLLMain` veya `WinMain`.  
  
##  <a name="m_hinstresource"></a>  CComModule::m_hInstResource  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, modül örneğinin tanıtıcısını içerir.  
  
 [Init](#init) yöntemi kümeleri `m_hInstResource` geçirilen işlenecek `DLLMain` veya `WinMain`. Açıkça ayarlayabilirsiniz `m_hInstResource` bir kaynağa işlenecek.  
  
 [GetResourceInstance](#getresourceinstance) yöntemi içinde depolanan bir tanıtıcı döndürür `m_hInstResource`.  
  
##  <a name="m_hinsttypelib"></a>  CComModule::m_hInstTypeLib  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, modül örneğinin tanıtıcısını içerir.  
  
 [Init](#init) yöntemi kümeleri `m_hInstTypeLib` geçirilen işlenecek `DLLMain` veya `WinMain`. Açıkça ayarlayabilirsiniz `m_hInstTypeLib` bir tür kitaplığı için işlenecek.  
  
 [GetTypeLibInstance](#gettypelibinstance) yöntemi içinde depolanan bir tanıtıcı döndürür `m_hInstTypeLib`.  
  
##  <a name="m_pobjmap"></a>  CComModule::m_pObjMap  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Modül örneği tarafından tutulan nesne eşlemesine işaret eder.  
  
##  <a name="registerclasshelper"></a>  CComModule::RegisterClassHelper  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *CLSID*  
 [in] CLSID kaydedilecek nesne.  
  
 *lpszProgID*  
 [in] Nesneyle ilişkili ProgID.  
  
 *lpszVerIndProgID*  
 [in] Sürümden bağımsız bir nesneyle ilişkili ProgID.  
  
 *nDescID*  
 [in] Nesnenin tanımı için bir dize kaynağı tanımlayıcısı.  
  
 *CertOpenStore*  
 [in] Kayıt defterinde girmek için iş parçacığı modelini belirtir. Olası değerler şunlardır: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Standart sınıf kaydı bir nesnenin sistem kayıt defterinde girer.  
  
 [UpdateRegistryClass](#updateregistryclass) yöntem çağrılarını `RegisterClassHelper`.  
  
##  <a name="registerclassobjects"></a>  CComModule::RegisterClassObjects  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dwClsContext*  
 [in] Sınıf nesnesi çalıştırılacak bağlamı belirtir. Olası değerler şunlardır: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER. Bu değerlerin açıklaması için bkz [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) Windows SDK.  
  
 *CertOpenStore*  
 [in] Bağlantı türleri sınıf nesnesi belirler. Olası değerler şunlardır: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE. Bu değerlerin açıklaması için bkz [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Diğer uygulamalar ona bağlanabilmesi için bir EXE sınıf nesnesini OLE ile kaydeder. Bu yöntem yalnızca exe için kullanılabilir.  
  
##  <a name="registerserver"></a>  CComModule::RegisterServer  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *bRegTypeLib*  
 [in] Tür kitaplığı kayıtlı olup olmadığını gösterir. Varsayılan değer FALSE olur.  
  
 *pCLSID*  
 [in] CLSID işaret kaydedilecek nesne. NULL (varsayılan değer), nesne eşlemesindeki tüm nesneleri kayıtlı değilse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Yapılandırmanıza bağlı olarak *pCLSID* parametre, bir tek sınıf nesnesini veya nesne eşlemesindeki tüm nesneleri için sistem kayıt defterini güncelleştirir.  
  
 Varsa *bRegTypeLib* TRUE ise tür kitaplığı bilgisi de güncelleştirilir.  
  
 Bkz: [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) için nesne eşleme girişi ekleme hakkında daha fazla bilgi için.  
  
 `RegisterServer` tarafından otomatik olarak çağrılacak `DLLRegisterServer` DLL ya da `WinMain` bir EXE ile çalıştırmak için `/RegServer` komut satırı seçeneği.  
  
##  <a name="registertypelib"></a>  CComModule::RegisterTypeLib  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszIndex*  
 [in] Biçim dizesindeki `"\\N"`burada `N` TYPELIB kaynak tamsayı dizinidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür kitaplığı hakkında bilgi için sistem kayıt defterine ekler.  
  
 Modül örneğinin birden fazla tür kitaplığı içeriyorsa, hangi tür kitaplığı kullanılması gerektiğini belirtmek için bu yöntemi ikinci sürümü kullanın.  
  
##  <a name="revokeclassobjects"></a>  CComModule::RevokeClassObjects  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf nesnesini kaldırır. Bu yöntem yalnızca exe için kullanılabilir.  
  
##  <a name="term"></a>  CComModule::Term  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri serbest bırakır.  
  
##  <a name="unregisterclasshelper"></a>  CComModule::UnregisterClassHelper  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>Parametreler  
 *CLSID*  
 [in] CLSID kaydı nesnesi.  
  
 *lpszProgID*  
 [in] Nesneyle ilişkili ProgID.  
  
 *lpszVerIndProgID*  
 [in] Sürümden bağımsız bir nesneyle ilişkili ProgID.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Standart sınıf kaydı bir nesnenin sistem kayıt defterinden kaldırır.  
  
 [UpdateRegistryClass](#updateregistryclass) yöntem çağrılarını `UnregisterClassHelper`.  
  
##  <a name="unregisterserver"></a>  CComModule::UnregisterServer  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 *bUnRegTypeLib*  
 TRUE ise tür kitaplığı da kaydı.  
  
 *pCLSID*  
 CLSID işaret silinmesine izin nesnesi. NULL (varsayılan değer), nesne eşlemesindeki tüm nesneleri kaydı silinecek durumunda.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Yapılandırmanıza bağlı olarak *pCLSID* parametresi, bir tek sınıf nesnesini veya nesne eşlemesindeki tüm nesneleri kaydını siler.  
  
 `UnregisterServer` tarafından otomatik olarak çağrılacak `DLLUnregisterServer` DLL ya da `WinMain` bir EXE ile çalıştırmak için `/UnregServer` komut satırı seçeneği.  
  
 Bkz: [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) için nesne eşleme girişi ekleme hakkında daha fazla bilgi için.  
  
##  <a name="updateregistryclass"></a>  CComModule::UpdateRegistryClass  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
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
 *CLSID*  
 Kayıtlı veya Kayıtsız CLSID nesne.  
  
 *lpszProgID*  
 Nesneyle ilişkili ProgID.  
  
 *lpszVerIndProgID*  
 Sürümden bağımsız bir nesneyle ilişkili ProgID.  
  
 *nDescID*  
 Nesnenin açıklamasını için dize kaynağı tanımlayıcısı.  
  
 *szDesc*  
 Nesnenin açıklamasını içeren bir dize.  
  
 *CertOpenStore*  
 Kayıt defterinde girmek için iş parçacığı modelini belirtir. Olası değerler şunlardır: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.  
  
 *bRegister*  
 Nesne kayıtlı olup olmadığını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *bRegister* doğru ise, bu yöntem, sistem kayıt defterinde nesnenin standart sınıf kayıt girer.  
  
 Varsa *bRegister* yanlış, nesnenin kaydını kaldırır.  
  
 Değerine bağlı olarak *bRegister*, `UpdateRegistryClass` ya da çağırır [RegisterClassHelper](#registerclasshelper) veya [UnregisterClassHelper](#unregisterclasshelper).  
  
 Belirterek [DECLARE_REGISTRY](registry-macros.md#declare_registry) makro `UpdateRegistryClass` nesne haritanızı işlendiğinde otomatik olarak çağrılır.  
  
##  <a name="updateregistryfromresourced"></a>  CComModule::UpdateRegistryFromResourceD  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
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
 *lpszRes*  
 [in] Bir kaynak adı.  
  
 *nResID*  
 [in] Bir kaynak kimliği  
  
 *bRegister*  
 [in] Nesne kayıtlı olup olmadığını gösterir.  
  
 *pMapEntries*  
 [in] Betiğin değiştirilebilir parametreler ile ilişkili değerleri depolamayı değiştirme eşlemesi için bir işaretçi. ATL otomatik olarak kullanan `%MODULE%`. Ek değiştirilebilir parametreler kullanmak için açıklamalar Ayrıntılar için bkz. Aksi takdirde, NULL varsayılan değeri kullanın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen kaynak yer alan komut dosyasını çalıştırır *lpszRes* veya *nResID*.  
  
 Varsa *bRegister* doğru ise, bu yöntem nesnenin sistem kayıt defterine kaydeder; Aksi takdirde, nesnenin kaydını siler.  
  
 Belirterek [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makro `UpdateRegistryFromResourceD` nesne haritanızı işlendiğinde otomatik olarak çağrılır.  
  
> [!NOTE]
>  Çalışma zamanında değiştirme değeri yerine koymak istediğiniz DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosu belirtmeyin. Bunun yerine, bir dizi oluşturma `_ATL_REGMAP_ENTRIES` yapıları, burada her giriş içeren bir değişken yer tutucu eşleştirilmiş bir değerle çalışma zamanında yer tutucusunu değiştirin. Ardından çağırın `UpdateRegistryFromResourceD`, dizi geçirmek için *pMapEntries* parametresi. Bu değiştirme değeri ekler `_ATL_REGMAP_ENTRIES` yapılarını şirketinin değiştirme eşlemesi.  
  
> [!NOTE]
>  ATL kayıt defteri bileşeni (Kaydedici) statik olarak bağlamak için bkz [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için bkz [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="updateregistryfromresources"></a>  CComModule::UpdateRegistryFromResourceS  
 ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
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
 *lpszRes*  
 [in] Bir kaynak adı.  
  
 *nResID*  
 [in] Bir kaynak kimliği  
  
 *bRegister*  
 [in] Kaynak betiği kayıtlı olup olmadığını gösterir.  
  
 *pMapEntries*  
 [in] Betiğin değiştirilebilir parametreler ile ilişkili değerleri depolamayı değiştirme eşlemesi için bir işaretçi. ATL otomatik olarak kullanan `%MODULE%`. Ek değiştirilebilir parametreler kullanmak için açıklamalar Ayrıntılar için bkz. Aksi takdirde, NULL varsayılan değeri kullanın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde [UpdateRegistryFromResourceD](#updateregistryfromresourced) dışında `UpdateRegistryFromResourceS` ATL kayıt defteri bileşeni (Kaydedici) statik bir bağlantı oluşturur.  
  
 `UpdateRegistryFromResourceS` Nesne haritanızı işlendiğinde, eklediğiniz sağlanan otomatik olarak çağrılacak `#define _ATL_STATIC_REGISTRY` , Stdafx.H'ye.  
  
> [!NOTE]
>  Çalışma zamanında değiştirme değeri yerine koymak istediğiniz belirtmeyin [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) makrosu. Bunun yerine, bir dizi oluşturma `_ATL_REGMAP_ENTRIES` yapıları, burada her giriş içeren bir değişken yer tutucu eşleştirilmiş bir değerle çalışma zamanında yer tutucusunu değiştirin. Ardından çağırın `UpdateRegistryFromResourceS`, dizi geçirmek için *pMapEntries* parametresi. Bu değiştirme değeri ekler `_ATL_REGMAP_ENTRIES` yapılarını şirketinin değiştirme eşlemesi.  
  
 Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için bkz [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
