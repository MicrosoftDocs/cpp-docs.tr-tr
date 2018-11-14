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
ms.openlocfilehash: 01bcc60b0c88a3953d5e75b53ac58877f7eb15df
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556393"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl Sınıfı

Uygular ve kayıtları [IRowsetNotify](https://docs.microsoft.com/previous-versions/windows/desktop/ms712959(v=vs.85)) Tüketici (diğer adıyla "havuz") bildirimleri işleyebilmeniz.

## <a name="syntax"></a>Sözdizimi

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[OnFieldChange](#onfieldchange)|Bir sütunun değeri herhangi bir değişiklik tüketicisinin bildirir.|
|[OnRowChange](#onrowchange)|İlk değişiklik bir satır veya satırın tamamını etkileyen herhangi bir değişiklik tüketici bildirir.|
|[OnRowsetChange](#onrowsetchange)|Tüm satır kümesini etkileyen herhangi bir değişiklik tüketicisinin bildirir.|

## <a name="remarks"></a>Açıklamalar

Bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md) tüketici üzerinde bağlantı noktası arabirimini uygulayan hakkında.

`IRowsetNotifyImpl` işlevsiz bir uygulamasını sağlar `IRowsetNotify`, için boş işlevlerle `IRowsetNotify` yöntemleri [OnFieldChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85)), [OnRowChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85)), ve [OnRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85)). Varsa, uyguladığınızda bu sınıftan devralınan bir `IRowsetNotify` arabirimi, yalnızca gereksinim duyduğunuz yöntemleri uygulayabilirsiniz. Ayrıca diğer yöntemler için boş uygulamaları kendiniz vermeniz gerekir.

## <a name="onfieldchange"></a> IRowsetNotifyImpl::onfieldchange

Bir sütunun değeri herhangi bir değişiklik tüketicisinin bildirir.

### <a name="syntax"></a>Sözdizimi

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

Bkz: [IRowsetNotify::OnFieldChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85)) parametre açıklamaları.

### <a name="return-value"></a>Dönüş Değeri

Bkz: [IRowsetNotify::OnFieldChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85)) dönüş değeri açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sarmalar [IRowsetNotify::OnFieldChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715961(v=vs.85)) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.

## <a name="onrowchange"></a> IRowsetNotifyImpl::onrowchange

İlk değişiklik bir satır veya satırın tamamını etkileyen herhangi bir değişiklik tüketici bildirir.

### <a name="syntax"></a>Sözdizimi

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

Bkz: [IRowsetNotify::OnRowChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85)) parametre açıklamaları.

### <a name="return-value"></a>Dönüş Değeri

Bkz: [IRowsetNotify::OnRowChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85)) dönüş değeri açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sarmalar [IRowsetNotify::OnRowChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722694(v=vs.85)) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.

## <a name="onrowsetchange"></a> IRowsetNotifyImpl::onrowsetchange

Tüm satır kümesini etkileyen herhangi bir değişiklik tüketicisinin bildirir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetNotify::OnRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85)) parametre açıklamaları.

### <a name="return-value"></a>Dönüş Değeri

Bkz: [IRowsetNotify::OnRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85)) dönüş değeri açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sarmalar [IRowsetNotify::OnRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms722669(v=vs.85)) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](https://docs.microsoft.com/previous-versions/windows/desktop/ms712959(v=vs.85))
[IRowsetNotifyCP sınıfı](../../data/oledb/irowsetnotifycp-class.md)