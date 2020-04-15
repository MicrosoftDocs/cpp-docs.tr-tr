---
title: CComTearOffObject Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: de7528d3972991c233ee4b9037f609b89d0f7434
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327316"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject Sınıfı

Bu sınıf bir yırtılma arabirimi uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Yırtılma sınıfınız, `CComTearOffObjectBase` türetilmiş ve yırtılma nesnenizin desteklenmesini istediğiniz arabirimler.

ATL, yırtılma arabirimlerini iki aşamada `CComTearOffObjectBase` uygular — yöntemler `QueryInterface`başvuru `CComTearOffObject` sayısını işler ve [IUnknown'u](/windows/win32/api/unknwn/nn-unknwn-iunknown)uygular.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomtearoffObject::ccomtearoffobject](#ccomtearoffobject)|Oluşturucu.|
|[CcomtearoffObject::~ccomtearoffObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomtearoffObject::Addref](#addref)|Bir `CComTearOffObject` nesne için başvuru sayısını artırımı.|
|[CcomtearoffObject::QueryInterface](#queryinterface)|Yırtılma sınıfınızda veya sahibi sınıfınızda istenen arabirime bir işaretçi döndürür.|
|[CcomtearoffObject::Sürüm](#release)|Bir `CComTearOffObject` nesne için başvuru sayısını erteler ve yok eder.|

### <a name="ccomtearoffobjectbase-methods"></a>CcomtearOffObjectBase Yöntemleri

|||
|-|-|
|[CcomtearOffObjectBase](#ccomtearoffobjectbase)|Oluşturucu.|

### <a name="ccomtearoffobjectbase-data-members"></a>CcomtearOffObjectBase Veri Üyeleri

|||
|-|-|
|[m_pOwner](#m_powner)|Sahibi sınıfından `CComObject` türetilen bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CComTearOffObject`yalnızca bu arabirim için sorgulandığında anlık olarak ayrı bir nesne olarak bir yırtılma arabirimi uygular. Başvuru sayısı sıfır olduğunda yırtılma silinir. Genellikle, bir yırtılma kullanarak ana nesnenizin tüm örneklerinde bir vtable işaretçisi kaydeder, çünkü nadiren kullanılan bir arabirim için bir yırtılma arabirimi oluşturun.

Yırtılma nesnenizi desteklemesini istediğiniz arabirimlerden ve hangi arabirimlerden `CComTearOffObjectBase` yırtılma uygulayan sınıfı türemelisiniz. `CComTearOffObjectBase`sahibi sınıf ve iş parçacığı modeli üzerinde templatized. Sahip sınıfı, yırtılma nın uygulandığı nesnenin sınıfıdır. Bir iş parçacığı modeli belirtmezseniz, varsayılan iş parçacığı modeli kullanılır.

Yırtılma sınıfınız için bir COM eşlemesi oluşturmalısınız. ATL yırtılmayı anında anladığında, bu `CComTearOffObject<CYourTearOffClass>` olay. `CComCachedTearOffObject<CYourTearOffClass>`

Örneğin, BEEPER örneğinde, `CBeeper2` sınıf yırtılma sınıfıdır `CBeeper` ve sınıf sahibi sınıfıdır:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a>CcomtearoffObject::Addref

`CComTearOffObject` Nesnenin başvuru sayısını bire bir erler.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a>CcomtearoffObject::ccomtearoffobject

Oluşturucu.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
[içinde] Bir `CComObject<Owner>` nesneye işaretçiye dönüştürülecek işaretçi.

### <a name="remarks"></a>Açıklamalar

Sahibinin referans sayısını bire kadar artımlar.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a>CcomtearoffObject::~ccomtearoffObject

Yıkıcı.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor, FinalRelease'i çağırır ve modül kilit sayısını atar.

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a>CcomtearoffObject::ccomtearoffobjectbase

Oluşturucu.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Açıklamalar

[m_pOwner](#m_powner) üyeyi NULL'a başharf.

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a>CComTearOffNesne::m_pOwner

*Sahibinden*türetilen bir [CComObject](../../atl/reference/ccomobject-class.md) nesnesine işaretçi.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parametreler

*Sahibi*<br/>
[içinde] Yırtılma nın uygulandığı sınıf.

### <a name="remarks"></a>Açıklamalar

İşaretçi, inşaat sırasında NULL olarak başolarak başlanır.

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CcomtearoffObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenilen arabirimin IID'si.

*ppvNesne*<br/>
[çıkış] Arabirim bulunamazsa *iid*veya NULL tarafından tanımlanan arabirim işaretçisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yırtılma sınıfınızdaki arabirimler için önce sorgular. Arabirim yoksa, sahip nesnesindeki arabirim için sorgular. İstenen arabirim, `IUnknown`sahibinin döndürür. `IUnknown`

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a>CcomtearoffObject::Sürüm

Referans sayısını bire indirir ve başvuru sayısı sıfırsa `CComTearOffObject`, .

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında her zaman sıfır döndürür. Hata ayıklama oluştururda, tanılama veya sınama için yararlı olabilecek bir değer verir.

## <a name="see-also"></a>Ayrıca bkz.

[CComCachedTearOffObject Sınıfı](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
