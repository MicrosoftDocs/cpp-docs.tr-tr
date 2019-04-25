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
ms.openlocfilehash: 52cdddb1d922ca21e24122422ca14d9c12d13a83
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259930"
---
# <a name="ccomaggobject-class"></a>CComAggObject sınıfı

Bu sınıfın uyguladığı [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) toplanan nesne için arabirim. Tanımı gereği, toplanan nesne bir dış nesne içinde yer alır. `CComAggObject` Sınıfı benzer [CComObject sınıfı](../../atl/reference/ccomobject-class.md)dışında dış istemcilere doğrudan erişilebilen bir arabirim sunar.

## <a name="syntax"></a>Sözdizimi

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*yer alan*<br/>
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer arabirimleri uğradıysa nesnede desteklemek istediğiniz gibi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|Oluşturucu.|
|[CComAggObject:: ~ CComAggObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject::AddRef](#addref)|Toplanan nesne başvuru sayısını artırır.|
|[CComAggObject::CreateInstance](#createinstance)|Bu statik işlev yeni bir oluşturmanıza olanak tanır **CComAggObject <** `contained` **>** yükü olmadan nesne [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComAggObject::FinalConstruct](#finalconstruct)|Öğesinin son başlatılmasını gerçekleştirir `m_contained`.|
|[CComAggObject::FinalRelease](#finalrelease)|Son yok edilmesini gerçekleştirir `m_contained`.|
|[CComAggObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComAggObject::Release](#release)|Toplanmış nesnede başvuru sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|Temsilciler `IUnknown` çağrıları için dış bilinmeyen.|

## <a name="remarks"></a>Açıklamalar

`CComAggObject` uygulayan [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) toplanan nesne için. `CComAggObject` kendi `IUnknown` arabirimi, dış nesne ayrı `IUnknown` arabirim ve kendi başvuru sayısını tutar.

Toplama hakkında daha fazla bilgi için bkz [ATL COM nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComAggObject::AddRef

Toplanan nesne başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject

Oluşturucu.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
[in] Dış bilinmeyen.

### <a name="remarks"></a>Açıklamalar

Başlatır `CComContainedObject` üyesi [m_contained](#m_contained)ve modülün kilit sayacını arttırır.

Modülün kilit sayısını yok Edicisi azaltır.

##  <a name="dtor"></a>  CComAggObject:: ~ CComAggObject

Yıkıcı.

```
~CComAggObject();
```

### <a name="remarks"></a>Açıklamalar

Çağrıları ayrılan tüm kaynakları serbest bırakan [FinalRelease](#finalrelease), ve modül kilit sayısını azaltır.

##  <a name="createinstance"></a>  CComAggObject::CreateInstance

Bu statik işlev yeni bir oluşturmanıza olanak tanır **CComAggObject <** `contained` **>** yükü olmadan nesne [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*PP*<br/>
[out] Bir işaretçi bir **CComAggObject\<**<em>bulunan</em> **>** işaretçi. Varsa `CreateInstance` başarısız, *pp* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesne başvuru sayısı sıfır sahiptir, bu nedenle çağrı `AddRef` hemen sonra kullanın `Release` işiniz bittiğinde, nesne işaretçinin başvurusu boşaltılacak.

Nesneye doğrudan erişim değildir, ancak yükü olmadan yeni bir nesne oluşturmak hala istiyorsanız `CoCreateInstance`, kullanın [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.

##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct

Nesne yapılandırmanın son aşamaları sırasında çağırılır, bu yöntem herhangi bir son başlatılmasını gerçekleştirir [m_contained](#m_contained) üyesi.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="finalrelease"></a>  CComAggObject::FinalRelease

Nesne yok etme sırasında çağrılır, bu yöntemi serbest bırakan [m_contained](#m_contained) üyesi.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComAggObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) , sınıftan türetilmiş bir nesneye.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*yer alan*<br/>
[in] Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer arabirimleri uğradıysa nesnede desteklemek istediğiniz gibi.

### <a name="remarks"></a>Açıklamalar

Tüm `IUnknown` aracılığıyla çağırır `m_contained` için dış bilinmeyen temsilcisi.

##  <a name="queryinterface"></a>  CComAggObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] İstenen arabirim tanımlayıcısı.

*ppvObject*<br/>
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*. Nesne bu arabirimi desteklemiyorsa *ppvObject* NULL olarak ayarlandı.

*PP*<br/>
[out] Türe göre belirlenen arabirim işaretçisi için bir işaretçi `Q`. Nesne bu arabirimi desteklemiyorsa *pp* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

İstenen arabirimi ise `IUnknown`, `QueryInterface` toplanmış nesnenin kendi bir işaretçi döndürür `IUnknown` ve başvuru sayısını artırır. Aksi takdirde, bu yöntem arabirimi aracılığıyla sorgular `CComContainedObject` üyesi [m_contained](#m_contained).

##  <a name="release"></a>  CComAggObject::Release

Toplanmış nesnede başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında `Release` tanılama için kullanışlı veya test olabilecek bir değer döndürür. Hata ayıklama olmayan yapılarında `Release` her zaman 0 değerini döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
