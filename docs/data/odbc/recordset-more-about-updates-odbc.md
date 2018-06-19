---
title: 'Kayıt kümesi: Hakkında daha fazla güncelleştirmeler (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ea46e0462f3763e04ec18ad9bff2b0d3ded1deee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098673"
---
# <a name="recordset-more-about-updates-odbc"></a>Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Gibi işlemler, diğer işlemlerin güncelleştirmeleri etkilemesi](#_core_how_transactions_affect_updates).  
  
-   [Yaptığınız güncelleştirmeler ve diğer kullanıcıların](#_core_your_updates_and_the_updates_of_other_users).  
  
-   [Update ve Delete üye işlevleri hakkında daha fazla](#_core_more_about_update_and_delete).  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uyguladıysanız, bazı bilgiler uygulanmaz. Örneğin, çağıramazsınız `AddNew`, **Düzenle**, **silmek**, ve **güncelleştirme** üye işlevleri; ancak, işlemler gerçekleştirebilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_how_other_operations_affect_updates"></a> Diğer işlemlerin güncelleştirmeleri etkilemesi  
 Güncelleştirmelerinizi yürürlükte güncelleştirme sırasında işlemleri tarafından bir işlem tamamlanmadan önce kayıt kapatarak ve işlem tamamlanmadan önce kaydırarak etkilenir.  
  
###  <a name="_core_how_transactions_affect_updates"></a> İşlemlerin güncelleştirmeleri etkilemesi  
 Anlama ötesinde nasıl `AddNew`, **Düzenle**, ve **silmek** iş, onu önemlidir anlamak nasıl **BeginTrans**, **CommitTrans**, ve **geri alma** üye işlevlerini [CDatabase](../../mfc/reference/cdatabase-class.md) güncelleştirme işlevlerini ile çalışmak [CRecordset](../../mfc/reference/crecordset-class.md).  
  
 Varsayılan olarak, çağrılar `AddNew` ve **Düzenle** çağırdığınızda hemen veri kaynağını etkileyen **güncelleştirme**. **Silme** çağrıları hemen etkili olur. Ancak bir işlem oluşturabilir ve bu tür çağrılar toplu yürütün. Bunları kaydedene kadar güncelleştirmeleri kalıcı değildir. Fikrinizi değiştirirseniz, bu uygulamadan yerine işlem geri alabilirsiniz.  
  
 İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a> Kayıt kümesi kapatma güncelleştirmeleri nasıl etkiler  
 Bir kayıt veya onun ilişkili kapatırsanız `CDatabase` nesnesiyle devam eden bir işlem (çağrılmaz [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) veya [CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback)), işlem alındı otomatik olarak (veritabanı arka ucu Microsoft Jet veritabanı altyapısı olmadığı sürece) yedekleyin.  
  
> [!CAUTION]
>  Microsoft Jet veritabanı altyapısı kullanıyorsanız, açık bir işlem içinde bir kayıt kümesi kapatma değiştirilen satırları veya açık işlem yürütülmeli veya geri kadar yerleştirildi kilitleri serbest oluşmaz. Bu, her zaman açık hem Kapat kayıt kümeleri içinde veya dışında açık bir Jet işlem önerilir.  
  
###  <a name="_core_how_scrolling_affects_updates"></a> Kaydırma güncelleştirmeleri nasıl etkiler  
 Olduğunda, [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) bir kayıt kümesinde düzenleme arabelleği (önceki kayıt önce depolanmaz) her yeni ve geçerli kayıt ile doldurulur. Atlar daha önce silinmiş kayıtları kaydırma. Sonra kaydırırsanız, bir `AddNew` veya **Düzenle** çağrısı çağırmadan **güncelleştirme**, **CommitTrans**, veya **geri alma** ilk, herhangi bir değişiklik Yeni bir kayıt düzenleme arabelleğine getirilene gibi (ile herhangi bir uyarı yapılmadan) kaybolur. Düzenleme arabelleği kaydırılan kayıt ile doldurulur, saklı kayıt serbest bırakılır ve veri kaynağı üzerinde hiçbir değişikliği oluşur. Bu, hem de geçerlidir `AddNew` ve **Düzenle**.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> Yaptığınız güncelleştirmeler ve diğer kullanıcıların güncelleştirmeleri  
 Verileri güncelleştirmek için bir kayıt kümesi kullandığınızda, güncelleştirmelerinin diğer kullanıcıları etkiler. Benzer şekilde, diğer kullanıcıların kümenizin kullanım ömrü süresince güncelleştirmeleri, etkiler.  
  
 Çok kullanıcılı bir ortamda, diğer kullanıcıların bazı kümenize seçtiğiniz aynı kayıtlar içeren kayıt kümeleri açabilirsiniz. Değişiklikler almadan önce bir kayda kümenize yansıtılır. Dinamik kümeler için kaydırma her zaman bir kayıt almak için dinamik kümeler için bir kayıt kaydırma her zaman değişiklikleri yansıtır. Anlık görüntüler bir kaydı anlık görüntüleri kayda ilk kaydırma önce gerçekleşen değişiklikleri yansıtacak şekilde, kaydırma ilk kez alın.  
  
 Requery sürece kayıt açtıktan sonra diğer kullanıcılar tarafından eklenen kayıtlar kümenize gösterme. Kümenizin bir dinamik ise, etkilenen kayda kaydırma yaptığınızda mevcut kayıtları diğer kullanıcılar tarafından yapılan düzenlemeler kümenize gösterilir. Kümenizin bir anlık görüntü ise, anlık görüntü requery kadar düzenlemeleri gösterme. Eklenen kayıtları görmek veya anlık görüntü veya kümenize diğer kullanıcılar tarafından eklenen kayıtları diğer kullanıcılar tarafından silinen çağrı istiyorsanız [CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery) kayıt yeniden oluşturma. (Diğer kullanıcıların silme kümenize gösterilmediğini unutmayın.) Ayrıca çağırabilirsiniz **Requery** kayıtları görmek için sizin silme işlemleri görmek için ancak eklediğiniz.  
  
> [!TIP]
>  Aynı anda anlık görüntü tüm önbelleğe alma zorlamak için arama `MoveLast` anlık görüntü açtıktan hemen sonra. ' I çağırın **MoveFirst** kayıtları ile çalışmaya başlamak için. `MoveLast` tüm kayıtları kaydırma için eşdeğer olan ancak bunları bir defada alır. Ancak, bu performans düzeyine düşürebilirsiniz ve bazı sürücüler için gerekli olmayabilir unutmayın.  
  
 Diğer kullanıcıların güncelleştirmelerinizi etkilerini, bunların etkileri benzerdir.  
  
##  <a name="_core_more_about_update_and_delete"></a> Güncelleştirme ve silme hakkında daha fazla bilgi  
 Bu bölümde, çalışmanıza yardımcı olacak ek bilgiler **güncelleştirme** ve **silmek**.  
  
### <a name="update-success-and-failure"></a>Güncelleştirme başarı ve başarısızlık  
 Varsa **güncelleştirme** başarılı, `AddNew` veya **Düzenle** modu sona erer. Başlamak için bir `AddNew` veya **Düzenle** yeniden modu, çağrı `AddNew` veya **Düzenle**.  
  
 Varsa **güncelleştirme** başarısız (döndürür **FALSE** veya bir özel durum oluşturur), durumunda kalır `AddNew` veya **Düzenle** bağlı olarak hangi işlevi, bilinen son modu. Ardından aşağıdakilerden birini yapabilirsiniz:  
  
-   Alan veri üyesi değiştirip deneyin **güncelleştirme** yeniden.  
  
-   Çağrı `AddNew` alan veri üyeleri Null olarak ayarlamak için alan veri üyeleri değerlerini ayarlayın ve ardından arama **güncelleştirme** yeniden.  
  
-   Çağrı **Düzenle** ilk çağrıda önce kayıt kümesinde olan değerleri yeniden yüklemek için `AddNew` veya **Düzenle**, alan veri üyeleri değerlerini ayarlayın ve ardından çağrısı **güncelleştirme**yeniden. Başarılı bir sonra **güncelleştirme** çağrı (sonra hariç bir `AddNew` çağrısı), yeni değerlerini alan veri üyeleri korur.  
  
-   Çağrı **taşımak** (dahil olmak üzere **taşımak** bir parametresi ile **AFX_MOVE_REFRESH**, veya 0), değişiklikleri ve sonlandıran herhangi temizler `AddNew` veya **Düzenle** etkisi modunda.  
  
### <a name="update-and-delete"></a>Güncelleştirme ve silme  
 Bu bölüm hem de geçerlidir **güncelleştirme** ve **silmek**.  
  
 Üzerinde bir **güncelleştirme** veya **silmek** işlemi, tek bir kayıt güncelleştirilmelidir. Bu kayıt kümesinin alanlarında veri değerlerine karşılık gelen geçerli kayıttır. Bazı kayıt etkilenen ya da birden fazla kayıt etkilenen nedenden dolayı bir özel durum aşağıdakilerden birini içeren oluşturulursa **RETCODE** değerler:  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED**  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**  
  
 Bu özel durumlar zaman içinde kalır `AddNew` veya **Düzenle** olduğunuz içinde çağırdığınızda durumu **güncelleştirme** veya **silmek**. Bu özel durumlar görür en yaygın senaryolar verilmiştir. Görmek büyük olasılıkla:  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED** İyimser kilitleme modu ve başka bir kullanıcı kullanırken kaydı güncelleştirmek veya silmek için doğru kayıt tanımlayan framework engelleyen bir şekilde değiştirdi.  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** güncelleştirdiğiniz tablonun birincil anahtarı yok veya benzersiz dizin ve değil yeterli sütuna sahip bir tablo satırının benzersiz şekilde tanımlamak için kayıt kümesinde olduğunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Nasıl kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [Özel durumlar: Veritabanı Özel Durumları](../../mfc/exceptions-database-exceptions.md)