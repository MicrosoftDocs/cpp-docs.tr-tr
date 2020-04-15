---
title: Sunucu Kaydı Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: fb6353b52f487d0511c54223fe9e31dab88704b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325922"
---
# <a name="server-registration-global-functions"></a>Sunucu Kaydı Genel İşlevleri

Bu işlevler, nesne eşlemi içinde sunucu nesnelerinin kaydedilmesi ve kaydedilmesi için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Bu işlev nesne sınıflarını kaydetmek için çağrılır.|
|[AtlComModuleRevokeClassNesneler](#atlcommodulerevokeclassobjects)|Bu işlev, bir COM modülünden sınıf nesneleri iptal etmek için çağrılır.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Bu işlev sınıf nesnesi almak için denir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer

Bu işlev, nesne eşlemesindeki her nesneyi kaydetmek için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülüne işaretçi.

*bRegTypeLib*<br/>
Tür kitaplığı kaydedilecekse DOĞRU.

*pCLSID*<br/>
Kaydedilecek nesnenin CLSID'sine işaret edin. NULL ise, nesne eşlemindeki tüm nesneler kaydedilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

`AtlComModuleRegisterServer`ATL otomatik olarak oluşturulmuş nesne eşlemi yürür ve her nesneyi haritada kaydeder. *pCLSID* NULL değilse, yalnızca *pCLSID* tarafından atıfta bulunulan nesne kaydedilir; aksi takdirde tüm nesneler kaydedilir.

Bu fonksiyon [CAtlComModule tarafından adlandırılır::RegisterServer](catlcommodule-class.md#registerserver).

## <a name="atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer

Bu işlev, nesne eşlemesindeki her nesnenin kaydını silmek için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülüne işaretçi.

*bUnRegTypeLib*<br/>
Tür kitaplığı kaydedilecekse DOĞRU.

*pCLSID*<br/>
Nesnenin CLSID'sine kayıtsız kalmak için işaret. NULL ise nesne eşlemindeki tüm nesneler kayıtsız kalır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

`AtlComModuleUnregisterServer`ATL nesne haritasını yürüer ve haritadaki her nesnenin kaydını silinir. *pCLSID* NULL değilse, yalnızca *pCLSID* tarafından başvurulan nesne kayıt dışıdır; aksi takdirde tüm nesneler kayıt dışıdır.

Bu fonksiyon [CAtlComModule tarafından adlandırılır::UnregisterServer](catlcommodule-class.md#unregisterserver).

## <a name="atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects

Bu işlev nesne sınıflarını kaydetmek için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülüne işaretçi.

*dwClsBağlam*<br/>
Sınıf nesnesinin çalıştırılacak olduğu bağlamı belirtir. Olası değerler CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER veya CLSCTX_LOCAL_SERVER. Daha fazla bilgi için [CLSCTX'e](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) bakın.

*Dwflags*<br/>
Sınıf nesnesine bağlantı türlerini belirler. Olası değerler REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE veya REGCLS_MULTI_SEPARATE. Daha fazla bilgi için [REGCLS'e](/windows/win32/api/combaseapi/ne-combaseapi-regcls) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [CComModule tarafından kullanılmaktadır::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0 eski) ve [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).

## <a name="atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassNesneler

Bu işlev Çalışan Nesne Tablosundan sınıf üretecini kaldırmak için çağrılır.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Parametreler

*pComModule*<br/>
COM modülüne işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [CComModule tarafından kullanılır::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0 eski) ve [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).

## <a name="atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject

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
COM modülüne işaretçi.

*rclsid*<br/>
Oluşturulacak nesnenin CLSID'si.

*Riid*<br/>
İstenen arabirimin IID'si.

*Ppv*<br/>
*riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *PPV* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [CComModule tarafından kullanılmaktadır::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0 eski) ve [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
