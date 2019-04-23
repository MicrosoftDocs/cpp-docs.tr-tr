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
ms.openlocfilehash: fab1ba2e496f4945eb56c0a67b833f6bf063404e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038780"
---
# <a name="ctable-class"></a>CTable Sınıfı

Bir basit satır kümesine (parametresi olmayan) doğrudan erişim için bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CNoAccessor,
            template <typename T> class TRowset = CRowset>
class CTable :
   public CAccessorRowset <TAccessor, TRowset>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Bir erişimci sınıfı.

*CRowset*<br/>
Bir satır kümesi sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[açın](#open)|Tablo açılır.|

## <a name="remarks"></a>Açıklamalar

Bkz: [CCommand](../../data/oledb/ccommand-class.md) bir satır kümesine erişmek için bir komutu nasıl çalıştıracağını hakkında bilgi için.

## <a name="open"></a> CTable::Open

Tablo açılır.

### <a name="syntax"></a>Sözdizimi

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

*Oturumu*<br/>
[in] Tablonun en iyi duruma açıldığında oturumu.

*wszTableName*<br/>
[in] Açmak için tablonun adını bir Unicode dize olarak geçirildi.

*szTableName*<br/>
[in] Açmak için tablonun adı bir ANSI dizesine geçirildi.

*dbid*<br/>
[in] `DBID` Açmak için tablo.

*pPropSet*<br/>
[in] Bir dizi işaretçi [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) özelliklerini ve değerlerini ayarlamak için içeren yapılar. Bkz: [özellik kümeleri ve özellik gruplarını](/previous-versions/windows/desktop/ms713696(v=vs.85)) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde. Varsayılan değeri NULL özellik belirtir.

*ulPropSets*<br/>
[in] Sayısını [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları geçirilen *pPropSet* bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla ayrıntı için [IOpenRowset::OpenRowset](/previous-versions/windows/desktop/ms716724(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)