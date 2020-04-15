---
title: 'Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
ms.openlocfilehash: 0aa9c082d2d04416358d948476f2ae0f9e2a35af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366985"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu açıklar:

- [Kayıtlarını seçerken rolünüz ve seçenekleriniz.](#_core_your_options_in_selecting_records)

- [Bir kayıt kümesi sql deyimini nasıl oluşturuyor ve kayıtları seçer.](#_core_how_a_recordset_constructs_its_sql_statement)

- [Seçimi özelleştirmek için yapabilecekleriniz.](#_core_customizing_the_selection)

Kayıt kümeleri, sürücüye SQL deyimleri göndererek bir Veri kaynağından ODBC sürücüsü aracılığıyla kayıtları seçer. Gönderilen SQL, kayıt kümesi sınıfınızı nasıl tasarlayıp açtığınıza bağlıdır.

## <a name="your-options-in-selecting-records"></a><a name="_core_your_options_in_selecting_records"></a>Kayıt Seçme Seçenekleriniz

Aşağıdaki tablo, kayıtları seçerken seçeneklerinizi gösterir.

### <a name="how-and-when-you-can-affect-a-recordset"></a>Kayıt Kümesini Nasıl ve Ne Zaman Etkileyebilirsiniz

|Ne zaman|Şunları yapabilirsiniz|
|--------------|-------------|
|**Sınıf Ekle** sihirbazıyla kayıt kümesi sınıfınızı bildirin|Hangi tablodan seçileceklerini belirtin.<br /><br /> Hangi sütunların eklenecek lerini belirtin.<br /><br /> Bkz. [MFC ODBC Tüketicisi Ekleme.](../../mfc/reference/adding-an-mfc-odbc-consumer.md)|
|Kayıt seti sınıf uygulamanızı tamamlayın|Uygulamaya özgü seçenekleri `OnSetOptions` ayarlamak veya varsayılanları değiştirmek için (gelişmiş) gibi üye işlevleri geçersiz kılın. Parametreli bir kayıt kümesi istiyorsanız parametre veri üyelerini belirtin.|
|Kayıt kümesi nesnesi oluşturma `Open`(aramadan önce)|Kayıtları filtreleyen bir **WHERE** yan tümcesinde kullanılmak üzere bir arama koşulu (büyük olasılıkla bileşik) belirtin. Bkz. [Recordset: Filtreleme Kayıtları (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Kayıtları sıralayan bir **ORDER BY** yan tümcesinde kullanılmak üzere bir sıralama sırası belirtin. Bkz. [Recordset: Kayıtları Sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Sınıfa eklediğiniz parametreler için parametre değerlerini belirtin. Bkz. [Kayıt Kümesi: Bir Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|

| Arayarak `Open`kayıt kümesinin sorgusunu çalıştırın | Sihirbaz tarafından ayarlanan varsayılan SQL dizesini değiştirmek için özel bir SQL dizesi belirtin. Bkz. [CRecordset::Sınıf](../../mfc/reference/crecordset-class.md#open) *Kitaplığı Başvurusu* ve [SQL'de Aç: Kayıt Setinizin SQL Bildirimini Özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).|

| `Requery` Veri kaynağındaki en son değerlerle kayıt kümesini yeniden sorgulamaçağrısı| Yeni parametreler, filtre veya sıralama belirtin. Bkz. [Recordset: Kayıt Kümesini Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).|

## <a name="how-a-recordset-constructs-its-sql-statement"></a><a name="_core_how_a_recordset_constructs_its_sql_statement"></a>Recordset SQL Deyimini Nasıl Oluşturuyor?

Bir kayıt kümesi nesnesinin [Açık](../../mfc/reference/crecordset-class.md#open) üye `Open` işlevini çağırdığınızda, aşağıdaki bileşenlerden bazılarını veya tümlerini kullanarak bir SQL deyimi oluşturuyor:

- *LPSZSQL* parametresi `Open`' ne geçti. NULL değilse, bu parametre özel bir SQL dizesini veya birinin bir parçasını belirtir. Çerçeve dize parses. Dize bir SQL **SELECT** deyimi veya ODBC **CALL** deyimi ise, çerçeve, string'i kaydedici setin SQL deyimi olarak kullanır. Dize "SELECT" veya "{CALL" ile başlamazsa, çerçeve bir SQL **FROM** yan tümcesi oluşturmak için sağlananları kullanır.

- GetDefaultSQL tarafından [döndürülen](../../mfc/reference/crecordset-class.md#getdefaultsql)dize. Varsayılan olarak, bu sihirbazda kayıt kümesi için belirttiğiniz tablonun adıdır, ancak işlevin döndürür ne döndürür değiştirebilirsiniz. Çerçeve çağrıları `GetDefaultSQL` — dize "SELECT" veya "{CALL" ile başlamazsa, bir SQL dizesi oluşturmak için kullanılan bir tablo adı olduğu varsayılır.

- Tablonun belirli sütunlarına bağlı olması gereken kayıt kümesinin alan veri üyeleri. Çerçeve, kayıt sütunlarını arabellek olarak kullanarak bu üyelerin adreslerine bağlar. Çerçeve, alan veri üyelerinin kayıt setinin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevindeki RFX veya Bulk [RFX](../../data/odbc/record-field-exchange-using-rfx.md) işlev çağrılarından tablo sütunları ile ilişkilendirinir.

- Varsa [filter](../../data/odbc/recordset-filtering-records-odbc.md) kayıt kümesi [filtresi, m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesinde bulunur. Çerçeve, bir SQL **WHERE** yan tümcesi oluşturmak için bu dizeyi kullanır.

- [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesinde bulunan kayıt kümesinin [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) sırası. Çerçeve, bir SQL ORDER **BY** yan tümcesi oluşturmak için bu dizeyi kullanır.

   > [!TIP]
   > SQL GROUP **BY** yan tümcesini (ve muhtemelen **HAVING** yan tümcesini) kullanmak için, yan tümceleri filtre dizenizin sonuna ekleyin.

- Sınıf için belirttiğiniz herhangi bir [parametre veri üyesinin](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) değerleri. Aramadan `Open` hemen önce parametre `Requery`değerlerini ayarlarsınız veya . Çerçeve, parametre değerlerini SQL dizesinde "?" yer tutucularına bağlar. Derleme zamanında, dizeyi yer tutucularla belirtirsiniz. Çalışma zamanında, çerçeve geçidiğiniz parametre değerlerini temel alan ayrıntıları doldurur.

`Open`bu bileşenlerden bir SQL **SELECT** deyimi oluşturuyor. Çerçevenin içeriği nasıl kullandığıyla ilgili ayrıntılar için [Seçimi Özelleştirme'ye](#_core_customizing_the_selection) bakın.

İfadeyi yaptıktan sonra, `Open` SQL'i ODBC Sürücü Yöneticisi'ne (ve bellekteyse ODBC Imleç Kitaplığı'na) gönderir ve bu da sql'i belirli DBMS için ODBC sürücüsüne gönderir. Sürücü, veri kaynağındaki seçimi gerçekleştirmek için DBMS ile iletişim kurar ve ilk kaydı getirir. Çerçeve, kaydı kayıt kümesinin alan veri üyelerine yükler.

[Tabloları](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) açmak ve birden çok tablonun [birleşimini](../../data/odbc/recordset-performing-a-join-odbc.md) temel alan bir sorgu oluşturmak için bu tekniklerin bir birleşimini kullanabilirsiniz. Ek özelleştirme yle, [önceden tanımlanmış sorguları](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (depolanan yordamlar) çağırabilir, tasarım zamanında tanınmayan tablo sütunlarını seçebilir ve bunları kaydedici alanlara [bağlayabilir](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) veya diğer veri erişim görevlerinin çoğunu gerçekleştirebilirsiniz. Kayıt kümelerini özelleştirerek gerçekleştiremeyeceğiniz [görevler, ODBC API işlevlerini arayarak](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) veya [CDatabase:ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)ile SQL deyimlerini doğrudan yürüterek yine de gerçekleştirilebilir.

## <a name="customizing-the-selection"></a><a name="_core_customizing_the_selection"></a>Seçimi Özelleştirme

Bir filtre, sıralama sırası veya parametreler sağlamanın yanı sıra, kayıt setinizin seçimini özelleştirmek için aşağıdaki işlemleri yapabilirsiniz:

- Kayıt seti için [Aç'ı](../../mfc/reference/crecordset-class.md#open) aradiğinizde *lpszSQL'de* özel bir SQL dizesi geçirin. *LPSQSQL'de* geçtiğiniz her şey [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) üye işlevinin döndürdüğünden üniverçe girer.

   Daha fazla bilgi için, aktarabileceğiniz SQL deyimi (veya kısmi deyimler) türlerini `Open` ve çerçevenin bunlarla ne yaptığını açıklayan [SQL: Recordset'inSQL Deyimini (ODBC) özelleştirme.](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

    > [!NOTE]
    >  Geçtiğiniz özel dize "SELECT" veya "{CALL" ile başlamazsa, MFC bir tablo adı içerdiğini varsayar. Bu, bir sonraki madde işaretli öğe için de geçerlidir.

- Sihirbazın kayıt setinizin `GetDefaultSQL` üye işlevinde yazdığı dizeyi değiştirin. Döndürdüğü nüzürü nüz Varsayılan olarak, sihirbaz `GetDefaultSQL` tek bir tablo adı döndüren bir işlev yazar.

   `GetDefaultSQL` *LpszSQL* parametresinde geçebileceğiniz öğelerden herhangi birini `Open`. *LpszSQL'de*özel bir SQL dizesini geçemezseniz, `GetDefaultSQL` çerçeve döndüren dizeyi kullanır. En azından, `GetDefaultSQL` tek bir tablo adı döndürmesi gerekir. Ancak birden çok tablo adı, **tam** SELECT deyimi, bir ODBC **CALL** deyimi ve benzeri döndürmesi için. *LPSZSQL'e* geçirebileceğiniz veya `GetDefaultSQL` geri dönebileceğiniz nelerin listesi için bkz. [SQL: Customizing Your Recordset's SQL Statement (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

   İki veya daha fazla tablonun birleşimini gerçekleştirecekseniz, SQL `GetDefaultSQL` **FROM** yan tümcesinde kullanılan tablo listesini özelleştirmek için yeniden yazın. Daha fazla bilgi için [bkz: Recordset: Performing a Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

- Ek alan veri üyelerini, belki de çalışma zamanında veri kaynağınızın şeması hakkında edindiğiniz bilgilere dayanarak el ile bağla. Alan veri üyelerini kayıt sınıfına eklersiniz, [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya Bulk RFX işlevi çağrıları [dofieldexchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) üye işlevine ve sınıf oluşturucusundaki veri üyelerinin başlatılmasına neden olur. Daha fazla bilgi için [Bkz. Kayıt Kümesi: Dinamik Bağlama Veri Sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- Uygulamaya özgü seçenekleri ayarlamak veya `OnSetOptions`varsayılanları geçersiz kılmak için kayıt kümesi üye işlevlerini geçersiz kılın.

Kayıt kümesini karmaşık bir SQL deyimine dayandırmak istiyorsanız, bu özelleştirme tekniklerinin bazı birleşimini kullanmanız gerekir. Örneğin, sql yan tümcelerini ve anahtar kelimeleri doğrudan kayıt kümeleri tarafından desteklenmeyen veya belki de birden çok tabloya katılmak istiyorsunuz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[ODBC Temelleri](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
