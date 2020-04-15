---
title: CComClassFactory2 Sınıfı
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
ms.openlocfilehash: 0cb2064cfaea6317c4522ff917f3963fca2219b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321011"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 Sınıfı

Bu sınıf [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular.

## <a name="syntax"></a>Sözdizimi

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Parametreler

*Lisans*<br/>
Aşağıdaki statik işlevleri uygulayan bir sınıf:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomclassFactory2::CreateInstance](#createinstance)|Belirtilen CLSID bir nesne oluşturur.|
|[CcomclassFactory2::CreateInstancelic](#createinstancelic)|Lisans anahtarı verildiğinde, belirtilen CLSID bir nesne oluşturur.|
|[CcomclassFactory2::Getlicinfo](#getlicinfo)|Sınıf fabrikasının lisanslama özelliklerini açıklayan bilgileri alır.|
|[CcomclassFactory2::LockServer](#lockserver)|Sınıf fabrikasını hafızaya kilitler.|
|[CcomclassFactory2::RequestlicKey](#requestlickey)|Bir lisans anahtarı oluşturur ve döndürür.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)bir uzantısıdır [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arayüzü, uygular. `IClassFactory2`bir lisans aracılığıyla nesne oluşturmayı denetler. Lisanslı bir makinede çalışan bir sınıf fabrikası, çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı, tam makine lisansı olmadığında bir uygulamanın nesneleri anında ani olarak anlamasına olanak tanır.

ATL nesneleri normalde [CComCoClass'tan](../../atl/reference/ccomcoclass-class.md)türeerek bir sınıf fabrikası satın ala.rıöleri. Bu sınıf, [CComClassFactory'yi](../../atl/reference/ccomclassfactory-class.md) varsayılan sınıf fabrikası olarak bildiren makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)içerir. Kullanmak `CComClassFactory2`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makro belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, şablon `CComClassFactory2`parametresi için , `VerifyLicenseKey`statik `GetLicenseKey`işlevleri `IsLicenseValid`uygulamak gerekir , ve . Aşağıdaki basit bir lisans sınıfı örneğidir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2`hem de `CComClassFactory2Base` *lisans*türetilmiştir. `CComClassFactory2Base`, sırayla, `IClassFactory2` türetilmiştir `CComObjectRootEx< CComGlobalsThreadModel >`ve .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`license`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomclassfactory2createinstance"></a><a name="createinstance"></a>CcomclassFactory2::CreateInstance

Belirtilen CLSID bir nesne oluşturur ve bu nesneye bir arabirim işaretçisi alır.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
[içinde] Nesne bir agreganın parçası olarak oluşturuluyorsa, *pUnkOuter* dış bilinmeyen olmalıdır. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*Riid*<br/>
[içinde] İstenen arabirimin IID'si. *pUnkOuter* non-NULL ise, *riid* olmalıdır. `IID_IUnknown`

*ppvObj*<br/>
[çıkış] *riid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Makinenin tam lisanslı olmasını gerektirir. Tam makine lisansı yoksa [CreateInstanceLic'i](#createinstancelic)arayın.

## <a name="ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>CcomclassFactory2::CreateInstancelic

[CreateInstance'a](#createinstance)benzer `CreateInstanceLic` , lisans anahtarı gerektirmesi dışında.

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
[içinde] Nesne bir agreganın parçası olarak oluşturuluyorsa, *pUnkOuter* dış bilinmeyen olmalıdır. Aksi takdirde, *pUnkOuter* NULL olmalıdır.

*pUnkReserved*<br/>
[içinde] Kullanılmaz. NULL olmalı.

*Riid*<br/>
[içinde] İstenen arabirimin IID'si. *pUnkOuter* non-NULL ise, *riid* olmalıdır. `IID_IUnknown`

*bstrKey*<br/>
[içinde] Daha önce bir aramadan elde edilen `RequestLicKey`çalışma zamanı lisans anahtarı. Bu anahtar nesneyi oluşturmak için gereklidir.

*ppvNesne*<br/>
[çıkış] *riid*tarafından belirtilen arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

[RequestLicKey'i](#requestlickey)kullanarak lisans anahtarı alabilirsiniz. Lisanssız bir makinede nesne oluşturmak için `CreateInstanceLic`.

## <a name="ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>CcomclassFactory2::Getlicinfo

[BIR LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) yapısını sınıf fabrikasının lisanslama yeteneklerini açıklayan bilgilerle doldurur.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Parametreler

*pLicInfo*<br/>
[çıkış] Bir `LICINFO` yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu `fRuntimeKeyAvail` yapının üyesi, bir lisans anahtarı verildiğinde, sınıf fabrikasının nesnelerin lisanssız bir makinede oluşturulmasına izin verip vermediğini gösterir. *fLicVerified* üyesi tam makine lisansının var olup olmadığını gösterir.

## <a name="ccomclassfactory2lockserver"></a><a name="lockserver"></a>CcomclassFactory2::LockServer

Modül kilidi sayısısırasıyla arayarak `_Module::Lock` ve sırasıyla `_Module::Unlock`artışlar ve kararnameler.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*Sürü*<br/>
[içinde] DOĞRUysa, kilit sayısı artımlı; aksi takdirde, kilit sayısı bozulür.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`_Module`[CComModule'in](../../atl/reference/ccommodule-class.md) veya ondan türetilen bir sınıfın genel örneğini ifade eder.

Arama, `LockServer` istemcinin bir sınıf fabrikasını tutmasına izin verir, böylece birden çok nesne hızla oluşturulabilir.

## <a name="ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>CcomclassFactory2::RequestlicKey

`fRuntimeKeyAvail` [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) yapısının üyesinin DOĞRU olması koşuluyla bir lisans anahtarı oluşturur ve döndürür.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametreler

*dwAyrılmış*<br/>
[içinde] Kullanılmaz. Sıfır olmalı.

*pbstrKey*<br/>
[çıkış] Lisans anahtarıiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Lisanssız bir makinede nesne oluşturmak için [CreateInstanceLic'i](#createinstancelic) aramak için lisans anahtarı gereklidir. FALSE `fRuntimeKeyAvail` ise, nesneler yalnızca tam lisanslı bir makinede oluşturulabilir.

Değerini almak için [GetLicInfo'yu](#getlicinfo) `fRuntimeKeyAvail`arayın.

## <a name="see-also"></a>Ayrıca bkz.

[CComClassFactoryAutoThread Sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton Sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Ccomglobalsthreadmodel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
