---
title: "CAtlDllModuleT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
dev_langs: C++
helpviewer_keywords: CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c178cb10c6f14d257e9c03b499ea8f2fa01eddf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT sınıfı
Bu sınıf için bir DLL modülü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınızda türetilmiş `CAtlDllModuleT`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Oluşturucu.|  
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Testleri DLL kaldırılmış olabilir.|  
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Bir sınıf fabrikası döndürür.|  
|[CAtlDllModuleT::DllMain](#dllmain)|Dinamik bağlantı kitaplığı (DLL) içine isteğe bağlı giriş noktası.|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|DLL içindeki nesneler için sistem kayıt defteri girdileri ekler.|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|DLL içindeki nesneler için sistem kayıt defteri girişlerini kaldırır.|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Bir sınıf fabrikası döndürür. Tarafından çağrılan [DllGetClassObject](#dllgetclassobject).|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlDllModuleT`dinamik bağlantı kitaplığı (DLL) için modülü temsil eder ve tüm DLL projeler tarafından kullanılan işlevler sağlar. Bu alt uzmanlaşması [CAtlModuleT](../../atl/reference/catlmodulet-class.md) sınıfı kaydı için destek içerir.  
  
 ATL modülleri hakkında daha fazla bilgi için bkz: [ATL modül sınıfları](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT  
 Oluşturucu.  
  
```
CAtlDllModuleT() throw();
```  
  
##  <a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT  
 Yok Edicisi.  
  
```
~CAtlDllModuleT() throw();
```  
  
##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow  
 Testleri DLL kaldırılmış olabilir.  
  
```
HRESULT DllCanUnloadNow() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başaramazsa DLL bellekten olabiliyorsa, S_OK veya S_FALSE döndürür.  
  
##  <a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClassObject  
 Sınıf Üreteç döndürür.  
  
```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rclsid`  
 Oluşturulacak nesnenin CLSID'si.  
  
 `riid`  
 İstenen arabirim IID.  
  
 `ppv`  
 Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppv` NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="dllmain"></a>CAtlDllModuleT::DllMain  
 Dinamik bağlantı kitaplığı (DLL) içine isteğe bağlı giriş noktası.  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwReason`  
 DLL_PROCESS_ATTACH, DllMain ve DLL_THREAD_ATTACH bildirim çağrıları kümesine devre dışı bırakılırsa.  
  
 *lpReserved*  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 DllMain devre dışı bırakma ve DLL_THREAD_ATTACH bildirim çağrıları birçok DLL'leri sahip birden çok iş parçacıklı uygulamalar için yararlı bir iyileştirme olabilir, sık oluşturmak ve iş parçacıkları silin ve, DLL'ler, bu iş parçacığı düzeyi bildirimler gerekmez Ek/ayrılmayı.  
  
##  <a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer  
 DLL içindeki nesneler için sistem kayıt defteri girdileri ekler.  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bRegTypeLib`  
 Tür kitaplığı kaydedilecek ise TRUE. Varsayılan değer True'dur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer  
 DLL içindeki nesneler için sistem kayıt defteri girişlerini kaldırır.  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bUnRegTypeLib`  
 Tür kitaplığı kayıt defterinden kaldırılacak ise TRUE. Varsayılan değer True'dur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="getclassobject"></a>CAtlDllModuleT::GetClassObject  
 Belirtilen CLSID bir nesne oluşturur.  
  
```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rclsid`  
 Oluşturulacak nesnenin CLSID'si.  
  
 `riid`  
 İstenen arabirim IID.  
  
 `ppv`  
 Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppv` NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) ve geriye doğru uyumluluk için bulunmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlModuleT sınıfı](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT sınıfı](../../atl/reference/catlexemodulet-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
