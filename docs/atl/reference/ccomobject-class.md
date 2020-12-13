---
description: 'Daha fazla bilgi edinin: CComObject Class'
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
ms.openlocfilehash: 086383172d5bb239bbac8ed90e9118838aea1254
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146529"
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
|[CComObject:: ~ CComObject](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObject:: AddRef](#addref)|Nesnedeki başvuru sayısını artırır.|
|[CComObject:: CreateInstance](#createinstance)|Se Yeni bir `CComObject` nesne oluşturur.|
|[CComObject:: QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComObject:: Release](#release)|Nesnedeki başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

`CComObject` toplanmayan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygular. Bununla birlikte,, ve ' a yönelik çağrılar `QueryInterface` `AddRef` `Release` için atanır `CComObjectRootEx` .

Kullanma hakkında daha fazla bilgi için `CComObject` , [atl com nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomobjectaddref"></a><a name="addref"></a> CComObject:: AddRef

Nesnedeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, nesnedeki yeni artan başvuru sayısını döndürür. Bu değer tanılama veya test için yararlı olabilir.

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a> CComObject:: CComObject

Oluşturucu modül kilit sayısını artırır.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Parametreler

<em>void\*</em><br/>
'ndaki Bu adlandırılmamış parametre kullanılmıyor. Diğer oluşturucularla birlikte simetri için de mevcuttur `CComXXXObjectXXX` .

### <a name="remarks"></a>Açıklamalar

Yıkıcı onu azaltır.

Türetilmiş bir `CComObject` nesne işleci kullanılarak başarıyla oluşturulursa **`new`** , ilk başvuru sayısı 0 ' dır. Başvuru sayısını uygun değere (1) ayarlamak için [AddRef](#addref) işlevine bir çağrı yapın.

## <a name="ccomobjectccomobject"></a><a name="dtor"></a> CComObject:: ~ CComObject

Yok edicisi.

```
CComObject();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır, [sonlandırmayı](ccomobjectrootex-class.md#finalrelease)çağırır ve modül kilit sayısını azaltır.

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a> CComObject:: CreateInstance

Bu statik işlev  `Base` **>** , [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)'ın ek yükü olmadan yeni bir CComObject<nesnesi oluşturmanıza olanak sağlar.

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
dışı Bir **CComObject<** işaretçisine yönelik işaretçi `Base` **>** . `CreateInstance`Başarısız olursa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen nesnenin başvuru sayısı sıfır, bu yüzden hemen çağırın, `AddRef` sonra `Release` işlemi bitirdiğinizde nesne İşaretçisinde başvuruyu serbest bırakmak için kullanın.

Nesneye doğrudan erişmeniz gerekmiyorsa ancak ek yükü olmadan yeni bir nesne oluşturmak istiyorsanız, `CoCreateInstance` bunun yerine [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a> CComObject:: QueryInterface

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
dışı *IID* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

*Sy*<br/>
dışı Tür tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi `Q` . Nesne bu arabirimi desteklemiyorsa, *PP* değeri null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomobjectrelease"></a><a name="release"></a> CComObject:: Release

Nesnedeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, nesnedeki yeni azaltma başvuru sayısını döndürür. Hata ayıklama yapılarında, dönüş değeri tanılama veya test için yararlı olabilir. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
