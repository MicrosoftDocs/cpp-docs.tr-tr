---
title: Sunucu kayıt genel işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08a4141ab5ff27e44f663a4d5f267c2b7d754283
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364711"
---
# <a name="server-registration-global-functions"></a>Sunucu kayıt genel işlevler
Bu işlevler kaydetme ve sunucu nesneleri nesneyi eşlemesindeki kaydını kaldırmak için destek sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Bu işlev nesne sınıflarını kaydetmek için çağrılır.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Bu işlev bir COM modülden sınıf nesnelerine iptal etmek için çağrılır.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Bu işlev, sınıf nesnesi almak için çağrılır.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer  
 Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parametreler  
 `pComModule`  
 COM modülü işaretçi.  
  
 `bRegTypeLib`  
 Tür kitaplığı kaydedilecek ise TRUE.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin kayıtlı olması gerekir. NULL ise, tüm nesneleri nesneyi eşlemesindeki kaydedilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlComModuleRegisterServer` ATL otomatik olarak oluşturulur nesne eşlemesi anlatılmaktadır ve her nesne eşlemesinde kaydeder. Varsa `pCLSID` değil NULL sonra başvurulan nesnenin `pCLSID` kaydedilir; Aksi takdirde tüm nesneler kaydedilir.  
  
 Bu işlev tarafından çağrılır [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parametreler  
 `pComModule`  
 COM modülü işaretçi.  
  
 `bUnRegTypeLib`  
 Tür kitaplığı kaydedilecek ise TRUE.  
  
 `pCLSID`  
 CLSID noktalarına nesnenin sona erdirilecek. NULL ise tüm nesneleri nesneyi eşlemesindeki kaydı kaldırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlComModuleUnregisterServer` ATL nesne eşlemesi anlatılmaktadır ve her nesne eşlemesindeki kaydını siler. Varsa `pCLSID` değil NULL sonra başvurulan nesnenin `pCLSID` kaydı; Aksi takdirde tüm nesneleri kaydı.  
  
 Bu işlev tarafından çağrılır [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 Bu işlev nesne sınıflarını kaydetmek için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `pComModule`  
 COM modülü işaretçi.  
  
 `dwClsContext`  
 Sınıf nesnesi çalıştırılsın mı bağlam belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER olur. Bkz: [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) daha fazla ayrıntı için.  
  
 `dwFlags`  
 Bağlantı türleri sınıf nesnesine belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE olur. Bkz: [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) daha fazla ayrıntı için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7. 0'te eski) ve [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 Bu işlev Çalışan Nesne Tablosundan sınıf üretecini kaldırmak için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Parametreler  
 `pComModule`  
 COM modülü işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7. 0'te eski) ve [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject  
 Sınıf üretecini döndürmek için bu işlev çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pComModule`  
 COM modülü işaretçi.  
  
 `rclsid`  
 Oluşturulacak nesnenin CLSID'si.  
  
 `riid`  
 İstenen arabirim IID.  
  
 `ppv`  
 Arabirim işaretçisi ile tanımlanan bir işaretçi `riid`. Nesne bu arabirim desteklemiyorsa `ppv` NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7. 0'te eski) ve [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
