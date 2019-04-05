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
ms.openlocfilehash: ae59abc542a4599d289c099801fc34d56b2b13d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028541"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl Sınıfı

Bir uygulamasını sağlar [IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85)) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>Parametreler

*T*<br/>
TÜRETİLMİŞ SINIFINIZIN

*SessionClass*<br/>
Oturum nesnesi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[CreateSession](#createsession)|Veri kaynağı nesnesinin yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirim döndürür.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı nesneleri üzerinde zorunlu bir arabirim.

## <a name="createsession"></a> Idbcreatesessionımpl::createsession

Veri kaynağı nesnesinin yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirim döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IDBCreateSession::CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)