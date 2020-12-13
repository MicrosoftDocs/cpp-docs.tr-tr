---
description: 'Daha fazla bilgi edinin: CComAggObject sınıfı'
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
ms.openlocfilehash: 84af79678221ae74a151a4821039ff1d7a743cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152366"
---
# <a name="ccomaggobject-class"></a>CComAggObject sınıfı

Bu sınıf, toplanmış bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimini uygular. Tanım olarak, toplanmış bir nesne bir dış nesne içinde yer alır. `CComAggObject`Sınıfı, [CComObject sınıfına](../../atl/reference/ccomobject-class.md)benzerdir, ancak dış istemciler için doğrudan erişilebilen bir arabirim sunar.

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
|[CComAggObject:: CreateInstance](#createinstance)|Bu statik işlev  `contained` **>** , [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)ek yükü olmadan yeni bir CComAggObject<nesnesi oluşturmanıza olanak sağlar.|
|[CComAggObject:: Finalyapısı](#finalconstruct)|Son başlatmayı gerçekleştirir `m_contained` .|
|[CComAggObject:: FinalRelease](#finalrelease)|Son yok etme işlemini gerçekleştirir `m_contained` .|
|[CComAggObject:: QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComAggObject:: yayın](#release)|Toplanmış nesne üzerindeki başvuru sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComAggObject:: m_contained](#m_contained)|`IUnknown`Bilinmeyen dıştaki çağrıları devreder.|

## <a name="remarks"></a>Açıklamalar

`CComAggObject` toplanan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. `CComAggObject` , kendi `IUnknown` arabirimine sahiptir ve dış nesnenin `IUnknown` arabiriminden ayrılır ve kendi başvuru sayısını korur.

Toplama hakkında daha fazla bilgi için, [atl com nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a> CComAggObject:: AddRef

Toplanmış nesne üzerindeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a> CComAggObject:: CComAggObject

Oluşturucu.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Dış bilinmiyor.

### <a name="remarks"></a>Açıklamalar

Üyeyi başlatır `CComContainedObject` , [m_contained](#m_contained)ve modül kilit sayısını artırır.

Yıkıcı modül kilit sayısını azaltır.

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a> CComAggObject:: ~ CComAggObject

Yok edicisi.

```
~CComAggObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, [sonlandırmayı](#finalrelease)çağırır ve modül kilit sayısını azaltır.

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a> CComAggObject:: CreateInstance

Bu statik işlev  `contained` **>** , [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)ek yükü olmadan yeni bir CComAggObject<nesnesi oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
dışı **CComAggObject \<**<em> </em>** işaretçisi> * * işaretçisi içeriyordu. `CreateInstance`Başarısız olursa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfır, bu yüzden hemen çağırın, `AddRef` sonra `Release` işlemi bitirdiğinizde nesne İşaretçisinde başvuruyu serbest bırakmak için kullanın.

Nesneye doğrudan erişmeniz gerekmiyorsa ancak ek yükü olmadan yeni bir nesne oluşturmak istiyorsanız, `CoCreateInstance` bunun yerine [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) kullanın.

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a> CComAggObject:: Finalyapısı

Nesne oluşumunun son aşamaları sırasında çağırılır, bu yöntem [m_contained](#m_contained) üyesinde son başlatmayı gerçekleştirir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a> CComAggObject:: FinalRelease

Nesne yok etme sırasında çağırılır, bu yöntem [m_contained](#m_contained) üyesini serbest bırakır.

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a> CComAggObject:: m_contained

Sınıfınızdan türetilmiş bir [Ccomkirinedobject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*içindedir*<br/>
'ndaki Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

### <a name="remarks"></a>Açıklamalar

`IUnknown`Aracılığıyla yapılan tüm çağrılar `m_contained` , bilinmeyen dış için temsilci olarak atanır.

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a> CComAggObject:: QueryInterface

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
dışı *IID* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

*Sy*<br/>
dışı Tür tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi `Q` . Nesne bu arabirimi desteklemiyorsa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İstenen arabirim ise, `IUnknown` `QueryInterface` toplanmış nesnenin kendisine bir işaretçi döndürür `IUnknown` ve başvuru sayısını artırır. Aksi takdirde, bu yöntem m_contained üye aracılığıyla arayüzü sorgular `CComContainedObject` . [](#m_contained)

## <a name="ccomaggobjectrelease"></a><a name="release"></a> CComAggObject:: yayın

Toplanmış nesne üzerindeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` Tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObject sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
