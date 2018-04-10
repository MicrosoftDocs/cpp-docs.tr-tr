---
title: 'Kayıt kümesi: Kayıtları kilitleme (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 76d7ab2df01e485ffff70120609227b9fbae6ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-locking-records-odbc"></a>Kayıt Kümesi: Kayıtları Kilitleme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Kayıt kullanılabilir kilitleme tür](#_core_record.2d.locking_modes).  
  
-   [Kayıt sırasında güncelleştirmeleri kümenize kilitlemek nasıl](#_core_locking_records_in_your_recordset).  
  
 Veri kaynağı kaydı güncelleştirmek için bir kayıt kümesi kullandığınızda, başka bir kullanıcı kaydı aynı anda güncelleştirebilmesi için uygulamanızın kaydı kilitleyebilir. Aynı anda iki kullanıcı tarafından güncelleştirilen bir kaydı durumunu, sistem iki kullanıcı aynı anda bir kaydı güncelleştiremezsiniz garanti edemediği sürece tanımlanmamıştır.  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uyguladıysanız, bazı bilgiler uygulanmaz. Örneğin, çağıramazsınız **Düzenle** ve **güncelleştirme** üye işlevleri. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_record.2d.locking_modes"></a>Kayıt kilitleme modları  
 Veritabanı sınıfları iki sağlar [kayıt kilitleme modu](../../mfc/reference/crecordset-class.md#setlockingmode):  
  
-   İyimser kilitleme (varsayılan)  
  
-   Kötümser kilitleme  
  
 Kaydı güncelleme üç adımda oluşur:  
  
1.  İşlemi başlamadan [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevi.  
  
2.  Geçerli kaydın uygun alanları değiştirin.  
  
3.  Yönelik işlemi sonlandıran — ve normalde güncellemeyi uygularsınız — çağırarak [güncelleştirme](../../mfc/reference/crecordset-class.md#update) üye işlevi.  
  
 İyimser kilitleme, kayıt sırasında yalnızca veri kaynağı üzerinde kilitler **güncelleştirme** çağırın. Çok kullanıcılı ortamda İyimser kilitleme kullanırsanız, uygulama işlemelidir bir **güncelleştirme** hata koşulu. Kötümser kilitleme kilitler kaydı çağırmanız hemen **Düzenle** ve dek çağrısı bırakmaz **güncelleştirme** (hataları aracılığıyla gösterilir `CDBException` değeritarafındanmekanizması**Yanlış** tarafından döndürülen **güncelleştirme**). Kötümser kilitleme sahip diğer kullanıcılar için olası başarım kaybı aynı kaydı eş zamanlı erişim, uygulamanızın tamamlanana kadar beklemeniz gerekebilir çünkü **güncelleştirme** işlemi.  
  
##  <a name="_core_locking_records_in_your_recordset"></a>Kümenizde kayıtları kilitleme  
 Kayıt kümesi nesnesinin değiştirmek istiyorsanız [kilitleme modu](#_core_record.2d.locking_modes) varsayılandan çağırmadan önce modu değiştirmelisiniz **Düzenle**.  
  
#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>Kümeniz için geçerli kilitleme modunu değiştirmek için  
  
1.  Çağrı [CRecordset::pessimistic](../../mfc/reference/crecordset-class.md#setlockingmode) ya da belirterek üye işlevi **CRecordset::pessimistic** veya **SetLockingMode**.  
  
 Yeni kilitleme modu yeniden değiştirmek veya kayıt kümesi kapatılana kadar etkin kalır.  
  
> [!NOTE]
>  Görece daha az ODBC sürücüleri şu anda kötümser kilitleme destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: bir birleşim gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)