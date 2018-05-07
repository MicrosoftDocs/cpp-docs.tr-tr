---
title: 'Kayıt kümesi: Nasıl kümelerinin kayıtları seçme biçimi (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9ff2f1e9946eb32356eb09fa2ee216aa636a351
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Rolünüze ve kayıtları seçme'deki seçeneklerinizi](#_core_your_options_in_selecting_records).  
  
-   [Nasıl bir kayıt kümesi kendi SQL deyimini oluşturur ve kayıtları seçer](#_core_how_a_recordset_constructs_its_sql_statement).  
  
-   [Seçimi özelleştirmek için yapabileceklerinizi](#_core_customizing_the_selection).  
  
 Kayıt kümeleri kayıtları bir veri kaynağı bir ODBC sürücüsü aracılığıyla sürücüye SQL deyimlerini göndererek seçin. Gönderilen SQL nasıl, tasarım ve kayıt kümesi sınıfınız açmak bağlıdır.  
  
##  <a name="_core_your_options_in_selecting_records"></a> Kayıtları seçme, seçenekleri  
 Aşağıdaki tabloda, kayıtları seçme seçeneklerinizi gösterir.  
  
### <a name="how-and-when-you-can-affect-a-recordset"></a>Ne zaman ve nasıl kayıt etkileyebilir  
  
|Olduğunda,|Şunları yapabilirsiniz|  
|--------------|-------------|  
|Kayıt kümesi sınıfınızı bildirmek **sınıfı Ekle** Sihirbazı|Seçim yapılacak tablo belirtin.<br /><br /> Hangi sütunların ekleneceğini belirtin.<br /><br /> Bkz: [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|  
|Kayıt kümesi sınıf uygulamanızı tamamlayın|Üye işlevleri gibi geçersiz kılma `OnSetOptions` (Gelişmiş) uygulamaya özgü seçeneklerini ayarlamak için veya varsayılanları değiştirmek için. Parametreli kayıt kümesi istiyorsanız parametre veri üyeleri belirtin.|  
|Kayıt kümesi nesnesi oluşturun (çağırmadan önce **açık**)|Kullanmak için (büyük olasılıkla bileşik) arama koşulu belirtin bir **burada** kayıtları filtre yan tümcesi. Bkz: [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Kullanmak için bir sıralama düzeni belirtin bir **ORDER BY** kayıtları sıralar yan tümcesi. Bkz: [kayıt kümesi: Kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Sınıfa eklediğiniz herhangi bir parametre için parametre değerlerini belirtin. Bkz: [kayıt kümesi: kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|  

| Çağırarak kümesinin sorgusunu çalıştırmak **açık**| Sihirbaz tarafından ayarlanan varsayılan SQL dizesini değiştirmek için özel bir SQL dizesi belirtin. Bkz: [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) içinde *sınıf kitaplığı başvurusu* ve [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |  

| Çağrı **Requery** kayıt kümesi veri kaynağında en son değerleri ile sorgulayacak | Yeni parametreler, filtre ya da sıralama belirtin. Bkz: [kayıt kümesi: kayıt kümesi (ODBC) yeniden sorgulama](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Bir kayıt kümesi kendi SQL deyimini nasıl oluşturur  
 Kayıt kümesi nesnesinin çağırdığınızda [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi **açık** bazılarını veya tümünü aşağıdaki içeriklerin kullanarak bir SQL deyimi oluşturur:  
  
-   **LpszSQL** parametresi geçirilen **açık**. Aksi takdirde **NULL**, bu parametre bir özel SQL dizesi ya da bir parçası belirtir. Çerçeve dizeyi ayrıştırır. Dize bir SQL ise **seçin** deyimi veya ODBC **ÇAĞRISI** deyimi, framework dize kayıt kümenizin SQL deyimini kullanır. Bir SQL oluşturmak için sağlanan dize "Seç" veya "{çağrı" ile başlamıyorsa çerçevesi kullanır **FROM** yan tümcesi.  
  
-   Tarafından döndürülen dize [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql). Varsayılan olarak, Kayıt Sihirbazı'nda için belirtilen tablo adıdır ancak işlevin getirdiğini değiştirebilirsiniz. Framework çağrıları `GetDefaultSQL` — dize "Seç" veya "{çağrı" ile başlamıyorsa, bir SQL dizesi oluşturmak için kullanılan bir tablo adı olduğu varsayılır.  
  

-   Tablonun belirli sütunlara bağlı olan alan veri üyeleri kayıt kümesi. Çerçeve kayıt sütunlarını arabellek olarak kullanarak, bu üyeler adreslerine bağlar. Tablo sütunlarından için alan veri üyeleri bağıntı framework belirler [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya toplu RFX işlev çağrılarını kayıt kümesinin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevi.  
  
-   [Filtre](../../data/odbc/recordset-filtering-records-odbc.md) içinde kayıt kümesi için varsa, barındırılan [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi. Çerçeve bir SQL oluşturmak için bu dizeyi kullanır **burada** yan tümcesi.  
  
-   [Sıralama](../../data/odbc/recordset-sorting-records-odbc.md) herhangi biri, içerdiği durumlarda kayıt kümesi için sipariş [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesi. Çerçeve bir SQL oluşturmak için bu dizeyi kullanır **ORDER BY** yan tümcesi.  

  
    > [!TIP]
    >  SQL kullanılacak **GROUP BY** yan tümcesi (ve muhtemelen **HAVING** yan tümcesi), yan tümceleri filtre dizesi sonuna.  
  
-   Değerlerin herhangi [parametre veri üyeleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) için sınıfı belirtin. Yalnızca çağırmadan önce parametre değerlerini ayarlamak **açık** veya **Requery**. Çerçeve parametre değerlerini bağlar "?" yer tutucuları SQL dizesi. Derleme zamanında yer tutucularını dizeyi belirtin. Çalışma zamanında geçirdiğiniz parametre değerlerine göre ayrıntıları framework doldurur.  
  
 **Açık** bir SQL yapıları **seçin** bu maddelerden deyimi. Bkz: [seçimi özelleştirme](#_core_customizing_the_selection) framework malzemeleri nasıl kullandığı hakkında ayrıntılar için.  
  
 Deyimi oluşturduktan sonra **açık** SQL ODBC Sürücü Yöneticisi (ve ODBC imleç kitaplığı bellekte ise), gönderir gönderen ODBC sürücüsüne belirli DBMS için. Sürücü veri kaynağında seçimi gerçekleştiremeyen DBMS ile iletişim kurar ve ilk kaydı getirir. Framework kayıt kümesinin alan veri üyeleri yükler.  
  
 Açmak için bu teknikler birleşimini kullanabilirsiniz [tabloları](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) ve dayalı bir sorgu oluşturmak için bir [birleştirme](../../data/odbc/recordset-performing-a-join-odbc.md) birden çok tablo. Ek özelleştirme ile çağırabilirsiniz [önceden tanımlanmış sorgular](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (saklı yordamları), select tablo tasarım zamanında bilinmiyor sütunları ve [bağlamak](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) kendilerine kayıt kümesi alanları veya diğer birçok gerçekleştirebilirsiniz Veri erişim görevleri. Olamaz gerçekleştirmek kayıt kümeleri özelleştirerek görevleri hala gerçekleştirilebilir tarafından [ODBC API işlevlerini çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) veya doğrudan SQL deyimleri ile çalıştırma [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
##  <a name="_core_customizing_the_selection"></a> Seçimi özelleştirme  
 Bir filtre, sıralama düzeni veya parametreler sağlamanın yanı sıra, kümenizin seçimi özelleştirmek için aşağıdaki eylemleri gerçekleştirebilirsiniz:  
  
-   İçinde özel bir SQL dizesi geçirin **lpszSQL** çağırdığınızda [açık](../../mfc/reference/crecordset-class.md#open) kayıt kümesi için. Geçirdiğiniz herhangi bir şey **lpsqSQL** ne önceliklidir [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) üye işlevi döndürür.  
  
     Daha fazla bilgi için bkz: [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), türlerini açıklayan SQL deyimleri (veya kısmi deyimleri) için geçirebilir **açık** ve framework yaptığı bunlarla.  
  
    > [!NOTE]
    >  Geçirdiğiniz özel bir dize "Seç" veya "{çağrı" ile başlamıyorsa MFC tablo adı içerdiğini varsayar. Bu durum, bir sonraki madde işaretli öğeye de geçerlidir.  
  
-   Sihirbaz tarafından kayıt kümenizin Yazar dize alter `GetDefaultSQL` üye işlevi. Ne döndürür değiştirmek için işlevin kodunu düzenleyin. Varsayılan olarak, sihirbaz Yazar bir `GetDefaultSQL` tek bir tablo adı döndüren bir işlev.  
  
     Sağlayabilirsiniz `GetDefaultSQL` içinde geçirebilir öğeleri iade **lpszSQL** parametresi **açık**. Özel bir SQL dize geçmeyin varsa **lpszSQL**, dize çerçevesi kullanır, `GetDefaultSQL` döndürür. En azından, `GetDefaultSQL` tek bir tablo adı döndürmesi gerekir. Ancak, birden çok tablo adları, tam iade sağlayabilirsiniz **seçin** deyimi, bir ODBC **ÇAĞRISI** deyimi ve benzeri. Bir listesi için geçirebilir için **lpszSQL** — veya `GetDefaultSQL` dönüş — bkz [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
     İki veya daha fazla tablo birleştirme gerçekleştiriyorsanız yeniden `GetDefaultSQL` SQL'de kullanılan tablo listesini özelleştirmek için **FROM** yan tümcesi. Daha fazla bilgi için bkz: [kayıt kümesi: bir birleştirme (ODBC) gerçekleştirme](../../data/odbc/recordset-performing-a-join-odbc.md).  
  

-   El ile belki de elde hakkında bilgileri şema veri kaynağınızın çalışma zamanında temel alarak ek alan veri üyeleri bağlayın. Alan veri üyeleri kayıt kümesi sınıfına ekleyin [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya toplu RFX işlev çağrılarını bunların [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) üye işlevini ve sınıf oluşturucu veri üyelerinde oluşturucusundaki. Daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Kayıt kümesi üye işlevleri gibi geçersiz kılma `OnSetOptions`, uygulamaya özgü seçeneklerini ayarlamak için veya Varsayılanları geçersiz kılmak için.  
  
 Kayıt kümesi üzerinde karmaşık bir SQL deyimini temel almasını istiyorsanız, bu özelleştirme tekniklerinin bir bileşimi kullanmanız gerekebilir. Örneğin, SQL yan tümceleri kullanmak istediğiniz belki ve kayıt kümeleri veya belki de tarafından doğrudan desteklenmeyen anahtar sözcükleri birden çok tablo birleştirme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Kayıt kümeleri Güncelleştirmesi (ODBC) nasıl kaydeder.](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [ODBC temelleri](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)