---
title: IRowsetNotifyImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8659897e411f703882f398fd7e96c8838b5ddafb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056177"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl Sınıfı

Uygular ve kayıtları [IRowsetNotify](/previous-versions/windows/desktop/ms712959) Tüketici (diğer adıyla "havuz") bildirimleri işleyebilmeniz.

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

`IRowsetNotifyImpl` işlevsiz bir uygulamasını sağlar `IRowsetNotify`, için boş işlevlerle `IRowsetNotify` yöntemleri [OnFieldChange](/previous-versions/windows/desktop/ms715961), [OnRowChange](/previous-versions/windows/desktop/ms722694), ve [OnRowsetChange](/previous-versions/windows/desktop/ms722669). Varsa, uyguladığınızda bu sınıftan devralınan bir `IRowsetNotify` arabirimi, yalnızca gereksinim duyduğunuz yöntemleri uygulayabilirsiniz. Ayrıca diğer yöntemler için boş uygulamaları kendiniz vermeniz gerekir.

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

Bkz: [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961) parametre açıklamaları.

### <a name="return-value"></a>Dönüş Değeri

Bkz: [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961) dönüş değeri açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sarmalar [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.

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

Bkz: [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694) parametre açıklamaları.

### <a name="return-value"></a>Dönüş Değeri

Bkz: [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694) dönüş değeri açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sarmalar [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.

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

Bkz: [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669) parametre açıklamaları.

### <a name="return-value"></a>Dönüş Değeri

Bkz: [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669) dönüş değeri açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem sarmalar [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959)
[IRowsetNotifyCP sınıfı](../../data/oledb/irowsetnotifycp-class.md)