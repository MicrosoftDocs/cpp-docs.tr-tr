---
title: CComPolyObject sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: deed29b5fb80ea8bbd06b3d50f45e38740b1619f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497146"
---
# <a name="ccompolyobject-class"></a>CComPolyObject sınıfı

Bu sınıf, `IUnknown` toplanmış veya toplanmayan bir nesne için uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*içindedir*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject:: CComPolyObject](#ccompolyobject)|Oluşturucu.|
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject:: AddRef](#addref)|Nesnenin başvuru sayısını artırır.|
|[CComPolyObject:: CreateInstance](#createinstance)|Se [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)ek yükü olmadan yeni bir **CComPolyObject <** `contained` **>** nesnesi oluşturmanıza olanak sağlar.|
|[CComPolyObject:: Finalyapısı](#finalconstruct)|Son başlatmayı `m_contained`gerçekleştirir.|
|[CComPolyObject:: FinalRelease](#finalrelease)|Son yok etme `m_contained`işlemini gerçekleştirir.|
|[CComPolyObject:: QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComPolyObject:: Release](#release)|Nesnenin başvuru sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject:: m_contained](#m_contained)|Nesne `IUnknown` toplanırsa, nesne toplanırsa veya `IUnknown` nesnesine yapılan çağrıları devreder.|

## <a name="remarks"></a>Açıklamalar

`CComPolyObject`toplanmış veya toplanmayan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular.

Bir örneği `CComPolyObject` oluşturulduğunda, bilinmeyen dıştaki değeri denetlenir. NULL ise, `IUnknown` toplanmayan bir nesne için uygulanır. Bilinmeyen dış değer null değilse, `IUnknown` toplanmış bir nesne için uygulanır.

Kullanmanın `CComPolyObject` avantajı, toplu ve toplu olmayan durumları işlemek için modülünüzün hem [CComAggObject](../../atl/reference/ccomaggobject-class.md) hem de [CComObject](../../atl/reference/ccomobject-class.md) sahip olmasını önlemenize yardımcı olur. Tek `CComPolyObject` bir nesne her iki durumu da işler. Bu, bir vtable 'ın yalnızca bir kopyasının ve modülünüzün bir kopyasının mevcut olduğu anlamına gelir. Vtable 'niz büyükse bu, modül boyutunuzu önemli ölçüde azaltabilir. Ancak, vtable 'niz küçükse,, `CComPolyObject` `CComAggObject` ve `CComObject`gibi toplanmış veya toplanmayan bir nesne için en iyi duruma getirilmediğinden, kullanmak biraz daha büyük bir modül boyutuna neden olabilir.

DECLARE_POLY_AGGREGATABLE makrosu, nesnenizin sınıf tanımında belirtilmişse, `CComPolyObject` nesnenizin oluşturulması için kullanılacaktır. Tam denetim veya Internet Explorer denetimi oluşturmak için ATL Proje Sihirbazı 'nı kullanırsanız DECLARE_POLY_AGGREGATABLE otomatik olarak bildirilecektir.

Toplanmışsa `CComPolyObject` , nesnesi kendi kendine `IUnknown`sahiptir ve dış nesneden `IUnknown`ayrı olarak kendi başvuru sayısını korur. `CComPolyObject`bilinmeyen dış temsilciye temsilci seçmek için [Ccomkirınedobject](../../atl/reference/ccomcontainedobject-class.md) kullanır.

Toplama hakkında daha fazla bilgi için, [atl com nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>CComPolyObject:: AddRef

Nesnedeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

##  <a name="ccompolyobject"></a>CComPolyObject:: CComPolyObject

Oluşturucu.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Nesne toplanırsa, dıştaki bilinmeyen bir işaretçi veya nesne toplanmayan nesne yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Veri üyesini başlatır, m_contained ve modül kilit sayısını artırır. [](#m_contained) `CComContainedObject`

Yıkıcı modül kilit sayısını azaltır.

##  <a name="dtor"></a>CComPolyObject:: ~ CComPolyObject

Yok edicisi.

```
~CComPolyObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, [sonlandırmayı](#finalrelease)çağırır ve modül kilit sayısını azaltır.

##  <a name="createinstance"></a>CComPolyObject:: CreateInstance

[Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)ek yükü olmadan yeni bir **CComPolyObject <** `contained` **>** nesnesi oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
dışı **CComPolyObject <** `contained` **>** işaretçisine yönelik bir işaretçi. Başarısız `CreateInstance` olursa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfır, bu yüzden hemen çağırın `AddRef` , sonra işlemi bitirdiğinizde nesne İşaretçisinde başvuruyu serbest bırakmak için kullanın. `Release`

Nesneye doğrudan erişmeniz gerekmiyorsa ancak ek yükü `CoCreateInstance`olmadan yeni bir nesne oluşturmak istiyorsanız, bunun yerine [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) kullanın.

##  <a name="finalconstruct"></a>CComPolyObject:: Finalyapısı

Nesne oluşumunun son aşamaları sırasında çağırılır, bu yöntem [m_contained](#m_contained) veri üyesinde son başlatmayı gerçekleştirir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="finalrelease"></a>CComPolyObject:: FinalRelease

Nesne yok etme sırasında çağırılır, bu yöntem [m_contained](#m_contained) veri üyesini serbest bırakır.

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComPolyObject:: m_contained

Sınıfınızdan türetilmiş bir [Ccomkirinedobject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*içindedir*<br/>
'ndaki Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

### <a name="remarks"></a>Açıklamalar

`IUnknown`aracılığıyla `m_contained` yapılan çağrılar, nesne toplanırsa veya nesne toplanmadığından bu nesnenin `IUnknown` öğesine devredildi.

##  <a name="queryinterface"></a>CComPolyObject:: QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*Ç*<br/>
COM arabirimi.

*'si*<br/>
'ndaki İstenen arabirimin tanımlayıcısı.

*ppvObject*<br/>
dışı *IID*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

*Sy*<br/>
dışı Tarafından `__uuidof(Q)`tanımlanan arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Toplanan bir nesne için, istenen arabirim ise `IUnknown` `QueryInterface` , toplanmış nesnenin kendisine `IUnknown` bir işaretçi döndürür ve başvuru sayısını artırır. Aksi takdirde, bu yöntem `CComContainedObject` [m_contained](#m_contained)veri üyesi aracılığıyla arabirimi sorgular.

##  <a name="release"></a>CComPolyObject:: Release

Nesnedeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
