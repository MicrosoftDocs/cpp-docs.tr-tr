---
description: 'Daha fazla bilgi edinin: CComObjectStack sınıfı'
title: CComObjectStack sınıfı
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
ms.openlocfilehash: 5713601a765ad9ff1c32992d1f9c517dd86affca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142421"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack sınıfı

Bu sınıf, geçici bir COM nesnesi oluşturur ve bunu bir iskelet uygulamasıyla sağlar `IUnknown` .

## <a name="syntax"></a>Sözdizimi

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer herhangi bir arabirimden.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectStack:: CComObjectStack](#ccomobjectstack)|Oluşturucu.|
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectStack:: AddRef](#addref)|Sıfır döndürür. Hata ayıklama modunda, çağırır `_ASSERTE` .|
|[CComObjectStack:: QueryInterface](#queryinterface)|E_NOINTERFACE döndürür. Hata ayıklama modunda, çağırır `_ASSERTE` .|
|[CComObjectStack:: yayın](#release)|Sıfır döndürür. Hata ayıklama modunda, çağırır `_ASSERTE` . ~|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectStack:: m_hResFinalConstruct](#m_hresfinalconstruct)|Nesnenin oluşturulması sırasında döndürülen HRESULT 'yi içerir `CComObjectStack` .|

## <a name="remarks"></a>Açıklamalar

`CComObjectStack` geçici bir COM nesnesi oluşturmak ve nesneye bir çatı uygulamasının sağlanması için kullanılır `IUnknown` . Genellikle nesne, bir işlev içinde yerel değişken olarak kullanılır (yani yığına gönderilir). İşlev bittiğinde nesne yok edileceği için, verimliliği artırmak için başvuru sayma gerçekleştirilmez.

Aşağıdaki örnek, bir işlev içinde kullanılan COM nesnesinin nasıl oluşturulacağını gösterir:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Geçici nesne `Tempobj` yığına gönderilir ve işlev bittiğinde otomatik olarak kaybolur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectStack`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a> CComObjectStack:: AddRef

Sıfır döndürür.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda, çağırır `_ASSERTE` .

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a> CComObjectStack:: CComObjectStack

Oluşturucu.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Açıklamalar

`FinalConstruct`Tarafından döndürülen HRESULT [m_hResFinalConstruct](#m_hresfinalconstruct) çağırır ve sonra ayarlar `FinalConstruct` . [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)' den temel sınıfınızı türettiğiniz takdirde kendi yönteminizi sağlamanız gerekir `FinalConstruct` . Yıkıcı çağırır `FinalRelease` .

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a> CComObjectStack:: ~ CComObjectStack

Yok edicisi.

```
CComObjectStack();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır ve [Sonlandıryayım](ccomobjectrootex-class.md#finalrelease)çağırır.

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectStack:: m_hResFinalConstruct

Nesnenin oluşturulması sırasında çağırmanın döndürdüğü HRESULT 'yi içerir `FinalConstruct` `CComObjectStack` .

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a> CComObjectStack:: QueryInterface

E_NOINTERFACE döndürür.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOINTERFACE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda, çağırır `_ASSERTE` .

## <a name="ccomobjectstackrelease"></a><a name="release"></a> CComObjectStack:: yayın

Sıfır döndürür.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda, çağırır `_ASSERTE` .

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal sınıfı](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
