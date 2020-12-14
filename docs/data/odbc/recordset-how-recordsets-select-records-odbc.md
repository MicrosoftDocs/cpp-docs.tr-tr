---
description: 'Daha fazla bilgi: kayıt kümesi: kayıt kümelerinin kayıtları seçme (ODBC)'
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
ms.openlocfilehash: 25032c1901513e0c99ddcf8018fb108eb7c1fbd2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304473"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Rolünüz ve kayıt seçerken seçenekleriniz](#_core_your_options_in_selecting_records).

- [Bir kayıt KÜMESI SQL Ifadesini nasıl oluşturur ve kayıtları seçer](#_core_how_a_recordset_constructs_its_sql_statement).

- [Seçimi özelleştirmek için](#_core_customizing_the_selection)yapabilecekleriniz.

Kayıt kümeleri, sürücüye SQL deyimleri göndererek bir ODBC sürücüsü aracılığıyla bir veri kaynağındaki kayıtları seçer. Gönderilen SQL, kayıt kümesi sınıfınızı nasıl tasarlayacağınızı ve açdığınıza bağlıdır.

## <a name="your-options-in-selecting-records"></a><a name="_core_your_options_in_selecting_records"></a> Kayıtları seçerken seçenekleriniz

Aşağıdaki tabloda kayıtları seçme seçenekleriniz gösterilmektedir.

### <a name="how-and-when-you-can-affect-a-recordset"></a>Bir kayıt kümesini nasıl ve ne zaman etkileyebilirsiniz

|Bunu yaptığınızda|Şunları yapabilirsiniz|
|--------------|-------------|
|**Sınıf ekleme** Sihirbazı ile kayıt kümesi sınıfınızı bildirin|Seçilecek tabloyu belirtin.<br /><br /> Hangi sütunların ekleneceğini belirtin.<br /><br /> Bkz. [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|
|Kayıt kümesi sınıfı uygulamanızı doldurun|`OnSetOptions`Uygulamaya özgü seçenekleri ayarlamak veya Varsayılanları değiştirmek için (Gelişmiş) gibi üye işlevlerini geçersiz kılın. Parametreli bir kayıt kümesi istiyorsanız parametre veri üyelerini belirtin.|
|Kayıt kümesi nesnesi oluşturma (çağrı yapmadan önce `Open` )|Kayıtları filtreleyen **WHERE** yan tümcesinde kullanılmak üzere bir arama koşulu (Belki de bileşik) belirtin. Bkz. [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Kayıtları sıralayan **order by** yan tümcesinde kullanılmak üzere bir sıralama düzeni belirtin. Bkz. [kayıt kümesi: kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Sınıfa eklediğiniz parametrelerin parametre değerlerini belirtin. Bkz. [kayıt kümesi: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|

| Çağırarak kayıt kümesinin sorgusunu çalıştırın `Open` | Sihirbaz tarafından ayarlanan varsayılan SQL dizesini değiştirmek için özel bir SQL dizesi belirtin. Bkz. [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) *sınıf kitaplığı başvurusu* ve [SQL: kayıt kümenizin sql deyiminizi özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |

| `Requery` Veri kaynağındaki en son değerlerle kayıt kümesini yeniden sorgulama çağrısı | Yeni parametreler, filtre veya sıralama belirtin. Bkz. [kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |

## <a name="how-a-recordset-constructs-its-sql-statement"></a><a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Bir kayıt kümesi SQL Ifadesini nasıl oluşturur

Bir kayıt kümesi nesnesinin [Open](../../mfc/reference/crecordset-class.md#open) üye işlevini çağırdığınızda, `Open` aşağıdaki MALZEMELERI kullanarak bir SQL ifadesini oluşturur:

- *LpszSQL* parametresi geçirildi `Open` . NULL değilse, bu parametre özel bir SQL dizesini veya bir kısmını belirtir. Çerçeve, dizeyi ayrıştırır. Dize bir SQL **Select** deyimidir veya bir ODBC **Call** deyimidir, çerçeve, dizeyi kayıt kümesinin SQL ifadesiyle kullanır. Dize "SELECT" veya "{CALL" ile başlamazsa, çerçeve bir SQL **from** yan tümcesi oluşturmak için verilen öğeleri kullanır.

- [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)tarafından döndürülen dize. Bu, varsayılan olarak, sihirbazda kayıt kümesi için belirttiğiniz tablonun adıdır, ancak işlevin ne geri döndüğünü de değiştirebilirsiniz. Çerçeve çağrıları `GetDefaultSQL` — dize "Select" veya "{Call" ile başlamaıyorsa, BIR SQL dizesi oluşturmak için kullanılan tablo adı olduğu varsayılır.

- Kayıt kümesinin, tablodaki belirli sütunlara bağlanacak olan alan veri üyeleri. Framework, kayıt sütunlarını bu üyelerin adreslerine bağlar ve bunları arabellekler olarak kullanarak bağlar. Framework, alan veri üyelerinin, kayıt kümesinin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye IŞLEVINDEKI [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya toplu RFX işlevi çağrılarından tablo sütunlarına bağıntısını belirler.

- [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesinde bulunan, kayıt kümesi için [filtre](../../data/odbc/recordset-filtering-records-odbc.md) . Framework, bu dizeyi bir SQL **WHERE** yan tümcesi oluşturmak için kullanır.

- [M_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesinde bulunan, kayıt kümesi için [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) düzeni. Framework, bu dizeyi bir SQL **order by** yan tümcesi oluşturmak için kullanır.

   > [!TIP]
   > SQL **Group By** yan tümcesini (ve muhtemelen **HAVING** yan tümcesini) kullanmak için, yan tümceleri filtre dizenizin sonuna ekleyin.

- Sınıf için belirttiğiniz tüm [parametre veri üyelerinin](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) değerleri. Ya da ' i çağırmadan önce parametre değerlerini ayarlarsınız `Open` `Requery` . Çerçeve, parametre değerlerini SQL dizesindeki "?" yer tutucularına bağlar. Derleme zamanında, dizeyi yer tutucuları ile belirtirsiniz. Çalışma zamanında, çerçeve geçirdiğiniz parametre değerlerine göre ayrıntıları doldurur.

`Open` Bu malzemeler arasından bir SQL **Select** açıklaması oluşturur. Framework 'ün malzemeleri nasıl kullandığını gösteren Ayrıntılar için bkz. [seçimi özelleştirme](#_core_customizing_the_selection) .

Deyimyi oluşturduktan sonra, `Open` SQL 'i belirli BIR DBMS IÇIN ODBC sürücüsüne gönderen ODBC Sürücü Yöneticisi 'ne (ve bellekde ODBC Imleç kitaplığına) gönderir. Sürücü, veri kaynağında seçimi yürütmek için DBMS ile iletişim kurar ve ilk kaydı getirir. Çerçeve, kaydı kayıt kümesinin alan veri üyelerine yükler.

Bu tekniklerin bileşimini kullanarak [tabloları](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) açabilir ve birden çok tablonun [JOIN](../../data/odbc/recordset-performing-a-join-odbc.md) 'i temel alan bir sorgu oluşturabilirsiniz. Ek özelleştirme sayesinde, [önceden tanımlanmış sorguları](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (saklı yordamlar) çağırabilir, tasarım zamanında bilinmeyen tablo sütunlarını seçebilir ve bunları kayıt kümesi alanlarına [bağlayabilir](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) veya diğer veri erişimi görevlerinin çoğunu gerçekleştirebilirsiniz. Kayıt kümelerini özelleştirerek yerine getirebileceğiniz görevler, [ODBC API işlevleri çağırarak](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) veya doğrudan SQL deyimlerini [CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)ile yürütülerek gerçekleştirilebilir.

## <a name="customizing-the-selection"></a><a name="_core_customizing_the_selection"></a> Seçimi özelleştirme

Filtre, sıralama düzeni veya parametreler sağlamanın yanı sıra, kayıt kümenizin seçimini özelleştirmek için aşağıdaki eylemleri gerçekleştirebilirsiniz:

- Kayıt kümesi için [Açık](../../mfc/reference/crecordset-class.md#open) ' i çağırdığınızda, *lpszSQL* 'de özel bir SQL dizesi geçirin. *LpsqSQL* 'e geçirdiğiniz her şey, [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) üye işlevinin döndürdüğü kadar önceliklidir.

   Daha fazla bilgi için bkz. [SQL: kayıt KÜMENIZIN SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md); bu, geçirebileceğinizi `Open` ve bu Framework ile birlikte ne yaptığını açıklayan SQL deyimlerinin (veya kısmi deyimlerinin) türlerini açıklar.

    > [!NOTE]
    >  Geçirdiğiniz özel dize "SELECT" veya "{CALL" ile başlamadıysanız, MFC bir tablo adı içerdiğini varsayar. Bu, bir sonraki madde işaretli öğe için de geçerlidir.

- Sihirbazın kayıt kümenizin üye işlevinde yazdığı dizeyi değiştirin `GetDefaultSQL` . İşlevin kodunu, döndürdüğü şeyi değiştirmek için düzenleyin. Varsayılan olarak, sihirbaz `GetDefaultSQL` tek bir tablo adı döndüren bir işlev yazar.

   `GetDefaultSQL` *LpszSQL* parametresinde geçirebilmeniz gereken öğelerden herhangi birini geri alabilirsiniz `Open` . *LpszSQL*'de özel bir SQL dizesi geçirmezseniz çerçeve, döndüren dizeyi kullanır `GetDefaultSQL` . En azından, `GetDefaultSQL` tek bir tablo adı döndürmelidir. Ancak birden çok tablo adı, tam **Select** EKSTRESI, ODBC **çağrı** ekstresi vb. döndürebilmenizi sağlayabilirsiniz. *LpszSQL* 'ye geçebileceğinize yönelik bir liste veya `GetDefaultSQL` döndürme — bkz. [SQL: Kayıt Kümenizin SQL DEYIMINIZI özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

   İki veya daha fazla tablonun bir birleştirmesini gerçekleştiriyorsanız, `GetDefaultSQL` SQL **from** yan tümcesinde kullanılan tablo listesini özelleştirmek için yeniden yazın. Daha fazla bilgi için bkz. [kayıt kümesi: JOIN gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

- Ek alan veri üyelerini, belki de çalışma zamanında veri kaynağınızın şeması hakkında elde ettiğiniz bilgilere bağlı olarak el ile bağlayın. Alan veri üyelerini, bu kayıt kümesi sınıfına, [RFX](../../data/odbc/record-field-exchange-using-rfx.md) veya toplu RFX işlev çağrılarını, [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) üye işlevine ekler ve sınıf oluşturucusunda veri üyelerinin başlatmaları için çağırır. Daha fazla bilgi için bkz. [kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- `OnSetOptions`Uygulamaya özgü seçenekleri ayarlamak veya Varsayılanları geçersiz kılmak için gibi, kayıt kümesi üye işlevlerini geçersiz kılın.

Kayıt kümesini karmaşık bir SQL deyimindeki temel almak istiyorsanız, bu özelleştirme tekniklerinin bir birleşimini kullanmanız gerekir. Örneğin, büyük olasılıkla, kayıt kümeleri tarafından doğrudan desteklenmeyen SQL yan tümceleri ve anahtar sözcükleri kullanmak istiyor olabilirsiniz veya belki birden çok tabloyu birleştiriyorsanız.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: kayıt kümelerinin kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[ODBC temelleri](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
