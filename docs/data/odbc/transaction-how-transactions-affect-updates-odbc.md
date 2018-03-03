---
title: "İşlem: İşlemlerin güncelleştirmeleri (ODBC) etkilemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59eb8aecbf2dd2138c8a0469d71364b55fd82774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)
Güncelleştirmeleri [veri kaynağı](../../data/odbc/data-source-odbc.md) düzenleme arabelleği (işlemleri dışında kullanılan aynı yöntemi) kullanımıyla işlemleri sırasında yönetilir. Kayıt alan veri üyeleri topluca geçici olarak sırasında kayıt yedekler geçerli kaydı içeren düzenleme arabelleği görevi gören bir `AddNew` veya **Düzenle**. Sırasında bir **silmek** işlemi, geçerli kayıt yedeklenmez bir işlem içinde. Düzenleme arabelleği ve nasıl geçerli kayıt güncelleştirmeleri depolamak hakkında daha fazla bilgi için bkz: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız, çağıramazsınız `AddNew`, **Düzenle**, veya **silmek**. Bunun yerine, veri kaynağı güncelleştirmelerini gerçekleştirmek için kendi işlevlerinizi yazmanız gerekir. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 İşlemleri sırasında `AddNew`, **Düzenle**, ve **silmek** işlem yürütülmeli veya geri alındı. Etkilerini **CommitTrans** ve **geri alma** geçerli kaydın düzenleme ara yüklenmemesine neden olabilir. Geçerli kayıt uygun şekilde geri yüklendiğinden emin olmak için anlamak önemlidir nasıl **CommitTrans** ve **geri alma** üye işlevlerini `CDatabase` güncellemeişlevleriylebirlikteçalışma`CRecordset`.  
  
##  <a name="_core_how_committrans_affects_updates"></a>CommitTrans Güncellemeleri nasıl etkiler  
 Aşağıdaki tabloda etkilerini açıklar **CommitTrans** hareketleri.  
  
### <a name="how-committrans-affects-updates"></a>CommitTrans Güncellemeleri nasıl etkiler  
  
|Çalışma|Veri kaynağının durumu|  
|---------------|---------------------------|  
|`AddNew`ve **güncelleştirme**ve ardından **CommitTrans**|Yeni kayıt veri kaynağına eklenir.|  
|`AddNew`(olmadan **güncelleştirme**) ve ardından **CommitTrans**|Yeni kayıt kaybolur. Kaydı veri kaynağına eklenmedi.|  
|**Düzen** ve **güncelleştirme**ve ardından **CommitTrans**|Veri kaynağına kaydedilen düzenlemeler.|  
|**Düzen** (olmadan **güncelleştirme**) ve ardından **CommitTrans**|Kayıt düzenlemeleri kaybolur. Kayıt veri kaynağında değişmeden kalır.|  
|**Silme** sonra **CommitTrans**|Veri kaynağından silinen kayıtlar.|  
  
##  <a name="_core_how_rollback_affects_updates"></a>Rollback işlemleri nasıl etkiler  
 Aşağıdaki tabloda etkilerini açıklar **geri alma** hareketleri.  
  
### <a name="how-rollback-affects-transactions"></a>Rollback işlemleri nasıl etkiler  
  
|Çalışma|Geçerli kayıt durumu|Ayrıca gerekir|Veri kaynağının durumu|  
|---------------|------------------------------|-------------------|---------------------------|  
|`AddNew`ve **güncelleştirme**, ardından **geri alma**|Geçerli kayıt içeriğini yeni bir kayıt için yer açmak için geçici olarak depolanır. Yeni kayıt düzenleme arabelleğine girilir. Sonra **güncelleştirme** çağrılır, geçerli kayıt düzenleme ara geri.||Veri kaynağına yapılan ekleme **güncelleştirme** ters çevrilir.|  
|`AddNew`(olmadan **güncelleştirme**), ardından **geri alma**|Geçerli kayıt içeriğini yeni bir kayıt için yer açmak için geçici olarak depolanır. Düzen arabellek yeni kaydı içerir.|Çağrı `AddNew` yeniden düzenleme arabelleği boş, yeni bir kayıt için geri yüklemek için. Veya arama **taşıma**eski değerleri düzenleme ara geri yüklemek için (0).|Çünkü **güncelleştirme** çağrılmadı, veri kaynağına yapılan bir değişiklik yoktur.|  
|**Düzen** ve **güncelleştirme**, ardından **geri alma**|Geçerli kayıt düzenlenmemiş sürümü geçici olarak depolanır. Düzenlemeler düzenleme arabelleği içeriğini yapılır. Sonra **güncelleştirme** çağrıldığında düzenlenmemiş kaydın sürüm hala geçici olarak depolanır.|*Dynaset*: geçerli kayıttan kaydın düzenlenmemiş sürüm düzenleme ara geri yüklemek için geri gelin.<br /><br /> *Anlık Görüntü*: çağrı **Requery** veri kaynağından kayıt kümesi yenilenecek.|Veri kaynağı tarafından yapılan değişiklikleri **güncelleştirme** ters çevrilir.|  
|**Düzen** (olmadan **güncelleştirme**), ardından **geri alma**|Geçerli kayıt düzenlenmemiş sürümü geçici olarak depolanır. Düzenlemeler düzenleme arabelleği içeriğini yapılır.|Çağrı **Düzenle** yeniden düzenleme ara belleğine kaydın düzenlenmemiş sürümünü geri yüklemek için.|Çünkü **güncelleştirme** çağrılmadı, veri kaynağına yapılan bir değişiklik yoktur.|  
|**Silme** sonra **geri alma**|Geçerli kayıt içeriği silinir.|Çağrı **Requery** veri kaynağından geçerli kayıt içeriğini geri yüklemek için.|Veri kaynağı silme işlemi ters çevrilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem (ODBC)](../../data/odbc/transaction-odbc.md)   
 [İşlem (ODBC)](../../data/odbc/transaction-odbc.md)   
 [İşlem: (ODBC) kayıt kümesinde işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)