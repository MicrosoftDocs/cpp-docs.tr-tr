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
ms.openlocfilehash: 8799ac36c443898f1e32b539f017e682bbf3e033
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212919"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda, sınıf `CRecordset` `AddNew`, `Edit`ve `Delete` üye işlevlerinin nasıl çalıştığı açıklanmaktadır. Ele alınan konular:

- [Kayıt ekleme nasıl yapılır?](#_core_adding_a_record)

- [Eklenen kayıtların görünürlüğü](#_core_visibility_of_added_records)

- [Kayıtları düzenlemenin nasıl çalıştığı](#_core_editing_an_existing_record)

- [Kayıtları silme çalışma şekli](#_core_deleting_a_record)

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Ek olarak, güncelleştirme işlemlerinde RFX 'in karşılık gelen rolünü açıklayan [kayıt alanı değişimi](../../data/odbc/record-field-exchange-how-rfx-works.md)'ni okumak isteyebilirsiniz.

##  <a name="adding-a-record"></a><a name="_core_adding_a_record"></a>Kayıt ekleme

Bir kayıt kümesine yeni bir kayıt eklemek, kayıt kümesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevinin çağrılmasını, yeni kaydın alan veri üyelerinin değerlerini ayarlamayı ve kaydı veri kaynağına yazmak için [Update](../../mfc/reference/crecordset-class.md#update) member işlevini çağırmayı içerir.

`AddNew`çağırmanın bir önkoşulu olarak, kayıt kümesi salt okunurdur olarak açılmamalıdır. `CanUpdate` ve `CanAppend` üye işlevleri bu koşulları belirlemenizi sağlar.

`AddNew`çağırdığınızda:

- Düzenleme arabelleğindeki kayıt depolanır, böylece işlem iptal edilirse içerikleri geri yüklenebilir.

- Alan veri üyeleri işaretlenir, böylece daha sonra yapılan değişiklikler algılanabilmesi mümkündür. Alan veri üyeleri de temiz (değiştirilmemiş) olarak işaretlenir ve null olarak ayarlanır.

`AddNew`çağırdıktan sonra, düzenleme arabelleği, değerlerle doldurulmaya yönelik yeni, boş bir kaydı temsil eder. Bunu yapmak için değerleri bunlara atayarak el ile ayarlarsınız. Bir alan için gerçek bir veri değeri belirtmek yerine, null değerini belirtmek için `SetFieldNull` çağırabilirsiniz.

Değişikliklerinizi kaydetmek için `Update`çağırın. Yeni kayıt için `Update` çağırdığınızda:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, kayıt verilerini veri kaynağına eklemek için işlevi kullanır. `::SQLSetPos`, MFC bir SQL ifadesini oluşturmak ve işlemek zorunda olmadığından, bir kaydı daha verimli bir şekilde ekleyebilir.

- `::SQLSetPos` kullanılmıyorsa MFC şunları yapar:

   1. Hiçbir değişiklik algılanmazsa `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklikler varsa `Update` bir SQL **Insert** ifadesini oluşturur. Tüm kirli alan verisi üyeleri tarafından temsil edilen sütunlar **Insert** ifadesinde listelenir. Bir sütunun eklenmesini zorlamak için [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) üye işlevini çağırın:

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update` yeni kaydı kaydeder — **Insert** deyimleri yürütülür ve bir işlem devam etmediği takdirde kayıt, veri kaynağındaki tabloya (ve anlık görüntü değilse) kaydedilir.

   1. Depolanan kayıt düzenleme arabelleğine geri yüklendi. `AddNew` çağrısından önce geçerli olan kayıt **Insert** ifadesinin başarıyla yürütülmediğine bakılmaksızın geçerli olur.

   > [!TIP]
   > Yeni bir kaydın tüm denetimi için aşağıdaki yaklaşımı uygulayın: değer olacak herhangi bir alanın değerini ayarlayın ve ardından `SetFieldNull` bir işaretçiye ve TRUE parametresine (varsayılan) sahip çağırarak null kalacak alanları açık olarak ayarlayın. Bir alanın veri kaynağına yazılmadığından emin olmak istiyorsanız, alana yönelik bir işaretçi ve FALSE parametresi ile birlikte `SetFieldDirty` çağırın ve alanın değerini değiştirmeyin. Bir alanın null olmasına izin verilip verilmeyeceğini anlamak için `IsFieldNullable`çağırın.

   > [!TIP]
   > Kayıt kümesi veri üyelerinin değeri ne zaman değiştiğini algılamak için, MFC bir kayıt kümesinde depolayabileceği her veri türü için uygun bir PSEUDO_NULL değeri kullanır. PSEUDO_NULL değerine açıkça bir alanı ayarlamanız gerekiyorsa ve alan null olarak işaretlendiyse, aynı zamanda, alanın adresini ilk parametrede ve ikinci parametrede FALSE olarak geçirerek `SetFieldNull`çağırmanız gerekir.

##  <a name="visibility-of-added-records"></a><a name="_core_visibility_of_added_records"></a>Eklenen kayıtların görünürlüğü

Kayıt kümenize eklenen bir kayıt ne zaman görünür? Eklenen kayıtlar bazen, iki duruma bağlı olarak görünür ve bazen görünür değildir:

- Sürücünüzün özelliği.

- Framework 'ün avantajından faydalanabilir.

ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, kayıt eklemek için işlevini kullanır. `::SQLSetPos`, eklenen kayıtlar güncellenebilir herhangi bir MFC kayıt kümesine görünür. İşlevi için destek olmadan, eklenen kayıtlar görünmez ve bunları görmek için `Requery` çağırmanız gerekir. `::SQLSetPos` kullanmak da daha etkilidir.

##  <a name="editing-an-existing-record"></a><a name="_core_editing_an_existing_record"></a>Mevcut bir kaydı düzenleniyor

Bir kayıt kümesindeki mevcut bir kaydı düzenlemek, kayda kaydırma, kayıt kümesinin üye [düzenleme](../../mfc/reference/crecordset-class.md#edit) işlevini çağırma, yeni kaydın alan veri üyelerinin değerlerini ayarlama ve değiştirilen kaydın veri kaynağına yazılması için [Update](../../mfc/reference/crecordset-class.md#update) member işlevini çağırma ile ilgilidir.

`Edit`çağırma önkoşulu olarak, kayıt kümesi güncelleştirilebilir ve bir kayıt üzerinde olmalıdır. `CanUpdate` ve `IsDeleted` üye işlevleri bu koşulları belirlemenizi sağlar. Geçerli kayıt zaten silinmemiş olmalıdır ve kayıt kümesinde kayıt olmalıdır (her ikisi de `IsBOF` ve `IsEOF` 0 döndürür).

`Edit`çağırdığınızda, Düzenleme arabelleğindeki kayıt (geçerli kayıt) depolanır. Depolanan kaydın değerleri daha sonra herhangi bir alanın değişip değişmediğini algılamak için kullanılır.

`Edit`çağırdıktan sonra, düzenleme arabelleği hala geçerli kaydı temsil eder, ancak artık alan veri üyelerinde yapılan değişiklikleri kabul etmeye hazırdır. Kaydı değiştirmek için, düzenlemek istediğiniz herhangi bir alan veri üyesinin değerlerini el ile ayarlarsınız. Bir alan için gerçek bir veri değeri belirtmek yerine, null değerini belirtmek için `SetFieldNull` çağırabilirsiniz. Değişikliklerinizi kaydetmek için `Update`çağırın.

> [!TIP]
> `AddNew` veya `Edit` modundan yararlanmak için *AFX_MOVE_REFRESH*parametresiyle `Move` çağırın.

`Update`çağırma önkoşulu olarak, kayıt kümesi boş olmamalı ve geçerli kayıt silinmemelidir. `IsBOF`, `IsEOF`ve `IsDeleted` hepsi 0 döndürmelidir.

Düzenlenen kayıt için `Update` çağırdığınızda:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, veri kaynağındaki kaydı güncelleştirmek için işlevini kullanır. `::SQLSetPos`, sürücü, düzenleme arabelleğini sunucudaki ilgili kayıtla karşılaştırır ve ikisi farklıysa sunucu üzerindeki kaydı güncelleyerek sunucuda kayıt güncelleştirilir. `::SQLSetPos`, MFC bir SQL ifadesini oluşturmak ve işlemek zorunda olmadığı için bir kaydı daha verimli bir şekilde güncelleştirebilir.

   \- veya-

- `::SQLSetPos` kullanılmıyorsa MFC şunları yapar:

   1. Değişiklik yoksa, `Update` hiçbir şey yapmaz ve 0 değerini döndürür.

   1. Değişiklikler varsa `Update` bir SQL **Update** bildirisi oluşturur. **Update** ifadesinde listelenen sütunlar değişmiş alan veri üyelerini temel alır.

   1. `Update` değişiklikleri kaydeder — **Update** ifadesini yürütür — ve kayıt veri kaynağında değiştirilir, ancak bir işlem devam ediyorsa (bkz. işlem [: bir kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) işlemin güncelleştirmeyi nasıl etkilediği hakkında bilgi için bkz. işlem. ODBC, kaydın bir kopyasını tutar ve bu da değişir.

   1. `AddNew`işleminin aksine `Edit` işlem, depolanan kaydı geri yüklemez. Düzenlenen kayıt geçerli kayıt olarak yerinde kalır.

   > [!CAUTION]
   > `Update`çağırarak bir kayıt kümesini güncelleştirmeye hazırlarken, kayıt kümenizin tablonun birincil anahtarını (veya tablodaki tüm benzersiz dizin sütunlarını veya satırı benzersiz olarak tanımlamak için yeterli sayıda sütunu) oluşturan tüm sütunları içerdiğinden emin olmalısınız. Bazı durumlarda Framework, tablonuzdaki hangi kaydın güncelleşdii belirlemek için yalnızca kayıt kümenizde seçilen sütunları kullanabilir. Tüm gerekli sütunlar olmadan, tabloda birden çok kayıt güncelleştirilemeyebilir. Bu durumda, `Update`çağırdığınızda çerçeve özel durumlar oluşturur.

   > [!TIP]
   > `AddNew` veya `Edit` daha önce herhangi bir işlevi çağırdıktan sonra ancak `Update`çağırmadan önce, düzenleme arabelleği saklı kayıtla yenilenir ve bu işlem devam etmekte olan yeni veya düzenlenmiş kaydı değiştirir. Bu davranış, bir `AddNew` veya `Edit` durdurmak ve yeni bir tane başlatmak için bir yol sağlar: devam eden kaydın hatalı olduğunu belirlerseniz, `Edit` veya `AddNew` yeniden çağırın.

##  <a name="deleting-a-record"></a><a name="_core_deleting_a_record"></a>Kayıt silme

Kayıt kümesinden bir kaydı silmek, kayda kaydırma ve kayıt kümesinin üye [silme](../../mfc/reference/crecordset-class.md#delete) işlevini çağırma işlemini içerir. `AddNew` ve `Edit`aksine `Delete` `Update`için eşleşen bir çağrı gerektirmez.

`Delete`çağırmanın bir önkoşulu olarak, kayıt kümesinin güncelleştirilebilir olması ve bir kayıtta olması gerekir. `CanUpdate`, `IsBOF`, `IsEOF`ve `IsDeleted` üye işlevleri bu koşulları belirlemenizi sağlar.

`Delete`çağırdığınızda:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, veri kaynağındaki kaydı silmek için işlevini kullanır. `::SQLSetPos` kullanmak, genellikle SQL kullanmaktan daha etkilidir.

   \- veya-

- `::SQLSetPos` kullanılmıyorsa MFC şunları yapar:

   1. Düzenleme arabelleğindeki geçerli kayıt `AddNew` ve `Edit`olarak yedeklenmez.

   1. `Delete` kaydı kaldıran bir SQL **Delete** ifadesini oluşturur.

      Düzenleme arabelleğindeki geçerli kayıt `AddNew` ve `Edit`olarak depolanmaz.

   1. silme işlemini işleme `Delete` — **Delete** ifadesini yürütür. Kayıt, veri kaynağında silinmiş olarak işaretlenir ve kayıt bir anlık görüntüdür, ODBC 'de.

   1. Silinen kaydın değerleri hala kayıt kümesinin alan veri üyeleridir, ancak alan veri üyeleri null olarak işaretlenmiş ve kayıt kümesinin `IsDeleted` member işlevi sıfır dışında bir değer döndürüyor.

   > [!NOTE]
   > Bir kaydı sildikten sonra, yeni kaydın verileriyle düzenleme arabelleğini yeniden doldurmak için başka bir kayda kaydırmanız gerekir. `Delete` yeniden çağırmak veya `Edit`çağırmak hatadır.

Güncelleştirme işlemlerinde kullanılan SQL deyimleri hakkında daha fazla bilgi için bkz. [SQL](../../data/odbc/sql.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
