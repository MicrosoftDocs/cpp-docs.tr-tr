---
title: CComObject Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: de6ffb45fe5c6f73ab656d5c6185b70d9f5edd38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327638"
---
# <a name="ccomobject-class"></a>CComObject Sınıfı

Bu sınıf, `IUnknown` birbirlmeyen bir nesne için uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomObject::ccomobject](#ccomobject)|Oluşturucu.|
|[CcomObject::~ccomObject](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomObject::Addref](#addref)|Nesne üzerinde başvuru sayısını artırımı.|
|[CComObject::CreateInstance](#createinstance)|(Statik) Yeni `CComObject` bir nesne oluşturur.|
|[CcomObject::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CcomObject::Sürüm](#release)|Başvuru sayısını nesneye ayarı eder.|

## <a name="remarks"></a>Açıklamalar

`CComObject`biraraya olmayan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. Ancak, çağırır `QueryInterface` `AddRef`, `Release` , ve `CComObjectRootEx`.

Kullanma `CComObject`hakkında daha fazla bilgi için, [ATL COM Nesnelerin](../../atl/fundamentals-of-atl-com-objects.md)makale temelleri bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomobjectaddref"></a><a name="addref"></a>CcomObject::Addref

Nesne üzerinde başvuru sayısını artırımı.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, nesneüzerinde yeni artışlı başvuru sayısını döndürür. Bu değer tanılama veya test için yararlı olabilir.

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a>CcomObject::ccomobject

Yapıcı, modül kilit sayısını artımlı.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Parametreler

<em>void\*</em><br/>
[içinde] Bu adsız parametre kullanılmaz. Diğer `CComXXXObjectXXX` yapıcılarla simetri için var olur.

### <a name="remarks"></a>Açıklamalar

Yıkıcı onu yok ediyor.

Türetilmiş bir `CComObject`nesne **yeni** işleç kullanılarak başarıyla oluşturulursa, ilk başvuru sayısı 0'dır. Başvuru sayısını uygun değere (1) ayarlamak için [AddRef](#addref) işlevini arayın.

## <a name="ccomobjectccomobject"></a><a name="dtor"></a>CcomObject::~ccomObject

Yıkıcı.

```
CComObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor, [FinalRelease'i](ccomobjectrootex-class.md#finalrelease)çağırır ve modül kilidi sayısını atar.

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::CreateInstance

Bu statik işlev, [CoCreateInstance'ın](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)yükü olmadan yeni bir **CComObject<** `Base` **>** nesnesi oluşturmanıza olanak tanır.

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Parametreler

*S*<br/>
[çıkış] **CComObject<** `Base` **>** işaretçisine işaretçi. Başarısız `CreateInstance` olursa, *pp* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfırdır, bu nedenle hemen arayın `AddRef` ve `Release` ardından işi bittiğinde nesne işaretçisi üzerindeki başvuruyu serbest bırakır.

Nesneye doğrudan erişime ihtiyacınız yoksa, ancak yine de ek yükü olmadan `CoCreateInstance`yeni bir nesne oluşturmak istiyorsanız, [CComCoClass kullanın::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) yerine.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a>CcomObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

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

## <a name="ccomobjectrelease"></a><a name="release"></a>CcomObject::Sürüm

Başvuru sayısını nesneye ayarı eder.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, nesne üzerinde yeni verilen başvuru sayısını döndürür. Hata ayıklama oluştururda, iade değeri tanılama veya sınama için yararlı olabilir. Hata ayıklama yapılarında `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
