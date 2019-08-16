---
title: CComObject sınıfı
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
ms.openlocfilehash: a2051932413d8658eb7cedb67ed0eab2077b599d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497141"
---
# <a name="ccomobject-class"></a>CComObject sınıfı

Bu sınıf, `IUnknown` toplanmayan bir nesne için uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer arabirimlerin yanı sıra.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObject:: CComObject](#ccomobject)|Oluşturucu.|
|[CComObject::~CComObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObject:: AddRef](#addref)|Nesnedeki başvuru sayısını artırır.|
|[CComObject::CreateInstance](#createinstance)|Se Yeni `CComObject` bir nesne oluşturur.|
|[CComObject:: QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComObject:: Release](#release)|Nesnedeki başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

`CComObject`toplanmayan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. Bununla birlikte,, `QueryInterface`ve `AddRef` `Release` ' a yönelik çağrılar için `CComObjectRootEx`atanır.

Kullanma `CComObject`hakkında daha fazla bilgi için, [atl com nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>CComObject:: AddRef

Nesnedeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, nesnedeki yeni artan başvuru sayısını döndürür. Bu değer tanılama veya test için yararlı olabilir.

##  <a name="ccomobject"></a>CComObject:: CComObject

Oluşturucu modül kilit sayısını artırır.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Parametreler

<em>Kağıt\*</em><br/>
'ndaki Bu adlandırılmamış parametre kullanılmıyor. Diğer `CComXXXObjectXXX` oluşturucularla birlikte simetri için de mevcuttur.

### <a name="remarks"></a>Açıklamalar

Yıkıcı onu azaltır.

Türetilmiş bir `CComObject`nesne **New** işleci kullanılarak başarıyla oluşturulursa, ilk başvuru sayısı 0 ' dır. Başvuru sayısını uygun değere (1) ayarlamak için [AddRef](#addref) işlevine bir çağrı yapın.

##  <a name="dtor"></a>  CComObject::~CComObject

Yok edicisi.

```
CComObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, [sonlandırmayı](ccomobjectrootex-class.md#finalrelease)çağırır ve modül kilit sayısını azaltır.

##  <a name="createinstance"></a>  CComObject::CreateInstance

Bu statik işlev, [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)'ın ek yükü olmadan yeni bir **CComObject <** `Base` **>** nesnesi oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
dışı Bir **CComObject <** `Base` **>** işaretçisine yönelik işaretçi. Başarısız `CreateInstance` olursa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfır, bu yüzden hemen çağırın `AddRef` , sonra işlemi bitirdiğinizde nesne İşaretçisinde başvuruyu serbest bırakmak için kullanın. `Release`

Nesneye doğrudan erişmeniz gerekmiyorsa ancak ek yükü `CoCreateInstance`olmadan yeni bir nesne oluşturmak istiyorsanız, bunun yerine [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

##  <a name="queryinterface"></a>  CComObject::QueryInterface

İstenen arabirim için bir işaretçi alır.

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

##  <a name="release"></a>CComObject:: Release

Nesnedeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, nesnedeki yeni azaltma başvuru sayısını döndürür. Hata ayıklama yapılarında, dönüş değeri tanılama veya test için yararlı olabilir. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
