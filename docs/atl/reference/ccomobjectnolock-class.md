---
title: CComObjectNoLock Class
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
ms.openlocfilehash: 50dc4505c1da8df9efc0c9d0028461ef49c0840e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246306"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock Class

Bu sınıfın uyguladığı `IUnknown` toplanmayan bir nesne, ancak mu modülün kilit sayacını oluşturucuda artırma.

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
Sınıfınız, türetilen [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)iyi herhangi diğer bir arabirim uğradıysa nesnede desteklemek istediğiniz gibi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Oluşturucu.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Nesnede başvuru sayısını artırır.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|İstenen arabirim için bir işaretçi döndürür.|
|[CComObjectNoLock::Release](#release)|Nesnede başvuru sayısını azaltır.|

## <a name="remarks"></a>Açıklamalar

`CComObjectNoLock` benzer [CComObject](../../atl/reference/ccomobject-class.md) uygular, [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) toplanmayan bir nesnenin; ancak, `CComObjectNoLock` artışı modülü kilit oluşturucuda sayar.

ATL kullanan `CComObjectNoLock` sınıf üreteçlerini için dahili olarak. Genel olarak, bu sınıf doğrudan kullanmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

Nesnede başvuru sayısını artırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama için kullanışlı veya test olabilir bir değer.

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

Oluşturucu. Farklı [CComObject](../../atl/reference/ccomobject-class.md), modülün kilit sayacını artırmaz.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Parametreler

<em>Geçersiz kılma\*</em><br/>
[in] Bu adlandırılmamış parametre kullanılmaz. Simetri diğer için mevcut `CComXXXObjectXXX` oluşturucular.

##  <a name="dtor"></a>  CComObjectNoLock::~CComObjectNoLock

Yıkıcı.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları ve aramalar boşaltır [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

İstenen arabirim için bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] İstenen arabirim tanımlayıcısı.

*ppvObject*<br/>
[out] Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*. Nesne bu arabirimi desteklemiyorsa *ppvObject* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="release"></a>  CComObjectNoLock::Release

Nesnede başvuru sayısını azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında `Release` tanılama için kullanışlı veya test olabilecek bir değer döndürür. Hata ayıklama olmayan yapılarında `Release` her zaman 0 değerini döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
