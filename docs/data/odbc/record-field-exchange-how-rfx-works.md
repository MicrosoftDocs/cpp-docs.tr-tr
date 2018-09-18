---
title: "Kayıt Alanı Değişimi: RFX'in çalışması | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cf22876ee49538f9e9a162e5defe4abe693617e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037105"
---
# <a name="record-field-exchange-how-rfx-works"></a>Kayıt Alanı Değişimi: RFX'in Çalışması

Bu konuda RFX işlemi açıklanmaktadır. Bu gelişmiş bir, konuyu kapsayan:  
  
- [RFX ve kayıt](#_core_rfx_and_the_recordset)  
  
- [RFX işlemi](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Bulk RFX) uygulanır. Toplu RFX RFX için benzerdir. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_rfx_and_the_recordset"></a> RFX ve kayıt  

Kayıt kümesi nesnenin alan veri üyeleri birlikte, bir kaydın Seçili sütunları tutan düzenleme arabelleği oluşturur. Kayıt kümesini ilk açıldığında ve ilk kaydı hakkında okunacak olduğunda RFX bağlar (ilişkilendirir her) sütun uygun alan veri üyesi adresine seçili. Kayıt bir kaydı güncelleştirir, RFX SQL göndermek için ODBC API işlevlerini çağıran **güncelleştirme** veya **Ekle** sürücü deyimi. RFX bildiğini alan veri üyeleri yazmak için sütunları belirlemek için kullanır.  
  
Bu içeriği gerekirse geri yükleyebilmek framework düzenleme arabelleğini belirli aşamalarda yedekler. RFX düzenleme arabelleğini yeni kayıt ekleme ve varolan bir kaydı düzenleme önce yedekler. Bazı durumlarda, örneğin, Düzen arabellek sonra yükler bir `Update` çağrı aşağıdaki `AddNew`. Düzenleme arabelleği, yeni değiştirilen düzenleme arabellek, örneğin, başka bir kayda çağırmadan önce taşıma iptal durumunda geri yüklenmez `Update`.  
  
RFX veri kümesinin alan veri üyeleri veri kaynağı arasındaki değişimi yanı sıra, bağlama parametreleri yönetir. Kayıt kümesi açıldığında, herhangi bir parametre veri üyesi sırasıyla ilişkili "?" SQL deyimi içindeki yer tutucuları, `CRecordset::Open` oluşturur. Daha fazla bilgi için [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
Kayıt kümesi sınıfınızın geçersiz kılmak `DoFieldExchange` her iki yönde veri taşıma tüm işi yapar. İletişim kutusu veri değişimi (DDX) gibi sınıf veri üyeleri hakkında bilgi RFX gerekir. Sihirbaz bir kayıt kümesi özel uygulanışı yazarak gerekli bilgileri sağlar. `DoFieldExchange` sizin için Sihirbazı'nı kullanarak belirttiğiniz üye adları ve veri türleri alan verileri temel alan.  
  
##  <a name="_core_the_record_field_exchange_process"></a> Kayıt alanı değişim işlemi  

Bu bölümde bir kayıt kümesi nesnesi açıldığında RFX olayların sırasını açıklanmaktadır ve ekledikçe, güncelleştirme ve kayıt silme. Tablo [dizisi, RFX işlemleri sırasında kayıt açık](#_core_sequence_of_rfx_operations_during_recordset_open) ve tablo [dizisi, kaydırma sırasında RFX işlemlerinin](#_core_sequence_of_rfx_operations_during_scrolling) bu konudaki işlemi RFX işlemleri olarak göster. bir `Move` komutunu kayıt kümesi ve bir güncelleştirme RFX yönetir. Bu işlemler sırasında [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) birçok farklı işlemler gerçekleştirmek üzere çağırılır. `m_nOperation` Veri üyesi [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesne, istenen hangi işlem belirler. Okunacak yararlı bulabileceğiniz [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) bu okumadan önce.  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX: Sütun ve parametre ilk bağlama  

Kayıt kümesi nesnesinin çağırdığınızda gösterilen sırada aşağıdaki RFX etkinlikleri ortaya [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi:  
  
- Kayıt kümesi parametre veri üyeleri varsa, framework çağırır `DoFieldExchange` parametreleri kayıt kümenizin SQL deyimini dize parametresi yer tutucuları bağlanamıyor. Bulunan türe bağımlı gösterimini parametresinin değeri her bir yer tutucu için kullanılan bir veri **seçin** deyimi. SQL deyimi hazırlandıktan sonra fakat bunu yürütülmeden önce gerçekleşir. Deyim hazırlama hakkında daha fazla bilgi için bkz: `::SQLPrepare` ODBC işlevinde *Programcının Başvurusu*.  
  
- Framework çağrıları `DoFieldExchange` kümesinde karşılık gelen alan veri üyeleri, seçili sütunların değerlerini bağlamak için ikinci bir kez. Bu, ilk kayıt sütunlarını içeren bir düzen arabellek olarak kayıt kümesi nesnesi oluşturur.  
  
- Kayıt kümesi SQL deyimini yürütür ve veri kaynağının ilk kaydı seçer. Kaydın sütun kümesinin alan veri üyeleri yüklenir.  
  
Aşağıdaki tabloda, bir kayıt kümesi açtığınızda RFX işlemlerin sırasını gösterir.  
  
### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a> Kayıt kümesi açma sırasında RFX işlem dizisi  
  
|İşlemi|DoFieldExchange işlemi|Veritabanı/SQL işlemi|  
|--------------------|-------------------------------|-----------------------------|  
|1. Kayıt kümesi açın.|||  
||2. Bir SQL deyimi oluşturun.||  
|||3. SQL gönderin.|  
||4. Parametre veri üyeleri bağlayın.||  
||5. Alan veri üyeleri, sütun bağlayın.||  
|||6. ODBC hareket eder ve verileri doldurur.|  
||7. Verileri yedeklemek için C++ düzeltin.||  
  
Kayıt kümeleri ODBC hazırlanan yürütme hızlı aynı SQL deyimi ile kümesinde yeniden sorgulama için izin vermek için kullanın. Hazırlanan yürütme hakkında daha fazla bilgi için bkz: ODBC SDK *Programcının Başvurusu* MSDN Kitaplığı'nda.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX: kaydırma  

Başka bir kayıttan kaydırma framework çağırır `DoFieldExchange` alan veri üyeleri için yeni kayıt değerlerle daha önce depolanan değerleri değiştirmek için.  
  
Aşağıdaki tabloda, kullanıcı kaydı başka bir kayıt hareket ettirdiğinde RFX işlemlerin sırasını gösterir.  
  
### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a> Kaydırma sırasında RFX işlem dizisi  
  
|İşlemi|DoFieldExchange işlemi|Veritabanı/SQL işlemi|  
|--------------------|-------------------------------|-----------------------------|  
|1. Çağrı `MoveNext` veya diğer taşıma işlevlerinden biri.|||  
|||2. ODBC hareket eder ve verileri doldurur.|  
||3. Verileri yedeklemek için C++ düzeltin.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: Yeni kayıtlar ekleyerek ve var olan kayıtların düzenleme  

Yeni bir kayıt eklemek, kayıt yeni bir kaydın içeriğini oluşturmak için bir düzen arabellek olarak çalışır. Kayıtları olarak ekleme ile kayıtlarının düzenlenmesi kümesinin alan veri üyelerinin değerlerini değiştirilmesini kapsar. RFX açısından bakıldığında, sırası aşağıdaki gibidir:  
  
1. Çağrınız kümesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevini, daha sonra geri yüklenebilmesi için geçerli düzenleme arabelleğini depolamak RFX neden olur.  
  
1. `AddNew` veya `Edit` alanları düzenleme arabelleğindeki RFX değiştirilen alan veri üyeleri algılayabilmesi için hazırlar.  
  
     Yeni bir kayıt yenilerini ile Karşılaştırılacak önceki değer olmadığından `AddNew` PSEUDO_NULL değerine her alan veri üyesinin değerini ayarlar. Daha sonra çağırdığınızda `Update`, RFX her veri üyesinin değerini PSEUDO_NULL değerle karşılaştırır. Bir fark varsa, veri üyesi olarak ayarlandı. (PSEUDO_NULL kayıt sütunu doğru bir Null değeri ile aynı değil ya da bunlardan birisi olan C++ NULL olarak aynı.)  
  
     Farklı `Update` çağrısı `AddNew`, `Update` çağrısı `Edit` karşılaştırır, daha önce depolanan değerleri ile PSEUDO_NULL kullanmak yerine değerler güncelleştirildi. Fark `AddNew` hiçbir daha önce depolanan değerleri karşılaştırma için vardır.  
  
1. Düzenlemek istediğiniz değerleri için yeni bir kayıt doldurulmuş istediğiniz veya doğrudan alan veri üyelerinin değerlerini ayarlayın. Bu arama içerebilir `SetFieldNull`.  
  
1. Çağrınız [güncelleştirme](../../mfc/reference/crecordset-class.md#update) değiştirilen alan veri üyeleri için 2. adımda açıklandığı gibi denetler (tabloya bakın [dizisi, kaydırma sırasında RFX işlemlerinin](#_core_sequence_of_rfx_operations_during_scrolling)). Değiştirdiyseniz, `Update` 0 döndürür. Bazı alan veri üyeleri değişip değişmediğini `Update` hazırlar ve bir SQL yürütür **Ekle** kayıttaki tüm güncelleştirilmiş alanları için değerleri içeren ifade.  
  
1. İçin `AddNew`, `Update` önce geçerli kaydın daha önce depolanan değerlerin geri yükleyerek sonucuna `AddNew` çağırın. İçin `Edit`, yeni ve düzenlenen değerleri değiştirilmez.  
  
Aşağıdaki tabloda yeni bir kayıt eklemek ya da varolan bir kaydı düzenlemek RFX işlemlerin sırasını gösterir.  
  
### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>Ekleme ve düzenleme sırasında RFX işlem dizisi  
  
|İşlemi|DoFieldExchange işlemi|Veritabanı/SQL işlemi|  
|--------------------|-------------------------------|-----------------------------|  
|1. Çağrı `AddNew` veya `Edit`.|||  
||2. Düzenleme arabelleğini yedekleyin.||  
||3. İçin `AddNew`, alan veri üyeleri "temiz" olarak işaretler ve Null.||  
|4. Kayıt kümesi alan veri üyeleri için değerler atayın.|||  
|5. Çağrı `Update`.|||  
||6. Değiştirilen alanları kontrol edin.||  
||7. SQL derleme **Ekle** bildirimi `AddNew` veya **güncelleştirme** bildirimi `Edit`.||  
|||8. SQL gönderin.|  
||9. İçin `AddNew`, düzenleme arabellek yedeklenen içeriğini geri yükleme. İçin `Edit`, yedek silme.||  
  
### <a name="rfx-deleting-existing-records"></a>RFX: Var olan kayıtların siliniyor  

Kaydı sildiğinizde RFX tüm alanları kaydı silinir ve devre dışı taşımanız bir anımsatıcı olarak NULL olarak ayarlar. Diğer bir RFX sıralama bilgisi gerekmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Makrolar, genel işlevler ve genel değişkenler](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CFieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)