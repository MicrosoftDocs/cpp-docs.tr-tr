---
title: "CAtlModuleT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
dev_langs: C++
helpviewer_keywords: CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4f1ba8d59e85a480af38e5b9778fee0c714a0db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlmodulet-class"></a>CAtlModuleT sınıfı
Bu sınıf bir ATL modül uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınızda türetilmiş `CAtlModuleT`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|Geçerli modül GUID içeren veri üyesi başlatır.|  
|[CAtlModuleT::RegisterAppId](#registerappid)|EXE kayıt defterine ekler.|  
|[CAtlModuleT::RegisterServer](#registerserver)|Hizmet kayıt defterine ekler.|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|EXE kayıt defterinden kaldırır.|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Hizmet kayıt defterinden kaldırır.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Kayıt defterinde EXE bilgilerini güncelleştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlModuleT`, türetilmiş [CAtlModule](../../atl/reference/catlmodule-class.md), bir yürütülebilir dosya (EXE) veya bir hizmet (EXE) ATL modül uygular. Bir hizmeti modülü Windows başladığında arka planda çalışan bir Windows uygulaması iken bir yürütülebilir yerel ve işlem dışı bir sunucu modülüdür.  
  
 `CAtlModuleT`başlatma, kaydetme ve modül, kaydını kaldırmak için destek sağlar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT  
 Oluşturucu.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlModuleT::InitLibId](#initlibid).  
  
##  <a name="initlibid"></a>CAtlModuleT::InitLibId  
 Geçerli modül GUID içeren veri üyesi başlatır.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yapıcı tarafından adlı [CAtlModuleT::CAtlModuleT](#catlmodulet).  
  
##  <a name="registerappid"></a>CAtlModuleT::RegisterAppId  
 EXE kayıt defterine ekler.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="registerserver"></a>CAtlModuleT::RegisterServer  
 Hizmet kayıt defterine ekler.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bRegTypeLib`  
 Tür kitaplığı kaydedilecek ise TRUE. Varsayılan değer FALSE olur.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin kayıtlı olması gerekir. NULL (varsayılan değer) tüm nesneleri nesneyi eşlemesindeki kayıtlı değilse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="unregisterappid"></a>CAtlModuleT::UnregisterAppId  
 EXE kayıt defterinden kaldırır.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="unregisterserver"></a>CAtlModuleT::UnregisterServer  
 Hizmet kayıt defterinden kaldırır.  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bUnRegTypeLib`  
 Tür kitaplığı kaydı için aynı zamanda ise TRUE.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin sona erdirilecek. NULL (varsayılan değer) tüm nesneleri nesneyi eşlemesindeki kaydı olacaksa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId  
 Kayıt defterinde EXE bilgilerini güncelleştirir.  
  
```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bRegister`  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlModule sınıfı](../../atl/reference/catlmodule-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
