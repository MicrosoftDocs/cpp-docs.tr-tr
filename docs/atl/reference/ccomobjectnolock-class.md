---
title: CcomobjectNoLock Sınıfı
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
ms.openlocfilehash: c190f495e284e98b27a6c6dc2099a8dfc4b1693d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327612"
---
# <a name="ccomobjectnolock-class"></a>CcomobjectNoLock Sınıfı

Bu sınıf, `IUnknown` birbirlmeyen bir nesne için uygular, ancak oluşturucudaki modül kilidi sayısını artımaz.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
CComObjectRoot veya [CComObjectRootEx'ten](../../atl/reference/ccomobjectrootex-class.md)türetilen sınıfınızın yanı sıra nesne üzerinde desteklemek istediğiniz diğer arabirimlerden de. [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomobjectnoLock::ccomobjectnolock](#ccomobjectnolock)|Oluşturucu.|
|[CcomobjectnoLock::~ccomobjectnolock](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomobjectnoLock::Addref](#addref)|Nesne üzerinde başvuru sayısını artırımı.|
|[CcomObjectNoLock::QueryInterface](#queryinterface)|İstenen arabirime bir işaretçi döndürür.|
|[CcomobjectNoLock::Sürüm](#release)|Başvuru sayısını nesneye ayarı eder.|

## <a name="remarks"></a>Açıklamalar

`CComObjectNoLock`biraraya gelen bir nesne için [IUnknown'u](/windows/win32/api/unknwn/nn-unknwn-iunknown) uyguladığı [CComObject'e](../../atl/reference/ccomobject-class.md) benzer; ancak, `CComObjectNoLock` modül kilidi sayısını oluşturucuya artımaz.

ATL `CComObjectNoLock` sınıf fabrikaları için dahili olarak kullanır. Genel olarak, bu sınıfı doğrudan kullanmazsınız.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomobjectnolockaddref"></a><a name="addref"></a>CcomobjectnoLock::Addref

Nesne üzerinde başvuru sayısını artırımı.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama veya test için yararlı olabilecek bir değer.

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="ccomobjectnolock"></a>CcomobjectnoLock::ccomobjectnolock

Oluşturucu. [CComObject](../../atl/reference/ccomobject-class.md)aksine, modül kilit sayısı artış yok.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Parametreler

<em>void\*</em><br/>
[içinde] Bu adsız parametre kullanılmaz. Diğer `CComXXXObjectXXX` yapıcılarla simetri için var olur.

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="dtor"></a>CcomobjectnoLock::~ccomobjectnolock

Yıkıcı.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları boşaltıyor ve [FinalRelease'i](ccomobjectrootex-class.md#finalrelease)çağırıyor.

## <a name="ccomobjectnolockqueryinterface"></a><a name="queryinterface"></a>CcomObjectNoLock::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenen arabirimin tanımlayıcısı.

*ppvNesne*<br/>
[çıkış] *iid*tarafından tanımlanan arabirim işaretçisine işaretçi. Nesne bu arabirimi desteklemiyorsa, *ppvObject* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomobjectnolockrelease"></a><a name="release"></a>CcomobjectNoLock::Sürüm

Başvuru sayısını nesneye ayarı eder.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, `Release` tanılama veya sınama için yararlı olabilecek bir değer verir. Hata ayıklama yapılarında `Release` her zaman 0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
