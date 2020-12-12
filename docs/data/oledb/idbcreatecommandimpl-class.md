---
description: 'Daha fazla bilgi edinin: IDBCreateCommandImpl sınıfı'
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
ms.openlocfilehash: aaa9e84b66bd8bcb93fa418eed56a3cdadd31d6f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287352"
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

### <a name="syntax"></a>Sözdizimi

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
