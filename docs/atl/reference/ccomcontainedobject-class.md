---
title: CcomcontainedObject Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 72ba27c3be6576621995ffb8c98995c6abc9324c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320791"
---
# <a name="ccomcontainedobject-class"></a>CcomcontainedObject Sınıfı

Bu sınıf [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) sahibi nesnenin `IUnknown`.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
CComObjectRoot veya [CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md) türetilen sınıf, . [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomcontainedObject::ccomcontainedobject](#ccomcontainedobject)|Oluşturucu. Üye işaretçiyi sahibi `IUnknown`nesnenin.|
|[CcomcontainedObject::~ccomcontainedobject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomcontainedObject::addref](#addref)|Başvuru sayısı sahibi nesnesi üzerinde artışlar.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Sahibi nesnenin . `IUnknown`|
|[CcomcontainedObject::QueryInterface](#queryinterface)|Sahibi nesneüzerinde istenen arabirim için bir işaretçi alır.|
|[CcomcontainedObject::Sürüm](#release)|Başvuru sayısını sahibi nesnesi üzerinde erteler.|

## <a name="remarks"></a>Açıklamalar

ATL `CComContainedObject` sınıflarda [cComAggObject](../../atl/reference/ccomaggobject-class.md)kullanır , [CComPolyObject](../../atl/reference/ccompolyobject-class.md), ve [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`sahibi [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) nesnenin `IUnknown`. (Sahibi ya bir toplama dış nesne, ya da bir yırtılma arabirimi oluşturulan nesnedir.) `CComContainedObject` `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`ve `OuterRelease`, tüm `Base`üzerinden devralınan çağırır .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComContainedObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a>CcomcontainedObject::addref

Başvuru sayısı sahibi nesnesi üzerinde artışlar.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>CcomcontainedObject::ccomcontainedobject

Oluşturucu.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
[içinde] Sahibi nesnenin `IUnknown`.

### <a name="remarks"></a>Açıklamalar

Üye `m_pOuterUnknown` işaretçiyi `Base` (sınıf boyunca devralınan) *pv'ye*ayarlar.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>CcomcontainedObject::~ccomcontainedobject

Yıkıcı.

```
~CComContainedObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown

Üye `m_pOuterUnknown` işaretçiyi *(Temel* sınıf üzerinden devralınan) sahibi `IUnknown`nesnenin .

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Sahibi nesnenin `IUnknown`.

### <a name="remarks"></a>Açıklamalar

`Base` [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) makrosu bildirmişse, bu yöntem sanal olabilir.

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>CcomcontainedObject::QueryInterface

Sahibi nesneüzerinde istenen arabirim için bir işaretçi alır.

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

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a>CcomcontainedObject::Sürüm

Başvuru sayısını sahibi nesnesi üzerinde erteler.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, `Release` tanılama veya sınama için yararlı olabilecek bir değer verir. Hata ayıklama yapılarında `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
