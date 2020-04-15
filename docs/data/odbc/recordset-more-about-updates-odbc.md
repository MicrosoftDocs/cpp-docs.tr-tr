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
ms.openlocfilehash: 955b26137ce976514d84f95f4d819779b93bd78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368684"
---
# <a name="recordset-more-about-updates-odbc"></a>Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu açıklar:

- [Hareketler gibi diğer işlemler güncelleştirmeleri nasıl etkiler?](#_core_how_transactions_affect_updates)

- [Güncellemeleriniz ve diğer kullanıcıların güncelleştirmeleri.](#_core_your_updates_and_the_updates_of_other_users)

- [Üye işlevleri Güncelleştir ve Sil hakkında daha fazla bilgi.](#_core_more_about_update_and_delete)

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma uyguladıysanız, bazı bilgiler geçerli değildir. Örneğin, `AddNew`, , `Edit` `Delete`, ve `Update` üye işlevleri arayamamazsınız; ancak, hareketleri gerçekleştirebilirsiniz. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a>Diğer İşlemler Güncelleştirmeleri Nasıl Etkiler?

Güncelleştirmeleriniz güncelleştirme sırasında geçerli olan işlemlerden, bir işlemi tamamlamadan önce kayıt kümesini kapatarak ve bir işlemi tamamlamadan önce kaydırarak etkilenir.

### <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a>Hareketler Güncelleştirmeleri Nasıl Etkiler?

`AddNew`CDatabase'in `Edit`ve `Delete` `BeginTrans` `CommitTrans` `Rollback` üye işlevlerinin [CRecordset'in](../../mfc/reference/crecordset-class.md)güncelleştirme işlevleriyle nasıl çalıştığını anlamak ve çalışmanın ötesinde önemlidir. [CDatabase](../../mfc/reference/cdatabase-class.md)

Varsayılan olarak, `AddNew` arama `Edit` yaptığınızda veri kaynağını `Update`hemen arar ve etkiler. `Delete`çağrılar hemen yürürlüğe girer. Ancak bir işlem kurabilir ve bu tür çağrıları niçin gerçekleştirebilirsiniz. Güncelleştirmeler, siz bunları işleyene kadar kalıcı değildir. Fikrinizi değiştirirseniz, işlemi işlemek yerine geri alabilirsiniz.

İşlemler hakkında daha fazla bilgi için [Bkz. Hareket (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a>Kayıt Kümesinin Kapatılması Güncelleştirmeleri Nasıl Etkiler?

Bir kayıt kümesini veya ilişkili `CDatabase` nesnesini devam eden bir işlemle kapatırsanız [(CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) veya [CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback)olarak adlandırmadınız), işlem otomatik olarak geri alınır (veritabanı arka ucunuz Microsoft Jet veritabanı altyapısı değilse).

> [!CAUTION]
> Microsoft Jet veritabanı altyapısını kullanıyorsanız, açık bir işlem içinde bir kayıt kümesini kapatmak, açık işlem işlenene veya geri alınana kadar değiştirilen satırların veya kilitlerin serbest bırakılmasına neden olmaz. Açık bir Jet işleminin içinde veya dışında her zaman kayıt kümelerini açmanız ve kapatmanız önerilir.

### <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a>Kaydırma Güncelleştirmeleri Nasıl Etkiler?

Recordset: Bir kayıt setinde [kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) yaptığınızda, edit arabelleği her yeni geçerli kayıtla doldurulur (önceki kayıt önce depolanmaz). Kaydırma, daha önce silinmiş kayıtları atlar. Bir `AddNew` veya aramayı `Edit` aramadan `Update`veya `CommitTrans` `Rollback` aramadan sonra kaydırırsanız, yeni bir kayıt önbelleğe getirildiğinde, herhangi bir değişiklik kaybolur (size uyarı olmaksızın). Edinme arabelleği kaydırılan kayıtla doldurulur, depolanan kayıt serbest bırakılır ve veri kaynağında herhangi bir değişiklik oluşmaz. Bu hem de `AddNew` `Edit`geçerlidir .

## <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a>Güncellemeleriniz ve Diğer Kullanıcıların Güncellemeleri

Verileri güncelleştirmek için bir kayıt kümesi kullandığınızda, güncelleştirmeleriniz diğer kullanıcıları etkiler. Benzer şekilde, kayıt setinizin ömrü boyunca diğer kullanıcıların güncelleştirmeleri de sizi etkiler.

Çok kullanıcılı bir ortamda, diğer kullanıcılar kayıt setinizde seçtiğiniz kayıtların bazılarını içeren kayıt kümelerini açabilir. Bir kaydı almadan önce yapılan değişiklikler kayıt setinize yansıtılır. Dynasets, her kaydırma yaptığınızda bir kayıt aldığınızda bir kayıt aldığı için, bir kayda her kaydırdığınızda değişiklikleri yansıtır. Anlık görüntüler bir kaydı ilk kez kaydırdığınızda alır, bu nedenle anlık görüntüler yalnızca kayda kaydırmadan önce gerçekleşen değişiklikleri yansıtır.

Kayıt kümesini açtıktan sonra diğer kullanıcılar tarafından eklenen kayıtlar, yeniden sorgulamadığınız sürece kayıt setinizde gösterilmez. Kayıt setiniz bir dinamitse, etkilenen kayda kaydırdığınızda diğer kullanıcılar tarafından varolan kayıtlara yapılan ayarlamalar dinamitinizde gösterir. Kayıt setiniz anlık görüntüyse, anlık görüntüyeniden sorgulanana kadar yapılan lar görüntülenmez. Anlık görüntünüzde diğer kullanıcılar tarafından eklenen veya silinen kayıtları veya dynaset'inizdeki diğer kullanıcılar tarafından eklenen kayıtları görmek istiyorsanız, kayıt kümesini yeniden oluşturmak için [CRecordset::Requery'yi](../../mfc/reference/crecordset-class.md#requery) arayın. (Diğer kullanıcıların silmelerinin dinamitinizde görünün.) Ayrıca eklediğiniz `Requery` kayıtları görmek için de arayabilirsiniz, ancak silmelerinizi görmek için değil.

> [!TIP]
> Tüm anlık görüntünün önbelleğe alınmasını zorlamak için, anlık fotoğrafı açtıktan hemen sonra arayın. `MoveLast` Sonra `MoveFirst` kayıtlarla çalışmaya başlamak için arayın. `MoveLast`tüm kayıtların üzerinde kaydırmaya eşdeğerdir, ancak hepsini aynı anda alır. Ancak, bunun performansı düşürebileceğini ve bazı sürücüler için gerekli olmayabileceğini unutmayın.

Güncelleştirmelerinizin diğer kullanıcılar üzerindeki etkileri, sizin üzerindeki etkilerine benzer.

## <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a>Güncelleme ve Silme Hakkında Daha Fazla Bilgi

Bu bölümde, birlikte `Update` çalışmanıza yardımcı `Delete`olacak ek bilgiler ve .

### <a name="update-success-and-failure"></a>Başarı ve Başarısızlığı Güncelleştir

`Update` Başarılı olursa, `AddNew` `Edit` mod sona erer. Bir `AddNew` modu `Edit` yeniden başlatmak `AddNew` için, arayın veya. `Edit`

Başarısız `Update` olursa (FALSE döndürür veya bir `AddNew` `Edit` özel durum atar), en son adlandırdığınız işleve bağlı olarak modda kalırsınız. Daha sonra aşağıdakilerden birini yapabilirsiniz:

- Bir alan veri üyesini `Update` değiştirin ve yeniden deneyin.

- Alan `AddNew` veri üyelerini Null'a sıfırlamak, alan veri üyelerinin değerlerini ayarlamak `Update` ve sonra yeniden aramak için çağrı.

- İlk `Edit` çağrıdan önce kayıt kümesinde bulunan değerleri yeniden `AddNew` `Edit`yüklemek veya alan veri üyelerinin değerlerini ayarlamak `Update` ve sonra yeniden aramak için arayın. Başarılı `Update` bir çağrıdan sonra `AddNew` (bir çağrıdan sonra hariç), alan veri üyeleri yeni değerlerini korur.

- Herhangi `Move` bir `Move` değişikliği temizleyen ve geçerli olan modu `AddNew` `Edit` sona erdirebilen (AFX_MOVE_REFRESH veya 0 parametresi dahil) arayın.

### <a name="update-and-delete"></a>Güncelleme ve Silme

Bu bölüm her `Update` ikisi `Delete`için de geçerlidir ve .

Bir `Update` veya `Delete` işlemde, bir ve yalnızca bir kayıt güncelleştirilmelidir. Bu kayıt, kayıt kümesinin alanlarındaki veri değerlerine karşılık gelen geçerli kayıttır. Herhangi bir nedenle hiçbir kayıt etkilenmiyorsa veya birden fazla kayıt etkileniyorsa, aşağıdaki **RETCODE** değerlerinden birini içeren bir özel durum atılır:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

Bu özel durumlar atıldığında, `AddNew` aradığınız `Edit` `Update` da içinde olduğunuz durumda `Delete`kalırsınız veya . Bu özel durumları görebileceğiniz en yaygın senaryolar aşağıda verilmiştir. Büyük olasılıkla şunları görebilirsiniz:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED iyimser kilitleme modu kullanıyorsanız ve başka bir kullanıcı kaydı, güncelleştirmek veya silmek için doğru kaydı tanımlamasını engelleyecek şekilde değiştirmiştir.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED, güncellediğiniz tablonun birincil anahtarı veya benzersiz dizini yoksa ve kayıt kümesinde tablo satırını benzersiz olarak tanımlamak için yeterli sütununuz yoksa.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Özel durumlar: Veritabanı Özel Durumları](../../mfc/exceptions-database-exceptions.md)
