---
title: "CAtlComModule sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83dfbb1792a569e359692ba55fb23a8ebb580c37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlcommodule-class"></a>CAtlComModule sınıfı
Bu sınıf bir COM sunucusu modülü uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|Oluşturucu.|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|Nesne eşlemesindeki her nesne için sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Tür kitaplığı kaydı için bu yöntemi çağırın.|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|Her nesne eşlemesi nesnesinde kaydını kaldırmak için bu yöntemi çağırın.|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Tür kitaplığı kaydı için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlComModule`Modülün bileşenlerine erişmek bir istemci sağlayan bir COM sunucusu modül uygular.  
  
 Bu sınıf artık kullanılmıyor değiştirir [CComModule](../../atl/reference/ccommodule-class.md) ATL önceki sürümlerinde kullanılan sınıf Bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md) daha fazla ayrıntı için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="catlcommodule"></a>CAtlComModule::CAtlComModule  
 Oluşturucu.  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Modül başlatır.  
  
##  <a name="dtor"></a>CAtlComModule:: ~ CAtlComModule  
 Yok Edicisi.  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm sınıf oluşturucuları boşaltır.  
  
##  <a name="registerserver"></a>CAtlComModule::RegisterServer  
 Nesne eşlemesindeki her nesne için sistem kayıt defterini güncelleştirmek için bu yöntemi çağırın.  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `bRegTypeLib`  
 Tür kitaplığı kaydedilecek ise TRUE. Varsayılan değer FALSE olur.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin kayıtlı olması gerekir. NULL (varsayılan değer) tüm nesneleri nesneyi eşlemesindeki kayıtlı değilse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Genel işlev çağrılarını [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).  
  
##  <a name="registertypelib"></a>CAtlComModule::RegisterTypeLib  
 Tür kitaplığı kaydı için bu yöntemi çağırın.  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszIndex`  
 Biçim dizesindeki "\\\N", N TYPELIB kaynak tamsayı dizinini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tür Kitaplığı hakkında bilgi için sistem kayıt defteri ekler. Modül örneğinin birden çok tür kitaplıklarının içeriyorsa, hangi tür kitaplığı kullanılması gerektiğini belirtmek için bu yöntem ilk sürümünü kullanın.  
  
##  <a name="unregisterserver"></a>CAtlComModule::UnregisterServer  
 Her nesne eşlemesi nesnesinde kaydını kaldırmak için bu yöntemi çağırın.  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `bRegTypeLib`  
 Tür kitaplığı kaydı ise TRUE. Varsayılan değer FALSE olur.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin sona erdirilecek. NULL (varsayılan değer) tüm nesneleri nesneyi eşlemesindeki kaydı olacaksa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Genel işlev çağrılarını [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).  
  
##  <a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib  
 Tür kitaplığı kaydı için bu yöntemi çağırın.  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszIndex`  
 Biçim dizesindeki "\\\N", N TYPELIB kaynak tamsayı dizinini alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Tür Kitaplığı hakkında bilgi sistem kayıt defterinden kaldırır. Modül örneğinin birden çok tür kitaplıklarının içeriyorsa, hangi tür kitaplığı kullanılması gerektiğini belirtmek için bu yöntem ilk sürümünü kullanın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
