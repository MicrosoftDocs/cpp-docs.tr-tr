---
title: CComObjectNoLock sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: 9253c7495f4d13ed6ce609988251d8abd09592ad
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497030"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock sınıfı

Bu sınıf, `IUnknown` toplanmayan bir nesne için uygular, ancak oluşturucuda modül kilit sayısını artırmaz.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer herhangi bir arabirimden.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Oluşturucu.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Nesnedeki başvuru sayısını artırır.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|İstenen arabirime bir işaretçi döndürür.|
|[CComObjectNoLock::Release](#release)|Nesnedeki başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

`CComObjectNoLock`, toplanmayan bir nesne için [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uyguladığından [CComObject](../../atl/reference/ccomobject-class.md) öğesine benzerdir; Ancak, `CComObjectNoLock` oluşturucuda modül kilit sayısını artırmaz.

ATL, `CComObjectNoLock` sınıf fabrikaları için dahili olarak kullanır. Genel olarak, bu sınıfı doğrudan kullancaksınız.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

Nesnedeki başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

Oluşturucu. [CComObject](../../atl/reference/ccomobject-class.md)aksine, modül kilit sayısını artırmaz.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Parametreler

<em>Kağıt\*</em><br/>
'ndaki Bu adlandırılmamış parametre kullanılmıyor. Diğer `CComXXXObjectXXX` oluşturucularla birlikte simetri için de mevcuttur.

##  <a name="dtor"></a>  CComObjectNoLock::~CComObjectNoLock

Yok edicisi.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır ve [Sonlandıryayım](ccomobjectrootex-class.md#finalrelease)çağırır.

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin tanımlayıcısı.

*ppvObject*<br/>
dışı *IID*tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="release"></a>CComObjectNoLock:: Release

Nesnedeki başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` tanılama veya test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
