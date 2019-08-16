---
title: CComAggObject sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 8b05284104f9d2e5e7704bceaee6f8adf9a33aac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497652"
---
# <a name="ccomaggobject-class"></a>CComAggObject sınıfı

Bu sınıf, toplanmış bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimini uygular. Tanım olarak, toplanmış bir nesne bir dış nesne içinde yer alır. Sınıfı, CComObject sınıfına benzerdir, ancak dış istemciler için doğrudan erişilebilen bir arabirim sunar. [](../../atl/reference/ccomobject-class.md) `CComAggObject`

## <a name="syntax"></a>Sözdizimi

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*içindedir*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject:: CComAggObject](#ccomaggobject)|Oluşturucu.|
|[CComAggObject:: ~ CComAggObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject:: AddRef](#addref)|Toplanmış nesne üzerindeki başvuru sayısını artırır.|
|[CComAggObject:: CreateInstance](#createinstance)|Bu statik işlev, [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)ek yükü olmadan yeni bir **CComAggObject <** `contained` **>** nesnesi oluşturmanıza olanak sağlar.|
|[CComAggObject:: Finalyapısı](#finalconstruct)|Son başlatmayı `m_contained`gerçekleştirir.|
|[CComAggObject:: FinalRelease](#finalrelease)|Son yok etme `m_contained`işlemini gerçekleştirir.|
|[CComAggObject:: QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComAggObject:: yayın](#release)|Toplanmış nesne üzerindeki başvuru sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject:: m_contained](#m_contained)|Bilinmeyen `IUnknown` dıştaki çağrıları devreder.|

## <a name="remarks"></a>Açıklamalar

`CComAggObject`toplanan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. `CComAggObject`, kendi `IUnknown` arabirimine sahiptir ve dış `IUnknown` nesnenin arabiriminden ayrılır ve kendi başvuru sayısını korur.

Toplama hakkında daha fazla bilgi için, [atl com nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>CComAggObject:: AddRef

Toplanmış nesne üzerindeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

##  <a name="ccomaggobject"></a>CComAggObject:: CComAggObject

Oluşturucu.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Dış bilinmiyor.

### <a name="remarks"></a>Açıklamalar

Üyeyi başlatır, m_contained ve modül kilit sayısını artırır. [](#m_contained) `CComContainedObject`

Yıkıcı modül kilit sayısını azaltır.

##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject

Yok edicisi.

```
~CComAggObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, [sonlandırmayı](#finalrelease)çağırır ve modül kilit sayısını azaltır.

##  <a name="createinstance"></a>CComAggObject:: CreateInstance

Bu statik işlev, [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)ek yükü olmadan yeni bir **CComAggObject <** `contained` **>** nesnesi oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
dışı **\<CComAggObject**işaretçisinin<em>bulunduğu</em> **>** işaretçi. Başarısız `CreateInstance` olursa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfır, bu yüzden hemen çağırın `AddRef` , sonra işlemi bitirdiğinizde nesne İşaretçisinde başvuruyu serbest bırakmak için kullanın. `Release`

Nesneye doğrudan erişmeniz gerekmiyorsa ancak ek yükü `CoCreateInstance`olmadan yeni bir nesne oluşturmak istiyorsanız, bunun yerine [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) kullanın.

##  <a name="finalconstruct"></a>CComAggObject:: Finalyapısı

Nesne oluşumunun son aşamaları sırasında çağırılır, bu yöntem [m_contained](#m_contained) üyesinde son başlatmayı gerçekleştirir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="finalrelease"></a>CComAggObject:: FinalRelease

Nesne yok etme sırasında çağırılır, bu yöntem [m_contained](#m_contained) üyesini serbest bırakır.

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComAggObject:: m_contained

Sınıfınızdan türetilmiş bir [Ccomkirinedobject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*içindedir*<br/>
'ndaki Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

### <a name="remarks"></a>Açıklamalar

`IUnknown` Aracılığıyla`m_contained` yapılan tüm çağrılar, bilinmeyen dış için temsilci olarak atanır.

##  <a name="queryinterface"></a>CComAggObject:: QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin tanımlayıcısı.

*ppvObject*<br/>
dışı *IID*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

*Sy*<br/>
dışı Tür `Q`tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İstenen arabirim ise `IUnknown` `QueryInterface` , toplanmış nesnenin kendisine `IUnknown` bir işaretçi döndürür ve başvuru sayısını artırır. Aksi takdirde, bu yöntem, `CComContainedObject` [m_contained](#m_contained)üye aracılığıyla arabirimi sorgular.

##  <a name="release"></a>CComAggObject:: yayın

Toplanmış nesne üzerindeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
