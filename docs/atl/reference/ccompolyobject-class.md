---
title: CComPolyObject Sınıfı
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
ms.openlocfilehash: c880d170a03196d0e15ea8741c786e560d90ddc4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747775"
---
# <a name="ccompolyobject-class"></a>CComPolyObject Sınıfı

Bu sınıf, `IUnknown` birleştirilmiş veya birleştirilmiş olmayan bir nesne için uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*Bulunan*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Ccompolyobject::ccompolyobject](#ccompolyobject)|Oluşturucu.|
|[Ccompolyobject::~ccompolyobject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Ccompolyobject::addref](#addref)|Nesnenin başvuru sayısını artırımına eder.|
|[Ccompolyobject::CreateInstance](#createinstance)|(Statik) [CoCreateInstance'ın](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)yükü olmadan yeni bir **CComPolyObject<** `contained` **>** nesne oluşturmanıza olanak sağlar.|
|[Ccompolyobject::finalconstruct](#finalconstruct)|'nin son `m_contained`başlatılmasını gerçekleştirir.|
|[Ccompolyobject::finalrelease](#finalrelease)|Son imha `m_contained`gerçekleştirir .|
|[CcompolyObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[Ccompolyobject::Sürüm](#release)|Nesnenin başvuru sayısını eriter.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|Nesne `IUnknown` toplanmışsa dış bilinmeyene veya `IUnknown` nesne toplanmış değilse temsilciler dış bilinmeyene çağrıda bulunur.|

## <a name="remarks"></a>Açıklamalar

`CComPolyObject`birleştirilmiş veya birleştirilmiş olmayan nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular.

Bir örnek `CComPolyObject` oluşturulduğunda, dış bilinmeyenin değeri denetlenir. NULL ise, `IUnknown` birbirlmeyen bir nesne için uygulanır. Dış bilinmeyen NULL değilse, `IUnknown` birleştirilmiş bir nesne için uygulanır.

Kullanmanın `CComPolyObject` avantajı, birleştirilmiş ve birbirlemeyen servis taleplerini işlemek için modülünüzde hem [CComAggObject](../../atl/reference/ccomaggobject-class.md) hem de [CComObject](../../atl/reference/ccomobject-class.md) olmasını önlemenizdir. Tek `CComPolyObject` bir nesne her iki durumda da işler. Bu, modülünüzde vtable'ın yalnızca bir kopyası ve işlevlerin bir kopyası olduğu anlamına gelir. Vtable'ınız büyükse, bu durum modül boyutunu önemli ölçüde azaltabilir. Ancak, vtable'ınız küçükse, `CComPolyObject` toplanmış veya birleştirilmiş olmayan bir nesne için optimize `CComAggObject` edilmedikve `CComObject`.

Nesnenizin sınıf tanımında DECLARE_POLY_AGGREGATABLE makro belirtilirse, `CComPolyObject` nesnenizi oluşturmak için kullanılır. Tam denetim veya Internet Explorer denetimi oluşturmak için ATL Project Sihirbazı'nı kullanırsanız DECLARE_POLY_AGGREGATABLE otomatik olarak bildirilir.

Toplanırsa, `CComPolyObject` nesnenin dış `IUnknown`nesneninkinden `IUnknown`ayrı kendi nesnesi vardır ve kendi başvuru sayısını korur. `CComPolyObject`dış bilinmeyene temsilci vermek için [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) kullanır.

Toplama hakkında daha fazla bilgi için, [ATL COM Nesnelerin](../../atl/fundamentals-of-atl-com-objects.md)makale temelleri bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccompolyobjectaddref"></a><a name="addref"></a>Ccompolyobject::addref

Nesne üzerinde başvuru sayısını artırımı.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccompolyobjectccompolyobject"></a><a name="ccompolyobject"></a>Ccompolyobject::ccompolyobject

Oluşturucu.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
[içinde] Nesne toplanacaksa dış bilinmeyene işaretçi veya nesne toplanmış değilse nesne NULL.

### <a name="remarks"></a>Açıklamalar

Veri üyesini, `CComContainedObject` [m_contained](#m_contained)ve modül kilit sayısını aşamalı olarak atar.

Yıkıcı modül kilit sayısını atar.

## <a name="ccompolyobjectccompolyobject"></a><a name="dtor"></a>Ccompolyobject::~ccompolyobject

Yıkıcı.

```
~CComPolyObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor, [FinalRelease'i](#finalrelease)çağırır ve modül kilidi sayısını atar.

## <a name="ccompolyobjectcreateinstance"></a><a name="createinstance"></a>Ccompolyobject::CreateInstance

[CoCreateInstance'ın](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)yükü olmadan yeni bir **CComPolyObject<** `contained` **>** nesne oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Parametreler

*S*<br/>
[çıkış] **CComPolyObject<** `contained` **>** işaretçisine işaretçi. Başarısız `CreateInstance` olursa, *pp* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfırdır, bu nedenle hemen arayın `AddRef` ve `Release` ardından işi bittiğinde nesne işaretçisi üzerindeki başvuruyu serbest bırakır.

Nesneye doğrudan erişime ihtiyacınız yoksa, ancak yine de ek yükü olmadan `CoCreateInstance`yeni bir nesne oluşturmak istiyorsanız, [CComCoClass kullanın::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.

## <a name="ccompolyobjectfinalconstruct"></a><a name="finalconstruct"></a>Ccompolyobject::finalconstruct

Nesne yapısının son aşamalarında çağrılan bu yöntem, [m_contained](#m_contained) veri üyesi üzerinde herhangi bir son başlatma gerçekleştirir.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccompolyobjectfinalrelease"></a><a name="finalrelease"></a>Ccompolyobject::finalrelease

Nesne imha sırasında çağrılan bu yöntem, [m_contained](#m_contained) veri üyesini serbest kılmış.

```cpp
void FinalRelease();
```

## <a name="ccompolyobjectm_contained"></a><a name="m_contained"></a>CComPolyObject::m_contained

Sınıfınızdan türetilen [bir CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*Bulunan*<br/>
[içinde] CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

### <a name="remarks"></a>Açıklamalar

`IUnknown``m_contained` üzerinden aramalar nesne toplanırsa dış bilinmeyene veya nesne `IUnknown` toplanmış değilse bu nesnenin bu nesnenin dikinene devredilir.

## <a name="ccompolyobjectqueryinterface"></a><a name="queryinterface"></a>CcompolyObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*S*<br/>
COM arabirimi.

*ııd*<br/>
[içinde] İstenen arabirimin tanımlayıcısı.

*ppvNesne*<br/>
[çıkış] *iid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* NULL olarak ayarlanır.

*S*<br/>
[çıkış] `__uuidof(Q)`Tarafından tanımlanan arabirimin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Toplanan bir nesne için, istenen `IUnknown`arabirim `QueryInterface` ise, bir işaretçiyi bir `IUnknown` araya gelen nesnenin kendi işaretçisine döndürür ve başvuru sayısını toplar. Aksi takdirde, bu yöntem `CComContainedObject` veri üyesi aracılığıyla arabirim için sorgular, [m_contained.](#m_contained)

## <a name="ccompolyobjectrelease"></a><a name="release"></a>Ccompolyobject::Sürüm

Başvuru sayısını nesneye ayarı eder.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, `Release` tanılama veya sınama için yararlı olabilecek bir değer verir. Nondebug oluşturur, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
