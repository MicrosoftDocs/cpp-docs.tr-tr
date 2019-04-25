---
title: CComObjectStack Class
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
ms.openlocfilehash: 19fd226e617e4cdb1bba8a113b8984c36bf28d59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259592"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack Class

Bu sınıf, geçici bir COM nesnesi oluşturur ve ile iskelet bir uygulamasını sağlar `IUnknown`.

## <a name="syntax"></a>Sözdizimi

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer bir arabirim uğradıysa nesnede desteklemek istediğiniz gibi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Oluşturucu.|
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectStack::AddRef](#addref)|Sıfır döndürür. Hata ayıklama modunda çağrı `_ASSERTE`.|
|[CComObjectStack::QueryInterface](#queryinterface)|Returns E_NOINTERFACE. Hata ayıklama modunda çağrı `_ASSERTE`.|
|[CComObjectStack::Release](#release)|Sıfır döndürür. Hata ayıklama modunda çağrı `_ASSERTE`. ~|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Oluşumu sırasında döndürülen HRESULT içeren `CComObjectStack` nesne.|

## <a name="remarks"></a>Açıklamalar

`CComObjectStack` geçici bir COM nesnesi oluşturup nesneyi bir iskelet uygulamasını sağlamak için kullanılan `IUnknown`. Genellikle, nesne (yani yığın üstüne itilir) bir işlev içinde yerel bir değişken olarak kullanılır. İşlev sona erdiğinde nesnesi yok edildikten sonra başvuru sayımı verimliliğini artırmak için yapılmaz.

Aşağıdaki örnek, bir işlev içinde kullanılan bir COM nesnesinin nasıl oluşturulacağını gösterir:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Geçici nesnenin `Tempobj` yığın üstüne itilir ve işlev sona erdiğinde otomatik olarak kaldırılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectStack`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComObjectStack::AddRef

Sıfır döndürür.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda çağrı `_ASSERTE`.

##  <a name="ccomobjectstack"></a>  CComObjectStack::CComObjectStack

Oluşturucu.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Açıklamalar

Çağrıları `FinalConstruct` ve ardından ayarlar [m_hResFinalConstruct](#m_hresfinalconstruct) döndürdüğü HRESULT için `FinalConstruct`. Varsa, temel sınıftan türetilmemiş [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), kendi sağlamalısınız `FinalConstruct` yöntemi. Yıkıcı çağrıları `FinalRelease`.

##  <a name="dtor"></a>  CComObjectStack:: ~ CComObjectStack

Yıkıcı.

```
CComObjectStack();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları ve aramalar boşaltır [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="m_hresfinalconstruct"></a>  CComObjectStack::m_hResFinalConstruct

Arama öğesinden döndürülen HRESULT içeren `FinalConstruct` yapımı sırasında `CComObjectStack` nesne.

```
HRESULT    m_hResFinalConstruct;
```

##  <a name="queryinterface"></a>  CComObjectStack::QueryInterface

Returns E_NOINTERFACE.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOINTERFACE.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda çağrı `_ASSERTE`.

##  <a name="release"></a>  CComObjectStack::Release

Sıfır döndürür.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama modunda çağrı `_ASSERTE`.

## <a name="see-also"></a>Ayrıca bkz.

[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal Sınıfı](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
