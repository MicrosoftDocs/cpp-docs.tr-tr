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
ms.openlocfilehash: 0661e61bceeedc0dd049ef47f5a0a0b71a8d82ed
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213076"
---
# <a name="record-field-exchange-how-rfx-works"></a>Kayıt Alanı Değişimi: RFX'in Çalışması

Bu konuda RFX işlemi açıklanmaktadır. Bu, kapsayan gelişmiş bir konudur:

- [RFX ve kayıt kümesi](#_core_rfx_and_the_recordset)

- [RFX işlemi](#_core_the_record_field_exchange_process)

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen sınıflar için geçerlidir. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (toplu RFX) uygulanır. Toplu RFX, RFX 'e benzerdir. Farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="rfx-and-the-recordset"></a><a name="_core_rfx_and_the_recordset"></a>RFX ve kayıt kümesi

Kayıt kümesi nesnesinin alan veri üyeleri, birlikte alınan bir kayıt için seçili sütunları tutan bir düzenleme arabelleği oluşturur. Kayıt kümesi ilk açıldığında ve ilk kaydı okumak üzere olduğunda, RFX her seçili sütunu ilgili alan veri üyesinin adresine bağlar (ilişkilendirir). Kayıt kümesi bir kaydı güncelleştirdiğinde, RFX, sürücüye bir SQL **Update** veya **Insert** DEYIMLERI göndermek için ODBC API işlevlerini çağırır. RFX, yazılacak sütunları belirtmek için alan veri üyelerinin bilgisini kullanır.

Çerçeve, gerektiğinde içeriğini geri yükleyebilmek için belirli aşamalardaki düzenleme arabelleğini yedekler. RFX, yeni bir kayıt eklemeden önce ve var olan bir kaydı düzenlemeden önce düzenleme arabelleğini yedekler. Bazı durumlarda düzenleme arabelleğini geri yükler, örneğin, `AddNew`aşağıdaki `Update` çağrısından sonra. Yeni değiştirilen bir düzenleme arabelleğini, örneğin `Update`çağrılmadan önce başka bir kayda geçiş yaparak iptal ederseniz düzenleme arabelleği geri yüklenmez.

Veri kaynağı ve kayıt kümesi alan veri üyeleri arasında veri değişimi yanında, RFX bağlama parametrelerini yönetir. Kayıt kümesi açıldığında, tüm parametre veri üyeleri, `CRecordset::Open` yapılarını SQL deyimindeki "?" yer tutucuları sırasıyla bağlanır. Daha fazla bilgi için bkz. [kayıt kümesi: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

Kayıt kümesi sınıfınızın `DoFieldExchange` geçersiz kılması tüm işleri yapar ve her iki yönde de verileri taşır. İletişim kutusu veri değişimi (DDX) gibi, RFX 'in sınıfınızın veri üyeleri hakkında bilgi ihtiyacı vardır. Sihirbaz, sihirbazla belirttiğiniz alan verileri üye adlarına ve veri türlerine bağlı olarak, `DoFieldExchange` için kayıt kümesine özgü bir uygulama yazarak gerekli bilgileri sağlar.

##  <a name="record-field-exchange-process"></a><a name="_core_the_record_field_exchange_process"></a>Kayıt alanı değişim Işlemi

Bu bölümde, kayıt kümesi nesnesi açıldığı ve kayıt eklediğinizde, güncelleştirdiğinizde ve silerken RFX olaylarının sırası açıklanmaktadır. [Kayıt kümesi açma SıRASıNDA RFX işlemlerinin tablo sırası](#_core_sequence_of_rfx_operations_during_recordset_open) ve bu konuda [kaydırma sırasında RFX işlemleri tablo sırası](#_core_sequence_of_rfx_operations_during_scrolling) , rfx kayıt kümesindeki bir `Move` komutunu işleyen ve RFX 'in bir güncelleştirmeyi yönettiği bir işlemi gösterir. Bu işlemler sırasında, [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) birçok farklı işlem gerçekleştirecek şekilde çağırılır. [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesinin `m_nOperation` veri üyesi, hangi işlemin istendiğini belirler. Kayıt [kümelerinin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [kayıt kümesi: kayıt KÜMELERININ kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) , bu malzemeyi okuyabilmeniz için nasıl güncelleştirdiğiniz hakkında bilgi edinebilirsiniz.

###  <a name="rfx-initial-binding-of-columns-and-parameters"></a><a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: sütunların ve parametrelerin Ilk bağlaması

Aşağıdaki RFX etkinlikleri, bir kayıt kümesi nesnesinin [Open](../../mfc/reference/crecordset-class.md#open) üye işlevini çağırdığınızda gösterilen sırayla gerçekleşir:

- Kayıt kümesinde parametre veri üyeleri varsa, çerçeve, parametreleri kayıt kümesinin SQL deyimindeki parametre yer tutucularına bağlamak için `DoFieldExchange` çağırır. Parametre değerinin bir veri türüne bağımlı temsili, **Select** ifadesinde bulunan her yer tutucu için kullanılır. Bu, SQL ifadesinin hazırlanmasından, ancak yürütülmeden önce oluşur. Deyimin hazırlanması hakkında daha fazla bilgi için, bkz. ODBC *Programcı başvurusu*içindeki `::SQLPrepare` işlevi.

- Çerçeve, Seçili sütunların değerlerini kayıt kümesindeki ilgili alan veri üyelerine bağlamak için ikinci kez `DoFieldExchange` çağırır. Bu, kayıt kümesi nesnesini, ilk kaydın sütunlarını içeren bir düzenleme arabelleği olarak oluşturur.

- Kayıt kümesi SQL ifadesini yürütür ve veri kaynağı ilk kaydı seçer. Kaydın sütunları, kayıt kümesinin alan veri üyelerine yüklenir.

Aşağıdaki tabloda bir kayıt kümesini açtığınızda RFX işlemlerinin sırası gösterilmektedir.

### <a name="sequence-of-rfx-operations-during-recordset-open"></a><a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>Kayıt kümesi açıkken RFX Işlemlerinin sırası

|Bu|DoFieldExchange işlemi|Veritabanı/SQL işlemi|
|--------------------|-------------------------------|-----------------------------|
|1. kayıt kümesini açın.|||
||2. bir SQL açıklaması oluşturun.||
|||3. SQL 'i gönderin.|
||4. parametre veri üyelerini bağlayın.||
||5. alan veri üyelerini sütunlara bağlayın.||
|||6. ODBC taşı ve verileri doldurur.|
||7. verileri onarın C++.||

Kayıt kümeleri ODBC 'nin hazırlanan yürütmesini, aynı SQL ifadesiyle hızlı yeniden sorgulama sağlamak için kullanır. Hazırlanan yürütme hakkında daha fazla bilgi için, MSDN Kitaplığı 'ndaki ODBC SDK *Programmer 's başvurusuna* bakın.

###  <a name="rfx-scrolling"></a><a name="_mfc_rfx.3a_.scrolling"></a>RFX: kaydırma

Bir kayıttan diğerine kaydırma yaptığınızda çerçeve, alan veri üyelerinde daha önce depolanan değerleri yeni kayıt değerleriyle değiştirmek için `DoFieldExchange` çağırır.

Aşağıdaki tabloda, kullanıcı kayıttan kayda kaymışken RFX işlemlerinin sırası gösterilmektedir.

### <a name="sequence-of-rfx-operations-during-scrolling"></a><a name="_core_sequence_of_rfx_operations_during_scrolling"></a>Kaydırma sırasında RFX Işlemlerinin sırası

|Bu|DoFieldExchange işlemi|Veritabanı/SQL işlemi|
|--------------------|-------------------------------|-----------------------------|
|1. `MoveNext` veya diğer taşıma işlevlerinden birini çağırın.|||
|||2. ODBC taşı ve verileri doldurur.|
||3. verileri onarın C++.||

###  <a name="rfx-adding-new-records-and-editing-existing-records"></a><a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: yeni kayıtlar ekleme ve var olan kayıtları düzenlemeyle

Yeni bir kayıt eklerseniz, kayıt kümesi yeni kaydın içeriğini oluşturmak için bir düzenleme arabelleği olarak çalışır. Kayıt ekleme ile birlikte kayıtları düzenlemede, kayıt kümesinin alan veri üyelerinin değerlerinin değiştirilmesi gerekir. RFX perspektifinden, sırası aşağıdaki gibidir:

1. Kayıt kümenizin [AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Edit](../../mfc/reference/crecordset-class.md#edit) üye IŞLEVINE yapılan çağrı, RFX 'in geçerli düzenleme arabelleğini depolamasına ve bu sayede daha sonra geri yüklenebilmesini sağlar.

1. `AddNew` veya `Edit`, bir düzenleme arabelleğindeki alanları, RFX 'in değiştirilen alan veri üyelerini algılayabilmesi için hazırlar.

   Yeni bir kaydın, yenilerini karşılaştırmak için önceki değerleri olmadığından, `AddNew` her bir alan veri üyesinin değerini bir PSEUDO_NULL değerine ayarlar. Daha sonra, `Update`çağırdığınızda, RFX her bir veri üyesinin değerini PSEUDO_NULL değeriyle karşılaştırır. Fark varsa, veri üyesi ayarlanmıştır. (PSEUDO_NULL, doğru null değeri olan bir kayıt sütunuyla aynı veya ikisi de C++ null ile aynı olamaz.)

   `AddNew``Update` çağrısının aksine, `Edit` `Update` çağrısı, güncelleştirilmiş değerleri PSEUDO_NULL kullanmak yerine önceden depolanmış değerlerle karşılaştırır. Fark, `AddNew` karşılaştırma için önceden depolanmış değerler içermez.

1. Değerlerini düzenlemek istediğiniz veya yeni bir kayıt için doldurulmasını istediğiniz alan veri üyelerinin değerlerini doğrudan ayarlarsınız. Bu, çağırma `SetFieldNull`içerebilir.

1. 2\. adım ( [kaydırma SıRASıNDA RFX işlemlerinin tablo dizisine](#_core_sequence_of_rfx_operations_during_scrolling)bakın) bölümünde açıklandığı gibi, değiştirilen alan veri üyelerini [güncelleştirme](../../mfc/reference/crecordset-class.md#update) için yapılan çağrılarınız. Hiçbiri değiştirilmişse `Update` 0 döndürür. Bazı alan veri üyeleri değiştiyse, `Update` kayıttaki tüm güncelleştirilmiş alanlar için değerler içeren bir SQL **Insert** ifadesini hazırlar ve yürütür.

1. `AddNew`için, `Update` `AddNew` çağrısından önce geçerli olan kaydın önceden depolanmış değerlerini geri yükleyerek sonlanır. `Edit`için, yeni ve düzenlenmiş değerler yerinde kalır.

Aşağıdaki tabloda, yeni bir kayıt eklediğinizde veya var olan bir kaydı düzenlerken RFX işlemlerinin sırası gösterilmektedir.

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew ve Edit sırasında RFX Işlemlerinin sırası

|Bu|DoFieldExchange işlemi|Veritabanı/SQL işlemi|
|--------------------|-------------------------------|-----------------------------|
|1. `AddNew` veya `Edit`çağırın.|||
||2. düzenleme arabelleğini yedekleyin.||
||3. `AddNew`için alan veri üyelerini "temiz" ve null olarak işaretleyin.||
|4. değerleri kayıt kümesi alan veri üyelerine atayın.|||
|5. `Update`çağırın.|||
||6. değiştirilen alanları kontrol edin.||
||7. `Edit`için `AddNew` veya **güncelleştirme** bildiriminde SQL **Insert** ifadesini derleyin.||
|||8. SQL 'i gönderin.|
||9. `AddNew`için düzenleme arabelleğini yedeklenen içeriğe geri yükleyin. `Edit`için yedeklemeyi silin.||

### <a name="rfx-deleting-existing-records"></a>RFX: mevcut kayıtları silme

Bir kaydı sildiğinizde, RFX, kaydın silindiğini belirten bir anımsatıcı olarak tüm alanları NULL olarak ayarlar. Başka bir RFX sırası bilgisine ihtiyacınız yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC tüketme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Makrolar, genel Işlevler ve genel değişkenler](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CFieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::D oFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)
