---
title: CComCachedTearOffObject Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: 43f914a52666788fc0bf394d9d14830b28f5adc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321036"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject Sınıfı

Bu sınıf, yırtılma arabirimi için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular.

## <a name="syntax"></a>Sözdizimi

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametreler

*Bulunan*<br/>
Yırtılma sınıfınız, `CComTearOffObjectBase` türetilmiş ve yırtılma nesnenizin desteklenmesini istediğiniz arabirimler.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Oluşturucu.|
|[CComCachedTearOffObject::~CComCachedTearOffObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|Bir `CComCachedTearOffObject` nesne için başvuru sayısını artırımı.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|(yırtılma sınıfı' yöntemini) `m_contained::FinalConstruct` çağırır.|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|(yırtılma sınıfı' yöntemini) `m_contained::FinalRelease` çağırır.|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Bir işaretçiyi `IUnknown` `CComCachedTearOffObject` nesnenin nesnesine veya yırtılma sınıfınızdaki (sınıf) `contained`istenen arabirime döndürür.|
|[CComCachedTearOffObject::Sürüm](#release)|Bir `CComCachedTearOffObject` nesne için başvuru sayısını eriter ve başvuru sayısı 0 ise onu yok eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|Yırtılma sınıfınızdan türetilen bir `CComContainedObject` `contained`nesne (sınıf).|

## <a name="remarks"></a>Açıklamalar

`CComCachedTearOffObject`yırtılma arabirimi için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. Bu sınıf, `CComTearOffObject` sahibi `CComCachedTearOffObject` nesnenin `IUnknown`(sahibi için yırtılma `IUnknown` oluşturulduğu nesnedir) ayrı, kendi vardır farklıdır. `CComCachedTearOffObject`kendi referans sayısını korur `IUnknown` ve referans sayısı sıfır olduğunda kendini siler. Ancak, yırtılma arabirimlerinden herhangi birini sorgularsanız, sahibi nesnenin `IUnknown` başvuru sayısı artımlı olacaktır.

Yırtılma yıkıntısını uygulayan `CComCachedTearOffObject` nesne zaten anında alınmışsa ve yırtılma arabirimi `CComCachedTearOffObject` yeniden sorgulanırsa, aynı nesne yeniden kullanılır. Buna karşılık, bir parçalama `CComTearOffObject` arabirimi tarafından uygulanan bir gözyaşı arabirimi `CComTearOffObject` yine sahibi nesne saracılığıyla sorgulanırsa, başka bir instantiated olacaktır.

Sahip sınıfı, `FinalRelease` başvuru `Release` sayısını azalacak `IUnknown` `CComCachedTearOffObject`olan önbelleğe alınmış olan alete başvurmalı ve çağrıda bulunmalıdır. Bu, `CComCachedTearOffObject` `FinalRelease` çağrılmasına ve yırtılmayı silmesine neden olur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a>CComCachedTearOffObject::AddRef

Nesnenin `CComCachedTearOffObject` başvuru sayısını 1 ile karşılar.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject

Oluşturucu.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
[içinde] Işaretçi `IUnknown` için `CComCachedTearOffObject`.

### <a name="remarks"></a>Açıklamalar

Üye, `CComContainedObject` [m_contained.](#m_contained)

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>CComCachedTearOffObject::~CComCachedTearOffObject

Yıkıcı.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor ve [FinalRelease'i](#finalrelease)çağırıyor.

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct

Oluşturma `m_contained::FinalConstruct` `m_contained`çağrıları , `CComContainedObject` <  `contained` yırtılma sınıfınız tarafından uygulanan arabirime erişmek için kullanılan> nesne.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease

Özgüre `m_contained::FinalRelease` `m_contained`çağırır `CComContainedObject` <  `contained` ,> nesnesi.

```
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a>CComCachedTearOffObject::m_contained

Yırtılma sınıfınızdan türetilen [bir CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*Bulunan*<br/>
[içinde] Yırtılma sınıfınız, `CComTearOffObjectBase` türetilmiş ve yırtılma nesnenizin desteklenmesini istediğiniz arabirimler.

### <a name="remarks"></a>Açıklamalar

Devralınan `m_contained` yöntemler, önbelleğe alınmış yırtılma nesnesinin `QueryInterface`, `FinalConstruct`ve `FinalRelease`.

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenmekte olan arabirimin GUID'i.

*ppvNesne*<br/>
[çıkış] Arabirim bulunamazsa *iid*veya NULL tarafından tanımlanan arabirim işaretçisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İstenen arabirim `IUnknown`ise, bir `CComCachedTearOffObject`işaretçiyi `IUnknown` 'nin kendi'sine döndürür ve başvuru sayısını nitonlarını genişletir. Aksi takdirde, [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yöntemini kullanarak yırtılma sınıfınızdaki arabirim sorguları `CComObjectRootEx`.

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a>CComCachedTearOffObject::Sürüm

Başvuru sayısını 1 ile erteler ve başvuru sayısı 0 ise `CComCachedTearOffObject` nesneyi siler.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında her zaman 0 döndürür. Hata ayıklama oluştururda, tanılama veya sınama için yararlı olabilecek bir değer verir.

## <a name="see-also"></a>Ayrıca bkz.

[CComTearOffObject Sınıfı](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
