---
title: IOpenRowsetImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
ms.openlocfilehash: a3c94c75db21218aae1205bf9c5c379ab772a7f8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843722"
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl Sınıfı

Arabirim için uygulama sağlar `IOpenRowset` .

## <a name="syntax"></a>Söz dizimi

```cpp
template <class SessionClass>
class IOpenRowsetImpl : public IOpenRowset
```

### <a name="parameters"></a>Parametreler

*SessionClass*<br/>
Sınıfınız, öğesinden türetilir `IOpenRowsetImpl` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[CreateRowset](#createrowset)|Satır kümesi nesnesi oluşturur. Doğrudan Kullanıcı tarafından çağrılmaz.|
|[OpenRowset](#openrowset)|' İ açar ve tek bir temel tablodan veya dizindeki tüm satırları içeren bir satır kümesi döndürür. (ATLDB 'de değil. Olsun|

## <a name="remarks"></a>Açıklamalar

[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85)) arabirimi bir oturum nesnesi için zorunludur. Açılır ve tek bir temel tablodaki veya dizindeki tüm satırları içeren bir satır kümesi döndürür.

## <a name="iopenrowsetimplcreaterowset"></a><a name="createrowset"></a> IOpenRowsetImpl:: CreateRowset

Satır kümesi nesnesi oluşturur. Doğrudan Kullanıcı tarafından çağrılmaz. *OLE DB Programcı başvurusunda* [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) öğesine bakın.

### <a name="syntax"></a>Söz dizimi

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   DBID* pTableID,
   DBID* pIndexID,
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>Parametreler

*RowsetClass*<br/>
Kullanıcının satır kümesi sınıfını temsil eden bir şablon sınıfı üyesi. Genellikle sihirbaz tarafından oluşturulur.

*pRowsetObj*<br/>
dışı Satır kümesi nesnesi işaretçisi. Genellikle bu parametre kullanılmaz, ancak bir COM nesnesine geçirmeden önce satır kümesinde daha fazla iş gerçekleştirmeniz gerekiyorsa kullanılabilir. *PRowsetObj* ömrü *ppRowset*ile ilişkilidir.

Diğer parametreler için *OLE DB Programcı başvurusunda* [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) bölümüne bakın.

## <a name="iopenrowsetimplopenrowset"></a><a name="openrowset"></a> IOpenRowsetImpl:: OpenRowset

' İ açar ve tek bir temel tablodan veya dizindeki tüm satırları içeren bir satır kümesi döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,
   DBID* pTableID,
   DBID* pIndexID,
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) öğesine bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ATLDB içinde bulunamadı. Olsun. Bir sağlayıcı oluşturduğunuzda ATL nesne Sihirbazı tarafından oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
