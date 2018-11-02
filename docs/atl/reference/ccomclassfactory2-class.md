---
title: CComClassFactory2 sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: ba5bda2e73964e7195c4955806e897f9496c244a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460209"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 sınıfı

Bu sınıfın uyguladığı [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) arabirimi.

## <a name="syntax"></a>Sözdizimi

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Parametreler

*Lisans*<br/>
Aşağıdaki statik işlevler uygulayan bir sınıf:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactory2::CreateInstance](#createinstance)|Belirtilen CLSID'yi bir nesne oluşturur.|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Bir lisans anahtarı, belirtilen CLSID'yi bir nesne oluşturur.|
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Sınıf üreteci lisans özelliklerini açıklayan bilgileri alır.|
|[CComClassFactory2::LockServer](#lockserver)|Sınıf üreteci bellekte kilitler.|
|[CComClassFactory2::RequestLicKey](#requestlickey)|Oluşturur ve bir lisans anahtarı döndürür.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactory2` uygulayan [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) uzantısıdır arabirimi, [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` bir lisans ile denetimleri nesne oluşturma. Bir sınıf üreteci lisanslı bir makinede çalıştırma, bir çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı tam makine lisans yoksa nesneleri somutlaştırmak bir uygulama sağlar.

ATL nesneleri normalde türetilen bir sınıf üreteci almak [CComCoClass](../../atl/reference/ccomcoclass-class.md). Bu sınıf makro içerir [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), hangi bildirir [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) olarak varsayılan sınıf üreteci. Kullanılacak `CComClassFactory2`, belirtin [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makrosu, nesnenin sınıf tanımında. Örneğin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, şablon parametresi olarak `CComClassFactory2`, statik işlevler uygulamalıdır `VerifyLicenseKey`, `GetLicenseKey`, ve `IsLicenseValid`. Aşağıdaki basit lisans sınıfının bir örneğidir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2` hem türetilen `CComClassFactory2Base` ve *lisans*. `CComClassFactory2Base`, sırasıyla türetildiği `IClassFactory2` ve `CComObjectRootEx< CComGlobalsThreadModel >`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance

Belirtilen CLSID'yi bir nesne oluşturur ve bu nesne için bir arabirim işaretçisi alır.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
[in] Nesne bir toplamanın parçası olarak ardından oluşturuluyorsa *pUnkOuter* dış bilinmeyen olması gerekir. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*riid*<br/>
[in] İstenen arabirim Laboratuvardaki. Varsa *pUnkOuter* kullanmaktan, *riid* olmalıdır `IID_IUnknown`.

*ppvObj*<br/>
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppvObj* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Makine tam olarak lisanslanması gerekir. Tam makine lisans yoksa çağrı [CreateInstanceLic](#createinstancelic).

##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic

Benzer şekilde [CreateInstance](#createinstance)dışında `CreateInstanceLic` bir lisans anahtarı gerektirir.

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
[in] Nesne bir toplamanın parçası olarak ardından oluşturuluyorsa *pUnkOuter* dış bilinmeyen olması gerekir. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*pUnkReserved*<br/>
[in] Kullanılmıyor. NULL olmalıdır.

*riid*<br/>
[in] İstenen arabirim Laboratuvardaki. Varsa *pUnkOuter* kullanmaktan, *riid* olmalıdır `IID_IUnknown`.

*bstrKey*<br/>
[in] Çalışma zamanı lisans anahtarı daha önce edindiğiniz çağrısından `RequestLicKey`. Bu anahtar nesneyi oluşturmak için gereklidir.

*ppvObject*<br/>
[out] Tarafından belirtilen arabirim işaretçisini bir işaretçi *riid*. Nesne bu arabirimi desteklemiyorsa *ppvObject* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Kullanarak bir lisans anahtarı edinebilirsiniz [RequestLicKey](#requestlickey). Bir nesne üzerinde lisanssız bir makine oluşturmak için çağırmalıdır `CreateInstanceLic`.

##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo

Dolduran bir [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo) sınıf üreteci açıklayan bilgileri yapısıyla lisans özellikleri.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Parametreler

*pLicInfo*<br/>
[out] İşaretçi bir `LICINFO` yapısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`fRuntimeKeyAvail` Bu yapı üyesi, bir lisans anahtarı göz önünde bulundurulduğunda, sınıf üreteci lisanssız bir makinede oluşturulması nesnelere izin verip vermediğini, gösterir. *FLicVerified* üye tam makine lisans var olup olmadığını gösterir.

##  <a name="lockserver"></a>  CComClassFactory2::LockServer

Artırır ve azaltır modülün kilit sayacını çağırarak `_Module::Lock` ve `_Module::Unlock`sırasıyla.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
[in] TRUE ise kilit sayacını artırılır; Aksi takdirde, kilit sayısı azaltılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`_Module` global örneğine başvurur [CComModule](../../atl/reference/ccommodule-class.md) veya ondan türetilmiş bir sınıf.

Çağırma `LockServer` bir istemci birden çok nesne hızla oluşturulabilen bir sınıf üreteci tutacak sağlar.

##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey

Oluşturur ve döndürür, sağlanan bir lisans anahtarı `fRuntimeKeyAvail` üyesi [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo) TRUE yapısıdır.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametreler

*dwReserved*<br/>
[in] Kullanılmıyor. Sıfır olmalıdır.

*pbstrKey*<br/>
[out] Lisans anahtarı için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Arama için bir lisans anahtarı gereklidir [CreateInstanceLic](#createinstancelic) nesne üzerinde lisanssız bir makine oluşturmak için. Varsa `fRuntimeKeyAvail` tam lisanslı bir makinede nesneleri yalnızca oluşturulabilir sonra FALSE ' tır.

Çağrı [GetLicInfo](#getlicinfo) değerini almak için `fRuntimeKeyAvail`.

## <a name="see-also"></a>Ayrıca Bkz.

[CComClassFactoryAutoThread Sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton Sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
