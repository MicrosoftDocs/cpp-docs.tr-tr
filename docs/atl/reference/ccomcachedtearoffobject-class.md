---
description: 'Daha fazla bilgi edinin: CComCachedTearOffObject sınıfı'
title: CComCachedTearOffObject sınıfı
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
ms.openlocfilehash: 321e92b6bdf59834cd6c74b417a1788beefbdcb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146919"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject sınıfı

Bu sınıf, bir tear arabirimi için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular.

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

*içindedir*<br/>
' Dan türetilmiş, `CComTearOffObjectBase` ve yırt nesnenizin olmasını istediğiniz arabirimlerden türeten kapalı sınıfınız.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject:: CComCachedTearOffObject](#ccomcachedtearoffobject)|Oluşturucu.|
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject:: AddRef](#addref)|Bir nesne için başvuru sayısını artırır `CComCachedTearOffObject` .|
|[CComCachedTearOffObject:: Finalyapısı](#finalconstruct)|' İ çağırır `m_contained::FinalConstruct` (tear sınıfı ' yöntemi).|
|[CComCachedTearOffObject:: FinalRelease](#finalrelease)|' İ çağırır `m_contained::FinalRelease` (tear sınıfı ' yöntemi).|
|[CComCachedTearOffObject:: QueryInterface](#queryinterface)|Nesne için bir işaretçi `IUnknown` `CComCachedTearOffObject` ya da (sınıf), yırt sınıfınıza veya istenen arabirime döner `contained` .|
|[CComCachedTearOffObject:: Release](#release)|Bir nesnenin başvuru sayısını azaltır `CComCachedTearOffObject` ve başvuru sayısı 0 ise bunu yok eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject:: m_contained](#m_contained)|Bir `CComContainedObject` nesne, yırt sınıfından (sınıf) türetilmiş bir nesne `contained` .|

## <a name="remarks"></a>Açıklamalar

`CComCachedTearOffObject` bir tear arabirimi için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. Bu sınıf, sahip `CComTearOffObject` olan öğesinden farklı `CComCachedTearOffObject` , sahip nesnesinden farklı olan ' den farklıdır `IUnknown` `IUnknown` (sahibi, onun oluşturulduğu nesnedir). `CComCachedTearOffObject` kendi başvuru sayısını saklar `IUnknown` ve başvuru sayısı sıfır olduğunda kendisini siler. Ancak, herhangi bir ayırma arabirimini sorgulayıp, sahip nesnesinin başvuru sayısı `IUnknown` artırılır.

`CComCachedTearOffObject`Tear uygulayan nesne zaten örneklenmiştir ve ayırma arabirimi tekrar için sorgulanırsa, aynı nesne yeniden kullanılır `CComCachedTearOffObject` . Buna karşılık, bir tarafından uygulanan bir yırt arabirimi, `CComTearOffObject` sahip nesnesi aracılığıyla için yeniden sorgulanırsa, başka bir `CComTearOffObject` örneği oluşturulur.

Sahip sınıfı `FinalRelease` için önbelleğe alınmış öğesine uymalıdır ve çağırmalıdır, `Release` Bu da `IUnknown` `CComCachedTearOffObject` başvuru sayısını azaltır. Bu `CComCachedTearOffObject` `FinalRelease` , çağrılıp silinmesine neden olur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a> CComCachedTearOffObject:: AddRef

Nesnenin başvuru sayısını `CComCachedTearOffObject` 1 ' i arttırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a> CComCachedTearOffObject:: CComCachedTearOffObject

Oluşturucu.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki İşaretçisinin işaretçisi `IUnknown` `CComCachedTearOffObject` .

### <a name="remarks"></a>Açıklamalar

`CComContainedObject` [M_contained](#m_contained)üyeyi başlatır.

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a> CComCachedTearOffObject:: ~ CComCachedTearOffObject

Yok edicisi.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır ve [Sonlandıryayım](#finalrelease)çağırır.

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a> CComCachedTearOffObject:: Finalyapısı

`m_contained::FinalConstruct` `m_contained` , Bir> nesnesi oluşturmak için, bu `CComContainedObject` <  `contained` sınıf tarafından uygulanan arabirime erişmek için kullanılan çağrılar.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a> CComCachedTearOffObject:: FinalRelease

`m_contained::FinalRelease` `m_contained` `CComContainedObject` <  `contained`> nesnesini ücretsiz olarak çağırır.

```cpp
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a> CComCachedTearOffObject:: m_contained

Tear sınıfından türetilmiş bir [Ccomkirinedobject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*içindedir*<br/>
'ndaki ' Dan türetilmiş, `CComTearOffObjectBase` ve yırt nesnenizin olmasını istediğiniz arabirimlerden türeten kapalı sınıfınız.

### <a name="remarks"></a>Açıklamalar

Devralınan Yöntemler, `m_contained` `QueryInterface` `FinalConstruct` ,, ve,,, ve,,,, ve ' ı kullanarak, ayırma sınıfındaki ayırma arabirimine erişim için kullanılır `FinalRelease` .

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a> CComCachedTearOffObject:: QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*ppvObject*<br/>
dışı Arabirim bulunmazsa, *IID* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi veya ARABIRIM bulunamazsa null.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İstenen arabirim ise, `IUnknown` kendisine bir işaretçi döndürür `CComCachedTearOffObject` `IUnknown` ve başvuru sayısını artırır. Aksi takdirde, ' den devralınan [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yöntemini kullanarak, çıkarma sınıfınızdan arabirim için sorgular `CComObjectRootEx` .

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a> CComCachedTearOffObject:: Release

Başvuru sayısını 1 ' den azaltır ve başvuru sayısı 0 ise `CComCachedTearOffObject` nesneyi siler.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan derlemelerde, her zaman 0 döndürür. Hata ayıklama yapılarında, tanılama veya test için yararlı olabilecek bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComTearOffObject sınıfı](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
