---
title: Sunucu kaydı genel işlevleri | Microsoft Docs
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
ms.openlocfilehash: a2cc139fa0aa933131e4e19b8efa397e4bddee50
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209234"
---
# <a name="server-registration-global-functions"></a>Sunucu kaydı genel işlevleri
Bu işlevler, kaydetme ve sunucu nesneleri nesne eşlemesindeki kaydını kaldırmak için destek sağlar.  
  
> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Bu işlev nesne sınıflarını kaydetmek için çağrılır.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Bu işlev sınıfı nesnelerinden bir COM modülü iptal etmek için çağrılır.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Bu işlev, sınıf nesnesini almak için çağrılır.|  

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
 *pComModule*  
 COM modülü için işaretçi.  
  
 *bRegTypeLib*  
 Tür kitaplığı kayıtlı olması ise TRUE.  
  
 *pCLSID*  
 CLSID işaret kaydedilecek nesne. NULL ise, nesne eşlemesindeki tüm nesneler kaydedilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlComModuleRegisterServer` ATL otomatik olarak oluşturulan nesne eşlemesine gezer ve eşlemesindeki her nesneyi kaydeder. Varsa *pCLSID* NULL ve ardından yalnızca tarafından başvurulan nesne değil *pCLSID* kaydedilir; Aksi takdirde tüm nesneler kaydedilir.  
  
 Bu işlevi çağıran [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parametreler  
 *pComModule*  
 COM modülü için işaretçi.  
  
 *bUnRegTypeLib*  
 Tür kitaplığı kayıtlı olması ise TRUE.  
  
 *pCLSID*  
 CLSID işaret silinmesine izin nesnesi. NULL ise nesne eşlemesindeki tüm nesneleri kaydı silinecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlComModuleUnregisterServer` ATL nesne eşlemesine gezer ve eşlemesindeki her nesnenin kaydını siler. Varsa *pCLSID* NULL ve ardından yalnızca tarafından başvurulan nesne değil *pCLSID* kaydı; Aksi takdirde tüm nesneleri kaydı.  
  
 Bu işlevi çağıran [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 Bu işlev nesne sınıflarını kaydetmek için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *pComModule*  
 COM modülü için işaretçi.  
  
 *dwClsContext*  
 Sınıf nesnesi çalıştırılacak bağlamı belirtir. Olası değerler şunlardır: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER. Bkz: [CLSCTX](https://msdn.microsoft.com/library/windows/desktop/ms693716) daha fazla ayrıntı için.  
  
 *CertOpenStore*  
 Bağlantı türleri sınıf nesnesi belirler. Olası değerler şunlardır: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE. Bkz: [REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls) daha fazla ayrıntı için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0 obsolete) ve [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 Bu işlev Çalışan Nesne Tablosundan sınıf üretecini kaldırmak için çağrılır.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Parametreler  
 *pComModule*  
 COM modülü için işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0 obsolete) ve [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
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
 *pComModule*  
 COM modülü için işaretçi.  
  
 *rclsid*  
 Oluşturulacak nesnenin CLSID.  
  
 *riid*  
 İstenen arabirim Laboratuvardaki.  
  
 *ppv*  
 Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppv* NULL olarak ayarlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0 obsolete) ve [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
