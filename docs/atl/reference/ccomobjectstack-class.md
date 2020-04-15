---
title: CComObjectStack Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 8c3fd56635da8b80c84f6151009586b7bd2b4341
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327580"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack Sınıfı

Bu sınıf geçici bir COM nesnesi oluşturur ve bir `IUnknown`iskelet uygulaması ile sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomobjectStack::ccomobjectstack](#ccomobjectstack)|Oluşturucu.|
|[CcomobjectStack::~ccomobjectstack](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomobjectStack::Addref](#addref)|Sıfır döndürür. Hata ayıklama modunda, çağırır. `_ASSERTE`|
|[CcomObjectStack::QueryInterface](#queryinterface)|E_NOINTERFACE döndürür. Hata ayıklama modunda, çağırır. `_ASSERTE`|
|[CcomobjectStack::Sürüm](#release)|Sıfır döndürür. Hata ayıklama modunda, çağırır. `_ASSERTE` ~|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Nesnenin yapımı sırasında döndürülen `CComObjectStack` HRESULT'ı içerir.|

## <a name="remarks"></a>Açıklamalar

`CComObjectStack`geçici bir COM nesnesi oluşturmak ve nesneye iskelet `IUnknown`uygulaması sağlamak için kullanılır. Genellikle, nesne tek bir işlev içinde yerel bir değişken olarak kullanılır (diğer bir şekilde yığına itilir). Işlev bittiğinde nesne yok edildiğinden, verimliliği artırmak için başvuru sayma yapılmaz.

Aşağıdaki örnek, bir işlev içinde kullanılan bir COM nesnesinin nasıl oluşturulacak olduğunu gösterir:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Geçici nesne `Tempobj` yığınüzerine itilir ve işlev bittiğinde otomatik olarak kaybolur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectStack`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a>CcomobjectStack::Addref

Sıfır döndürür.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda, çağırır. `_ASSERTE`

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a>CcomobjectStack::ccomobjectstack

Oluşturucu.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Açıklamalar

Aramalar `FinalConstruct` ve daha sonra tarafından döndürülen HRESULT [m_hResFinalConstruct](#m_hresfinalconstruct) `FinalConstruct`ayarlar. Taban sınıfınızı [CComObjectRoot'dan](../../atl/reference/ccomobjectroot-class.md)türemediyseniz, kendi `FinalConstruct` yönteminizi sağlamanız gerekir. Yıkıcı arıyor. `FinalRelease`

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a>CcomobjectStack::~ccomobjectstack

Yıkıcı.

```
CComObjectStack();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor ve [FinalRelease'i](ccomobjectrootex-class.md#finalrelease)çağırıyor.

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct

Nesnenin yapımı sırasında `FinalConstruct` çağrıdan döndürülen HRESULT'ı `CComObjectStack` içerir.

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a>CcomObjectStack::QueryInterface

E_NOINTERFACE döndürür.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOINTERFACE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda, çağırır. `_ASSERTE`

## <a name="ccomobjectstackrelease"></a><a name="release"></a>CcomobjectStack::Sürüm

Sıfır döndürür.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda, çağırır. `_ASSERTE`

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal Sınıfı](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
