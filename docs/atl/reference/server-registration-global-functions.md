---
title: Sunucu kaydı genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: f9c3697259e1cee2b1107ded785ca583d730b55e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78863250"
---
# <a name="server-registration-global-functions"></a>Sunucu kaydı genel Işlevleri

Bu işlevler, nesne eşlemesindeki sunucu nesnelerinin kaydı ve kaydını silme desteği sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Bu işlev nesne sınıflarını kaydetmek için çağrılır.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Bu işlev, COM modülünden sınıf nesnelerini iptal etmek için çağrılır.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Bu işlev, sınıf nesnesini almak için çağrılır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer

Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülünün işaretçisi.

*bRegTypeLib*<br/>
Tür kitaplığının kaydı varsa TRUE.

*pCLSID*<br/>
Kaydedilecek nesnenin CLSID değerini gösterir. NULL ise, nesne haritadaki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`AtlComModuleRegisterServer` ATL tarafından otomatik olarak oluşturulan nesne eşlemesini açıklar ve haritadaki her nesneyi kaydeder. *PCLSıD* null değilse, yalnızca *pCLSID* tarafından başvurulan nesne kaydedilir; Aksi takdirde tüm nesneler kaydedilir.

Bu işlev, [CAtlComModule:: RegisterServer](catlcommodule-class.md#registerserver)tarafından çağrılır.

##  <a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer

Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülünün işaretçisi.

*bUnRegTypeLib*<br/>
Tür kitaplığının kaydı varsa TRUE.

*pCLSID*<br/>
Kaydı kaldırılacak nesnenin CLSID değerini gösterir. NULL ise nesne haritadaki tüm nesnelerin kaydı silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`AtlComModuleUnregisterServer` ATL nesne eşlemesini açıklar ve haritadaki her nesnenin kaydını siler. *PCLSıD* null değilse, yalnızca *pCLSID* tarafından başvurulan nesnenin kaydı silindi. Aksi takdirde tüm nesneler kaydı silinir.

Bu işlev, [CAtlComModule:: UnregisterServer](catlcommodule-class.md#unregisterserver)tarafından çağrılır.

##  <a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects

Bu işlev nesne sınıflarını kaydetmek için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülünün işaretçisi.

*dwClsContext*<br/>
Sınıf nesnesinin çalıştırılacağı bağlamı belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER. Daha fazla ayrıntı için bkz. [clsctx](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) .

*dwFlags*<br/>
Sınıf nesnesine bağlantı türlerini belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE. Daha fazla ayrıntı için bkz. [regcls](/windows/win32/api/combaseapi/ne-combaseapi-regcls) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [CComModule:: RegisterClassObjects](ccommodule-class.md#registerclassobjects) (atl 7,0 ' de kullanılmıyor) ve [CAtlExeModuleT:: RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)tarafından kullanılır.

##  <a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects

Bu işlev Çalışan Nesne Tablosundan sınıf üretecini kaldırmak için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülünün işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [CComModule:: RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (atl 7,0 ' de kullanılmıyor) ve [CAtlExeModuleT:: RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects)tarafından kullanılır.

##  <a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject

Sınıf üretecini döndürmek için bu işlev çağrılır.

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülünün işaretçisi.

*rclsıd*<br/>
Oluşturulacak nesnenin CLSID değeri.

*riıd*<br/>
İstenen arabirimin IID 'si.

*PPV*<br/>
*Riıd*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [CComModule:: GetClassObject](ccommodule-class.md#getclassobject) (atl 7,0 ' de kullanılmıyor) ve [Catldllmodület:: GetClassObject](catldllmodulet-class.md#getclassobject)tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
