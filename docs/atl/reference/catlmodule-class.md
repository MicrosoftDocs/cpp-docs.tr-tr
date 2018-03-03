---
title: "CAtlModule sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c969341656d0861224cf0835d08e31907328b5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlmodule-class"></a>CAtlModule sınıfı
Bu sınıfın birkaç ATL modül sınıfları tarafından kullanılan yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Oluşturucu.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL kayıt defteri bileşeni (Kaydedici) değiştirme eşlemesine parametreleri eklemek için bu yöntemi geçersiz kılın.|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Modül sonlandırıldığında çağrılacak yeni bir işlev ekler.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Genel arabirim işaretçisi döndürür.|  
|[CAtlModule::GetLockCount](#getlockcount)|Kilit sayımını döndürür.|  
|[CAtlModule::Lock](#lock)|Kilit sayısını artırır.|  
|[CAtlModule::Term](#term)|Tüm veri üyeleri serbest bırakır.|  
|[CAtlModule::Unlock](#unlock)|Azaltır kilit sayısı.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Kaydetmek veya kaydı bir nesne için belirtilen bir kaynak içinde yer alan komut dosyasını çalıştırır.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Bu yöntem tarafından çağrılır `UpdateRegistryFromResourceD` kayıt defteri güncelleştirme gerçekleştirmek için.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Kaydetmek veya kaydı bir nesne için belirtilen bir kaynak içinde yer alan komut dosyasını çalıştırır. Bu yöntem statik olarak ATL kayıt defteri bileşenine bağlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Geçerli modül GUID içerir.|  
|[CAtlModule::m_pGIT](#m_pgit)|Genel arabirim tablosu işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf tarafından kullanılan [CAtlDllModuleT sınıfı](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT sınıfı](../../atl/reference/catlexemodulet-class.md), ve [CAtlServiceModuleT sınıfı](../../atl/reference/catlservicemodulet-class.md) EXE uygulamaları DLL uygulamaları için destek sağlamak için ve Windows, sırasıyla Hizmetleri.  
  
 ATL modülleri hakkında daha fazla bilgi için bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md).  
  
 Bu sınıf artık kullanılmıyor değiştirir [CComModule sınıfı](../../atl/reference/ccommodule-class.md) ATL önceki sürümlerinde kullanılan  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 ATL kayıt defteri bileşeni (Kaydedici) değiştirme eşlemesine parametreleri eklemek için bu yöntemi geçersiz kılın.  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 *pRegistrar*  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Değiştirilebilir parametreler çalışma zamanı verileri belirtmek bir kayıt şirketinizin istemci izin verin. Bunu yapmak için kayıt şirketi içine komut değiştirilebilir parametreler ile ilişkili değerleri girer değiştirme harita tutar. Kayıt şirketi bu girişler çalışma zamanında yapar.  
  
 Konusuna [kullanarak değiştirilebilir parametreler (kayıt şirketinizin önişlemci)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) daha fazla ayrıntı için.  
  
##  <a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 Modül sonlandırıldığında çağrılacak yeni bir işlev ekler.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pFunc*  
 Eklemek için işlev işaretçisi.  
  
 `dw`  
 Kullanıcı tanımlı veri işlevine geçirildi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="catlmodule"></a>CAtlModule::CAtlModule  
 Oluşturucu.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Veri üyeleri başlatır ve önemli bir bölümü modülün iş parçacığı geçici başlatır.  
  
##  <a name="dtor"></a>CAtlModule:: ~ CAtlModule  
 Yok Edicisi.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri serbest bırakır.  
  
##  <a name="getgitptr"></a>CAtlModule::GetGITPtr  
 Genel arabirim tablosu için bir işaretçi alır.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ppGIT`  
 Genel arabirim tablosu işaretçisine alır gereken değişkeni işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarılı veya başarısız olduğunda bir hata kodu döndürür. E_POINTER ise döndürülür `ppGIT` NULL değerine eşittir.  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim tablosu nesne yok, oluşturulur ve adresini üye değişkeninde depolanan [CAtlModule::m_pGIT](#m_pgit).  
  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `ppGIT` NULL değerine eşit olan veya genel arabirim tablosu işaretçi aldıysanız.  
  
 Bkz: [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) genel arabirim tablosu hakkında bilgi için.  
  
##  <a name="getlockcount"></a>CAtlModule::GetLockCount  
 Kilit sayımını döndürür.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit sayımını döndürür. Bu değer, hata ayıklama ve tanılama için yararlı olabilir.  
  
##  <a name="lock"></a>CAtlModule::Lock  
 Kilit sayısını artırır.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit sayısını artırır ve güncelleştirilmiş değeri döndürür. Bu değer, hata ayıklama ve tanılama için yararlı olabilir.  
  
##  <a name="m_libid"></a>CAtlModule::m_libid  
 Geçerli modül GUID içerir.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>CAtlModule::m_pGIT  
 Genel arabirim tablosu işaretçi.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>CAtlModule::Term  
 Tüm veri üyeleri serbest bırakır.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri serbest bırakır. Bu yöntem yıkıcı tarafından çağrılır.  
  
##  <a name="unlock"></a>CAtlModule::Unlock  
 Azaltır kilit sayısı.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Azaltır kilit sayısı ve güncelleştirilmiş değeri döndürür. Bu değer, hata ayıklama ve tanılama için yararlı olabilir.  
  
##  <a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 Kaydetmek veya kaydı bir nesne için belirtilen bir kaynak içinde yer alan komut dosyasını çalıştırır.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszRes`  
 Bir kaynak adı.  
  
 `nResID`  
 Bir kaynak kimliği  
  
 `bRegister`  
 **DOĞRU** nesne kayıtlı olması; **FALSE** Aksi takdirde.  
  
 `pMapEntries`  
 Komut dosyanızın değiştirilebilir parametreler ile ilişkili değerlerini depolama değiştirme eşlemesi için bir işaretçi. ATL MODÜL % otomatik olarak kullanır. Ek değiştirilebilir parametreler kullanmak için bkz: [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde kullanın **NULL** varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen kaynak içinde yer alan komut dosyasını çalıştırır *lpszRes veya nResID*. Varsa `bRegister` olan **doğru**, bu yöntem nesne sistem kayıt defterinde kaydeder; Aksi takdirde nesne kayıt defterinden kaldırır.  
  
 ATL kayıt defteri bileşeni (Kaydedici) statik olarak bağlamak için bkz: [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Bu yöntemi çağırır [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) ve [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 Bu yöntem tarafından çağrılır `UpdateRegistryFromResourceD` kayıt defteri güncelleştirme gerçekleştirmek için.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszRes`  
 Bir kaynak adı.  
  
 `bRegister`  
 Nesne kayıtlı olup olmadığını belirtir.  
  
 `pMapEntries`  
 Komut dosyanızın değiştirilebilir parametreler ile ilişkili değerlerini depolama değiştirme eşlemesi için bir işaretçi. ATL MODÜL % otomatik olarak kullanır. Ek değiştirilebilir parametreler kullanmak için bkz: [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde kullanın **NULL** varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem uygulamasını sağlar [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 Kaydetmek veya kaydı bir nesne için belirtilen bir kaynak içinde yer alan komut dosyasını çalıştırır. Bu yöntem statik olarak ATL kayıt defteri bileşenine bağlar.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nResID`  
 Bir kaynak kimliği  
  
 `lpszRes`  
 Bir kaynak adı.  
  
 `bRegister`  
 Kaynak betik kayıtlı olup olmadığını belirtir.  
  
 `pMapEntries`  
 Komut dosyanızın değiştirilebilir parametreler ile ilişkili değerlerini depolama değiştirme eşlemesi için bir işaretçi. ATL MODÜL % otomatik olarak kullanır. Ek değiştirilebilir parametreler kullanmak için bkz: [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Aksi takdirde kullanın **NULL** varsayılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) dışında `CAtlModule::UpdateRegistryFromResourceS` ATL kayıt defteri bileşeni (Kaydedici) statik bir bağlantı oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)   
 [Kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md)  
