---
title: Iopenrowsetımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 72ca35ad6f2246a517c8a8d103c1a7f37e142534
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063438"
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

[IOpenRowset](/previous-versions/windows/desktop/ms716946) arabirimi için bir oturum nesnesi zorunludur. Bu açılır ve tek bir temel tablo veya dizini tablosundan tüm satırları içeren bir satır kümesi döndürür.

## <a name="createrowset"></a> Iopenrowsetımpl::createrowset

Bir satır kümesi nesnesi oluşturur. Doğrudan kullanıcı tarafından çağrılır değil. Bkz: [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724) içinde *OLE DB Programcının Başvurusu.*

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

Diğer parametreler için bkz: [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724) içinde *OLE DB Programcının Başvurusu.*

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

Bkz: [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ATLDB içinde bulunamadı. H Sağlayıcı oluşturduğunuzda ATL nesnesi Sihirbazı tarafından oluşturulur.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)