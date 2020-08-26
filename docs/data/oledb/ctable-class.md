---
title: CTable Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
ms.openlocfilehash: a967ef8fa2832afd56442ae4f988ba080d0b2872
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845646"
---
# <a name="ctable-class"></a>CTable Sınıfı

Basit bir satır kümesine (parametresi olmayan) doğrudan erişmek için bir yol sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class TAccessor = CNoAccessor,
            template <typename T> class TRowset = CRowset>
class CTable :
   public CAccessorRowset <TAccessor, TRowset>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıfı.

*TRowset*<br/>
Satır kümesi sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[Aç](#open)|Tabloyu açar.|

## <a name="remarks"></a>Açıklamalar

Bir satır kümesine erişmek için bir komutun nasıl yürütüleceği hakkında bilgi için bkz. [CCommand](../../data/oledb/ccommand-class.md) .

## <a name="ctableopen"></a><a name="open"></a> CTable:: Open

Tabloyu açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   LPCSTR szTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   DBID& dbid,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();
```

#### <a name="parameters"></a>Parametreler

*oturumuna*<br/>
'ndaki Tablonun açıldığı oturum.

*wszTableName*<br/>
'ndaki Açılacak tablonun adı, Unicode dizesi olarak geçirilir.

*szTableName*<br/>
'ndaki Açılacak tablonun adı, ANSI dizesi olarak geçirilir.

*DBID*<br/>
'ndaki `DBID` Açılacak tablo.

*pPropSet*<br/>
'ndaki Ayarlanacak özellikleri ve değerleri içeren bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisine yönelik bir işaretçi. Windows SDK *OLE DB Programcı başvurusu* Içindeki [özellik kümeleri ve özellik grupları](/previous-versions/windows/desktop/ms713696(v=vs.85)) bölümüne bakın. Varsayılan NULL değeri, özellik olmadığını belirtir.

*ulPropSets*<br/>
'ndaki *PPropset* bağımsız değişkeninde geçirilen [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapılarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla ayrıntı için *OLE DB Programcı başvurusunda* [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
