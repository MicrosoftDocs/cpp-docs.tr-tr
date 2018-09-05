---
title: CComContainedObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42aea64c0a6881dcc3ca9a3465a436b33f19ad6d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761633"
---
# <a name="ccomcontainedobject-class"></a>CComContainedObject sınıfı

Bu sınıfın uyguladığı [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) sahibi nesnenin temsilci tarafından `IUnknown`.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>  
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*  
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Oluşturucu. Üye işaretçisi sahibi nesnenin başlatır `IUnknown`.|
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComContainedObject::AddRef](#addref)|Sahip nesne başvuru sayısını artırır.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Sahip nesne alır `IUnknown`.|
|[CComContainedObject::QueryInterface](#queryinterface)|Sahip nesne üzerinde istenen arabirim işaretçisi alır.|
|[CComContainedObject::Release](#release)|Sahibi nesnede başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

ATL kullanan `CComContainedObject` sınıflardaki [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), ve [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject` uygulayan [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) sahibi nesnenin temsilci tarafından `IUnknown`. (Dış nesne bir toplama veya bölünmüş arabirim oluşturulduğu nesnenin sahibi değil.) `CComContainedObject` çağrıları `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`, ve `OuterRelease`, üzerinden devralınan tüm `Base`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComContainedObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComContainedObject::AddRef

Sahip nesne başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

##  <a name="ccomcontainedobject"></a>  CComContainedObject::CComContainedObject

Oluşturucu.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*  
[in] Sahibi nesnenin `IUnknown`.

### <a name="remarks"></a>Açıklamalar

Kümeleri `m_pOuterUnknown` üye işaretçisi (devralınan `Base` sınıfı) için *pv*.

##  <a name="dtor"></a>  CComContainedObject:: ~ CComContainedObject

Yıkıcı.

```
~CComContainedObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown

Döndürür `m_pOuterUnknown` üye işaretçisi (devralınan *temel* sınıfı) nesnenin sahibi tutan `IUnknown`.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Sahibi nesnenin `IUnknown`.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sanal varsa `Base` gözükeceğini [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) makrosu.

##  <a name="queryinterface"></a>  CComContainedObject::QueryInterface

Sahip nesne üzerinde istenen arabirim işaretçisi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametreler

*IID*  
[in] İstenen arabirim tanımlayıcısı.

*ppvObject*  
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*. Nesne bu arabirimi desteklemiyorsa *ppvObject* NULL olarak ayarlandı.

*PP*  
[out] Türe göre belirlenen arabirim işaretçisi için bir işaretçi `Q`. Nesne bu arabirimi desteklemiyorsa *pp* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="release"></a>  CComContainedObject::Release

Sahibi nesnede başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında `Release` tanılama için kullanışlı veya test olabilecek bir değer döndürür. Hata ayıklama olmayan yapılarında `Release` her zaman 0 değerini döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
