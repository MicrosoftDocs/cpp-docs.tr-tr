---
title: 'Kayıt kümesi: Güncelleştirmeler hakkında daha fazla (ODBC)'
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
ms.openlocfilehash: c29ff110fc507c4e449b2f3d082d98c159a35107
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397776"
---
# <a name="recordset-more-about-updates-odbc"></a>Kayıt kümesi: Güncelleştirmeler hakkında daha fazla (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu şunları açıklar:

- [İşlemleri gibi diğer işlemler güncelleştirmeleri etkilemesi](#_core_how_transactions_affect_updates).

- [Yaptığınız güncelleştirmeler ve diğer kullanıcıların](#_core_your_updates_and_the_updates_of_other_users).

- [Update ve Delete üye işlevleri hakkında daha fazla](#_core_more_about_update_and_delete).

> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uyguladıysanız, bazı bilgiler geçerli değildir. Örneğin, çağıramazsınız `AddNew`, `Edit`, `Delete`, ve `Update` üye işlevleri; ancak, işlemleri gerçekleştirebilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_how_other_operations_affect_updates"></a> Diğer işlemlerin güncelleştirmeleri etkilemesi

Güncelleştirmelerinizi yürürlükte güncelleştirmesi sırasındaki işlem tarafından işlem tamamlanmadan önce kayıt kapatarak ve işlem tamamlanmadan önce kaydırma etkilenir.

###  <a name="_core_how_transactions_affect_updates"></a> İşlemlerin güncelleştirmeleri etkilemesi

Anlama ötesinde nasıl `AddNew`, `Edit`, ve `Delete` iş önemlidir anlamak nasıl `BeginTrans`, `CommitTrans`, ve `Rollback` üye işlevleri [CDatabase](../../mfc/reference/cdatabase-class.md) ile çalışma Güncelleştirme işlevlerini [CRecordset](../../mfc/reference/crecordset-class.md).

Varsayılan olarak, çağrılar `AddNew` ve `Edit` çağırdığınızda hemen veri kaynağını etkileyen `Update`. `Delete` çağrıları, hemen geçerli olur. Ancak, bir işlem oluşturabilir ve böyle çağrılar toplu yürütün. Güncelleştirmeleri, onları yürütene kadar kalıcı değildir. Fikrinizi değiştirirseniz, kabul etmek yerine işlem geri alabilirsiniz.

İşlemler hakkında daha fazla bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

###  <a name="_core_how_closing_the_recordset_affects_updates"></a> Kayıt kümesi kapatma güncelleştirmeleri nasıl etkiler

Bir kayıt veya ilişkili kapatırsanız `CDatabase` sahip bir işlem devam eden bir nesneyi (çağrılmazsa [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) veya [CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback)), işlem alındı otomatik olarak (veritabanı arka ucunuzu Microsoft Jet veritabanı altyapısı olmadığı sürece) yedekleyin.

> [!CAUTION]
>  Microsoft Jet veritabanı altyapısı kullanıyorsanız, açık bir işlem içinde bir kayıt kümesi kapatma değiştirilen satırları veya açık işlem kaydedilmiş veya geri alınmış kadar yerleştirildi kilitleri serbest sonuçlanmaz. Bu, her zaman açık hem Kapat kayıt kümeleri içinde veya dışında açık Jet işlem önerilir.

###  <a name="_core_how_scrolling_affects_updates"></a> Kaydırma güncelleştirmeleri nasıl etkiler

Olduğunda, [kayıt kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) bir kayıt kümesinde düzenleme arabelleği (önceki kaydı önce depolanmaz) her yeni geçerli kayıt ile doldurulur. Önceden silinen kayıtlar atlar kaydırma. Sonra kaydırırsanız bir `AddNew` veya `Edit` çağırmadan çağrı `Update`, `CommitTrans`, veya `Rollback` yeni bir kaydı düzenleme arabelleğe getirildikten gibi ilk olarak, tüm değişiklikler (ile herhangi bir uyarı yapılmadan) kaybedilir. Düzenleme arabelleği kaydırılan kayıt ile doldurulur, depolanmış kayıt serbest bırakılır ve veri kaynağında değişiklik gerçekleşir. Bu, her ikisi için de geçerlidir `AddNew` ve `Edit`.

##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> Güncelleştirmeleri ve diğer kullanıcıların güncelleştirmeleri

Verileri güncelleştirmek için bir kayıt kümesi kullandığınızda, güncelleştirmelerinizi diğer kullanıcıları etkiler. Benzer şekilde, diğer kullanıcıların kayıt kullanım ömrü süresince güncelleştirmeleri, etkiler.

Çok kullanıcılı bir ortamda, bazı kümenize seçtiğiniz aynı kayıt içeren kayıt kümeleri diğer kullanıcılar açabilir. Kümenizde almadan önce bir kayıttaki değişiklikler yansıtılır. Dynaset'ler için kaydırma her zaman bir kaydı almak için dinamik kümeler her zaman bir kayda kaydırma değişiklikleri yansıtır. Anlık görüntüleri anlık görüntüleri kayda ilk kaydırma önce gerçekleşen değişiklikleri yansıtacak şekilde, kaydırma ilk kez bir kaydı alır.

Requery sürece kayıt açtıktan sonra diğer kullanıcılar tarafından eklenen kayıtlar, kayıt kümenize gösterme. Kümenizin bir dinamik ise, etkilenen kayda kaydırdığınızda var olan kayıtların diğer kullanıcılar tarafından yapılan düzenlemeler kümenize gösterilir. Kümenizin bir anlık görüntüyse kadar anlık görüntü requery düzenlemeler gösterme. Eklenen kayıtlar görmek veya diğer kullanıcıların anlık görüntü veya kümenize diğer kullanıcılar tarafından eklenen kayıtları silinen çağırmak istiyorsanız [CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery) kayıt kümesini yeniden oluşturmak için. (Diğer kullanıcıların silme kümenize gösterilmediğini unutmayın.) Ayrıca çağırabilirsiniz `Requery` kayıtları görmek için ancak, silme işlemleri görmek için eklediğiniz.

> [!TIP]
>  Tek seferde anlık görüntü tüm önbelleğe alma zorlamak için çağrı `MoveLast` anlık görüntü açıldıktan hemen sonra. Ardından çağırın `MoveFirst` kayıtları ile çalışmaya başlamak için. `MoveLast` tüm kayıtlar kaydırmaya eşdeğerdir, ancak aynı anda bunları alır. Ancak, bu başarımı düşürebilir ve bazı sürücüler için gerekli olmayabilir unutmayın.

Diğer kullanıcıların güncelleştirmelerinizi etkilerini, bunların etkilerini benzerdir.

##  <a name="_core_more_about_update_and_delete"></a> Güncelleştirme ve silme hakkında daha fazla

Bu bölümde çalışmanıza yardımcı olacak ek bilgiler `Update` ve `Delete`.

### <a name="update-success-and-failure"></a>Güncelleştirme başarı ve başarısızlık

Varsa `Update` başarılı, `AddNew` veya `Edit` modu sona erer. Başlamak için bir `AddNew` veya `Edit` yeniden modu, çağrı `AddNew` veya `Edit`.

Varsa `Update` başarısız (false değerini döndürür veya bir özel durum oluşturur), durumunda kalır `AddNew` veya `Edit` hangi işlevi bağlı olarak, adlı son modu. Ardından aşağıdakilerden birini yapabilirsiniz:

- Alan veri üyesi değiştirip deneyin `Update` yeniden.

- Çağrı `AddNew` alan veri üyeleri Null olarak ayarlamak için alan veri üyelerinin değerlerini ayarlayın ve sonra çağrı `Update` yeniden.

- Çağrı `Edit` ilk çağırmadan önce kümesinde olan değerleri yeniden `AddNew` veya `Edit`alan veri üyelerinin değerlerini ayarlayın ve sonra çağrı `Update` yeniden. Başarılı bir sonra `Update` çağırın (sonra hariç bir `AddNew` çağrısı), alan veri üyeleri yeni değerlerini korur.

- Çağrı `Move` (dahil olmak üzere `Move` AFX_MOVE_REFRESH veya 0'ın bir parametresiyle), herhangi temizler ve değişiklikleri sonlandıran `AddNew` veya `Edit` etkisi modunda.

### <a name="update-and-delete"></a>Güncelleştirme ve silme

Bu bölüm, her ikisi için de geçerlidir `Update` ve `Delete`.

Üzerinde bir `Update` veya `Delete` işlemi, yalnızca tek bir kaydı güncelleştirilmelidir. Bu kayıt kayıt kümesinin alanları veri değerlerine karşılık gelen geçerli kaydıdır. Bazı kayıt etkilenen veya birden fazla kayıtla etkilenen herhangi bir nedenle bir özel durum aşağıdakilerden birini içeren oluşturulursa **RETCODE** değerleri:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

Bu özel durumlar oluşturulduğunda, kalan `AddNew` veya `Edit` olduğunuz olarak çağırdığınızda durumu `Update` veya `Delete`. Bu özel durumları görmek en yaygın senaryolar aşağıda verilmiştir. Görmek büyük olasılıkla:

- İyimser kilitleme modunu kullanırken ve başka bir kullanıcı kaydı bir şekilde değiştirdi AFX_SQL_ERROR_NO_ROWS_AFFECTED, güncelleştirmek veya silmek için doğru kayıt tanımasını framework engeller.

- Tablo güncelleştirmekte olduğunuz AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED birincil anahtarı yok veya yeterli sayıda sütun benzersiz dizin ve tablo satırı benzersiz olarak tanımlanabilmesi için kayıt kümesinde yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Özel Durumlar: Veritabanı Özel Durumları](../../mfc/exceptions-database-exceptions.md)