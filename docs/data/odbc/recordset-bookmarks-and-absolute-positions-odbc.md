---
title: "Kayıt kümesi: Yer işaretleri ve Mutlak Konumlar (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetAbsolutePosition
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b206e5d09d86613af0585df7510b0f88397984a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Kayıt kümesi içinde gezinirken genellikle belirli bir kayda döndüren bir yol gerekir. Bir kaydın yer işareti ve mutlak konum iki tür yöntem sağlar.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Yer işaretlerini kullanma](#_core_bookmarks_in_mfc_odbc).  
  
-   [Mutlak Konumlar kullanılarak geçerli kayıt ayarlama](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a>MFC ODBC içinde yer işaretleri  
 Yer işareti bir kaydı benzersiz şekilde tanımlar. Kayıt kümesi içinde gittiğinizde kayıtlar kayıt kümesinden silinebilir çünkü bir kaydın mutlak konumuna her zaman yeterli olmaz. Bir kaydın konumunu izlemek için güvenilir bir yolu, yer işareti kullanmaktır. Sınıf `CRecordset` için üye işlevleri sağlar:  
  
-   Bir değişkende kaydedebilmeniz için geçerli kaydın yer alma ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).  
  
-   Bir değişkende daha önce kaydettiğiniz kendi yer işareti belirterek belirli bir kayda hızla taşıma ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).  
  
 Aşağıdaki örnek, bu üye işlevleri geçerli kaydı işaretleyin ve daha sonra döndürmek için nasıl kullanılacağı gösterilmektedir:  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 Temel alınan veri türünden ayıklamak gerekmez [CDBVariant sınıfı](../../mfc/reference/cdbvariant-class.md) nesnesi. Değeriyle atayın `GetBookmark` ve o yer işareti ile geri dönüp `SetBookmark`.  
  
> [!NOTE]
>  Yer işaretleri ODBC sürücüsü ve kayıt kümesi türüne bağlı olarak desteklenmiyor olabilir. Yer işaretleri çağırarak desteklenip desteklenmediğini kolayca belirleyebilir [CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Yer işaretleri destekleniyorsa, ayrıca, açıkça bunları belirterek uygulama seçmeniz gerekir **CRecordset::useBookmarks** seçeneğini [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) üye işlevi. Yer işaretleri Kalıcılık belirli kayıt işlemlerinden sonra de denetlemeniz gerekir. Örneğin, varsa, **Requery** bir kayıt yer işaretleri artık geçerli olabilir. Çağrı [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) güvenle çağırabilirsiniz olup olmadığını denetlemek için `SetBookmark`.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a>MFC ODBC içinde mutlak konumlar  
 Yer işaretleri yanı sıra, sınıf `CRecordset` bir sıralı bir konum belirterek geçerli kayıt ayarlamanıza olanak tanır. Bu, mutlak konumlandırma olarak adlandırılır.  
  
> [!NOTE]
>  Mutlak konumlandırma salt iletme kayıt kümeleri üzerinde kullanılabilir değil. Salt iletme kayıt kümeleri hakkında daha fazla bilgi için bkz: [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).  
  
 Mutlak konum kullanarak geçerli kayıt işaretçisi taşımak için arama [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition). Bir değere geçirdiğiniz zaman `SetAbsolutePosition`, sıralı konumu geçerli kaydı olur karşılık gelen kayıt.  
  
> [!NOTE]
>  Bir kaydın mutlak konumu potansiyel olarak güvenilir değil. Kullanıcı kayıt kümesinden kayıtları silerse, herhangi bir sonraki kaydının sıralı konumunu değiştirir. Yer işaretleri geçerli kaydın taşınması için önerilen bir yöntemdir. Daha fazla bilgi için bkz: [MFC ODBC içinde yer işaretleri](#_core_bookmarks_in_mfc_odbc).  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için bkz: [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)