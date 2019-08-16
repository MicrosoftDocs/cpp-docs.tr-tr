---
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
ms.openlocfilehash: d993a349d38342bda30a83dfdbe25577953799b3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497545"
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
' Dan türetilmiş, ve yırt nesnenizin `CComTearOffObjectBase` olmasını istediğiniz arabirimlerden türeten kapalı sınıfınız.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject:: CComCachedTearOffObject](#ccomcachedtearoffobject)|Oluşturucu.|
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject:: AddRef](#addref)|Bir `CComCachedTearOffObject` nesne için başvuru sayısını artırır.|
|[CComCachedTearOffObject:: Finalyapısı](#finalconstruct)|' İ çağırır (tear sınıfı ' yöntemi). `m_contained::FinalConstruct`|
|[CComCachedTearOffObject:: FinalRelease](#finalrelease)|' İ çağırır (tear sınıfı ' yöntemi). `m_contained::FinalRelease`|
|[CComCachedTearOffObject:: QueryInterface](#queryinterface)|Nesne için `IUnknown` bir işaretçi ya da (sınıf `contained`), yırt sınıfınıza veya istenen arabirime döner. `CComCachedTearOffObject`|
|[CComCachedTearOffObject:: Release](#release)|Bir `CComCachedTearOffObject` nesnenin başvuru sayısını azaltır ve başvuru sayısı 0 ise bunu yok eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCachedTearOffObject:: m_contained](#m_contained)|Bir `CComContainedObject` nesne, yırt sınıfından (sınıf `contained`) türetilmiş bir nesne.|

## <a name="remarks"></a>Açıklamalar

`CComCachedTearOffObject`bir tear arabirimi için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. Bu sınıf `IUnknown`, sahip `CComTearOffObject` olan `CComCachedTearOffObject` öğesinden farklı, sahip nesnesinden `IUnknown` farklı olan ' den farklıdır (sahibi, onun oluşturulduğu nesnedir). `CComCachedTearOffObject`kendi başvuru sayısını `IUnknown` saklar ve başvuru sayısı sıfır olduğunda kendisini siler. Ancak, herhangi bir ayırma arabirimini sorgulayıp, sahip nesnesinin `IUnknown` başvuru sayısı artırılır.

Tear uygulayan `CComCachedTearOffObject` nesne zaten örneklenmiştir ve ayırma arabirimi tekrar için sorgulanırsa, aynı nesne yeniden kullanılır. `CComCachedTearOffObject` Buna karşılık, bir `CComTearOffObject` tarafından uygulanan bir yırt arabirimi, sahip nesnesi aracılığıyla için yeniden sorgulanırsa, başka `CComTearOffObject` bir örneği oluşturulur.

Sahip `FinalRelease` sınıfı için `Release` `IUnknown` önbelleğe alınmış öğesine uymalıdır ve çağırmalıdır, bu da başvuru sayısını azaltır. `CComCachedTearOffObject` Bu, çağrılıp `FinalRelease` silinmesine neden `CComCachedTearOffObject`olur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>CComCachedTearOffObject:: AddRef

`CComCachedTearOffObject` Nesnenin başvuru sayısını 1 ' i arttırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

##  <a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject:: CComCachedTearOffObject

Oluşturucu.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki `IUnknown` İşaretçisinin`CComCachedTearOffObject`işaretçisi.

### <a name="remarks"></a>Açıklamalar

[M_contained](#m_contained)üyesini başlatır `CComContainedObject` .

##  <a name="dtor"></a>CComCachedTearOffObject:: ~ CComCachedTearOffObject

Yok edicisi.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır ve [Sonlandıryayım](#finalrelease)çağırır.

##  <a name="finalconstruct"></a>CComCachedTearOffObject:: Finalyapısı

, `m_contained::FinalConstruct` Bir `CComContainedObject` `m_contained` < > nesnesioluşturmakiçin,`contained`Bu sınıf tarafından uygulanan arabirime erişmek için kullanılan çağrılar.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="finalrelease"></a>CComCachedTearOffObject:: FinalRelease

`m_contained::FinalRelease` `m_contained` >Nesnesini`CComContainedObject`ücretsiz olarak< çağırır. `contained`

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComCachedTearOffObject:: m_contained

Tear sınıfından türetilmiş bir [Ccomkirinedobject](../../atl/reference/ccomcontainedobject-class.md) nesnesi.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Parametreler

*içindedir*<br/>
'ndaki ' Dan türetilmiş, ve yırt nesnenizin `CComTearOffObjectBase` olmasını istediğiniz arabirimlerden türeten kapalı sınıfınız.

### <a name="remarks"></a>Açıklamalar

Devralınan Yöntemler `m_contained` , `FinalConstruct`,, ve,,, ve,,,, ve `FinalRelease`' ı kullanarak `QueryInterface`, ayırma sınıfındaki ayırma arabirimine erişim için kullanılır.

##  <a name="queryinterface"></a>CComCachedTearOffObject:: QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*ppvObject*<br/>
dışı Arabirim bulunmazsa, *IID*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi veya ARABIRIM bulunamazsa null.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İstenen arabirim ise `IUnknown`, kendisine `IUnknown` bir işaretçi `CComCachedTearOffObject`döndürür ve başvuru sayısını artırır. Aksi takdirde, ' den `CComObjectRootEx`devralınan [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yöntemini kullanarak, çıkarma sınıfınızdan arabirim için sorgular.

##  <a name="release"></a>CComCachedTearOffObject:: Release

Başvuru sayısını 1 ' den azaltır ve başvuru sayısı 0 ise `CComCachedTearOffObject` nesneyi siler.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama olmayan derlemelerde, her zaman 0 döndürür. Hata ayıklama yapılarında, tanılama veya test için yararlı olabilecek bir değer döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComTearOffObject Sınıfı](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
