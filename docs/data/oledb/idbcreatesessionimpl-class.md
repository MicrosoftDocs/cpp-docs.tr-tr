---
description: 'Daha fazla bilgi edinin: IDBCreateSessionImpl sınıfı'
title: IDBCreateSessionImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
ms.openlocfilehash: 8456ce4ec7bde5721ac6753ed9ec64d69c63e41f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317486"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl Sınıfı

[IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85)) arabirimi için bir uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>Parametreler

*T*<br/>
SıNıFıNDAN TÜRETILMIŞ

*SessionClass*<br/>
Oturum nesnesi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

| Ad | Açıklama |
|-|-|
|[CreateSession](#createsession)|Veri kaynağı nesnesinden yeni bir oturum oluşturur ve yeni oluşturulan oturumdaki istenen arabirimi döndürür.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnelerinde zorunlu arabirim.

## <a name="idbcreatesessionimplcreatesession"></a><a name="createsession"></a> IDBCreateSessionImpl:: CreateSession

Veri kaynağı nesnesinden yeni bir oturum oluşturur ve yeni oluşturulan oturumdaki istenen arabirimi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IDBCreateSession:: CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
