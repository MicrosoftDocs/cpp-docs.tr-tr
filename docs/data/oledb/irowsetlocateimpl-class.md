---
title: IRowsetLocateImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
ms.openlocfilehash: 06e860425215d9fde268b780c001301b14a1caa1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210437"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl Sınıfı

Bir satır kümesinden rastgele satırlar getiren OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) arabirimini uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,
   class BookmarkKeyType = LONG,
   class BookmarkType = LONG,
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<
       T,
       RowsetInterface,
       RowClass,
       MapClass>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`IRowsetLocateImpl`türetilen bir sınıf.

*RowsetInterface*<br/>
`IRowsetImpl`türetilen bir sınıf.

*RowClass*<br/>
`HROW`için depolama birimi.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm satır tutamaçları için depolama birimi.

*BookmarkKeyType*<br/>
Yer işaretinin, uzun veya bir dize gibi türü. Sıradan yer işaretleri en az iki bayt uzunluğunda olmalıdır. (Tek baytlık uzunluk, OLE DB [Standart yer işaretleri](/previous-versions/windows/desktop/ms712954(v=vs.85))`DBBMK_FIRST`, `DBBMK_LAST`ve `DBBMK_INVALID`için ayrılmıştır.)

*BookmarkType*<br/>
Yer işareti-veri ilişkilerini sürdürmek için eşleme mekanizması.

