---
title: CComAggObject Sınıfı
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
ms.openlocfilehash: 9f05e83c8d0a1fd68fce3228dea9cfeab6183c96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321168"
---
# <a name="ccomaggobject-class"></a>CComAggObject Sınıfı

Bu sınıf, birleştirilmiş bir nesne için [Bilinmeyen](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimini uygular. Tanım olarak, birleştirilmiş nesne bir dış nesne içinde bulunur. Sınıf `CComAggObject` [CComObject Sınıfına](../../atl/reference/ccomobject-class.md)benzer , ancak dış istemciler tarafından doğrudan erişilebilir bir arabirim ortaya çıkarır.

## <a name="syntax"></a>Sözdizimi

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*Bulunan*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|Oluşturucu.|
|[CComAggObject::~CComAggObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComAggObject::AddRef](#addref)|Toplanan nesneüzerinde başvuru sayısını artırımı.|
|[CComAggObject::CreateInstance](#createinstance)|Bu statik [işlev, CoCreateInstance'ın](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)yükü olmadan yeni bir **CComAggObject<** `contained` **>** nesne oluşturmanıza olanak sağlar.|
|[CComAggObject::FinalConstruct](#finalconstruct)|'nin son `m_contained`başlatılmasını gerçekleştirir.|
|[CComAggObject::FinalRelease](#finalrelease)|Son imha `m_contained`gerçekleştirir .|
|[CComAggObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComAggObject::Sürüm](#release)|Başvuru sayısını toplanan nesneye erteler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComAggNesne::m_contained](#m_contained)|Temsilciler `IUnknown` dış bilinmeyene çağrı da bulunur.|

## <a name="remarks"></a>Açıklamalar

`CComAggObject`toplanan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. `CComAggObject`dış nesnenin `IUnknown` `IUnknown` arabiriminden ayrı kendi arabirimi vardır ve kendi başvuru sayısını korur.

Toplama hakkında daha fazla bilgi için, [ATL COM Nesnelerin](../../atl/fundamentals-of-atl-com-objects.md)makale temelleri bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a>CComAggObject::AddRef

Toplanan nesneüzerinde başvuru sayısını artırımı.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>CComAggObject::CComAggObject

Oluşturucu.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
[içinde] Dış bilinmeyen.

### <a name="remarks"></a>Açıklamalar

Üyeyi, `CComContainedObject` [m_contained](#m_contained)ve modül kilit sayısını aşamalı olarak atar.

Yıkıcı modül kilit sayısını atar.

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a>CComAggObject::~CComAggObject

Yıkıcı.

```
~CComAggObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor, [FinalRelease'i](#finalrelease)çağırır ve modül kilidi sayısını atar.

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a>CComAggObject::CreateInstance

Bu statik [işlev, CoCreateInstance'ın](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)yükü olmadan yeni bir **CComAggObject<** `contained` **>** nesne oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*S*<br/>
[çıkış] **CComAggObject\<** için bir işaretçi işaretçi<em>silik içeriyordu.</em> **>** Başarısız `CreateInstance` olursa, *pp* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfırdır, bu nedenle hemen arayın `AddRef` ve `Release` ardından işi bittiğinde nesne işaretçisi üzerindeki başvuruyu serbest bırakır.

Nesneye doğrudan erişime ihtiyacınız yoksa, ancak yine de ek yükü olmadan `CoCreateInstance`yeni bir nesne oluşturmak istiyorsanız, [CComCoClass kullanın::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>CComAggObject::FinalConstruct

Nesne yapısının son aşamalarında çağrılan bu yöntem, [m_contained](#m_contained) üyesi üzerinde herhangi bir son başlatma gerçekleştirir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>CComAggObject::FinalRelease

Nesne imha sı sırasında çağrılan bu yöntem, [m_contained](#m_contained) üyeyi serbest kılmış.

```
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a>CComAggNesne::m_contained

Sınıfınızdan türetilen [bir CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*Bulunan*<br/>
[içinde] CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

### <a name="remarks"></a>Açıklamalar

Tüm `IUnknown` aramalar `m_contained` dış bilinmeyene devredilir.

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>CComAggObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenen arabirimin tanımlayıcısı.

*ppvNesne*<br/>
[çıkış] *iid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* NULL olarak ayarlanır.

*S*<br/>
[çıkış] Türüne göre tanımlanan arabirim `Q`işaretçisi için bir işaretçi . Nesne bu arabirimi desteklemiyorsa, *pp* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İstenen arabirim `IUnknown` `QueryInterface` ise, bir işaretçiyi toplanan `IUnknown` nesnenin kendi sine döndürür ve başvuru sayısını toplar. Aksi takdirde, bu yöntem `CComContainedObject` üye aracılığıyla arabirim için sorgular, [m_contained.](#m_contained)

## <a name="ccomaggobjectrelease"></a><a name="release"></a>CComAggObject::Sürüm

Başvuru sayısını toplanan nesneye erteler.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, `Release` tanılama veya sınama için yararlı olabilecek bir değer verir. Hata ayıklama yapılarında `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
