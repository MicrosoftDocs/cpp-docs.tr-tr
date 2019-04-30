---
title: 'Kayıt kümesi: Nasıl AddNew, düzenleme ve silme çalışma (ODBC)'
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
ms.openlocfilehash: e5fc6ad2a1fe00367cd8a0b1c53ac914b95018ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397841"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Kayıt kümesi: Nasıl AddNew, düzenleme ve silme çalışma (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu açıklar nasıl `AddNew`, `Edit`, ve `Delete` sınıfın üye işlevleri `CRecordset` çalışır. Kapsanan konular şunlardır:

- [Kayıt eklemeler nasıl çalışır](#_core_adding_a_record)

- [Eklenen kayıtların görünürlüğü](#_core_visibility_of_added_records)

- [Kayıtları düzenleme nasıl çalışır](#_core_editing_an_existing_record)

- [Kayıtların işleri nasıl silinir](#_core_deleting_a_record)

> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Ek olarak, okumak isteyebilirsiniz [kayıt alanı değişimi: RFX'in çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md), RFX güncelleştirme işlemlerine karşılık gelen rolünü açıklar.

##  <a name="_core_adding_a_record"></a> Kayıt ekleme

Bir kayıt kümesine yeni bir kayıt eklenmesini kapsar kayıt kümesinin çağırma [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevi, yeni kayıttaki alan veri üyelerinin değerlerini ayarlama ve çağırma [güncelleştirme](../../mfc/reference/crecordset-class.md#update) yazmak için üye işlevi veri kaynağına kayıt.

Arama için bir önkoşul olarak `AddNew`, kayıt kümesinin salt okunur olarak açılmış olmalıdır değil. `CanUpdate` Ve `CanAppend` üye işlevleri, bu koşullar belirlemenize olanak tanır.

Çağırdığınızda `AddNew`:

- Kaydı düzenleme arabelleğindeki depolanır, bu işlemi iptal edildi durumunda içeriğinin geri yüklenebilmesi için.

- Alan veri üyeleri, daha sonra bunları değişikliklerini algılamak olası olacak şekilde işaretlenir. Alan veri üyeleri ayrıca işaretlenir (değişmeden) temizlemek ve Null değerine ayarlayın.

Çağırdıktan sonra `AddNew`kayda hazır değerleri doldurulacak boş, yeni bir düzenleme arabelleğini temsil eder. Bunu yapmak için el ile değerlerini atayarak ayarlayın. Bir alan için gerçek bir veri değeri belirtmek yerine çağırabilirsiniz `SetFieldNull` Null değer belirtebilirsiniz.

Değişikliklerinizi kaydetmek için çağrı `Update`. Çağırdığınızda `Update` yeni kayıt için:

- ODBC sürücünüz destekliyorsa `::SQLSetPos` MFC ODBC API işlevini, veri kaynağında kayıt eklemek için işlevi kullanır. İle `::SQLSetPos`, MFC ekleyebileceğiniz bir kayıt daha verimli bir şekilde çünkü bir SQL deyimi oluşturmak ve işlemek yok.

- Varsa `::SQLSetPos` olamaz kullanıldığında, MFC şunları yapar:

   1. Değişiklik algılanırsa `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklikleri, varsa `Update` SQL yapıları **Ekle** deyimi. Tüm kirli alan veri üyeleri tarafından temsil edilen sütunlar listelenen **Ekle** deyimi. Dahil edilecek sütun zorlamak için çağrı [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) üye işlevi:

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update` Yeni kayıt uygular — **Ekle** deyimi yürütülür ve bir işlem devam ediyor sürece veri kaynağına (ve kayıt, bir anlık görüntü değilse) tablosunda hassastır kaydıdır.

   1. Depolanmış kayıt düzenleme ara geri yüklenir. Önce geçerli kaydı `AddNew` çağrıdır yeniden bakılmaksızın geçerli **Ekle** bildirimi başarıyla yürütüldü.

   > [!TIP]
   > Yeni bir kaydın tam denetim için aşağıdaki yaklaşımı: değerleri ve Null çağırarak kalacak herhangi bir alan açıkça ayarlanmış herhangi bir alan değerlerini ayarlayın `SetFieldNull` alan ve parametre bir işaretçi ile (varsayılan) TRUE. Bir alan veri kaynağına çağrı yazılmaz emin olmak istiyorsanız `SetFieldDirty` alan ve yanlış parametre bir işaretçi ile ve alanın değerini değiştirmeyin. Bir alan Null olmasına izin verilip verilmeyeceğini belirlemek için çağrı `IsFieldNullable`.

   > [!TIP]
   > Kayıt kümesi veri üyeleri, değer değiştirdiğinizde algılamak için bir kayıt kümesinde depoladığınız her bir veri türü için uygun bir PSEUDO_NULL değer MFC kullanır. Bir alan açıkça PSEUDO_NULL değerine ayarlamanız gerekir ve Null işaretlenecek alanı zaten olur, ayrıca çağırmanız gerekir `SetFieldNull`, ikinci parametre ilk parametre ve yanlış adres alanının geçirme.

##  <a name="_core_visibility_of_added_records"></a> Eklenen kayıtların görünürlüğü

Eklenen bir kayıt kümenize görünür olduğunda olmadığı? Eklenen kayıtlar bazen gösterir ve bazen bağlı olarak iki şey görünür değildir:

- Sürücünüzün neyi sahiptir.

- Framework yararlanabilirsiniz.

ODBC sürücünüz destekliyorsa `::SQLSetPos` MFC ODBC API işlevini kayıtları eklemek için işlevi kullanır. İle `::SQLSetPos`, kayıtları herhangi güncelleştirilebilir bir MFC kayıt görünür eklenir. Kayıtları görünür değildir ve çağırmalısınız işlevine yönelik desteği olmadan eklenen `Requery` bunları görmek için. Kullanarak `::SQLSetPos` de daha etkilidir.

##  <a name="_core_editing_an_existing_record"></a> Varolan bir kaydı düzenleme

Bir kayıt kümesinde varolan bir kaydı düzenleme içerir kayıt kümesinin çağırma kaydı için kaydırma [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevi, yeni kayıttaki alan veri üyelerinin değerlerini ayarlama ve çağırma [güncelleştirme](../../mfc/reference/crecordset-class.md#update)değiştirilmiş bir kaydı veri kaynağına yazmak için üye işlevi.

Arama için bir önkoşul olarak `Edit`, güncelleştirilebilir ve kayıtla ilgili kayıt olması gerekir. `CanUpdate` Ve `IsDeleted` üye işlevleri, bu koşullar belirlemenize olanak tanır. Geçerli kayıt de zaten silinmemiş gerekir ve kayıt kümesindeki kayıtları olmalıdır (her ikisi de `IsBOF` ve `IsEOF` 0 döndürür).

Çağırdığınızda `Edit`, kayıt düzenleme arabelleği (geçerli kaydı) içinde depolanır. Saklı kaydın değerler daha sonra herhangi bir alanın değişip değişmediğini algılamak için kullanılır.

Çağırdıktan sonra `Edit`, düzenleme arabellek hala geçerli kayıt temsil eder ancak artık alan veri üyeleri değişiklikleri kabul etmeye hazır. Kaydı değiştirmek için el ile düzenlemek istediğiniz herhangi bir alan veri üyelerinin değerlerini ayarlayın. Bir alan için gerçek bir veri değeri belirtmek yerine çağırabilirsiniz `SetFieldNull` Null değer belirtebilirsiniz. Değişikliklerinizi kaydetmek için çağrı `Update`.

> [!TIP]
> Faydalanmaya yönelik `AddNew` veya `Edit` modu, çağrı `Move` parametresiyle *AFX_MOVE_REFRESH*.

Arama için bir önkoşul olarak `Update`, kayıt kümesi boş olmamalı ve geçerli kayıt öğeleri silinmemiş gerekir. `IsBOF`, `IsEOF`, ve `IsDeleted` tüm 0 döndürmelidir.

Çağırdığınızda `Update` düzenlenen kaydı için:

- ODBC sürücünüz destekliyorsa `::SQLSetPos` MFC ODBC API işlevini, veri kaynağındaki kaydı güncelleştirmek için işlevi kullanır. İle `::SQLSetPos`, sürücü düzenleme arabelleğin iki farklı ise, sunucunun kaydını güncelleştirme sunucusundaki karşılık gelen kayıt ile karşılaştırır. İle `::SQLSetPos`, MFC güncelleştirebilirsiniz kayıt daha verimli bir şekilde çünkü bir SQL deyimi oluşturmak ve işlemek yok.

   \- veya -

- Varsa `::SQLSetPos` olamaz kullanıldığında, MFC şunları yapar:

   1. Herhangi bir değişiklik olduğunda `Update` hiçbir şey yapmaz ve 0 döndürür.

   1. Değişiklikleri, varsa `Update` SQL yapıları **güncelleştirme** deyimi. Listelenen sütunları **güncelleştirme** ifadesi, değişen alan veri üyeleri dayalı.

   1. `Update` değişiklikleri uygular — yürütür **güncelleştirme** deyimi — ve veri kaynağında kayıt değiştirilir, ancak bir işlem değil taahhüt varsa ediyor (bkz [işlem: Bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) işlem güncelleştirme nasıl etkilediği hakkında bilgi için). ODBC kaydı da değiştiren bir kopyasını tutar.

   1. İşlemin aksine `AddNew`, `Edit` işlem depolanmış kayıt geri yüklemiyor. Düzenlenmiş kayıt yerinde geçerli kayıt olarak kalır.

   > [!CAUTION]
   > Bir kayıt kümesi çağırarak güncelleştirmek hazırlama zaman `Update`, kümenizin tabloyu (veya tüm sütunları tablosunda benzersiz bir dizin veya satırın benzersiz olarak tanımlanabilmesi için yeterli sütun) birincil anahtar yapma tüm sütunları içeren ilgileniriz. Bazı durumlarda, framework kümenize Seçili sütunları güncelleştirmek için tablodaki hangi kaydı tanımlamak için kullanabilirsiniz. Tüm gerekli sütunları, birden çok kayıt tablodaki güncelleştirilebilir. Bu durumda, framework istisnalar fırlatıyorsa çağırdığınızda `Update`.

   > [!TIP]
   > Çağırırsanız `AddNew` veya `Edit` ya da daha önce ancak önce çağrılan işlev sonra çağırma `Update`, değiştirme yeni veya düzenlenen kaydının sürüyor depolanmış kayıt düzenleme arabelleği yenilenir. Bu davranış, iptal etmek için bir yol sağlar bir `AddNew` veya `Edit` ve yeni bir tane başlayın: ilerleme içinde kaydı hatalı olduğunu belirlerseniz, yalnızca çağrı `Edit` veya `AddNew` yeniden.

##  <a name="_core_deleting_a_record"></a> Kayıt silme

Bir kayıt kümesinden bir kaydı silmek için kayıt kaydırma ve kümesinin çağırma ilgilidir [Sil](../../mfc/reference/crecordset-class.md#delete) üye işlevi. Farklı `AddNew` ve `Edit`, `Delete` eşleşen bir çağrı gerektirmez `Update`.

Arama için bir önkoşul olarak `Delete`kayıt güncelleştirilebilir olmalıdır ve bir kayıt üzerinde olmalıdır. `CanUpdate`, `IsBOF`, `IsEOF`, Ve `IsDeleted` üye işlevleri, bu koşullar belirlemenize olanak tanır.

Çağırdığınızda `Delete`:

- ODBC sürücünüz destekliyorsa `::SQLSetPos` MFC ODBC API işlevini, veri kaynağındaki bir kaydı silmek için işlevi kullanır. Kullanarak `::SQLSetPos` SQL kullanmaktan genellikle daha verimli olur.

   \- veya -

- Varsa `::SQLSetPos` olamaz kullanıldığında, MFC şunları yapar:

   1. Geçerli kayıt düzenleme arabellek olarak yedeklenmez `AddNew` ve `Edit`.

   1. `Delete` bir SQL yapıları **Sil** deyimi kaydını kaldırır.

      Geçerli kayıt düzenleme arabellek olarak depolanmaz `AddNew` ve `Edit`.

   1. `Delete` silme işlemi uygular — yürütür **Sil** deyimi. Kayıt veri kaynağında silindi olarak işaretlenir ve kaydın bir anlık görüntü ODBC içinde ise.

   1. Yine de alan veri üyeleri kayıt kümesinin silinmiş kaydın değerlerdir ancak alan veri üyeleri, Null ve kümesinin işaretlenmiş `IsDeleted` üye işlevi, sıfır olmayan bir değer döndürür.

   > [!NOTE]
   > Bir kayıt sildikten sonra yeni kayıttaki verilerle düzenleme arabelleği puanı almak için başka bir kayda gitmeniz gerekir. Çağırmak için bir hata olduğunu `Delete` yeniden veya çağrılacak `Edit`.

Güncelleştirme işlemlerinde kullanılan SQL deyimleri hakkında daha fazla bilgi için bkz. [SQL](../../data/odbc/sql.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Güncelleştirmeler Hakkında Daha Fazla Bilgi (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)