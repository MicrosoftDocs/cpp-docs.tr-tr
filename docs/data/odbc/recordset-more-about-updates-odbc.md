---
description: 'Daha fazla bilgi: kayıt kümesi: güncelleştirmeler hakkında daha fazla bilgi (ODBC)'
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
ms.openlocfilehash: 9d125456189828d50f1fbfd4aece00a16790424f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304447"
---
# <a name="recordset-more-about-updates-odbc"></a>Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda aşağıdakiler açıklanmaktadır:

- [İşlemler gibi diğer işlemlerin güncelleştirmeleri etkilemesi](#_core_how_transactions_affect_updates).

- [Güncelleştirmelerinizin ve diğer kullanıcılarınızın diğer kullanıcıları](#_core_your_updates_and_the_updates_of_other_users).

- [Güncelleştirme ve silme üye işlevleri hakkında daha fazla bilgi](#_core_more_about_update_and_delete).

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme uyguladıysanız bazı bilgiler uygulanmaz. Örneğin,,, `AddNew` `Edit` `Delete` ve `Update` üye işlevlerini çağrılamaz; ancak, işlem gerçekleştirebilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a> Diğer Işlemlerin güncelleştirmeleri etkilemesi

Güncelleştirmeleriniz güncelleştirme sırasında yürürlükte olan işlemlere, işlem tamamlanmadan önce kayıt kümesini kapatarak ve bir işlem tamamlanmadan önce kaydırarak etkilenir.

### <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a> Işlemler güncelleştirmeleri nasıl etkiler

, Ve ' nin nasıl çalıştığını `AddNew` `Edit` anladıktan sonra, `Delete` `BeginTrans` CDatabase 'in, `CommitTrans` ve `Rollback` üye işlevlerinin [CRecordset](../../mfc/reference/crecordset-class.md)'in güncelleştirme işlevleriyle [](../../mfc/reference/cdatabase-class.md) nasıl çalıştığını anlamak önemlidir.

Varsayılan olarak, ' i `AddNew` çağırdığınızda veri kaynağını çağırır ve ' ı `Edit` hemen etkiler `Update` . `Delete` çağrılar hemen geçerli olur. Ancak bir işlem oluşturabilir ve bu tür çağrıların toplu işlemini yürütebilirsiniz. Güncelleştirmeler, kaydedilene kadar kalıcı olmaz. Fikrinizi değiştirirseniz, işlemi yürütmek yerine geri alabilirsiniz.

İşlemler hakkında daha fazla bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a> Kayıt kümesini kapatma, güncelleştirmeleri nasıl etkiler

Bir kayıt kümesini veya ilişkili `CDatabase` nesnesini devam eden bir işlem ( [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) veya [CDatabase:: Rollback](../../mfc/reference/cdatabase-class.md#rollback)) olarak kapatırsanız işlem otomatik olarak geri alınır (veritabanı arka ucu Microsoft Jet veritabanı altyapısı değilse).

> [!CAUTION]
> Microsoft Jet veritabanı altyapısını kullanıyorsanız, açık bir işlem içindeki bir kayıt kümesini kapatmak, açık işlem kaydedilene veya geri alınana kadar değiştirilmiş olan veya kilitli satırlardan herhangi birinin serbest bırakılmasıyla sonuçlanır. Her zaman açık bir Jet işleminin içinde veya dışında kayıt kümelerini açmanız ve kapatmanız önerilir.

### <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a> Kaydırma, güncelleştirmeleri nasıl etkiler

Kayıt [kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) bir kayıt kümesinde, düzenleme arabelleği her yeni geçerli kayıtla doldurulur (önceki kayıt önce depolanmaz). Kaydırma, daha önce silinen kayıtları atlar. `AddNew` `Edit` , Veya çağrısından sonra, veya çağrısından sonra, `Update` Yeni bir `CommitTrans` `Rollback` kayıt düzenleme arabelleğine getirilen değişiklikler kaybedilir (size hiçbir uyarı olmadan). Düzenleme arabelleği kaydırılan kayıt ile doldurulur, depolanan kayıt serbest bırakılır ve veri kaynağında hiçbir değişiklik gerçekleşmez. Bu hem hem de için geçerlidir `AddNew` `Edit` .

## <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a> Diğer kullanıcıların güncelleştirmeleri ve güncelleştirmeleri

Verileri güncelleştirmek için bir kayıt kümesi kullandığınızda, güncelleştirmeleriniz diğer kullanıcıları etkiler. Benzer şekilde, kayıt kümenizin ömrü boyunca diğer kullanıcıların güncelleştirmeleri sizi etkiler.

Çok kullanıcılı bir ortamda, diğer kullanıcılar kayıt kümenizde seçtiğiniz kayıtların bazılarını içeren kayıt kümelerini açabilir. Kayıt kümenizde yansıtılmadan önce bir kayıttaki değişiklikler. Dinamik kümeler, her kaydırışınızda bir kayıt alındığından, dinamik kümeler bir kayda her kaydırışınızda değişiklikleri yansıtır. Anlık görüntüler, ilk kaydırdığınızda bir kaydı alır, bu nedenle anlık görüntüler yalnızca kayda kaymadan önce gerçekleşen değişiklikleri yansıtır.

Kayıt kümesini açtıktan sonra diğer kullanıcılar tarafından eklenen kayıtlar, ' i yeniden sorgulayana kadar kayıt kümenizde gösterilmez. Kayıt kümeniz bir Dynaset ise, etkilenen kayda kaydırdığınızda, diğer kullanıcılar tarafından varolan kayıtlara yapılan düzenlemeler, küme kümenizin içinde görünür. Kayıt kümeniz bir anlık görüntü ise, anlık görüntüyü yeniden sorgulayana kadar düzenlemeler gösterilmez. Anlık görüntüdeki diğer kullanıcılar tarafından eklenen veya silinen kayıtları veya dinamik kümenize diğer kullanıcılar tarafından eklenen kayıtları görmek isterseniz, kayıt kümesini yeniden derlemek için [CRecordset:: Requery](../../mfc/reference/crecordset-class.md#requery) ' i çağırın. (Diğer kullanıcıların silinmesinin dinamik kümenize görünür olduğunu unutmayın.) Ayrıca `Requery` , eklediğiniz kayıtları görmek için öğesini çağırabilirsiniz, ancak sillerinizi görmeyebilirsiniz.

> [!TIP]
> Bir anlık görüntünün tamamının önbelleğe alınmasını zorlamak için `MoveLast` anlık görüntüyü açtıktan hemen sonra çağırın. Sonra `MoveFirst` kayıtlarla çalışmaya başlamak için öğesini çağırın. `MoveLast` Tüm kayıtları kaydırmaya eşdeğerdir, ancak tümünü bir kez alır. Bununla birlikte, bunun performansı düşürebileceğini ve bazı sürücüler için gerekli olmayabilir.

Diğer kullanıcılara yaptığınız güncelleştirmelerin etkileri, sizin için etkileri ile benzerdir.

## <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a> Güncelleştirme ve silme hakkında daha fazla bilgi

Bu bölüm, ve ile çalışmanıza yardımcı olmak için ek bilgiler sağlar `Update` `Delete` .

### <a name="update-success-and-failure"></a>Güncelleştirme başarısı ve başarısızlığı

`Update`Başarılı olursa `AddNew` veya `Edit` modu sonlanır. Bir `AddNew` veya `Edit` moduna yeniden başlamak için veya ' i çağırın `AddNew` `Edit` .

`Update`Başarısız olursa (yanlış döndürür veya bir özel durum oluşturursa), `AddNew` `Edit` en son hangi işleve bağlı olarak, veya modunda kalır. Bundan sonra aşağıdakilerden birini yapabilirsiniz:

- Bir alan veri üyesini değiştirip `Update` yeniden deneyin.

- `AddNew`Alan veri üyelerini null olarak sıfırlamak için çağırın, alan veri üyelerinin değerlerini ayarlayın ve sonra `Update` yeniden çağırın.

- `Edit`Kayıt kümesinde olan değerleri, veya için ilk çağrıdan önce yeniden yüklemek için çağırın `AddNew` `Edit` , alan veri üyelerinin değerlerini ayarlayın ve sonra `Update` yeniden çağırın. Başarılı bir `Update` çağrıdan sonra (bir çağrıdan sonra `AddNew` ), alan veri üyeleri yeni değerlerini korurlar.

- `Move` `Move` Her türlü değişikliği temizlemeleri ve herhangi bir `AddNew` ya da modu sona erdirir `Edit` . AFX_MOVE_REFRESH

### <a name="update-and-delete"></a>Güncelleştir ve Sil

Bu bölüm hem hem de için geçerlidir `Update` `Delete` .

Bir `Update` veya `Delete` işleminde, bir ve yalnızca bir kayıt güncellenmelidir. Bu kayıt, kayıt kümesinin alanlarındaki veri değerlerine karşılık gelen geçerli kayıttır. Bazı nedenlerle hiçbir kayıt etkilenmeden veya birden çok kayıt etkileniyorsa, aşağıdaki **Ekcode** değerlerinden birini içeren bir özel durum atılır:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

Bu özel durumlar oluştuğunda, `AddNew` `Edit` veya çağırdığınızda yaptığınız veya durumunda kalacaksınız `Update` `Delete` . Bu özel durumları görebileceğiniz en yaygın senaryolar aşağıda verilmiştir. En büyük ihtimalle şunları görebilirsiniz:

- İyimser kilitleme modunu kullanırken AFX_SQL_ERROR_NO_ROWS_AFFECTED ve başka bir kullanıcı kaydı, Framework 'ün güncelleştirme veya silme için doğru kaydı tanımmasını engelleyecek şekilde değiştirdi.

- Güncelleştirdiğiniz tablo birincil anahtar veya benzersiz dizin olmadığında AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED ve kayıt kümesinde tablo satırını benzersiz şekilde tanımlamak için yeterli sütun yok.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: kayıt kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md)
