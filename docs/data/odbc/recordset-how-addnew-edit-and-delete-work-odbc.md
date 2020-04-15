---
title: 'Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
ms.openlocfilehash: 63718a6be3a9ce19ddbce923a84def21448c42a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366999"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu `AddNew`konu, sınıfın `Edit` `CRecordset` , `Delete` ve üye işlevlerinin nasıl çalıştığını açıklar. Ele alınan konular:

- [Kayıt Ekleme Nasıl Çalışır?](#_core_adding_a_record)

- [Eklenen Kayıtların Görünürlüğü](#_core_visibility_of_added_records)

- [Kayıtları Düzenleme Nasıl Çalışır?](#_core_editing_an_existing_record)

- [Kayıtları Silme Nasıl Çalışır?](#_core_deleting_a_record)

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma kullanıyorsanız, [bkz.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Ek olarak, Kayıt Alanı [Değişimi okumak isteyebilirsiniz: Nasıl RFX Çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md), güncelleştirme işlemlerinde RFX karşılık gelen rolünü açıklar.

## <a name="adding-a-record"></a><a name="_core_adding_a_record"></a>Kayıt Ekleme

Bir kayıt kümesine yeni bir kayıt eklemek, kayıt kümesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevini çağırmayı, yeni kaydın alan veri üyelerinin değerlerini ayarlamayı ve kaydı veri kaynağına yazmak için [Update](../../mfc/reference/crecordset-class.md#update) üye işlevini çağırmayı içerir.

Arama `AddNew`için bir ön koşul olarak, kayıt kümesi salt okunur olarak açılmamış olmalıdır. Ve `CanUpdate` `CanAppend` üye işlevler bu koşulları belirlemenize izin sağlar.

Ne zaman: `AddNew`

- Düzenarabelleği'ndeki kayıt depolanır, böylece işlem iptal edilirse içeriği geri yüklenebilir.

- Alan veri üyeleri işaretlenir, böylece değişiklikler daha sonra algılanır. Alan verileri üyeleri de temiz (değişmeden) olarak işaretlenir ve Null olarak ayarlanır.

Aramadan `AddNew`sonra, edit arabelleği, değerlerle doldurulmaya hazır yeni, boş bir kaydı temsil eder. Bunu yapmak için, değerleri el ile bunlara atayarak ayarlarsınız. Bir alan için gerçek bir veri değeri belirtmek `SetFieldNull` yerine, Null değerini belirtmek için arayabilirsiniz.

Değişikliklerinizi işlemek için `Update`. Yeni kayıt `Update` için aradiğinizde:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC kaydı veri kaynağına eklemek için işlevi kullanır. Ile, `::SQLSetPos`MFC bir SQL deyimi oluşturmak ve işlemek zorunda değildir, çünkü daha verimli bir kayıt ekleyebilirsiniz.

- Kullanılamıyorsa, `::SQLSetPos` MFC aşağıdakileri yapar:

   1. Hiçbir değişiklik algılanmadıysa, `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklik varsa, `Update` bir SQL **INSERT** deyimi oluşturuyor. Tüm kirli alan veri üyeleri tarafından temsil edilen sütunlar **INSERT** deyiminde listelenir. Bir sütunu dahil etmeye zorlamak için [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) üye işlevini arayın:

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update`yeni kaydı işler — **INSERT** deyimi yürütülür ve bir işlem devam etmediği sürece kayıt veri kaynağındaki tabloya (ve anlık görüntü değilse kayıt kümesine) adamıştır.

   1. Depolanan kayıt düzen arabelleği geri yüklenir. `AddNew` **INSERT** deyiminin başarıyla yürütülüp yürütülmediğine bakılmaksızın, aramadan önce geçerli olan kayıt yeniden geçerlidir.

   > [!TIP]
   > Yeni bir kaydın tam denetimi için aşağıdaki yaklaşımı alın: değerlere sahip olacak tüm alanların değerlerini ayarlayın ve `SetFieldNull` ardından alana işaretçi ve DOĞRU (varsayılan) parametreyle çağırarak Null kalacak alanları açıkça ayarlayın. Bir alanın veri kaynağına yazılmadığından emin olmak `SetFieldDirty` istiyorsanız, alan için bir işaretçi ve FALSE parametresi ile arayın ve alanın değerini değiştirmeyin. Bir alanın Null olup olmadığını belirlemek `IsFieldNullable`için.

   > [!TIP]
   > Kayıt kümesi veri üyelerinin değeri ne zaman değiştirdiğini algılamak için, MFC bir kayıt kümesinde depolayabildiğiniz her veri türüne uygun PSEUDO_NULL bir değer kullanır. PSEUDO_NULL değerine açıkça bir alan ayarlamanız gerekiyorsa ve alan zaten Null olarak `SetFieldNull`işaretlenmişse, alanın adresini ilk parametrede ve FALSE'u ikinci parametrede geçirerek de aramalısınız.

## <a name="visibility-of-added-records"></a><a name="_core_visibility_of_added_records"></a>Eklenen Kayıtların Görünürlüğü

Ek bir kayıt kayıt setinizde ne zaman görünür? Eklenen kayıtlar bazen görünür ve bazen iki şeye bağlı olarak görünmez:

- Şoförünün yapabilecekleri.

- Çerçevenin yararlanabileceği şey.

ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC kayıt eklemek için işlevi kullanır. Ile `::SQLSetPos`, eklenen kayıtlar herhangi bir güncelmis MFC kayıt kümesi için görülebilir. İşlev için destek olmadan, eklenen kayıtlar görünmez `Requery` ve bunları görmek için aramanız gerekir. Kullanmak `::SQLSetPos` da daha verimlidir.

## <a name="editing-an-existing-record"></a><a name="_core_editing_an_existing_record"></a>Varolan Kaydı Düzenleme

Bir kayıt kümesindeki varolan bir kaydı düzenlemek, kayda kaydırmayı, kayıt setinin [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevini çağırmayı, yeni kaydın alan veri üyelerinin değerlerini ayarlamayı ve değiştirilen kaydı veri kaynağına yazmak için [Update](../../mfc/reference/crecordset-class.md#update) üye işlevini çağırmayı içerir.

Arama `Edit`için bir ön koşul olarak, kayıt kümesi güncellenebilir ve kayıt üzerinde olmalıdır. Ve `CanUpdate` `IsDeleted` üye işlevler bu koşulları belirlemenize izin sağlar. Geçerli kayıt da zaten silinmemiş olmalı ve kayıt kümesinde (her `IsBOF` `IsEOF` ikisi de ve 0 döndürün) kayıtlar olmalıdır.

Aradığınızda, `Edit`edit arabelleğindeki kayıt (geçerli kayıt) depolanır. Depolanan kaydın değerleri daha sonra herhangi bir alanın değişip değişmediğini algılamak için kullanılır.

Aradıktan `Edit`sonra, edit arabelleği hala geçerli kaydı temsil eder, ancak şimdi alan veri üyelerideğişiklikleri kabul etmeye hazırdır. Kaydı değiştirmek için, değiştirmek istediğiniz alan veri üyelerinin değerlerini el ile ayarlarsınız. Bir alan için gerçek bir veri değeri belirtmek `SetFieldNull` yerine, Null değerini belirtmek için arayabilirsiniz. Değişikliklerinizi işlemek için `Update`.

> [!TIP]
> Çıkmak `AddNew` veya `Edit` modda, `Move` *parametre AFX_MOVE_REFRESH*ile arayın.

Arama `Update`için ön koşul olarak, kayıt kümesi boş olmamalı ve geçerli kayıt silinmemiş olmalıdır. `IsBOF`, `IsEOF`, `IsDeleted` ve tüm 0 dönmelidir.

Düzenlenen kaydı `Update` aradiğinizde:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC veri kaynağındaki kaydı güncelleştirmek için işlevi kullanır. Sürücü, `::SQLSetPos`düzenleme arabelleğinizi sunucudaki ilgili kayıtla karşılaştırır ve ikisi farklıysa sunucudaki kaydı günceller. Ile, `::SQLSetPos`MFC bir SQL deyimi oluşturmak ve işlemek zorunda değildir, çünkü daha verimli bir kayıt güncelleştirebilirsiniz.

   \-veya -

- Kullanılamıyorsa, `::SQLSetPos` MFC aşağıdakileri yapar:

   1. Herhangi bir değişiklik olmadıysa, `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklik varsa, `Update` bir SQL **UPDATE** deyimi oluşturuyor. **UPDATE** deyiminde listelenen sütunlar, değişen alan veri üyelerini temel alır.

   1. `Update`değişiklikleri işler — **UPDATE** deyimini yürütür ve bir işlem devam ediyorsa kayıt veri kaynağında değiştirilir, ancak işlem devam ediyorsa kaydedilmez (bkz. işlemin güncelleştirmeyi nasıl etkilediği hakkında bilgi almak için [Kayıt Kümesinde İşlem Gerçekleştirme (ODBC).](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) ODBC, kaydın bir kopyasını tutar ve bu da değişir.

   1. Için işlemin `AddNew`aksine, `Edit` işlem depolanan kaydı geri yüklemez. Düzenlenen kayıt geçerli kayıt olarak yerinde kalır.

   > [!CAUTION]
   > Bir kayıt kümesini arayarak `Update`güncelleştirmeye hazırlanırken, kayıt setinizin tablonun birincil anahtarını oluşturan tüm sütunları (veya tablodaki benzersiz dizinin tüm sütunlarını veya satırı benzersiz olarak tanımlamak için yeterli sütunları) içerdiğine dikkat edin. Bazı durumlarda, çerçeve yalnızca kayıt setinizde seçilen sütunları kullanarak tablonuzdaki hangi kaydın güncelleştirilemesini belirleyebilir. Gerekli tüm sütunlar olmadan, tabloda birden çok kayıt güncelleştirilebilir. Bu durumda, çerçeve çağırdığınızda `Update`özel durumlar atar.

   > [!TIP]
   > Daha önce `AddNew` `Edit` işlevden birini aradıysanız veya aradıktan `Update`sonra, düzenleme arabelleği depolanan kayıtla yenilenir ve devam eden yeni veya düzenlenen kaydın yerine yenilenir. Bu `AddNew` davranış, bir iptal etmek veya `Edit` yeni bir başlangıç için bir yol verir: kayıt devam hatalı `Edit` olduğunu `AddNew` belirlerseniz, sadece arama veya tekrar.

## <a name="deleting-a-record"></a><a name="_core_deleting_a_record"></a>Kaydı Silme

Bir kaydı niçin kayıt kümesinden silmek, kayda kaydırmayı ve kayıt setinin [Delete](../../mfc/reference/crecordset-class.md#delete) üye işlevini çağırmayı içerir. Aksine `AddNew` `Edit`ve `Delete` , '' için `Update`eşleşen bir çağrı gerektirmez.

Arama `Delete`için bir ön koşul olarak, kayıt kümesi güncellenebilir olmalı ve bir kayıt olmalıdır. , `CanUpdate` `IsBOF`, `IsEOF`ve `IsDeleted` üye işlevler bu koşulları belirlemenize izin sağlar.

Ne zaman: `Delete`

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC veri kaynağındaki kaydı silmek için işlevi kullanır. Kullanmak `::SQLSetPos` genellikle SQL kullanmaktan daha etkilidir.

   \-veya -

- Kullanılamıyorsa, `::SQLSetPos` MFC aşağıdakileri yapar:

   1. Edit arabelleğindeki geçerli kayıt, içinde olduğu `AddNew` `Edit`gibi yedeklenmez ve.

   1. `Delete`kaydı kaldıran bir SQL **DELETE** deyimi oluşturuyor.

      Edit arabelleğindeki geçerli kayıt içinde `AddNew` olduğu `Edit`gibi depolanmaz ve .

   1. `Delete`silme işlemini işler — **DELETE** deyimini yürütür. Kayıt veri kaynağında silinir ve kayıt anlık görüntü ise, ODBC'de silinir.

   1. Silinen kaydın değerleri hala kayıt kümesinin alan veri üyelerindedir, ancak alan veri üyeleri `IsDeleted` Null olarak işaretlenir ve kayıt kümesinin üye işlevi sıfır olmayan bir değer döndürür.

   > [!NOTE]
   > Bir kaydı sildikten sonra, yeni kaydın verileriyle birlikte edit arabelleği yeniden doldurmak için başka bir kayda kaydırmanız gerekir. Tekrar aramak `Delete` veya aramak `Edit`bir hatadır.

Güncelleştirme işlemlerinde kullanılan SQL deyimleri hakkında bilgi [için](../../data/odbc/sql.md)BKZ.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
