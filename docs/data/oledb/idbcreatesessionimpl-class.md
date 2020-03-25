---
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
ms.openlocfilehash: cff1ca374c9489cb9c5df0dad153c4bf7a4cbc9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210788"
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

*Şı*<br/>
SıNıFıNDAN TÜRETILMIŞ

*SessionClass*<br/>
Oturum nesnesi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[CreateSession](#createsession)|Veri kaynağı nesnesinden yeni bir oturum oluşturur ve yeni oluşturulan oturumdaki istenen arabirimi döndürür.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnelerinde zorunlu arabirim.

## <a name="idbcreatesessionimplcreatesession"></a><a name="createsession"></a>IDBCreateSessionImpl:: CreateSession

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
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
