---
title: 'Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
ms.openlocfilehash: f11c723e4589cb28a3f38100050a69a78fc0809e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212855"
---
# <a name="recordset-more-about-updates-odbc"></a>Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda aşağıdakiler açıklanmaktadır:

- [İşlemler gibi diğer işlemlerin güncelleştirmeleri etkilemesi](#_core_how_transactions_affect_updates).

- [Güncelleştirmelerinizin ve diğer kullanıcılarınızın diğer kullanıcıları](#_core_your_updates_and_the_updates_of_other_users).

- [Güncelleştirme ve silme üye işlevleri hakkında daha fazla bilgi](#_core_more_about_update_and_delete).

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen nesneler için geçerlidir. Toplu satır getirme uyguladıysanız bazı bilgiler uygulanmaz. Örneğin, `AddNew`, `Edit`, `Delete`ve `Update` üye işlevleri çağrılamaz; Ancak, işlemler gerçekleştirebilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a>Diğer Işlemlerin güncelleştirmeleri etkilemesi

Güncelleştirmeleriniz güncelleştirme sırasında yürürlükte olan işlemlere, işlem tamamlanmadan önce kayıt kümesini kapatarak ve bir işlem tamamlanmadan önce kaydırarak etkilenir.

###  <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a>Işlemler güncelleştirmeleri nasıl etkiler

`AddNew`, `Edit`ve `Delete` nasıl çalıştığını anladıktan sonra, [CDatabase](../../mfc/reference/cdatabase-class.md) 'in `BeginTrans`, `CommitTrans`ve `Rollback` üye işlevlerinin [CRecordset](../../mfc/reference/crecordset-class.md)'in güncelleştirme işlevleriyle nasıl çalıştığını anlamak önemlidir.

Varsayılan olarak, `AddNew` ve `Edit` çağrıları `Update`çağırdığınızda veri kaynağını hemen etkiler. `Delete` çağrılar hemen etkili olur. Ancak bir işlem oluşturabilir ve bu tür çağrıların toplu işlemini yürütebilirsiniz. Güncelleştirmeler, kaydedilene kadar kalıcı olmaz. Fikrinizi değiştirirseniz, işlemi yürütmek yerine geri alabilirsiniz.

İşlemler hakkında daha fazla bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

###  <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a>Kayıt kümesini kapatma, güncelleştirmeleri nasıl etkiler

Bir kayıt kümesini veya ilişkili `CDatabase` nesnesini devam eden bir işlem ile kapatırsanız ( [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) veya [CDatabase:: Rollback](../../mfc/reference/cdatabase-class.md#rollback)çağrılmadı), işlem otomatik olarak geri alınır (veritabanınızın arka ucu Microsoft Jet veritabanı altyapısı değilse).

> [!CAUTION]
>  Microsoft Jet veritabanı altyapısını kullanıyorsanız, açık bir işlem içindeki bir kayıt kümesini kapatmak, açık işlem kaydedilene veya geri alınana kadar değiştirilmiş olan veya kilitli satırlardan herhangi birinin serbest bırakılmasıyla sonuçlanır. Her zaman açık bir Jet işleminin içinde veya dışında kayıt kümelerini açmanız ve kapatmanız önerilir.

###  <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a>Kaydırma, güncelleştirmeleri nasıl etkiler

Kayıt [kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) bir kayıt kümesinde, düzenleme arabelleği her yeni geçerli kayıtla doldurulur (önceki kayıt önce depolanmaz). Kaydırma, daha önce silinen kayıtları atlar. Önce `Update`, `CommitTrans`veya `Rollback` çağırılmadan bir `AddNew` veya `Edit` çağrısından sonra kayırsanız, yeni bir kayıt düzenleme arabelleğine getirildiğinde değişiklikler kaybedilir (size hiçbir uyarı olmadan). Düzenleme arabelleği kaydırılan kayıt ile doldurulur, depolanan kayıt serbest bırakılır ve veri kaynağında hiçbir değişiklik gerçekleşmez. Bu hem `AddNew` hem de `Edit`için geçerlidir.

##  <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a>Diğer kullanıcıların güncelleştirmeleri ve güncelleştirmeleri

Verileri güncelleştirmek için bir kayıt kümesi kullandığınızda, güncelleştirmeleriniz diğer kullanıcıları etkiler. Benzer şekilde, kayıt kümenizin ömrü boyunca diğer kullanıcıların güncelleştirmeleri sizi etkiler.

Çok kullanıcılı bir ortamda, diğer kullanıcılar kayıt kümenizde seçtiğiniz kayıtların bazılarını içeren kayıt kümelerini açabilir. Kayıt kümenizde yansıtılmadan önce bir kayıttaki değişiklikler. Dinamik kümeler, her kaydırışınızda bir kayıt alındığından, dinamik kümeler bir kayda her kaydırışınızda değişiklikleri yansıtır. Anlık görüntüler, ilk kaydırdığınızda bir kaydı alır, bu nedenle anlık görüntüler yalnızca kayda kaymadan önce gerçekleşen değişiklikleri yansıtır.

Kayıt kümesini açtıktan sonra diğer kullanıcılar tarafından eklenen kayıtlar, ' i yeniden sorgulayana kadar kayıt kümenizde gösterilmez. Kayıt kümeniz bir Dynaset ise, etkilenen kayda kaydırdığınızda, diğer kullanıcılar tarafından varolan kayıtlara yapılan düzenlemeler, küme kümenizin içinde görünür. Kayıt kümeniz bir anlık görüntü ise, anlık görüntüyü yeniden sorgulayana kadar düzenlemeler gösterilmez. Anlık görüntüdeki diğer kullanıcılar tarafından eklenen veya silinen kayıtları veya dinamik kümenize diğer kullanıcılar tarafından eklenen kayıtları görmek isterseniz, kayıt kümesini yeniden derlemek için [CRecordset:: Requery](../../mfc/reference/crecordset-class.md#requery) ' i çağırın. (Diğer kullanıcıların silinmesinin dinamik kümenize görünür olduğunu unutmayın.) Ayrıca, eklediğiniz kayıtları görmek için `Requery` çağırabilirsiniz, ancak sillerinizi görmeyebilirsiniz.

> [!TIP]
>  Bir anlık görüntünün tamamının önbelleğe alınmasını zorlamak için anlık görüntüyü açtıktan hemen sonra `MoveLast` çağırın. Sonra kayıtlarla çalışmaya başlamak için `MoveFirst` çağırın. `MoveLast` tüm kayıtları kaydırmaya eşdeğerdir, ancak tümünü bir kez alır. Bununla birlikte, bunun performansı düşürebileceğini ve bazı sürücüler için gerekli olmayabilir.

Diğer kullanıcılara yaptığınız güncelleştirmelerin etkileri, sizin için etkileri ile benzerdir.

##  <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a>Güncelleştirme ve silme hakkında daha fazla bilgi

Bu bölüm `Update` ve `Delete`çalışmanıza yardımcı olacak ek bilgiler sağlar.

### <a name="update-success-and-failure"></a>Güncelleştirme başarısı ve başarısızlığı

`Update` başarılı olursa `AddNew` veya `Edit` modu sonlanır. Bir `AddNew` veya `Edit` moduna yeniden başlamak için `AddNew` veya `Edit`çağırın.

`Update` başarısız olursa (yanlış döndürür veya bir özel durum oluşturursa), en son hangi işleve bağlı olarak `AddNew` veya `Edit` modunda kalır. Bundan sonra aşağıdakilerden birini yapabilirsiniz:

- Bir alan veri üyesini değiştirip `Update` yeniden deneyin.

- Alan veri üyelerini null olarak sıfırlamak için `AddNew` çağırın, alan veri üyelerinin değerlerini ayarlayın ve sonra yeniden `Update` çağırın.

- `AddNew` veya `Edit`ilk çağrısından önce kayıt kümesinde olan değerleri yeniden yüklemek için `Edit` çağırın, alan veri üyelerinin değerlerini ayarlayın ve ardından `Update` yeniden çağırın. Başarılı bir `Update` çağrısından sonra (bir `AddNew` çağrısından sonra), alan veri üyeleri yeni değerlerini korurlar.

- `Move` (bir AFX_MOVE_REFRESH veya 0) `Move` dahil olmak üzere, tüm değişiklikleri temizlemeleri ve herhangi bir `AddNew` veya `Edit` modunu sona erdirir.

### <a name="update-and-delete"></a>Güncelleştir ve Sil

Bu bölüm hem `Update` hem de `Delete`için geçerlidir.

Bir `Update` veya `Delete` işleminde, tek bir kayıt da güncelleştirilmeleri gerekir. Bu kayıt, kayıt kümesinin alanlarındaki veri değerlerine karşılık gelen geçerli kayıttır. Bazı nedenlerle hiçbir kayıt etkilenmeden veya birden çok kayıt etkileniyorsa, aşağıdaki **Ekcode** değerlerinden birini içeren bir özel durum atılır:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

Bu özel durumlar oluştuğunda, `Update` veya `Delete`çağırdığınızda yaptığınız `AddNew` veya `Edit` durumunda kalacaksınız. Bu özel durumları görebileceğiniz en yaygın senaryolar aşağıda verilmiştir. En büyük ihtimalle şunları görebilirsiniz:

- İyimser kilitleme modunu kullanırken AFX_SQL_ERROR_NO_ROWS_AFFECTED ve başka bir kullanıcı kaydı, Framework 'ün güncelleştirme veya silme için doğru kaydı tanımmasını engelleyecek şekilde değiştirdi.

- Güncelleştirdiğiniz tablo birincil anahtar veya benzersiz dizin olmadığında AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED ve kayıt kümesinde tablo satırını benzersiz şekilde tanımlamak için yeterli sütun yok.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Özel durumlar: Veritabanı Özel Durumları](../../mfc/exceptions-database-exceptions.md)
