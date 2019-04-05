---
title: 'Kayıt kümesi: Kayıtları seçme biçimi (ODBC) nasıl kaydeder'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
ms.openlocfilehash: 310481a6ea6637de817bf29d528cbdfe70ae70db
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041331"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Kayıt kümesi: Kayıtları seçme biçimi (ODBC) nasıl kaydeder

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu şunları açıklar:

- [Rolünüz ve kayıt seçme içinde seçeneklerinizi](#_core_your_options_in_selecting_records).

- [Bir kayıt kümesi nasıl kendi SQL deyimini oluşturan ve kayıtları seçer](#_core_how_a_recordset_constructs_its_sql_statement).

- [Seçimi özelleştirmek için yapabilecekleriniz](#_core_customizing_the_selection).

Kayıt kümeleri kayıtları bir veri kaynağına ODBC sürücüsü aracılığıyla bir sürücü için SQL deyimleri göndererek seçin. Gönderilen SQL tasarlama ve açın, kayıt kümesi sınıfı üzerinde bağlıdır.

##  <a name="_core_your_options_in_selecting_records"></a> Kayıtları seçme içinde seçenekleri

Aşağıdaki tablo, kayıt seçme içinde seçeneklerinizi gösterir.

### <a name="how-and-when-you-can-affect-a-recordset"></a>Nasıl ve ne zaman bir kayıt kümesi etkileyebilir.

|Olduğunda,|Şunları yapabilirsiniz|
|--------------|-------------|
|Kayıt kümesi sınıfınızı bildirmek **sınıfı Ekle** Sihirbazı|Seçim yapılacak tablo belirtin.<br /><br /> Hangi sütunların dahil edileceğini belirtin.<br /><br /> Bkz: [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|
|Kayıt kümesi sınıf uygulamanızı tamamlayın|Üye işlevleri gibi geçersiz kılma `OnSetOptions` (Gelişmiş) uygulamaya özgü seçenekleri ayarlayın ya da varsayılan ayarları değiştirmek için. Parametreli bir kayıt kümesi istiyorsanız parametre veri üyeleri belirtin.|
|Kayıt kümesi nesnesi oluşturun (çağırmadan önce `Open`)|Kullanılmak üzere (büyük olasılıkla bileşik) arama koşulu belirtin bir **burada** kayıtları süzer yan tümcesi. Bkz: [kayıt kümesi: Kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Bir sıralama düzeni kullanmak için belirtin bir **ORDER BY** kayıtları sıralar yan tümcesi. Bkz: [kayıt kümesi: Kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Sınıfa eklediğiniz herhangi bir parametre için parametre değerlerini belirtin. Bkz: [kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|

| Çağırarak kümesinin sorgusu `Open`| Sihirbaz tarafından ayarlanmış varsayılan SQL dizesi değiştirilecek özel bir SQL dizesi belirtin. Bkz: [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) içinde *sınıf kitaplığı başvurusu* ve [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |

| Çağrı `Requery` kayıt veri kaynağındaki en son değerlerle sorgulayacak | Yeni parametreleri, filtre veya sıralama belirtin. Bkz: [kayıt kümesi: (ODBC) bir kayıt kümesinde yeniden sorgulama](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |

##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Bir kayıt kümesi, SQL deyimini nasıl oluşturur

Kayıt kümesi nesnesinin çağırdığınızda [açık](../../mfc/reference/crecordset-class.md#open) üye işlevini `Open` bazılarını veya tümünü aşağıdaki içeriklerin kullanarak bir SQL deyimi oluşturur:

- *LpszSQL* geçirilen `Open`. BOŞ değilse bu parametre özel SQL dizesi veya bir parçası olarak belirtir. Çerçeve dizeyi ayrıştırır. Bir SQL bir dize ise **seçin** deyimi veya bir ODBC **çağrı** deyim, framework dize kayıt kümenizin SQL deyimini kullanır. Bir SQL oluşturmak için sağlanan dize "Seçin" veya "{ÇAĞRISI" ile başlamıyorsa framework kullanan **FROM** yan tümcesi.

- Tarafından döndürülen dize [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql). Varsayılan olarak, bu sihirbazdaki kayıt kümesi için belirtilen tablo adıdır ancak ne işlevi döndürür değiştirebilirsiniz. Framework çağrıları `GetDefaultSQL` — dize "Seçin" veya "{ÇAĞRISI" ile başlamıyorsa, bu SQL dizesi oluşturmak için kullanılan bir tablo adı olduğu varsayılır.


- Belirli bir tablonun sütunlarını için bağlı olan alan veri üyeleri kümesi. Çerçeve kaydı sütunları arabellek olarak kullanarak, bu üyeler adreslerine bağlar. Alan veri üyeleri bağıntısını framework tablo sütunlarından belirler [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya Bulk RFX işlevi çağıran kümenizin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevi.

- [Filtre](../../data/odbc/recordset-filtering-records-odbc.md) varsa, kayıt kümesi için kapsanıyorsa [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi. Framework, bir SQL oluşturmak için bu dizeyi kullanır. **burada** yan tümcesi.

- [Sıralama](../../data/odbc/recordset-sorting-records-odbc.md) herhangi biri, içerdiği durumlarda kayıt kümesi için sipariş [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesi. Framework, bir SQL oluşturmak için bu dizeyi kullanır. **ORDER BY** yan tümcesi.

   > [!TIP]
   > SQL kullanmak için **GROUP BY** yan tümcesi (ve muhtemelen **HAVING** yan tümcesi), yan tümceleri, filtre dizesinin sonuna.

- Tüm değerleri [parametre veri üyeleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) için sınıfı belirtin. Parametre değerleri yalnızca çağırmadan önce ayarladığınız `Open` veya `Requery`. Çerçeve parametre değerlerini bağlar "?" SQL dizesinde yer tutucular. Derleme zamanında yer tutucuları olan dize belirtin. Çalışma zamanında, geçirdiğiniz parametre değerine göre ayrıntıları framework doldurur.

`Open` bir SQL yapıları **seçin** bu maddelerden deyimi. Bkz: [seçimi özelleştirme](#_core_customizing_the_selection) framework malzemeleri nasıl kullandığı hakkında ayrıntılar için.

Deyimi yapılandırılırken sonra `Open` ODBC Sürücü Yöneticisi (ve ODBC imleç kitaplığı bellekte ise), SQL gönderir gönderen ODBC sürücüsüne belirli DBMS için. Sürücü, veri kaynağında seçimi gerçekleştirmek için DBMS ile iletişim kurar ve ilk kayıt getirir. Çerçeve kaydı alan veri üyeleri kayıt kümesinin yükler.

Açmak için bu tekniklerin bir birleşimini kullanabilir [tabloları](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) ve temel bir sorgu oluşturmak için bir [birleştirme](../../data/odbc/recordset-performing-a-join-odbc.md) birden çok tablo. Ek özelleştirme ile çağırabilirsiniz [önceden tanımlanmış sorgular](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (saklı yordamlar), select tablo sütunları tasarım zamanında bilinmiyor ve [bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) kendilerine kayıt kümesi alanlarını veya diğer birçok gerçekleştirebilirsiniz Veri erişim görevleri Olamaz gerçekleştirmek kayıt kümeleri özelleştirerek görevler yine de gerçekleştirilebilir tarafından [ODBC API işlevlerini çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) veya doğrudan SQL deyimleri ile yürütme [CDatabase:: Executesql'den](../../mfc/reference/cdatabase-class.md#executesql).

##  <a name="_core_customizing_the_selection"></a> Seçimi özelleştirme

Bir filtre, sıralama düzeni veya parametreleri sağlamanın yanı sıra, kümenizin seçimi özelleştirmek için aşağıdaki eylemleri gerçekleştirebilirsiniz:

- Özel bir SQL dizesine geçmenizi *lpszSQL* çağırdığınızda [açık](../../mfc/reference/crecordset-class.md#open) kayıt kümesi için. Geçirdiğiniz her şeyi *lpsqSQL* ne üzerinde önceliklidir [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) üye işlevi döndürür.

   Daha fazla bilgi için [SQL: Kümenizin SQL deyimini (ODBC) özelleştirme](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), türleri açıklayan SQL deyimleri (veya kısmi deyimleri) öğesine iletebileceğiniz `Open` ve framework bunlarla ne yapar.

    > [!NOTE]
    >  Geçirdiğiniz özel dize "Seçin" veya "{ÇAĞRISI" ile başlamıyorsa MFC tablo adı içerdiğini varsayar. Bu, sonraki madde işaretli öğesi için de geçerlidir.

- Sihirbaz, kayıt kümesinin Yazar dize alter `GetDefaultSQL` üye işlevi. Ne döndürür değiştirmek için işlevin kodunu düzenleyin. Varsayılan olarak, sihirbaz Yazar bir `GetDefaultSQL` tek bir tablo adı döndüren işlev.

   Sahip olduğunuz `GetDefaultSQL` de geçirebilirsiniz öğeleri iade *lpszSQL* parametresi `Open`. Özel bir SQL dizesinde geçmeyin, *lpszSQL*, dize framework kullanan, `GetDefaultSQL` döndürür. En azından `GetDefaultSQL` tek bir tablo adı döndürmelidir. Ancak birden çok tablo adları, tam bir dönüş sağlayabilirsiniz **seçin** deyimi, bir ODBC **çağrı** deyimi ve benzeri. Öğesine iletebileceğiniz listesi için *lpszSQL* — veya `GetDefaultSQL` dönüş — bkz [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

   İki veya daha fazla tablo birleşimi gerçekleştiriyorsanız, yeniden `GetDefaultSQL` SQL'de kullanılan tablo listesini özelleştirmek için **FROM** yan tümcesi. Daha fazla bilgi için [kayıt kümesi: Birleşim gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).


- Ek alan veri üyeleri, belki de elde şeması hakkında bilgi veri kaynağınızın çalışma zamanında göre el ile bağlayın. Kayıt kümesi sınıfı için alan veri üyeleri ekleme [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya Bulk RFX işlevi çağıran bunların [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) üye işlevi, ve veri üyeleri sınıf oluşturucu başlatmalar. Daha fazla bilgi için [kayıt kümesi: (ODBC) veri sütunlarını dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- Kayıt kümesi üye işlevleri gibi geçersiz kılma `OnSetOptions`, uygulamaya özgü seçenekleri ayarlayın veya Varsayılanları geçersiz kılmak için.

Kayıt üzerinde karmaşık bir SQL deyimi temel almasını istiyorsanız, bu özelleştirme bileşimi kullanmanız gerekir. Örneğin, belki de SQL yan tümceler kullanmak istediğiniz ve anahtar sözcükleri kayıt kümeleri veya belki de tarafından doğrudan desteklenmeyen birden fazla tabloyu katıldığınız.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[ODBC Temelleri](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Kayıt kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)