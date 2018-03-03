---
title: "Kayıt Alanı Değişimi: RFX'in çalışması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5eac97bb87103bd72dfd721515baf58324fc851f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-how-rfx-works"></a>Kayıt Alanı Değişimi: RFX'in Çalışması
Bu konu RFX işlemini açıklar. Gelişmiş budur konu kapsayıcı:  
  
-   [RFX ve kayıt kümesi](#_core_rfx_and_the_recordset)  
  
-   [RFX işlemi](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX için benzer. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_rfx_and_the_recordset"></a>RFX ve kayıt kümesi  
 Kayıt kümesi nesnesinin alan veri üyeleri birlikte, bir kayıt seçili sütunlarını tutan düzenleme arabelleği oluşturur. Kayıt kümesi ilk açıldığında ve yaklaşık ilk kaydı okumak üzere olduğunda RFX bağlar (ilişkilendirir her) sütun adresine uygun alan veri üyesi seçilir. Kayıt kümesi bir kaydı güncelleştirdiğinde, bir SQL göndermek için ODBC API işlevlerini RFX çağrılarını **güncelleştirme** veya **Ekle** sürücü deyimi. RFX bildiğini alan veri üyeleri yazmak için sütunları belirlemek için kullanır.  
  
 Bu içeriği gerekirse geri yükleyebilmek framework belirli aşamalarda düzenleme arabelleğini yedekler. RFX, yeni bir kayıt ekleme ve varolan bir kaydı düzenleme önce düzenleme arabelleğini yedekler. Sonra bazı durumlarda, örneğin, düzenleme arabelleği yükler bir **güncelleştirme** çağrısı aşağıdaki `AddNew`. Varsa, yeni değiştirilen düzenleme arabelleği, örneğin, başka bir kayıtla çağırmadan önce taşıma abandon düzenleme arabelleği geri yüklenmez **güncelleştirme**.  
  
 Veri kaynağı ve kayıt kümesinin alan veri üyeleri arasında veri değişimi yanı sıra RFX bağlama parametrelerini yönetir. Kayıt kümesi açıldığında, herhangi bir parametre veri üyesi sırasına göre bağlanır "?" SQL deyimi yer tutucuları, `CRecordset::Open` oluşturur. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Kayıt kümesi sınıfınızın geçersiz kılmak `DoFieldExchange` her iki yönde de veri taşıma tüm işlerini yapar. İletişim kutusu veri değişimi (DDX) gibi RFX sınıfınızın veri üyeleri hakkında bilgi gerekiyor. Kayıt kümesi özgü uyarlamasını yazarak sihirbaz gerekli bilgileri sağlar `DoFieldExchange` Sihirbazı'nı kullanarak belirttiğiniz üye adları ve veri türleri, alan verileri temel alan.  
  
##  <a name="_core_the_record_field_exchange_process"></a>Kayıt alanı değişim işlemi  
 Eklediğinizde, güncelleştirme ve kayıtları silin ve kayıt kümesi nesnesi açıldığında RFX olayların sırası Bu bölümde açıklanmaktadır. Tablo [sırası, RFX işlemleri sırasında kayıt kümesi açık](#_core_sequence_of_rfx_operations_during_recordset_open) ve tablo [sırası, kaydırma sırasında RFX işlemlerinin](#_core_sequence_of_rfx_operations_during_scrolling) bu konudaki RFX işlemleri olarak işlem Göster bir **taşıma**kümesinde komutunu ve bir güncelleştirme RFX yönetir. Bu işlemler sırasında [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) birçok farklı işlemler gerçekleştirmek üzere çağırılır. **CFieldExchange** veri üyesi [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesne belirler hangi işlemi istendi. Okumak yararlı bulabileceğiniz [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) bu okumadan önce.  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: Sütun ve parametre ilk bağlama  
 Kayıt kümesi nesnesinin çağırdığınızda gösterilen sırada aşağıdaki RFX etkinlikleri, ortaya [açık](../../mfc/reference/crecordset-class.md#open) üye fonksiyonu:  
  
-   Kayıt kümesi parametre veri üyeleri varsa, framework çağırması `DoFieldExchange` kayıt kümenizin SQL deyimini dizesi parametre yer tutucularını parametreleri bağlamak için. Bir veri türüne bağlı gösterimi parametre değeri için her bir yer tutucu kullanılan bulunan **seçin** deyimi. SQL deyimi hazırlandıktan sonra fakat çalıştırılmadan önce gerçekleşir. Deyim hazırlama hakkında daha fazla bilgi için bkz: **:: SQLPrepare** ODBC işlevinde *Programcının Başvurusu*.  
  
-   Framework çağrıları `DoFieldExchange` kümesinde karşılık gelen alan veri üyeleri, seçili sütunların değerlerini bağlamak için ikinci kez. Bu, ilk kaydı sütunları içeren bir düzenleme arabellek kayıt kümesi nesnesi oluşturur.  
  
-   Kayıt kümesi SQL deyimini yürütür ve veri kaynağı ilk kaydı seçer. Kaydın sütunları kayıt kümesinin alan veri üyeleri yüklenir.  
  
 Bir kayıt kümesi açtığınızda, aşağıdaki tabloda RFX işlemleri dizisini gösterir.  
  
### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>Kayıt kümesi açma sırasında RFX işlemlerinin sırası  
  
|İşlemi|DoFieldExchange işlemi|Veritabanı/SQL işlemi|  
|--------------------|-------------------------------|-----------------------------|  
|1. Kayıt kümesi'ni açın.|||  
||2. Bir SQL deyimi oluşturun.||  
|||3. SQL gönderin.|  
||4. Parametre veri üyeleri bağlayın.||  
||5. Alan veri üyeleri sütunlarına bağlayın.||  
|||6. ODBC hareket eder ve verileri doldurur.|  
||7. Verileri yedeklemek için C++ düzeltin.||  
  
 Kayıt kümeleri ODBC hazırlanan yürütme aynı SQL deyimi ile hızlı yeniden sorgulama için izin vermek için kullanın. Hazırlanan yürütme hakkında daha fazla bilgi için bkz: ODBC SDK *Programcının Başvurusu* MSDN Kitaplığı'nda.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a>RFX: kaydırma  
 Başka bir kayıttan gezinirken framework çağırması `DoFieldExchange` alan veri üyeleri yeni kayıt değerleri ile önceden depolanan değerleri değiştirmek için.  
  
 Kullanıcı kaydı başka bir kayıt getirdiğinde aşağıdaki tabloda RFX işlemleri dizisini gösterir.  
  
### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a>Kaydırma sırasında RFX işlem dizisi  
  
|İşlemi|DoFieldExchange işlemi|Veritabanı/SQL işlemi|  
|--------------------|-------------------------------|-----------------------------|  
|1. Çağrı `MoveNext` veya diğer taşıma işlevlerinden biri.|||  
|||2. ODBC hareket eder ve verileri doldurur.|  
||3. Verileri yedeklemek için C++ düzeltin.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: Yeni kayıtlar ekleme ve varolan kayıtları düzenleme  
 Yeni bir kayıt eklerseniz, yeni kaydın içeriği oluşturmak için bir düzenleme arabellek olarak kayıt çalışır. Kayıtlar ekleme gibi ile kayıtlarını düzenleme kayıt kümesinin alan veri üyeleri değerlerini değiştirilmesidir. RFX açısından dizisi aşağıdaki gibidir:  
  
1.  Aramanız kümesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevi daha sonra geri yüklenebilmesi için geçerli düzenleme arabelleğini depolamak RFX neden olur.  
  
2.  `AddNew`veya **Düzenle** düzenleme arabelleği alanları RFX değiştirilen alan veri üyeleri algılayabilmesi için hazırlar.  
  
     Yeni bir kayıt yenilerini ile karşılaştırmak için önceki değer olmadığından `AddNew` her alan veri üyesi değerini ayarlar bir **PSEUDO_NULL** değeri. Daha sonra çağırdığınızda **güncelleştirme**, RFX her veri üyesinin değerle karşılaştırır **PSEUDO_NULL** değeri. Bir fark ise, veri üyesi ayarlandı. (**PSEUDO_NULL** true Null değerine sahip bir kayıt sütunu aynı değildir veya bunlardan değil C++ aynı **NULL**.)  
  
     Farklı **güncelleştirme** çağrısı `AddNew`, **güncelleştirme** çağrısı **Düzenle** karşılaştırır, önceden depolanan değerleri ile kullanmakyerinedeğerlerigüncelleştirilmiş**PSEUDO_NULL**. Aralarındaki fark `AddNew` karşılaştırma için önceden depolanan hiçbir değerlerine sahip.  
  
3.  Düzenlemek istediğiniz değerleri veya yeni bir kayıt için doldurulmasını istediğiniz doğrudan alan veri üyeleri değerlerini ayarlayın. Bu arama içerebilir `SetFieldNull`.  
  
4.  Aramanız için [güncelleştirme](../../mfc/reference/crecordset-class.md#update) 2. adımda açıklandığı gibi değiştirilen alan veri üyeleri için denetler (tabloya bakın [sırası, kaydırma sırasında RFX işlemlerinin](#_core_sequence_of_rfx_operations_during_scrolling)). Değiştirdiyseniz, **güncelleştirme** 0 döndürür. Bazı alan veri üyeleri değiştirdiyseniz, **güncelleştirme** hazırlar ve bir SQL yürütür **Ekle** kaydındaki tüm güncelleştirilmiş alanların değerlerini içeren ifade.  
  
5.  İçin `AddNew`, **güncelleştirme** önce geçerli kaydı önceden depolanan değerlerini geri yükleyerek sonlanır `AddNew` çağırın. İçin **Düzenle**, yeni ve düzenlenen değerleri yerinde kalır.  
  
 Aşağıdaki tabloda, yeni bir kayıt eklemek ya da varolan bir kaydı düzenlediğinizde RFX işlemleri dizisini gösterir.  
  
### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>Ekleme ve düzenleme sırasında RFX işlemlerinin sırası  
  
|İşlemi|DoFieldExchange işlemi|Veritabanı/SQL işlemi|  
|--------------------|-------------------------------|-----------------------------|  
|1. Çağrı `AddNew` veya **Düzenle**.|||  
||2. Düzenleme arabelleğini yedekleyin.||  
||3. İçin `AddNew`, alan veri üyeleri "temiz" olarak işaretler ve Null.||  
|4. Kayıt kümesi alan veri üyeleri için değerler atayın.|||  
|5. Çağrı **güncelleştirme**.|||  
||6. Değiştirilen alanları kontrol edin.||  
||7. SQL derleme **Ekle** bildirimi `AddNew` veya **güncelleştirme** bildirimi **Düzenle**.||  
|||8. SQL gönderin.|  
||9. İçin `AddNew`, düzenleme arabelleği yedeklenen içeriğini geri yükleme. İçin **Düzenle**, yedekleme silin.||  
  
### <a name="rfx-deleting-existing-records"></a>RFX: Varolan kayıtları silme  
 Kaydı sildiğinizde, RFX tüm alanları ayarlar **NULL** kaydı silinir ve devre dışı taşımalısınız bir anımsatıcı olarak. Diğer bir RFX sıralama bilgisi gerekmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Makrolar, genel işlevler ve genel değişkenler](../../mfc/reference/mfc-macros-and-globals.md)  
 [CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)