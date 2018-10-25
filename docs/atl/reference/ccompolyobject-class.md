---
title: CComPolyObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78e45db5cf68c4a92fc9e8165ed648760d02e8fb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069457"
---
# <a name="ccompolyobject-class"></a>CComPolyObject sınıfı

Bu sınıfın uyguladığı `IUnknown` toplanmış veya toplanmayan bir nesne için.

## <a name="syntax"></a>Sözdizimi

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*yer alan*<br/>
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer arabirimleri uğradıysa nesnede desteklemek istediğiniz gibi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Oluşturucu.|
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|Nesnenin başvuru sayısını artırır.|
|[CComPolyObject::CreateInstance](#createinstance)|(Statik) Yeni bir oluşturmanıza olanak tanır **CComPolyObject <** `contained` **>** yükü olmadan nesne [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComPolyObject::FinalConstruct](#finalconstruct)|Öğesinin son başlatılmasını gerçekleştirir `m_contained`.|
|[CComPolyObject::FinalRelease](#finalrelease)|Son yok edilmesini gerçekleştirir `m_contained`.|
|[CComPolyObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComPolyObject::Release](#release)|Nesnenin başvuru sayısını azaltır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|Temsilciler `IUnknown` çağrıları için dış bilinmeyen nesne toplanırsa veya için `IUnknown` nesne değil toplanırsa nesne.|

## <a name="remarks"></a>Açıklamalar

`CComPolyObject` uygulayan [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) toplanmış veya toplanmayan bir nesne için.

Örneği `CComPolyObject` oluşturulur, dış değeri bilinmeyen denetlenir. NULL ise `IUnknown` toplanmayan bir nesne için uygulanır. Dış bilinmeyen NULL değilse `IUnknown` toplanan nesne için uygulanır.

Kullanmanın avantajı `CComPolyObject` ikisinin önlemek olan [CComAggObject](../../atl/reference/ccomaggobject-class.md) ve [CComObject](../../atl/reference/ccomobject-class.md) toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesi, her iki durumda işler. Bu işlevler bir kopyasını ve yalnızca bir kopyasını vtable modülünüzde mevcut anlamına gelir. Vtable büyükse, bu, modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesnesi için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.

DECLARE_POLY_AGGREGATABLE makrosu, nesnenin sınıf tanımında belirtilirse `CComPolyObject` nesneyi oluşturmak için kullanılacak. Tam Denetim veya Internet Explorer denetim oluşturmak için ATL projesi Sihirbazı'nı kullanırsanız DECLARE_POLY_AGGREGATABLE otomatik olarak bildirilir.

Toplanan, `CComPolyObject` nenesindeki kendi `IUnknown`dış nesnenin ayrı `IUnknown`ve kendi başvuru sayısını tutar. `CComPolyObject` kullanan [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) temsilci için dış bilinmeyen.

Toplama hakkında daha fazla bilgi için bkz [ATL COM nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComPolyObject::AddRef

Nesnede başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject

Oluşturucu.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
[in] Dış bilinmeyen nesne toplanmasını veya yoksa NULL ise bir işaretçi bir nesne değil toplanırsa nesne.

### <a name="remarks"></a>Açıklamalar

Başlatır `CComContainedObject` veri üyesi [m_contained](#m_contained)ve modülün kilit sayacını arttırır.

Modülün kilit sayısını yok Edicisi azaltır.

##  <a name="dtor"></a>  CComPolyObject:: ~ CComPolyObject

Yıkıcı.

```
~CComPolyObject();
```

### <a name="remarks"></a>Açıklamalar

Çağrıları ayrılan tüm kaynakları serbest bırakan [FinalRelease](#finalrelease), ve modül kilit sayısını azaltır.

##  <a name="createinstance"></a>  CComPolyObject::CreateInstance

Yeni bir oluşturmanıza olanak tanır **CComPolyObject <** `contained` **>** yükü olmadan nesne [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*PP*<br/>
[out] Bir işaretçi bir **CComPolyObject <** `contained` **>** işaretçi. Varsa `CreateInstance` başarısız, *pp* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesne başvuru sayısı sıfır sahiptir, bu nedenle çağrı `AddRef` hemen sonra kullanın `Release` işiniz bittiğinde, nesne işaretçinin başvurusu boşaltılacak.

Doğrudan nesne erişim yoktur, ancak yükü olmadan yeni bir nesne oluşturmak hala istiyorsanız `CoCreateInstance`, kullanın [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.

##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct

Nesne yapılandırmanın son aşamaları sırasında çağırılır, bu yöntem herhangi bir son başlatılmasını gerçekleştirir [m_contained](#m_contained) veri üyesi.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease

Nesne yok etme sırasında çağrılır, bu yöntemi serbest bırakan [m_contained](#m_contained) veri üyesi.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComPolyObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) , sınıftan türetilmiş bir nesneye.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*yer alan*<br/>
[in] Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer arabirimleri uğradıysa nesnede desteklemek istediğiniz gibi.

### <a name="remarks"></a>Açıklamalar

`IUnknown` aracılığıyla çağırır `m_contained` için dış bilinmeyen nesne toplanırsa veya için temsilci `IUnknown` nesne değil toplanırsa, bu nesnenin.

##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*Q*<br/>
COM arabirimi.

*IID*<br/>
[in] İstenen arabirim tanımlayıcısı.

*ppvObject*<br/>
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*. Nesne bu arabirimi desteklemiyorsa *ppvObject* NULL olarak ayarlandı.

*PP*<br/>
[out] Bir işaretçi tarafından tanımlanan arabirimi `__uuidof(Q)`.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

İstenen arabirimi ise toplu bir nesne için `IUnknown`, `QueryInterface` toplanmış nesnenin kendi bir işaretçi döndürür `IUnknown` ve başvuru sayısını artırır. Aksi takdirde, bu yöntem arabirimi aracılığıyla sorgular `CComContainedObject` veri üyesi [m_contained](#m_contained).

##  <a name="release"></a>  CComPolyObject::Release

Nesnede başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında `Release` tanılama için kullanışlı veya test olabilecek bir değer döndürür. Nondebug yapılarında `Release` her zaman 0 değerini döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
