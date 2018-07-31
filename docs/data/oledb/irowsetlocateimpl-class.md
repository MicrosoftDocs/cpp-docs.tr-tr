---
title: IRowsetLocateImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0cb4531f1a86d61b72363669d0f722f8dcf204d3
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338395"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl Sınıfı
OLE DB uygulayan [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx) arabirimi, bir satır kümesinden rastgele satırları getirir.  
  
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
 *T*  
 Öğesinden türetilen bir sınıf `IRowsetLocateImpl`.  
  
 *RowsetInterface*  
 Öğesinden türetilen bir sınıf `IRowsetImpl`.  
  
 *RowClass*  
 Depolama birimi için `HROW`.  
  
 *MapClass*  
 Sağlayıcı tarafından tutulan tüm olan satır işleyicilerini depolama birimi.  
  
 *BookmarkKeyType*  
 UZUN veya dize gibi yer işareti türü. Sıradan yer işaretleri, en az iki bayt uzunluğunu olması gerekir. (OLE DB için tek baytlık bir uzunluk ayrılmıştır [standart yer işaretleri](https://msdn.microsoft.com/library/ms712954.aspx)`DBBMK_FIRST`, `DBBMK_LAST`, ve `DBBMK_INVALID`.)  
  
 *BookmarkType*  
 Yer işareti veri ilişkileri sürdürmek için eşleme mekanizması.  
  
 *BookmarkMapClass*  
 Yer işareti tarafından tutulan tüm olan satır işleyicilerini depolama birimi.  

## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[Karşılaştırma](#compare)|İki yer işaretleri karşılaştırır.|  
|[GetRowsAt](#getrowsat)|Bir yer işareti uzaklığı tarafından belirtilen satır ile başlayan satırları getirir.|  
|[GetRowsByBookmark](#getrowsbybookmark)|Belirtilen yer işaretleri eşleşen satırları getirir.|  
|[Karma](#hash)|Belirtilen yer işaretleri için değerleri verir karma.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_rgBookmarks](#rgbookmarks)|Yer işaretleri dizisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IRowsetLocateImpl` OLE DB Şablonları uygulamasıdır [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx) arabirimi. `IRowsetLocate` rastgele satırlarını satır kümesinden alması için kullanılır. Bu arabirimini uygulamıyor bir satır kümesi bir `sequential` satır kümesi. Zaman `IRowsetLocate` var olan bir satır kümesinde, 0 sütun satırlar için yer işareti; bu sütun okuma aynı satıra yeniden konumlandırmak için kullanılan bir yer işareti değeri elde.  
  
 `IRowsetLocateImpl` yer işareti desteği sağlayıcıları uygulamak için kullanılır. Yer işaretleri verilere yüksek hızlı erişim sağlayan bir satır için hızlı bir şekilde geri dönmek tüketici sağlayan (bir satır kümesi dizinlerini) yer tutuculardır. Ne benzersiz olarak yer işaretleri için sağlayıcı belirleyen bir satırı tanımlamak. Kullanarak `IRowsetLocateImpl` yöntemleri, yer işaretleri karşılaştırabilirsiniz, getirme satırları göre uzaklığı, yer işareti, getirme satır ve yer işaretleri için karma değerlerini döndürür.  
  
 OLE DB yer işaretleri bir satır kümesinde desteklemek için bu sınıftan devralınan satır kümesi olun.  
  
 Yer işareti desteği sağlama hakkında daha fazla bilgi için bkz: [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md) içinde *Visual C++ Programcı Kılavuzu* ve [yer işaretleri](https://msdn.microsoft.com/library/ms709728.aspx) içinde*OLE DB Programcının Başvurusu* Platform SDK içindeki.  

## <a name="compare"></a> IRowsetLocateImpl::COMPARE
İki yer işaretleri karşılaştırır.  
  
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
 Bkz: [IRowsetLocate::Compare](https://msdn.microsoft.com/library/ms709539.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdakilerden birini yer işaretleri standart olabilir OLE DB tanımlı [standart yer işareti](https://msdn.microsoft.com/library/ms712954.aspx) (`DBBMK_FIRST`, `DBBMK_LAST`, veya `DBBMK_INVALID`). Döndürülen değer `pComparison` iki yer işaretleri arasındaki ilişkiyi gösterir:  
  
-   DBCOMPARE_LT (`cbBookmark1` önce `cbBookmark2`.)  
  
-   DBCOMPARE_EQ (`cbBookmark1` eşittir `cbBookmark2`.)  
  
-   DBCOMPARE_GT (`cbBookmark1` sonra `cbBookmark2`.)  
  
-   DBCOMPARE_NE (yer işaretleri eşit ve sıralı değildir.)  
  
-   DBCOMPARE_NOTCOMPARABLE (yer işaretleri karşılaştırılamaz.) 

## <a name="getrowsat"></a> IRowsetLocateImpl::GetRowsAt
Bir yer işareti uzaklığı tarafından belirtilen satır ile başlayan satırları getirir.  
  
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
 Bkz: [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/library/ms723031.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 İmleç konumundan yerine getirmek için kullanmak [IRowset::GetRowsAt](https://msdn.microsoft.com/library/ms723031.aspx).  
  
 `IRowsetLocateImpl::GetRowsAt` imleç konumu değiştirmez. 

## <a name="getrowsbybookmark"></a> IRowsetLocateImpl::getrowsbybookmark
Belirtilen yer işaretleri uyan bir veya daha fazla satırları getirir.  
  
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
 *hReserved*  
 [in] Karşılık gelen *hChapter* parametresi [IRowsetLocate::GetRowsByBookmark](https://msdn.microsoft.com/library/ms725420.aspx).  
  
 Diğer parametreler için bkz: [IRowsetLocate::GetRowsByBookmark](https://msdn.microsoft.com/library/ms725420.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Yer işareti, tanımladığınız bir değer veya bir OLE DB olabilir [standart yer işaretleri](https://msdn.microsoft.com/library/ms712954.aspx) (`DBBMK_FIRST` veya `DBBMK_LAST`). İmleç konumu değiştirmez.  

## <a name="hash"></a> IRowsetLocateImpl::hash
Belirtilen yer işaretleri için değerleri verir karma.  
  
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
 *hReserved*  
 [in] Karşılık gelen *hChapter* parametresi [IRowsetLocate::Hash](https://msdn.microsoft.com/library/ms709697.aspx).  
  
 Diğer parametreler için bkz: [IRowsetLocate::Hash](https://msdn.microsoft.com/library/ms709697.aspx) içinde *OLE DB Programcının Başvurusu*.  

## <a name="rgbookmarks"></a> IRowsetLocateImpl::m_rgbookmarks
Yer işaretleri dizisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/library/ms721190.aspx)   
 [Yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md)   
 [Yer İşaretleri](https://msdn.microsoft.com/library/ms709728.aspx)