---
title: IOpenRowsetImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
ms.openlocfilehash: 6f0dfb90b0ea79e115f459968558e48ae9827e40
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029099"
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl Sınıfı

Uygulamasını sağlar `IOpenRowset` arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class SessionClass>
class IOpenRowsetImpl : public IOpenRowset
```

### <a name="parameters"></a>Parametreler

*SessionClass*<br/>
Sınıfınız, türetilen `IOpenRowsetImpl`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CreateRowset](#createrowset)|Bir satır kümesi nesnesi oluşturur. Doğrudan kullanıcı tarafından çağrılır değil.|
|[OpenRowset](#openrowset)|Açar ve tek bir temel tablo veya dizini tablosundan tüm satırları içeren bir satır kümesi döndürür. (ATLDB içinde değil. H)|

## <a name="remarks"></a>Açıklamalar

[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85)) arabirimi için bir oturum nesnesi zorunludur. Bu açılır ve tek bir temel tablo veya dizini tablosundan tüm satırları içeren bir satır kümesi döndürür.

## <a name="createrowset"></a> Iopenrowsetımpl::createrowset

Bir satır kümesi nesnesi oluşturur. Doğrudan kullanıcı tarafından çağrılır değil. Bkz: [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) içinde *OLE DB Programcının Başvurusu.*

### <a name="syntax"></a>Sözdizimi

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
Kullanıcının satır kümesi sınıfı temsil eden bir şablon sınıfı üyesinin. Genellikle sihirbaz tarafından oluşturulan.

*pRowsetObj*<br/>
[out] Bir satır kümesi nesnesi işaretçisi. Genellikle bu parametre kullanılmaz, ancak, daha fazla iş satır kümesinde bir COM nesnesine iletmeden önce gerçekleştirmeniz gerekirse kullanılabilir. Ömrünü *pRowsetObj* bağlı olan *ppRowset*.

Diğer parametreler için bkz: [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) içinde *OLE DB Programcının Başvurusu.*

## <a name="openrowset"></a> Iopenrowsetımpl::OPENROWSET

Açar ve tek bir temel tablo veya dizini tablosundan tüm satırları içeren bir satır kümesi döndürür.

### <a name="syntax"></a>Sözdizimi

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

Bkz: [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ATLDB içinde bulunamadı. H Sağlayıcı oluşturduğunuzda ATL nesnesi Sihirbazı tarafından oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)