*BookmarkMapClass*<br/>
Yer işareti tarafından tutulan tüm satır tutamaçları için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[Compare](#compare)|İki yer işaretini karşılaştırır.|
|[GetRowsAt](#getrowsat)|Bir yer işaretinin içindeki bir uzaklığa göre belirtilen satırdan başlayarak satırları getirir.|
|[GetRowsByBookmark](#getrowsbybookmark)|Belirtilen yer işaretleriyle eşleşen satırları getirir.|
|[Yla](#hash)|Belirtilen yer işaretleri için karma değerleri döndürür.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_rgBookmarks](#rgbookmarks)|Yer işareti dizisi.|

## <a name="remarks"></a>Açıklamalar

`IRowsetLocateImpl`, [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) arabiriminin OLE DB Şablonları uygulamasıdır. `IRowsetLocate`, bir satır kümesinden rastgele satırları getirmek için kullanılır. Bu arabirimi uygulamayan bir satır kümesi `sequential` satır kümesidir. Satır kümesinde `IRowsetLocate` bulunduğunda, sütun 0 satır için yer işaretidir; Bu sütunu okumak, aynı satıra yeniden konumlandırmak için kullanılabilecek bir yer işareti değeri elde eder.

`IRowsetLocateImpl`, sağlayıcılarda yer işareti desteğini uygulamak için kullanılır. Yer işaretleri, tüketicinin bir satıra hızla dönmesini sağlayan yer tutuculardır (bir satır kümesinde dizinler) ve verilere yüksek hızlı erişim sağlar. Sağlayıcı, hangi yer işaretlerinin bir satırı benzersiz bir şekilde tanımlayabileceğini belirler. `IRowsetLocateImpl` yöntemleri kullanarak, yer işaretlerini karşılaştırabilir, satırları uzaklığa göre alabilir, satırları yer işaretine göre alabilir ve yer işaretleri için karma değerleri döndürebilir.

Bir satır kümesinde OLE DB yer işaretlerini desteklemek için, satır kümesinin bu sınıftan devralmasını sağlayın.

Yer işareti desteğini uygulama hakkında daha fazla bilgi için bkz. *Visual C++ Programcı Kılavuzu* 'Nda [yer işaretleri Için sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md) [ve](/previous-versions/windows/desktop/ms709728(v=vs.85)) *OLE DB Programcı 'nın* , Platform SDK 'daki başvurusu.

## <a name="irowsetlocateimplcompare"></a><a name="compare"></a>IRowsetLocateImpl:: Compare

İki yer işaretini karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmark1,
   const BYTE* pBookmark1,
   DBBKMARK cbBookmark2,
   const BYTE* pBookmark2,
   DBCOMPARE* pComparison);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IRowsetLocate:: Compare](/previous-versions/windows/desktop/ms709539(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Yer işaretlerinin ikisi de standart OLE DB tanımlı [Standart yer işareti](/previous-versions/windows/desktop/ms712954(v=vs.85)) (`DBBMK_FIRST`, `DBBMK_LAST`veya `DBBMK_INVALID`) olabilir. `pComparison` döndürülen değer iki yer işareti arasındaki ilişkiyi gösterir:

- DBCOMPARE_LT (`cbBookmark1` `cbBookmark2`öncedir.)

- DBCOMPARE_EQ (`cbBookmark1` `cbBookmark2`eşittir.)

- DBCOMPARE_GT (`cbBookmark1` `cbBookmark2`.)

- DBCOMPARE_NE (yer işaretleri eşit ve sıralı değildir.)

- DBCOMPARE_NOTCOMPARABLE (yer işaretleri karşılaştırılamıyor.)

## <a name="irowsetlocateimplgetrowsat"></a><a name="getrowsat"></a>IRowsetLocateImpl:: GetRowsAt

Bir yer işaretinin içindeki bir uzaklığa göre belirtilen satırdan başlayarak satırları getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,
   HCHAPTER hReserved2,
   DBBKMARK cbBookmark,
   const BYTE* pBookmark,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IRowsetLocate:: GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Bunun yerine imleç konumundan getirmek için [IRowset:: GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85))kullanın.

`IRowsetLocateImpl::GetRowsAt`, imleç konumunu değiştirmez.

## <a name="irowsetlocateimplgetrowsbybookmark"></a><a name="getrowsbybookmark"></a>IRowsetLocateImpl:: GetRowsByBookmark

Belirtilen yer işaretleriyle eşleşen bir veya daha fazla satırı getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const DBBKMARK rgcbBookmarks[],
   const BYTE* rgpBookmarks,
   HROW rghRows[],
   DBROWSTATUS* rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

*Hayrılmış*<br/>
'ndaki [IRowsetLocate:: GetRowsByBookmark](/previous-versions/windows/desktop/ms725420(v=vs.85))Için *hbölüm* parametresine karşılık gelir.

Diğer parametreler için *OLE DB Programcı başvurusunda* [IRowsetLocate:: GetRowsByBookmark](/previous-versions/windows/desktop/ms725420(v=vs.85)) başlığına bakın.

### <a name="remarks"></a>Açıklamalar

Yer işareti, tanımladığınız bir değer veya OLE DB [Standart yer işaretleri](/previous-versions/windows/desktop/ms712954(v=vs.85)) (`DBBMK_FIRST` veya `DBBMK_LAST`) olabilir. İmleç konumunu değiştirmez.

## <a name="irowsetlocateimplhash"></a><a name="hash"></a>IRowsetLocateImpl:: Hash

Belirtilen yer işaretleri için karma değerleri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmarks,
   const DBBKMARK* rgcbBookmarks[],
   const BYTE* rgpBookmarks[],
   DBHASHVALUE rgHashValues[],
   DBROWSTATUS rgBookmarkStatus[]);
```

#### <a name="parameters"></a>Parametreler

*Hayrılmış*<br/>
'ndaki [IRowsetLocate:: Hash](/previous-versions/windows/desktop/ms709697(v=vs.85))Için *hbölüm* parametresine karşılık gelir.

Diğer parametreler için *OLE DB Programcı başvurusunda* [IRowsetLocate:: Hash](/previous-versions/windows/desktop/ms709697(v=vs.85)) ' a bakın.

## <a name="irowsetlocateimplm_rgbookmarks"></a><a name="rgbookmarks"></a>IRowsetLocateImpl:: m_rgBookmarks

Yer işareti dizisi.

### <a name="syntax"></a>Sözdizimi

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate: IRowset](/previous-versions/windows/desktop/ms721190(v=vs.85))
[yer Işaretleri için sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[Yer İşaretleri](/previous-versions/windows/desktop/ms709728(v=vs.85))
