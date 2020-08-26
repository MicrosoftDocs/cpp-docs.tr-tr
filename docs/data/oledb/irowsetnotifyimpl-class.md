---
title: IRowsetNotifyImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
ms.openlocfilehash: f938d9e92bc2f447ecfa82f2bfb27c8fda7652ab
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845113"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl Sınıfı

, Bildirimleri işleyebilmesi için tüketiciden ("havuz" olarak da bilinir) bir [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) uygular ve kaydettirir.

## <a name="syntax"></a>Syntax

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[OnFieldChange](#onfieldchange)|Bir sütunun değerindeki herhangi bir değişikliği tüketiciye bildirir.|
|[OnRowChange](#onrowchange)|İlk değişikliğin tüketicisini bir satıra veya tüm satırı etkileyen herhangi bir değişikliğe bildirir.|
|[OnRowsetChange](#onrowsetchange)|Tüm satır kümesini etkileyen herhangi bir değişikliğin tüketicisini bilgilendirir.|

## <a name="remarks"></a>Açıklamalar

Bkz. tüketici üzerinde bağlantı noktası arabirimini uygulamayla ilgili [Bildirimler alma](../../data/oledb/receiving-notifications.md) .

`IRowsetNotifyImpl``IRowsetNotify` `IRowsetNotify` [OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)), [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85))ve [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85))yöntemleri için boş işlevlerle birlikte için kukla bir uygulama sağlar. Bir arabirim uygularken bu sınıftan devralma yaparsanız `IRowsetNotify` , yalnızca ihtiyacınız olan yöntemleri uygulayabilirsiniz. Ayrıca, diğer yöntemler için de boş uygulamalar sağlamanız gerekir.

## <a name="irowsetnotifyimplonfieldchange"></a><a name="onfieldchange"></a> IRowsetNotifyImpl:: OnFieldChange

Bir sütunun değerindeki herhangi bir değişikliği tüketiciye bildirir.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(OnFieldChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ HROW /* hRow */,
/* [in] */ DBORDINAL /* cColumns */,
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parametreler

Bkz: parametre açıklamaları için [IRowsetNotify:: OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) .

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamaları için bkz. [IRowsetNotify:: OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [ırowsetnotıfy:: OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) metodunu sarmalanmış. Ayrıntılar için OLE DB Programcı başvurusu içindeki yöntemin açıklamasına bakın.

## <a name="irowsetnotifyimplonrowchange"></a><a name="onrowchange"></a> IRowsetNotifyImpl:: OnRowChange

İlk değişikliğin tüketicisini bir satıra veya tüm satırı etkileyen herhangi bir değişikliğe bildirir.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(OnRowChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBCOUNTITEM /* cRows */,
/* [size_is][in] */ const HROW /* rghRows*/ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parametreler

Bkz: parametre açıklamaları için [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) .

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamaları için bkz. [IRowsetNotify:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [ırowsetnotıfy:: OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) metodunu sarmalanmış. Ayrıntılar için OLE DB Programcı başvurusu içindeki yöntemin açıklamasına bakın.

## <a name="irowsetnotifyimplonrowsetchange"></a><a name="onrowsetchange"></a> IRowsetNotifyImpl:: OnRowsetChange

Tüm satır kümesini etkileyen herhangi bir değişikliğin tüketicisini bilgilendirir.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parametreler

Bkz: parametre açıklamaları için [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) .

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamaları için bkz. [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [IRowsetNotify:: OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) metodunu sarmalanmış. Ayrıntılar için OLE DB Programcı başvurusu içindeki yöntemin açıklamasına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) 
 [IRowsetNotifyCP sınıfı](../../data/oledb/irowsetnotifycp-class.md)
