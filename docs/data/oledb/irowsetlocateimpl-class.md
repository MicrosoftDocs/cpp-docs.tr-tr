---
title: "IRowsetLocateImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetLocateImpl
dev_langs: C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff76d78cd3f624e3bdb0d21af550a340a2aa498e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl Sınıfı
OLE DB uygulayan [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) rasgele satır satır kümesinden getirir arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >  
>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
   T,   
   RowsetInterface,   
   RowClass,   
   MapClass  
>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilmiş bir sınıf `IRowsetLocateImpl`.  
  
 `RowsetInterface`  
 Öğesinden türetilmiş bir sınıf `IRowsetImpl`.  
  
 `RowClass`  
 Depolama birimi için **HROW**.  
  
 `MapClass`  
 Sağlayıcı tarafından tutulan tüm satır işleyicilerini depolama birimi.  
  
 `BookmarkKeyType`  
 Bir uzun veya dize gibi yer türü. Sıradan yer işaretleri, en az iki bayt uzunlukta olmalıdır. (Tek baytlı uzunluğu OLE DB için ayrılmış [standart yer işaretleri](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK_FIRST**, **DBBMK_LAST**, ve **DBBMK_INVALID**.)  
  
 `BookmarkType`  
 Yer işareti veri ilişkileri korumak için eşleme mekanizması.  
  
 `BookmarkMapClass`  
 Yer işareti tarafından tutulan tüm satır işleyicilerini depolama birimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[Karşılaştırma](../../data/oledb/irowsetlocateimpl-compare.md)|İki yer işaretleri karşılaştırır.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|Yer işareti uzaklık tarafından belirtilen satır ile başlayan satırlar getirir.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|Belirtilen yer işaretleri eşleşen satırları getirir.|  
|[Karma](../../data/oledb/irowsetlocateimpl-hash.md)|Karma değeri belirtilen yer işaretleri için döndürür.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|Yer işaretleri dizisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IRowsetLocateImpl`OLE DB Şablonları uygulamasıdır [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) arabirimi. `IRowsetLocate`bir satır kümesinden rasgele satırlarını alması için kullanılır. Bu arabirimini uygulamayan bir satır kümesi bir `sequential` satır kümesi. Zaman `IRowsetLocate` var olan bir satır kümesinde sütun 0 satırların yer işareti; bu sütun okuma aynı satır yeniden konumlandırmak için kullanılan bir yer işareti değeri edineceği.  
  
 `IRowsetLocateImpl`yer işareti desteği sağlayıcıları uygulamak için kullanılır. Yer işaretleri yüksek hızlı veri izin veren bir satır için hızlı bir şekilde döndürülecek tüketici sağlayan yer tutucuları (bir satır kümesi dizinlerini) var. Ne benzersiz olarak yer işaretleri için sağlayıcı belirleyen bir satır tanımlayın. Kullanarak `IRowsetLocateImpl` yöntemleri yer işaretleri karşılaştırabilirsiniz, fetch satır göre uzaklığı, yer işareti, fetch satırlar ve yer işaretleri için karma değerleri döndürür.  
  
 OLE DB yer işaretleri bir satır kümesinde desteklemek için bu sınıftan devralınan satır kümesi olun.  
  
 Yer işareti desteği uygulama hakkında daha fazla bilgi için bkz: [yer işaretleri için sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md) içinde *Visual C++ Programcı Kılavuzu* ve [yer işaretleri](https://msdn.microsoft.com/en-us/library/ms709728.aspx) içinde*OLE DB Programcının Başvurusu* Platform SDK.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [Yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md)   
 [Yer işaretleri](https://msdn.microsoft.com/en-us/library/ms709728.aspx)