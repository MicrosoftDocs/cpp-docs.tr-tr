---
title: IDBCreateCommandImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: 4b8c713bcf00cd68f9621b8c112d4d6fd27aec01
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556407"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl Sınıfı

Bir uygulamasını sağlar [IDBCreateCommand](https://docs.microsoft.com/previous-versions/windows/desktop/ms711625(v=vs.85)) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Oturum nesnesi türetilen `IDBCreateCommandImpl`.

*CommandClass*<br/>
Komutu sınıfınızın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[CreateCommand](#createcommand)|Yeni bir komut oluşturur.|

## <a name="remarks"></a>Açıklamalar

Yeni bir komut almak için oturum nesnesi üzerinde isteğe bağlı bir arabirim.

## <a name="createcommand"></a> Idbcreatecommandımpl::CreateCommand

Yeni bir komut oluşturur ve istenen arabirim döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IDBCreateCommand::CreateCommand](https://docs.microsoft.com/previous-versions/windows/desktop/ms709772(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin `IDBCreateCommand::CreateCommand`:

|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)