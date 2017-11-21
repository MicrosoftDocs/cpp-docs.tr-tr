---
title: "Kayıt kümesi: Kayıt kümeleri Güncelleştirmesi (ODBC) nasıl kayıtları. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5ca360ce914fea69163a400df2f9bc00750920e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bir veri kaynağından kayıtları seçmek için kendi yeteneği yanı sıra kayıt kümeleri (isteğe bağlı) güncelleştirin veya seçili kayıtları silebilir veya yeni kayıtlar ekleme. Üç etken bir kayıt kümesinin güncellenebilirliğini belirler: bağlı veri kaynağı güncelleştirilebilir olup, bir kayıt kümesi nesnesi ve oluşturulan SQL oluştururken belirlediğiniz seçenekleri.  
  
> [!NOTE]
>  SQL, `CRecordset` nesne temel kümenizin güncellenebilirliğini etkileyebilir. Örneğin, SQL bir birleşim içeriyorsa veya **GROUP BY** yan tümcesi, MFC ayarlar güncellenebilirliğini **FALSE**.  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Bu konuda açıklanmaktadır:  
  
-   [Kayıt kümesi güncellemede sizin rolünüz](#_core_your_role_in_recordset_updating) ve ne framework sizin için yapar.  
  
-   [Kayıt düzenleme arabelleği olarak](#_core_the_edit_buffer) ve [dinamik kümeler ve anlık görüntüleri arasındaki farklar](#_core_dynasets_and_snapshots).  
  
 [Kayıt kümesi: Nasıl AddNew, düzenleme ve silme çalışma (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) açısından kayıt kümesinin bu işlevlerin eylemleri açıklar.  
  
 [Kayıt kümesi: Daha fazla ilgili güncelleştirmeleri (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) işlemlerin güncelleştirmeleri etkilemesi, bir kayıt kümesi kapatma veya kaydırma güncelleştirmeler sürüyor nasıl etkiler ve yaptığınız güncelleştirmeler diğer güncelleştirmeleri ile nasıl etkileşim açıklayarak kayıt kümesi güncelleştirme hikayesi tamamlar Kullanıcılar.  
  
##  <a name="_core_your_role_in_recordset_updating"></a>Kayıt kümesi güncellemede sizin rolünüz  
 Aşağıdaki tabloda, eklemek, düzenlemek veya framework sizin için ne yaptığını birlikte kayıtları silmek için kayıt kümeleri kullanarak rolünüze gösterir.  
  
### <a name="recordset-updating-you-and-the-framework"></a>Kayıt kümesi güncelleştiriliyor: Siz ve Framework  
  
|Bunun için,|Çerçeve|  
|---------|-------------------|  
|Veri kaynağı güncellenebilir (veya eklenebilir) olup olmadığını belirler.|Kaynakları [CDatabase](../../mfc/reference/cdatabase-class.md) veri kaynağının güncellenebilirliğini veya eklenebilirliğini denetlemek için üye işlevleri.|  
|Güncelleştirilebilir bir kayıt kümesi (herhangi bir türde) açın.||  
|Kayıt kümesi çağırarak güncelleştirilebilir olup `CRecordset` işlevleri gibi güncelleştirme `CanUpdate` veya `CanAppend`.||  
|Kayıt kümesi eklemek, düzenlemek ve kayıtları silmek için üye işlevleri çağırma.|Kayıt kümesi nesneniz ve veri kaynağı arasında veri değişimi mekanizması yönetir.|  
|İsteğe bağlı olarak, güncelleştirme işlemini denetlemek için işlemleri kullanın.|Kaynakları `CDatabase` işlemleri desteklemek için üye işlevleri.|  
  
 İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_the_edit_buffer"></a>Düzenleme arabelleği  
 Topluca alındığında, bir kayıt kümesi alan veri üyeleri bir kayıt içeren bir düzenleme arabellek hizmet — geçerli kayıt. Güncelleştirme işlemleri bu arabellek geçerli kayıt üzerinde çalışmak için kullanın.  
  
-   Bir kayıt eklediğinizde, düzenleme arabelleği yeni bir kayıt oluşturmak için kullanılır. Kayıt eklemeyi bitirdiğinizde, daha önce geçerli kayıt tekrar geçerli olur.  
  
-   Güncelleştirmesi yaptığınızda (düzenleme) bir kaydı düzenleme arabelleği kayıt alan veri üyeleri için yeni değerleri ayarlamak için kullanılır. Güncelleştirmeyi tamamladığınızda, güncelleştirilmiş kayıt hala geçerli olur.  
  
 Çağırdığınızda [AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Düzenle](../../mfc/reference/crecordset-class.md#edit), geçerli kayıt depolanır, böylece daha sonra gerektikçe geri yüklenebilir. Çağırdığınızda [silmek](../../mfc/reference/crecordset-class.md#delete), geçerli kayıt yok depolanır, ancak silinmiş olarak işaretlenmiş ve başka bir kayıtla kaydırın.  
  
> [!NOTE]
>  Düzenleme arabelleği kayıt silinmesine hiçbir rol oynar. Geçerli kaydı sildiğinizde, kaydı silinmiş olarak işaretlenmiş ve farklı bir kayda kaydırma dek "kaydında değil" kayıt kümesi olur.  
  
##  <a name="_core_dynasets_and_snapshots"></a>Dinamik kümeler ve anlık görüntüleri  
 [Dinamik kümeler](../../data/odbc/dynaset.md) kayda kaydırma gibi bir kaydın içeriği yenileyin. [Anlık Görüntü](../../data/odbc/snapshot.md) çağırmanız sürece bir kaydın içeriği yenilenmez kayıtları statik gösterimlerini olan [Requery](../../mfc/reference/crecordset-class.md#requery). Dinamik kümeler tüm işlevselliğini kullanmak için doğru düzeyde ODBC API desteği uyan bir ODBC sürücüsü ile çalışmalısınız. Daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md) ve [Dynaset](../../data/odbc/dynaset.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: AddNew, düzenleme ve Delete nasıl çalışır (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)