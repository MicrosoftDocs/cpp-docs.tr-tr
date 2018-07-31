---
title: 'Kayıt kümesi: Yer işaretleri ve Mutlak Konumlar (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 84288a5da836661bfda5720872008adf248fb246
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338333"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)
Bu konu MFC ODBC sınıflarına uygulanır.  
  
 Bir kayıt kümesi gittiğinizde, genellikle belirli bir kayda döndüren bir yol gerekir. Bir kaydın yer işareti ve mutlak konum iki yöntem sağlar.  
  
 Bu konu şunları açıklar:  
  
-   [Yer işaretlerini kullanma](#_core_bookmarks_in_mfc_odbc).  
  
-   [Mutlak Konumlar kullanarak geçerli bir kayıt kümesinin nasıl](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC içinde yer işaretleri  
 Bir yer işareti, bir kaydı benzersiz olarak tanımlar. Bir kayıt kümesi gittiğinizde, kayıtlar, kayıt kümesinden silinebilir olduğundan her zaman bir kaydın mutlak konumu üzerinde güvenemezsiniz. Bir kayıt konumu izlemek için en güvenilir yolu, yer işareti kullanmaktır. Sınıf `CRecordset` için üye işlevleri sağlar:  
  
-   Bir değişkene kaydetmek için yer işareti geçerli kaydın alma ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).  
  
-   Bir değişken daha önce kaydettiğiniz, yer işareti belirterek belirli bir kayda hızlı bir şekilde taşıma ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).  
  
 Aşağıdaki örnek, geçerli kaydı işaretleyin ve daha sonra döndürmek için bu üye işlevleri kullanılması gösterilmektedir:  
  
```cpp  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 Temel alınan veri türünden ayıklamak gerekmez [CDBVariant sınıfı](../../mfc/reference/cdbvariant-class.md) nesne. Değeriyle atayın `GetBookmark` ve bu yer işareti ile geri dönüp `SetBookmark`.  
  
> [!NOTE]
>  ODBC sürücüsü ve kayıt kümesi türüne bağlı olarak yer işaretleri desteklenmiyor olabilir. Yer işaretleri çağırarak desteklenen olup olmadığını kolayca belirleyebilirsiniz [CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Yer işaretleri destekleniyorsa, ayrıca, açıkça belirterek uygulamak seçtiğiniz gerekir `CRecordset::useBookmarks` seçeneğini [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) üye işlevi. Ayrıca, belirli kayıt işlemlerinden sonra yer işaretlerini sürekliliği denetlemeniz gerekir. Örneğin, varsa, `Requery` bir kayıt yer işaretleri artık geçerli olmayabilir. Çağrı [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) güvenli bir şekilde çağırıp çağırmayacağınızı denetlenecek `SetBookmark`.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC içinde mutlak konumlar  
 Yer işaretleri yanı sıra, sınıf `CRecordset` bir sıralı bir konum belirterek geçerli kayıtla ayarlamanıza olanak tanır. Bu, mutlak konumlandırma olarak adlandırılır.  
  
> [!NOTE]
>  Mutlak konumlandırma salt iletme kayıt kümeleri üzerinde mevcut değildir. Salt iletme kayıt kümeleri hakkında daha fazla bilgi için bkz: [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).  
  
 Geçerli kayıt işaretçiyi kullanarak mutlak konum taşımak için çağrı [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition). Bir değere gönderdiğinizde `SetAbsolutePosition`, sıralı konumu geçerli kaydı olur karşılık gelen kayıt.  
  
> [!NOTE]
>  Bir kaydın mutlak konumunu potansiyel olarak güvenilir değil. Kullanıcı kayıtları, kayıt kümesinden silerse, herhangi bir sonraki kayıt sıralı konumunu değiştirir. Yer işaretleri, geçerli kayıt taşımak için önerilen bir yöntemdir. Daha fazla bilgi için [MFC ODBC içinde yer işaretleri](#_core_bookmarks_in_mfc_odbc).  
  
 Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)