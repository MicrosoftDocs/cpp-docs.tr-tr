---
description: 'Daha fazla bilgi edinin: CComPolyObject sınıfı'
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
ms.openlocfilehash: 1584fd03882b0eb0618bd20b54134317efd17ba8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142408"
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
|[CComPolyObject:: CreateInstance](#createinstance)|Se CoCreateInstance ek yükü olmadan yeni bir **CComPolyObject<** nesnesi oluşturmanıza olanak sağlar `contained` **>** . [](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)|
|[CComPolyObject:: Finalyapısı](#finalconstruct)|Son başlatmayı gerçekleştirir `m_contained` .|
|[CComPolyObject:: FinalRelease](#finalrelease)|Son yok etme işlemini gerçekleştirir `m_contained` .|
|[CComPolyObject:: QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComPolyObject:: Release](#release)|Nesnenin başvuru sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject:: m_contained](#m_contained)|Nesne toplanırsa, nesne `IUnknown` toplanırsa veya nesnesine yapılan çağrıları devreder `IUnknown` .|

## <a name="remarks"></a>Açıklamalar

`CComPolyObject` toplanmış veya toplanmayan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular.

Bir örneği `CComPolyObject` oluşturulduğunda, bilinmeyen dıştaki değeri denetlenir. NULL ise, `IUnknown` toplanmayan bir nesne için uygulanır. Bilinmeyen dış değer NULL değilse, `IUnknown` toplanmış bir nesne için uygulanır.

Kullanmanın avantajı, `CComPolyObject` toplu ve toplu olmayan durumları işlemek için modülünüzün hem [CComAggObject](../../atl/reference/ccomaggobject-class.md) hem de [CComObject](../../atl/reference/ccomobject-class.md) sahip olmasını önlemenize yardımcı olur. Tek bir `CComPolyObject` nesne her iki durumu da işler. Bu, bir vtable 'ın yalnızca bir kopyasının ve modülünüzün bir kopyasının mevcut olduğu anlamına gelir. Vtable 'niz büyükse bu, modül boyutunuzu önemli ölçüde azaltabilir. Ancak, vtable 'niz küçükse,, `CComPolyObject` ve gibi toplanmış veya toplanmayan bir nesne için en iyi duruma getirilmediğinden, kullanmak biraz daha büyük bir modül boyutuna neden olabilir `CComAggObject` `CComObject` .

DECLARE_POLY_AGGREGATABLE makro nesnenizin sınıf tanımında belirtilmişse, `CComPolyObject` nesnenizin oluşturulması için kullanılacaktır. Tam denetim veya Internet Explorer denetimi oluşturmak için ATL Proje Sihirbazı 'nı kullanırsanız DECLARE_POLY_AGGREGATABLE otomatik olarak bildirilecektir.

Toplanmışsa, `CComPolyObject` nesnesi kendi kendine sahiptir `IUnknown` ve dış nesneden ayrı olarak `IUnknown` kendi başvuru sayısını korur. `CComPolyObject` bilinmeyen dış temsilciye temsilci seçmek için [Ccomkirınedobject](../../atl/reference/ccomcontainedobject-class.md) kullanır.

Toplama hakkında daha fazla bilgi için, [atl com nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccompolyobjectaddref"></a><a name="addref"></a> CComPolyObject:: AddRef

Nesnedeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccompolyobjectccompolyobject"></a><a name="ccompolyobject"></a> CComPolyObject:: CComPolyObject

Oluşturucu.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Nesne toplanırsa, dıştaki bilinmeyen bir işaretçi veya nesne toplanmayan nesne yoksa NULL.

### <a name="remarks"></a>Açıklamalar

`CComContainedObject`Veri üyesini başlatır, [m_contained](#m_contained)ve modül kilit sayısını artırır.

Yıkıcı modül kilit sayısını azaltır.

## <a name="ccompolyobjectccompolyobject"></a><a name="dtor"></a> CComPolyObject:: ~ CComPolyObject

Yok edicisi.

```
~CComPolyObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, [sonlandırmayı](#finalrelease)çağırır ve modül kilit sayısını azaltır.

## <a name="ccompolyobjectcreateinstance"></a><a name="createinstance"></a> CComPolyObject:: CreateInstance

CoCreateInstance ek yükü olmadan yeni bir **CComPolyObject<** nesnesi oluşturmanıza olanak sağlar `contained` **>** . [](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
dışı **CComPolyObject<** işaretçisine yönelik bir işaretçi `contained` **>** . `CreateInstance`Başarısız olursa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfır, bu yüzden hemen çağırın, `AddRef` sonra `Release` işlemi bitirdiğinizde nesne İşaretçisinde başvuruyu serbest bırakmak için kullanın.

Nesneye doğrudan erişmeniz gerekmiyorsa ancak ek yükü olmadan yeni bir nesne oluşturmak istiyorsanız, `CoCreateInstance` bunun yerine [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) kullanın.

## <a name="ccompolyobjectfinalconstruct"></a><a name="finalconstruct"></a> CComPolyObject:: Finalyapısı

Nesne oluşumunun son aşamaları sırasında çağırılır, bu yöntem [m_contained](#m_contained) veri üyesinde son başlatmayı gerçekleştirir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccompolyobjectfinalrelease"></a><a name="finalrelease"></a> CComPolyObject:: FinalRelease

Nesne yok etme sırasında çağırılır, bu yöntem [m_contained](#m_contained) veri üyesini serbest bırakır.

```cpp
void FinalRelease();
```

## <a name="ccompolyobjectm_contained"></a><a name="m_contained"></a> CComPolyObject:: m_contained

Sınıfınızdan türetilmiş bir [Ccomkirinedobject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*içindedir*<br/>
'ndaki Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

### <a name="remarks"></a>Açıklamalar

`IUnknown` aracılığıyla yapılan çağrılar, `m_contained` Nesne toplanırsa veya nesne `IUnknown` toplanmadığından bu nesnenin öğesine devredildi.

## <a name="ccompolyobjectqueryinterface"></a><a name="queryinterface"></a> CComPolyObject:: QueryInterface

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
dışı *IID* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

*Sy*<br/>
dışı Tarafından tanımlanan arabirime yönelik bir işaretçi `__uuidof(Q)` .

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Toplanan bir nesne için, istenen arabirim ise, `IUnknown` `QueryInterface` toplanmış nesnenin kendisine bir işaretçi döndürür `IUnknown` ve başvuru sayısını artırır. Aksi takdirde, bu yöntem `CComContainedObject` [m_contained](#m_contained)veri üyesi aracılığıyla arabirimi sorgular.

## <a name="ccompolyobjectrelease"></a><a name="release"></a> CComPolyObject:: Release

Nesnedeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` Tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
