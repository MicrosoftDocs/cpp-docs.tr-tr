---
title: IDBCreateCommandImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: 4a4978401ba90e3a7a91ac40cc1b0668adf12ee8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210723"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl Sınıfı

[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`IDBCreateCommandImpl`türetilen oturum nesnesi.

*CommandClass*<br/>
Komut sınıfınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[CreateCommand](#createcommand)|Yeni bir komut oluşturur.|

## <a name="remarks"></a>Açıklamalar

Yeni bir komut almak için oturum nesnesi üzerinde isteğe bağlı bir arabirim.

## <a name="idbcreatecommandimplcreatecommand"></a><a name="createcommand"></a>IDBCreateCommandImpl:: CreateCommand

Yeni bir komut oluşturur ve istenen arabirimi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IDBCreateCommand:: CreateCommand](/previous-versions/windows/desktop/ms709772(v=vs.85)) öğesine bakın.

Bazı parametreler, `IDBCreateCommand::CreateCommand`açıklanan farklı adların *OLE DB Programcı Başvuru* parametrelerine karşılık gelir:

|OLE DB şablon parametreleri|*OLE DB Programcı Başvuru* parametreleri|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
