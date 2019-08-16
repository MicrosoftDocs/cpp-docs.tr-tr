---
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
ms.openlocfilehash: c5e2fa64cc0938e632a37eac7dd1d6e9111c3d98
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497314"
---
# <a name="ccomcontainedobject-class"></a>Ccomkirinedobject sınıfı

Bu sınıf, [](/windows/win32/api/unknwn/nn-unknwn-iunknown) sahip nesnesine `IUnknown`temsilci seçerek IUnknown uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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
|[Ccomkirinedobject:: Ccomkirinedobject](#ccomcontainedobject)|Oluşturucu. Üye işaretçisini sahip nesnesine `IUnknown`başlatır.|
|[Ccomkirinedobject:: ~ Ccomkirinedobject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomkirinedobject:: AddRef](#addref)|Sahip nesnesindeki başvuru sayısını artırır.|
|[Ccomkirinedobject:: GetControllingUnknown](#getcontrollingunknown)|Sahip nesnesini `IUnknown`alır.|
|[Ccomkirinedobject:: QueryInterface](#queryinterface)|Sahip nesnesinde istenen arabirime yönelik bir işaretçi alır.|
|[Ccomkirinedobject:: Release](#release)|Sahip nesnesindeki başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

ATL, `CComContainedObject` [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md)ve [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)sınıflarında kullanır. `CComContainedObject`sahip [](/windows/win32/api/unknwn/nn-unknwn-iunknown) nesnesine `IUnknown`temsilci seçerek IUnknown uygular. (Sahip, bir toplama 'nın dıştaki nesnesidir ya da bir yırma arabiriminin oluşturulduğu nesne.) ,ve`CComObjectRootEx` 'nin`OuterQueryInterface` tümdevralınan`Base`çağrıları. `OuterAddRef` `CComContainedObject` `OuterRelease`

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComContainedObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>Ccomkirinedobject:: AddRef

Sahip nesnesindeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

##  <a name="ccomcontainedobject"></a>Ccomkirinedobject:: Ccomkirinedobject

Oluşturucu.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Sahip nesnesi `IUnknown`.

### <a name="remarks"></a>Açıklamalar

Üye işaretçisini ( `Base` sınıf üzerinden devralınmış) BD olarak ayarlar. `m_pOuterUnknown`

##  <a name="dtor"></a>Ccomkirinedobject:: ~ Ccomkirinedobject

Yok edicisi.

```
~CComContainedObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="getcontrollingunknown"></a>Ccomkirinedobject:: GetControllingUnknown

Sahip nesnesini`IUnknown`tutan üyeişaretçisini(tabansınıfıaracılığıyladevralınmış)`m_pOuterUnknown` döndürür.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Sahip nesnesi `IUnknown`.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `Base` [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) makrosunu bildirmişse sanal olabilir.

##  <a name="queryinterface"></a>Ccomkirinedobject:: QueryInterface

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
dışı *IID*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

*Sy*<br/>
dışı Tür `Q`tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="release"></a>Ccomkirinedobject:: Release

Sahip nesnesindeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
