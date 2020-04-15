---
title: "Kayıt Alanı Değişimi: RFX'in Çalışması"
ms.date: 11/04/2016
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
ms.openlocfilehash: 903acf4f55fb2708f4998a2babf3f143c895429b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367166"
---
# <a name="record-field-exchange-how-rfx-works"></a>Kayıt Alanı Değişimi: RFX'in Çalışması

Bu konu RFX işlemini açıklar. Bu kapsayan gelişmiş bir konudur:

- [RFX ve kayıt seti](#_core_rfx_and_the_recordset)

- [RFX süreci](#_core_the_record_field_exchange_process)

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı sınıflar için geçerlidir. Toplu satır alma kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX benzer. Farklılıkları anlamak için bkz: [Recordset: Kayıtları Toplu Olarak Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="rfx-and-the-recordset"></a><a name="_core_rfx_and_the_recordset"></a>RFX ve Kayıt Kümesi

Kaydedici nesnenin alan veri üyeleri, birlikte ele alındığında, bir kaydın seçili sütunlarını tutan bir edit arabelleği oluşturur. Kayıt kümesi ilk açıldığında ve ilk kaydı okumak üzereyken, RFX seçilen her sütunu uygun alan veri üyesinin adresine bağlar (ilişkilendirer). Kayıt kümesi bir kaydı güncelleştirdiğinde, RFX sürücüye bir SQL **UPDATE** veya **INSERT** deyimi göndermek için ODBC API işlevlerini çağırır. RFX, yazacak sütunları belirtmek için alan veri üyeleri hakkındaki bilgilerini kullanır.

Çerçeve, gerekirse içeriğini geri yükleyebilmek için belirli aşamalarda düzenarabellebellesini yedekler. RFX, yeni bir kayıt eklemeden ve varolan bir kaydı düzenlemeden önce düzenleme arabelleği yedekler. Bazı durumlarda, örneğin, bir `Update` çağrı aşağıdaki `AddNew`sonra düzeneği geri yükler. Örneğin, başka bir kayda geçerek yeni değiştirilen bir düzenleme arabelleği terk ederseniz düzenleme `Update`arabelleği geri yüklenmez.

RFX, veri kaynağı ile kayıt kümesinin alan veri üyeleri arasında veri alışverişinin yanı sıra bağlama parametrelerini yönetir. Kayıt kümesi açıldığında, herhangi bir parametre veri üyesi, `CRecordset::Open` sql deyimini oluşturan "?" yer tutucularının sırasına bağlanır. Daha fazla bilgi için [bkz: Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

Recordset sınıfınızın geçersiz kılma `DoFieldExchange` tüm işi yapar, verileri her iki yöne de hareket ettirin. İletişim veri alışverişi (DDX) gibi, RFX'in de sınıfınızın veri üyeleri hakkında bilgiye ihtiyacı vardır. Sihirbaz, sihirbazla belirttiğiniz alan verileri üye `DoFieldExchange` adlarını ve veri türlerini temel alarak sizin için kayıt kümesine özgü bir uygulama yazarak gerekli bilgileri sağlar.

## <a name="record-field-exchange-process"></a><a name="_core_the_record_field_exchange_process"></a>Kayıt Alanı Değişim Süreci

Bu bölümde, rfx olaylarının sırasını, kayıt kümesi nesnesi açılırken ve siz kayıtları ekledikçe, güncellerken ve sildiğinizde açıklar. [Recordset Open sırasında RFX İşlemleri tablo sırası](#_core_sequence_of_rfx_operations_during_recordset_open) ve bu konuda Kaydırma sırasında RFX İşlemleri tablo `Move` [sırası, RFX](#_core_sequence_of_rfx_operations_during_scrolling) kayıt kümesinde bir komut u işlerken ve RFX bir güncelleştirmeyi yönetirken işlemi gösterir. Bu işlemler sırasında, [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) birçok farklı işlemleri gerçekleştirmek için çağrılır. `m_nOperation` [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesinin veri üyesi hangi işlemin istendiğini belirler. [Recordset: How Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [Recordset: How Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) bu materyali okumadan önce okumayı yararlı bulabilirsiniz.

### <a name="rfx-initial-binding-of-columns-and-parameters"></a><a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: Sütunların ve Parametrelerin İlk Bağlanması

Aşağıdaki RFX etkinlikleri, gösterilen sırada, bir kayıt kümesi nesnesinin [Açık](../../mfc/reference/crecordset-class.md#open) üye işlevini çağırdığınızda oluşur:

- Kayıt kümesinde parametre veri üyeleri varsa, çerçeve parametreleri kayıt kümesinin SQL deyimi dizesinde parametre yer tutucularına bağlamayı çağırır. `DoFieldExchange` **SELECT** deyiminde bulunan her yer tutucu için parametre değerinin veri türüne bağlı gösterimi kullanılır. Bu, SQL deyimi hazırlandıktan sonra ancak yürütülmeden önce oluşur. İfade hazırlama hakkında bilgi `::SQLPrepare` için, ODBC *Programcısının Başvurusu*işlevine bakın.

- Çerçeve, `DoFieldExchange` seçili sütunların değerlerini kayıt kümesindeki ilgili alan veri üyelerine bağlamak için ikinci kez çağrıda bulunur. Bu, kayıt kümesi nesnesini ilk kaydın sütunlarını içeren bir edit arabelleği olarak kurar.

- Kaydedici aygıt SQL deyimini yürütür ve veri kaynağı ilk kaydı seçer. Kaydın sütunları kayıt kümesinin alan veri üyelerine yüklenir.

Aşağıdaki tablo, bir kayıt kümesini açtığınızda RFX işlemlerinin dizisini gösterir.

### <a name="sequence-of-rfx-operations-during-recordset-open"></a><a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>Recordset Open Sırasında RFX İşlemleri dizisi

|Bu|DoFieldExchange işlemi|Veritabanı/SQL işlemi|
|--------------------|-------------------------------|-----------------------------|
|1. Kayıt kümesini açın.|||
||2. Bir SQL deyimi oluşturun.||
|||3. SQL'i gönderin.|
||4. Parametre veri üyelerini bağla.||
||5. Alan veri üyelerini sütunlara bağla.||
|||6. ODBC taşıma yapar ve verileri doldurur.|
||7. C++'ın verilerini düzeltin.||

Kayıt kümeleri, aynı SQL deyimiyle hızlı yeniden sorgulamaya olanak sağlamak için ODBC'nin hazır yürütmesini kullanır. Hazırlanan yürütme hakkında daha fazla bilgi için MSDN Kitaplığı'ndaki ODBC SDK *Programcısı* Referansı'na bakın.

### <a name="rfx-scrolling"></a><a name="_mfc_rfx.3a_.scrolling"></a>RFX: Kaydırma

Bir kayıttan diğerine kaydırdığınızda, `DoFieldExchange` çerçeve, alan veri saklarında daha önce depolanan değerleri yeni kayıt değerleriyle değiştirmeyi çağırır.

Aşağıdaki tabloda, kullanıcı kayıttan kayda geçtiğinde RFX işlemlerinin sırasını gösterilmektedir.

### <a name="sequence-of-rfx-operations-during-scrolling"></a><a name="_core_sequence_of_rfx_operations_during_scrolling"></a>Kaydırma Sırasında RFX İşlemleri dizisi

|Bu|DoFieldExchange işlemi|Veritabanı/SQL işlemi|
|--------------------|-------------------------------|-----------------------------|
|1. `MoveNext` Arama veya diğer Taşı işlevlerinden birini arayın.|||
|||2. ODBC taşıma yapar ve verileri doldurur.|
||3. C++'ın verilerini düzeltin.||

### <a name="rfx-adding-new-records-and-editing-existing-records"></a><a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: Yeni Kayıt Ekleme ve Varolan Kayıtları Düzenleme

Yeni bir kayıt eklerseniz, kayıt kümesi yeni kaydın içeriğini oluşturmak için bir edit arabelleği olarak çalışır. Kayıt eklemede olduğu gibi, kayıtları düzenleme, kayıt kümesinin alan veri üyelerinin değerlerini değiştirmeyi içerir. RFX perspektifinden, sıra aşağıdaki gibidir:

1. Kaydedici setin [in AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Edit](../../mfc/reference/crecordset-class.md#edit) üye işlevine yapılan çağrınız, RFX'in geçerli düzen arabelleği depolamasına neden olur, böylece daha sonra geri yüklenebilir.

1. `AddNew`veya `Edit` RFX'in değişen alan veri üyelerini algılayabilmesi için edit arabelleğindeki alanları hazırlar.

   Yeni bir kaydın yenileriyle karşılaştırılacak önceki `AddNew` değerleri olmadığından, her alan veri üyesinin değerini PSEUDO_NULL değerine ayarlar. Daha sonra, `Update`çağrı yaptığınızda, RFX her veri üyesinin değerini PSEUDO_NULL değeriyle karşılaştırır. Bir fark varsa, veri üyesi ayarlanmıştır. (PSEUDO_NULL gerçek Null değeri olan bir kayıt sütunu ile aynı değildir ne de bunların her ikisi de C++ NULL ile aynıdır.)

   Çağrının `Update` `AddNew` `Update` aksine, çağrı, `Edit` PSEUDO_NULL kullanmak yerine güncelleştirilen değerleri daha önce depolanan değerlerle karşılaştırır. Fark karşılaştırma `AddNew` için daha önce depolanmış değerleri olmasıdır.

1. Değerlerini yeniden ayarlamak istediğiniz veya yeni bir kayıt için doldurulmasını istediğiniz alan veri üyelerinin değerlerini doğrudan ayarlarsınız. Bu arama `SetFieldNull`içerebilir.

1. Değiştirilen alan veri üyeleri denetimlerini [güncelleştirme](../../mfc/reference/crecordset-class.md#update) çağrınız, adım 2'de açıklandığı gibi [(Kaydırma sırasında RFX İşlemleri tablo sırasına](#_core_sequence_of_rfx_operations_during_scrolling)bakın). Hiçbiri değişmemişse, `Update` 0 döndürür. Bazı alan verileri üyeleri `Update` değiştiyse, kayıttaki tüm güncelleştirilen alanlar için değerler içeren bir SQL **INSERT** deyimi hazırlar ve yürütür.

1. `AddNew`Çünkü, `Update` `AddNew` aramadan önce geçerli olan kaydın daha önce depolanan değerlerini geri alarak sona erer. Çünkü, `Edit`yeni, düzenlenmiş değerler yerinde kalır.

Aşağıdaki tablo, yeni bir kayıt eklediğinizde veya varolan bir kaydı düzenlediğınızda RFX işlemlerinin sırasını gösterir.

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>Ekle Yeni ve Düzenlediğim Demle sırasında RFX İşlemleri dizisi

|Bu|DoFieldExchange işlemi|Veritabanı/SQL işlemi|
|--------------------|-------------------------------|-----------------------------|
|1. `AddNew` Arama `Edit`veya .|||
||2. Edit arabelleği yedek.||
||3. `AddNew`Için, alan veri üyelerini "temiz" ve Null olarak işaretleyin.||
|4. Kayıt alanı veri üyelerine değer atayın.|||
|5. `Update`Çağrı .|||
||6. Değiştirilen alanları denetleyin.||
||7. Için `AddNew` SQL **INSERT** deyimi `Edit`veya **UPDATE** deyimi oluşturun.||
|||8. SQL'i gönderin.|
||9. `AddNew`Bunun için, düzen arabelleği yedeklenen içeriğine geri yükleyin. Bunun `Edit`için, yedeklemeyi silin.||

### <a name="rfx-deleting-existing-records"></a>RFX: Varolan Kayıtları Silme

Bir kaydı sildiğinizde, RFX tüm alanları kaydın silindiğini ve kayıttan çıkmanız gerektiğini hatırlatıcı olarak NULL olarak ayarlar. Başka bir RFX sıra bilgisine ihtiyacınız yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC Tüketimi](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Makrolar, Genel Fonksiyonlar ve Genel Değişkenler](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CfieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)
