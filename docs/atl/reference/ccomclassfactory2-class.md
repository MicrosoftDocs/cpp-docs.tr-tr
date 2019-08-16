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
ms.openlocfilehash: e34ebffc937c3e4ef1272fdf13ddcde7513d28e4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497467"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 sınıfı

Bu sınıf [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular.

## <a name="syntax"></a>Sözdizimi

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Parametreler

*lisan*<br/>
Aşağıdaki statik işlevleri uygulayan bir sınıf:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComClassFactory2:: CreateInstance](#createinstance)|Belirtilen CLSID 'nin bir nesnesini oluşturur.|
|[CComClassFactory2:: Createınstancelik](#createinstancelic)|Bir lisans anahtarı verildiğinde, belirtilen CLSID 'nin bir nesnesini oluşturur.|
|[CComClassFactory2:: GetLicInfo](#getlicinfo)|Sınıf fabrikasının lisanslama özelliklerini açıklayan bilgileri alır.|
|[CComClassFactory2:: LockServer](#lockserver)|Bellek içinde sınıf fabrikasını kilitler.|
|[CComClassFactory2:: RequestLicKey](#requestlickey)|Bir lisans anahtarı oluşturur ve döndürür.|

## <a name="remarks"></a>Açıklamalar

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)'nin bir uzantısı olan [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) arabirimini uygular. `IClassFactory2`bir lisans aracılığıyla nesne oluşturmayı denetler. Lisanslı bir makinede yürütülen bir sınıf fabrikası, çalışma zamanı lisans anahtarı sağlayabilir. Bu lisans anahtarı, bir tam makine lisansı mevcut olmadığında bir uygulamanın nesneleri örneketmesine olanak tanır.

ATL nesneleri, normal olarak [CComCoClass](../../atl/reference/ccomcoclass-class.md)'tan türeterek bir sınıf fabrikası elde ettiliyor. Bu sınıf, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 'yi varsayılan sınıf fabrikası olarak bildiren [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)makrosunu içerir. Kullanmak `CComClassFactory2`için, nesnenizin sınıf tanımında [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makrosunu belirtin. Örneğin:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, için `CComClassFactory2`şablon parametresi, ve `GetLicenseKey` `IsLicenseValid`statik işlevlerini `VerifyLicenseKey`uygulamalıdır. Aşağıda basit bir lisans sınıfına bir örnek verilmiştir:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2`hem hem de `CComClassFactory2Base` *lisandan*türetilir. `CComClassFactory2Base`, sırasıyla ve `IClassFactory2` `CComObjectRootEx< CComGlobalsThreadModel >`' den türetilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="createinstance"></a>CComClassFactory2:: CreateInstance

Belirtilen CLSID 'nin bir nesnesini oluşturur ve bu nesneye bir arabirim işaretçisi alır.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
'ndaki Nesne bir toplamanın parçası olarak oluşturulduysa, *pUnkOuter* , bilinmeyen dıştaki olmalıdır. Aksi halde, *pUnkOuter* null olmalıdır.

*riıd*<br/>
'ndaki İstenen arabirimin IID 'si. *PUnkOuter* null değilse, *riıd* olmalıdır `IID_IUnknown`.

*ppvObj*<br/>
dışı *Riıd*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObj* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Makinenin tam lisansa sahip olmasını gerektirir. Tam bir makine lisansı yoksa, [Createınstancelik](#createinstancelic)'i çağırın.

##  <a name="createinstancelic"></a>CComClassFactory2:: Createınstancelik

Bir lisans [](#createinstance)anahtarı `CreateInstanceLic` gerektirmesi dışında, CreateInstance 'ya benzer.

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
'ndaki Nesne bir toplamanın parçası olarak oluşturulduysa, *pUnkOuter* , bilinmeyen dıştaki olmalıdır. Aksi halde, *pUnkOuter* null olmalıdır.

*Punkayrýlmýþ*<br/>
'ndaki Kullanılmıyor. NULL olmalıdır.

*riıd*<br/>
'ndaki İstenen arabirimin IID 'si. *PUnkOuter* null değilse, *riıd* olmalıdır `IID_IUnknown`.

*bstrKey*<br/>
'ndaki Daha önce bir çağrıdan `RequestLicKey`elde edilen çalışma zamanı lisans anahtarı. Bu anahtar, nesneyi oluşturmak için gereklidir.

*ppvObject*<br/>
dışı *Riıd*tarafından belirtilen arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

[RequestLicKey](#requestlickey)kullanarak bir lisans anahtarı elde edebilirsiniz. Lisanssız bir makinede bir nesne oluşturmak için, çağrısı `CreateInstanceLic`yapmanız gerekir.

##  <a name="getlicinfo"></a>CComClassFactory2:: GetLicInfo

Bir [Licınfo](/windows/win32/api/ocidl/ns-ocidl-licinfo) yapısını, sınıf fabrikasının lisanslama özelliklerini açıklayan bilgilerle doldurur.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Parametreler

*Plicınfo*<br/>
dışı `LICINFO` Yapı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu `fRuntimeKeyAvail` yapının üyesi, bir lisans anahtarı verildiğinde, sınıf fabrikası 'nin lisanssız bir makinede nesnelerin oluşturulmasına izin verip vermediğini belirtir. *Titreşme* üyesi, bir tam makine lisansının mevcut olup olmadığını gösterir.

##  <a name="lockserver"></a>CComClassFactory2:: LockServer

Sırasıyla ve `_Module::Lock` `_Module::Unlock`çağırarak modül kilit sayısını artırır ve azaltır.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*<br/>
'ndaki TRUE ise kilit sayısı artırılır; Aksi takdirde kilit sayısı azaltılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`_Module`[CComModule](../../atl/reference/ccommodule-class.md) 'un genel örneğine veya ondan türetilmiş bir sınıfa başvurur.

Çağırma `LockServer` , bir istemcinin birden fazla nesnenin hızla oluşturulabilmesi için bir sınıf fabrikasına sahip olmasını sağlar.

##  <a name="requestlickey"></a>CComClassFactory2:: RequestLicKey

`fRuntimeKeyAvail` [Licınfo](/windows/win32/api/ocidl/ns-ocidl-licinfo) yapısının üyesinin true olması şartıyla, bir lisans anahtarı oluşturur ve döndürür.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametreler

*Dwayrýlmýþ*<br/>
'ndaki Kullanılmıyor. Sıfır olmalıdır.

*pbstrKey*<br/>
dışı Lisans anahtarına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Lisanssız bir makinede bir nesne oluşturmak için [Createınstancelik](#createinstancelic) çağırmak üzere bir lisans anahtarı gereklidir. `fRuntimeKeyAvail` Yanlışsa, nesneler yalnızca tam olarak lisanslanmış bir makinede oluşturulabilir.

Değerini`fRuntimeKeyAvail`almak Için [GetLicInfo](#getlicinfo) çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CComClassFactoryAutoThread Sınıfı](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton Sınıfı](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
