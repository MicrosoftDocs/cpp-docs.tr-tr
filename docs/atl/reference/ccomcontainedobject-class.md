---
description: 'Daha fazla bilgi edinin: Ccomkirinedobject sınıfı'
title: Ccomkirinedobject sınıfı
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
ms.openlocfilehash: 9c0993d5ce71a557b71939f60a7019d3c062bac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152210"
---
# <a name="ccomcontainedobject-class"></a>Ccomkirinedobject sınıfı

Bu sınıf, sahip nesnesine temsilci seçerek [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular `IUnknown` .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)sınıfından türetilmiş sınıfınız.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ccomkirinedobject:: Ccomkirinedobject](#ccomcontainedobject)|Oluşturucu. Üye işaretçisini sahip nesnesine başlatır `IUnknown` .|
|[Ccomkirinedobject:: ~ Ccomkirinedobject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomkirinedobject:: AddRef](#addref)|Sahip nesnesindeki başvuru sayısını artırır.|
|[Ccomkirinedobject:: GetControllingUnknown](#getcontrollingunknown)|Sahip nesnesini alır `IUnknown` .|
|[Ccomkirinedobject:: QueryInterface](#queryinterface)|Sahip nesnesinde istenen arabirime yönelik bir işaretçi alır.|
|[Ccomkirinedobject:: Release](#release)|Sahip nesnesindeki başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

ATL `CComContainedObject` , [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md)ve [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)sınıflarında kullanır. `CComContainedObject` sahip nesnesine temsilci seçerek [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular `IUnknown` . (Sahip, bir toplama 'nın dıştaki nesnesidir ya da bir yırma arabiriminin oluşturulduğu nesne.) `CComContainedObject` , `CComObjectRootEx` ve ' nin `OuterQueryInterface` `OuterAddRef` `OuterRelease` tüm devralınan çağrıları `Base` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComContainedObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a> Ccomkirinedobject:: AddRef

Sahip nesnesindeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a> Ccomkirinedobject:: Ccomkirinedobject

Oluşturucu.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Sahip nesnesi `IUnknown` .

### <a name="remarks"></a>Açıklamalar

`m_pOuterUnknown`Üye işaretçisini (sınıf üzerinden devralınmış `Base` ) *BD* olarak ayarlar.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a> Ccomkirinedobject:: ~ Ccomkirinedobject

Yok edicisi.

```
~CComContainedObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a> Ccomkirinedobject:: GetControllingUnknown

`m_pOuterUnknown`Sahip nesnesini tutan üye işaretçisini ( *taban* sınıfı aracılığıyla devralınmış) döndürür `IUnknown` .

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Sahip nesnesi `IUnknown` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem `Base` , [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) makrosunu bildirmişse sanal olabilir.

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a> Ccomkirinedobject:: QueryInterface

Sahip nesnesinde istenen arabirime yönelik bir işaretçi alır.

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

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a> Ccomkirinedobject:: Release

Sahip nesnesindeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` Tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
