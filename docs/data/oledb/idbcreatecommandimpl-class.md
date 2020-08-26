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
ms.openlocfilehash: b7b658b2b365eb84a39ae94cef7c77e18d7bd4a0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845555"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl Sınıfı

[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesinden türetilen oturum nesnesi `IDBCreateCommandImpl` .

*CommandClass*<br/>
Komut sınıfınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

| Ad | Açıklama |
|-|-|
|[CreateCommand](#createcommand)|Yeni bir komut oluşturur.|

## <a name="remarks"></a>Açıklamalar

Yeni bir komut almak için oturum nesnesi üzerinde isteğe bağlı bir arabirim.

## <a name="idbcreatecommandimplcreatecommand"></a><a name="createcommand"></a> IDBCreateCommandImpl:: CreateCommand

Yeni bir komut oluşturur ve istenen arabirimi döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IDBCreateCommand:: CreateCommand](/previous-versions/windows/desktop/ms709772(v=vs.85)) öğesine bakın.

Bazı parametreler, ' de açıklanan farklı adların *OLE DB Programcı Başvuru* parametrelerine karşılık gelir `IDBCreateCommand::CreateCommand` :

|OLE DB şablon parametreleri|*OLE DB Programcı Başvuru* parametreleri|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
