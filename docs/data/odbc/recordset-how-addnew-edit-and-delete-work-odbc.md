---
description: 'Daha fazla bilgi: kayıt kümesi: AddNew, düzenleme ve silme Işi (ODBC)'
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
ms.openlocfilehash: 44211b6e1b1a0fc80c874e86ba83c2e6ea0ea43e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151404"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda `AddNew` `Edit` sınıfının, ve `Delete` üye işlevlerinin nasıl çalıştığı açıklanmaktadır `CRecordset` . Ele alınan konular:

- [Kayıt ekleme nasıl yapılır?](#_core_adding_a_record)

- [Eklenen kayıtların görünürlüğü](#_core_visibility_of_added_records)

- [Kayıtları düzenlemenin nasıl çalıştığı](#_core_editing_an_existing_record)

- [Kayıtları silme çalışma şekli](#_core_deleting_a_record)

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Ek olarak, güncelleştirme işlemlerinde RFX 'in karşılık gelen rolünü açıklayan [kayıt alanı değişimi](../../data/odbc/record-field-exchange-how-rfx-works.md)'ni okumak isteyebilirsiniz.

## <a name="adding-a-record"></a><a name="_core_adding_a_record"></a> Kayıt ekleme

Bir kayıt kümesine yeni bir kayıt eklemek, kayıt kümesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevinin çağrılmasını, yeni kaydın alan veri üyelerinin değerlerini ayarlamayı ve kaydı veri kaynağına yazmak için [Update](../../mfc/reference/crecordset-class.md#update) member işlevini çağırmayı içerir.

Çağırma için bir önkoşul olarak `AddNew` , kayıt kümesi salt okunurdur olarak açılmamalıdır. `CanUpdate`Ve `CanAppend` üye işlevleri bu koşulları belirlemenizi sağlar.

Şunu çağırdığınızda `AddNew` :

- Düzenleme arabelleğindeki kayıt depolanır, böylece işlem iptal edilirse içerikleri geri yüklenebilir.

- Alan veri üyeleri işaretlenir, böylece daha sonra yapılan değişiklikler algılanabilmesi mümkündür. Alan veri üyeleri de temiz (değiştirilmemiş) olarak işaretlenir ve null olarak ayarlanır.

`AddNew`' İ çağırdığınızda, düzenleme arabelleği yeni, boş bir kaydı, değerlerle doldurulmaya hazırlanmak üzere temsil eder. Bunu yapmak için değerleri bunlara atayarak el ile ayarlarsınız. Bir alan için gerçek bir veri değeri belirtmek yerine, `SetFieldNull` null değerini belirtmek için öğesini çağırabilirsiniz.

Değişikliklerinizi yürütmek için ' i çağırın `Update` . `Update`Yeni kayıt için ' i çağırdığınızda:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, kayıt verilerini veri kaynağına eklemek için işlevi kullanır. İle `::SQLSetPos` , MFC BIR SQL ifadesini oluşturmak ve işlemek zorunda olmadığı için bir kaydı daha verimli bir şekilde ekleyebilir.

- Kullanılamaz ise `::SQLSetPos` MFC şunları yapar:

   1. Hiçbir değişiklik algılanmazsa, `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklikler varsa, `Update` BIR SQL **Insert** ifadesini oluşturur. Tüm kirli alan verisi üyeleri tarafından temsil edilen sütunlar **Insert** ifadesinde listelenir. Bir sütunun eklenmesini zorlamak için [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) üye işlevini çağırın:

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update` Yeni kaydı kaydeder — **Insert** deyimleri yürütülür ve bir işlem devam etmediği takdirde kayıt, veri kaynağındaki tabloya (ve bir anlık görüntü yoksa, bu kayıt kümesine) kaydedilir.

   1. Depolanan kayıt düzenleme arabelleğine geri yüklendi. Çağrıdan önce geçerli olan kayıt `AddNew` **Insert** ifadesinin başarıyla yürütülüp yürütülmediğine bakılmaksızın geçerli olur.

   > [!TIP]
   > Yeni bir kaydın tüm denetimi için aşağıdaki yaklaşımı uygulayın: değer olacak herhangi bir alanın değerini ayarlayın ve ardından `SetFieldNull` alana yönelik bir işaretçi ve true parametresi (varsayılan) ile çağırarak null kalacak alanları açık olarak ayarlayın. Bir alanın veri kaynağına yazılmadığından emin olmak istiyorsanız, `SetFieldDirty` alana yönelik bir işaretçi ve false parametresini çağırın ve alanın değerini değiştirmeyin. Bir alanın null olmasına izin verilip verilmeyeceğini anlamak için çağrısı yapın `IsFieldNullable` .

   > [!TIP]
   > Kayıt kümesi veri üyelerinin değeri ne zaman değiştiğini algılamak için, MFC bir kayıt kümesinde depolayabileceği her veri türü için uygun bir PSEUDO_NULL değeri kullanır. PSEUDO_NULL değerine açıkça bir alan ayarlamanız gerekirse ve alan null olarak işaretlendiyse, aynı zamanda `SetFieldNull` ilk parametresindeki alanın adresini ve ikinci parametrede false değerini geçirerek çağırmanız gerekir.

## <a name="visibility-of-added-records"></a><a name="_core_visibility_of_added_records"></a> Eklenen kayıtların görünürlüğü

Kayıt kümenize eklenen bir kayıt ne zaman görünür? Eklenen kayıtlar bazen, iki duruma bağlı olarak görünür ve bazen görünür değildir:

- Sürücünüzün özelliği.

- Framework 'ün avantajından faydalanabilir.

ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, kayıt eklemek için işlevini kullanır. İle `::SQLSetPos` , eklenen kayıtlar güncellenebilir herhangi BIR MFC kayıt kümesi tarafından görülebilir. İşlevi için destek olmadan, eklenen kayıtlar görünmez ve bunları görmek için öğesini çağırmanız gerekir `Requery` . Kullanmak `::SQLSetPos` da daha etkilidir.

## <a name="editing-an-existing-record"></a><a name="_core_editing_an_existing_record"></a> Mevcut bir kaydı düzenleniyor

Bir kayıt kümesindeki mevcut bir kaydı düzenlemek, kayda kaydırma, kayıt kümesinin üye [düzenleme](../../mfc/reference/crecordset-class.md#edit) işlevini çağırma, yeni kaydın alan veri üyelerinin değerlerini ayarlama ve değiştirilen kaydın veri kaynağına yazılması için [Update](../../mfc/reference/crecordset-class.md#update) member işlevini çağırma ile ilgilidir.

Çağırma için bir önkoşul olarak `Edit` , kayıt kümesi güncelleştirilebilir ve bir kayıt üzerinde olmalıdır. `CanUpdate`Ve `IsDeleted` üye işlevleri bu koşulları belirlemenizi sağlar. Geçerli kayıt zaten silinmemiş olmalıdır ve kayıt kümesinde kayıt olmalıdır (her ikisi de `IsBOF` `IsEOF` 0 döndürür).

`Edit`' İ çağırdığınızda, Düzenleme arabelleğindeki kayıt (geçerli kayıt) depolanır. Depolanan kaydın değerleri daha sonra herhangi bir alanın değişip değişmediğini algılamak için kullanılır.

`Edit`' İ çağırdığınızda, düzenleme arabelleği hala geçerli kaydı temsil eder, ancak artık alan veri üyelerinde yapılan değişiklikleri kabul etmeye hazırdır. Kaydı değiştirmek için, düzenlemek istediğiniz herhangi bir alan veri üyesinin değerlerini el ile ayarlarsınız. Bir alan için gerçek bir veri değeri belirtmek yerine, `SetFieldNull` null değerini belirtmek için öğesini çağırabilirsiniz. Değişikliklerinizi yürütmek için çağrısı yapın `Update` .

> [!TIP]
> Veya modundan yararlanmak için `AddNew` `Edit` `Move` *AFX_MOVE_REFRESH* parametresiyle çağırın.

Çağırma için bir önkoşul olarak `Update` , kayıt kümesi boş olmamalı ve geçerli kayıt silinmemelidir. `IsBOF`, `IsEOF` , ve `IsDeleted` hepsi 0 döndürmelidir.

`Update`Düzenlenen kayıt için öğesini çağırdığınızda:

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, veri kaynağındaki kaydı güncelleştirmek için işlevini kullanır. İle `::SQLSetPos` , sürücü, düzenleme arabelleğini sunucu üzerindeki ilgili kayıtla karşılaştırır ve ikisi farklıysa sunucu üzerindeki kaydı güncelleyerek sunucuda kayıt güncelleştirilir. İle `::SQLSetPos` MFC, BIR SQL ifadesini oluşturmak ve işlemek zorunda olmadığından bir kaydı daha verimli bir şekilde güncelleştirebilir.

   \- veya

- Kullanılamaz ise `::SQLSetPos` MFC şunları yapar:

   1. Değişiklik yoksa, `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklikler varsa, `Update` BIR SQL **Update** ekstresi oluşturur. **Update** ifadesinde listelenen sütunlar değişmiş alan veri üyelerini temel alır.

   1. `Update` değişiklikleri kaydeder — **Update** ifadesini yürütür — ve kayıt veri kaynağında değiştirilir, ancak bir işlem devam ediyorsa (bkz. işlem [: bir kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) , işlemin güncelleştirmeyi nasıl etkilediği hakkında bilgi edinmek için). ODBC, kaydın bir kopyasını tutar ve bu da değişir.

   1. İşlemin aksine `AddNew` , `Edit` işlem depolanan kaydı geri yüklemez. Düzenlenen kayıt geçerli kayıt olarak yerinde kalır.

   > [!CAUTION]
   > Çağırarak bir kayıt kümesini güncelleştirmeye hazırlarken `Update` , kayıt kümenizin tablonun birincil anahtarını (veya tablodaki tüm benzersiz dizin sütunlarının tümünü veya satırı benzersiz olarak tanımlamak için yeterli sayıda sütunu) oluşturan tüm sütunları içerdiğinden emin olmalısınız. Bazı durumlarda Framework, tablonuzdaki hangi kaydın güncelleşdii belirlemek için yalnızca kayıt kümenizde seçilen sütunları kullanabilir. Tüm gerekli sütunlar olmadan, tabloda birden çok kayıt güncelleştirilemeyebilir. Bu durumda çerçeve, çağırdığınızda özel durum oluşturur `Update` .

   > [!TIP]
   > Çağrı `AddNew` yaptıktan sonra veya daha önce bir işlev çağırdıysanız `Edit` , çağrı yapmadan önce `Update` , düzenleme arabelleği saklı kayıtla yenilenir, bu da yeni veya düzenlenmiş kaydın devam ettiği şekilde değiştirilerek yapılır. Bu davranış, bir veya işlemini durdurmak için bir yol sağlar `AddNew` `Edit` ve yeni bir işlem başlatabilir: devam eden kaydın hatalı olduğunu belirlerseniz, `Edit` veya `AddNew` yeniden çağırın.

## <a name="deleting-a-record"></a><a name="_core_deleting_a_record"></a> Kayıt silme

Kayıt kümesinden bir kaydı silmek, kayda kaydırma ve kayıt kümesinin üye [silme](../../mfc/reference/crecordset-class.md#delete) işlevini çağırma işlemini içerir. Ve öğelerinden farklı olarak `AddNew` `Edit` , `Delete` öğesine eşleşen bir çağrı gerektirmez `Update` .

Çağırma için bir önkoşul olarak `Delete` , kayıt kümesi güncelleştirilebilir olmalıdır ve bir kayıt üzerinde olmalıdır. `CanUpdate`,, `IsBOF` , `IsEOF` Ve `IsDeleted` üye işlevleri bu koşulları belirlemenizi sağlar.

Şunu çağırdığınızda `Delete` :

- ODBC sürücünüz `::SQLSetPos` ODBC API işlevini destekliyorsa, MFC, veri kaynağındaki kaydı silmek için işlevini kullanır. Kullanmak `::SQLSetPos` genellıkle SQL kullanmaktan daha etkilidir.

   \- veya

- Kullanılamaz ise `::SQLSetPos` MFC şunları yapar:

   1. Düzenleme arabelleğindeki geçerli kayıt, ve ' de olduğu gibi yedeklenmez `AddNew` `Edit` .

   1. `Delete` kaydı kaldıran bir SQL **Delete** ifadesini oluşturur.

      Düzenleme arabelleğindeki geçerli kayıt, ve içinde olarak depolanmaz `AddNew` `Edit` .

   1. `Delete` silme işlemini kaydeder — **Delete** ifadesini yürütür. Kayıt, veri kaynağında silinmiş olarak işaretlenir ve kayıt bir anlık görüntüdür, ODBC 'de.

   1. Silinen kaydın değerleri hala kayıt kümesinin alan veri üyeleridir, ancak alan veri üyeleri null olarak işaretlenmiş ve kayıt kümesinin `IsDeleted` üye işlevi sıfır dışında bir değer döndürüyor.

   > [!NOTE]
   > Bir kaydı sildikten sonra, yeni kaydın verileriyle düzenleme arabelleğini yeniden doldurmak için başka bir kayda kaydırmanız gerekir. Yeniden çağırmak veya çağırmak için bir hata oluştu `Delete` `Edit` .

Güncelleştirme işlemlerinde kullanılan SQL deyimleri hakkında daha fazla bilgi için bkz. [SQL](../../data/odbc/sql.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: güncelleştirmeler hakkında daha fazla bilgi (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
