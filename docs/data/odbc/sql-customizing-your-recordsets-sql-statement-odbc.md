---
description: 'Şu konuda daha fazla bilgi edinin: SQL: Kayıt Kümenizin SQL Ifadesini özelleştirme (ODBC)'
title: 'SQL: Kayıt Kümenizin SQL Deyimini Özelleştirme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: 73765ed66dacbc017cca6236ae5a90388390fa45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278694"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: Kayıt Kümenizin SQL Deyimini Özelleştirme (ODBC)

Bu konuda aşağıdakiler açıklanmaktadır:

- Framework bir SQL ifadesini nasıl oluşturur

- SQL ifadesini geçersiz kılma

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıflarıyla çalışıyorsanız, DAO yardımı 'nda "Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL karşılaştırması" konusuna bakın.

## <a name="sql-statement-construction"></a>SQL deyiminin oluşturulması

Kayıt kümeniz, kayıt seçimini birincil olarak bir SQL **Select** ifadesine dayandırır. Sınıfınızı bir sihirbaz ile bildirdiğinizde, `GetDefaultSQL` üye işlevinin şuna benzer bir şekilde (bir kayıt kümesi sınıfı için) bir geçersiz kılma sürümü yazar `CAuthors` .

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

Varsayılan olarak, bu geçersiz kılma sihirbazla belirttiğiniz tablo adını döndürür. Örnekte, tablo adı "yazarlar" dır. Kayıt kümesinin üye işlevini daha sonra çağırdığınızda `Open` , `Open` formun son bir **Select** ifadesini oluşturur:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

, `table-name` çağırarak `GetDefaultSQL` ve `rfx-field-list` içindeki RFX işlevi çağrılarından elde edilen `DoFieldExchange` . Bu, çalışma zamanında bir geçersiz kılma sürümü ile değiştirmediğiniz takdirde bir **Select** ifadesine sahip olduğunuz şeydir, ancak varsayılan ifadeyi parametreler veya filtre ile de değiştirebilirsiniz.

> [!NOTE]
> Boşluk içeren (veya içerebilen) bir sütun adı belirtirseniz, adı köşeli ayraç içine almalısınız. Örneğin, "First Name" adı "[First Name]" olmalıdır.

Varsayılan **Select** ifadesini geçersiz kılmak için, öğesini çağırdığınızda bir **Select** ifadesini içeren bir dize geçirin `Open` . Kendi varsayılan dizesini oluşturmak yerine, kayıt kümesi sağladığınız dizeyi kullanır. Değiştirme deyiminiz bir **WHERE** yan tümcesi içeriyorsa, ' de iki filtre deyimi olacak şekilde bir filtre belirtmeyin `m_strFilter` . Benzer şekilde, değiştirme deyiminiz **order by** yan tümcesi içeriyorsa, `m_strSort` iki sıralama deyiminiz olmayacak şekilde bir sıralama belirtmeyin.

> [!NOTE]
> Filtreinizde (veya SQL deyimin diğer bölümlerinde) değişmez dizeler kullanırsanız, DBMS 'ye özgü sabit değer ön eki ve sabit son ek karakteri (veya karakterleri) ile bu tür dizeler "QUOTE" (belirtilen sınırlayıcılardan Çevrele) gerekebilir.

Ayrıca, DBMS 'nize bağlı olarak dış birleşimler gibi işlemler için özel sözdizimsel gereksinimlerle karşılaşabilirsiniz. Bu bilgileri DBMS için sürücüden elde etmek için ODBC işlevlerini kullanın. Örneğin, `::SQLGetTypeInfo` `SQL_VARCHAR` LITERAL_PREFIX ve LITERAL_SUFFIX karakterleri istemek için gibi belirli bir veri türü için çağrı yapın. Veritabanı bağımsız kodu yazıyorsanız, ayrıntılı sözdizimi bilgileri için bkz. [Ek C: SQL dilbilgisi](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) , [ODBC Programcı başvurusu](/sql/odbc/reference/odbc-programmer-s-reference) .

Bir kayıt kümesi nesnesi, özel bir SQL ifadesini geçirmediğiniz müddetçe kayıtları seçmek için kullandığı SQL ifadesini oluşturur. Bu işlem, genellikle üye işlevin *lpszSQL* parametresinde geçirdiğiniz değere bağlıdır `Open` .

Bir SQL **Select** ifadesinin genel formu:

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

Kayıt Kümenizin SQL deyiminize **DISTINCT** anahtar sözcüğünü eklemenin bir yolu, anahtar sözcüğünü IÇINDEKI ilk RFX işlevi çağrısına eklemektir `DoFieldExchange` . Örneğin:

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> Bu tekniği yalnızca salt okunurdur olarak açılan bir kayıt kümesiyle kullanın.

## <a name="overriding-the-sql-statement"></a>SQL Ifadesini geçersiz kılma

Aşağıdaki tabloda, öğesine *lpszSQL* parametresi olanakları gösterilmektedir `Open` . Tablodaki durumlar, tablosundan sonra açıklanmaktadır.

**LpszSQL parametresi ve elde edilen SQL dizesi**

|Case (Olay)|LpszSQL 'de geçirdiğiniz Özellikler|Sonuç SELECT ekstresi|
|----------|------------------------------|------------------------------------|
|1|NULL| *Tablo-adından* *RFX-alan listesi* ' ni **seçin**<br /><br /> `CRecordset::Open``GetDefaultSQL`tablo adını almak için çağırır. Elde edilen dize, neyin dönüşdiğine bağlı olarak 2 ila 5 arası bir şeydir `GetDefaultSQL` .|
|2|Tablo adı| *Tablo-adından* *RFX-alan listesi* ' ni **seçin**<br /><br /> Alan listesi, içindeki RFX deyimlerinden alınmıştır `DoFieldExchange` . `m_strFilter`Ve `m_strSort` boş değilse, **WHERE** ve/veya **order by** yan tümcelerini ekler.|
|03 \*|Tam bir **Select** deyimi, ancak **WHERE** veya **order by** yan tümcesi olmadan|Geçti. `m_strFilter`Ve `m_strSort` boş değilse, **WHERE** ve/veya **order by** yan tümcelerini ekler.|
|4 \*|**WHERE** ve/veya **order by** yan tümcesinin bulunduğu tam bir **Select** deyimi|Geçti. `m_strFilter` ve/veya `m_strSort` boş kalması gerekir ya da iki filtre ve/veya sıralama ifadesi üretilmelidir.|
|e \*|Saklı yordama çağrı|Geçti.|

\*`m_nFields` **Select** ifadesinde belirtilen sütun sayısından küçük veya buna eşit olmalıdır. **Select** ifadesinde belirtilen her sütunun veri türü, KARŞıLıK gelen RFX çıkış sütununun veri türüyle aynı olmalıdır.

### <a name="case-1---lpszsql--null"></a>Durum 1 lpszSQL = NULL

Kayıt kümesi seçimi, çağırdığında ne `GetDefaultSQL` getirdiğinize bağlıdır `CRecordset::Open` . 2 ila 5 arasındaki durumlar olası dizeleri açıklıyor.

### <a name="case-2---lpszsql--a-table-name"></a>Durum 2 lpszSQL = bir tablo adı

Kayıt kümesi, kayıt alanı değişimi (RFX) öğesini kullanarak, kayıt kümesi sınıfının geçersiz kılındığı RFX işlevi çağrılarında belirtilen sütun adlarından sütun listesini oluşturur `DoFieldExchange` . Kayıt kümesi sınıfınızı bildirmek için bir sihirbaz kullandıysanız, bu durum büyük/küçük harf 1 ile aynı sonuca sahiptir (sihirbazda belirttiğiniz tablo adını geçirdiğiniz şekilde sunulmaktadır). Sınıfınızı yazmak için bir sihirbaz kullanmıyorsanız, büyük/küçük harf 2, SQL ifadesini oluşturmanın en kolay yoludur.

Aşağıdaki örnek, bir MFC veritabanı uygulamasından kayıtları seçen bir SQL ifadesini oluşturur. Çerçeve `GetDefaultSQL` üye işlevini çağırdığında, işlev tablonun adını döndürür `SECTION` .

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

SQL **Select** ifadesiyle ilgili sütunların adlarını almak için, çerçeve `DoFieldExchange` üye işlevini çağırır.

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

Bu tamamlandığında, SQL açıklaması şöyle görünür:

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Durum 3 lpszSQL = bir SELECT/FROM deyimidir

Sütun listesini, RFX 'in otomatik olarak oluşturulması yerine el ile belirtirsiniz. Bunu yapmak isteyebilirsiniz:

- **Aşağıdakilerden** **ayrı** anahtar sözcüğü belirtmek istiyorsunuz.

   Sütun listeniz, sütun adlarıyla ve türleriyle listelendikleri şekilde aynı sırada eşleşmelidir `DoFieldExchange` .

- `::SQLGetData`Sütunları sizin için bağlamak ve almak üzere RFX 'e güvenmek yerıne ODBC işlevini kullanarak sütun değerlerini el ile alma nedeninizi görürsünüz.

   Örneğin, uygulama dağıtıldıktan sonra, uygulamanızın bir müşterisi olan veritabanı tablolarına eklenen yeni sütunlara uyum sağlamak isteyebilirsiniz. Bu ek alan veri üyelerini eklemeniz gerekir, bu, sınıfı bir sihirbaz ile bildirdiğiniz sırada bilinmez.

   Sütun listeniz, sütun adları ve türleriyle, içinde listelendikleri sırada ve `DoFieldExchange` ardından el ile bağlantılı sütunların adları ile eşleşmelidir. Daha fazla bilgi için bkz. [kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- **From** yan tümcesinde birden çok tablo belirterek tabloları birleştirmek istiyorsunuz.

   Bilgi ve bir örnek için bkz. [Recordset: JOIN (ODBC) gerçekleştirme](../../data/odbc/recordset-performing-a-join-odbc.md).

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Durum 4 lpszSQL = SEÇIM/KIMDEN artı ve/veya SıRALAMA ölçütü

Her şeyi belirtirsiniz: sütun listesi (içindeki RFX çağrılarına göre `DoFieldExchange` ), Tablo listesi ve bir **WHERE** ve/veya **order by** yan tümcesinin içeriği. **WHERE** ve/veya **order by** yan tümcelerinizi bu şekilde belirtirseniz, `m_strFilter` ve/veya kullanmayın `m_strSort` .

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Durum 5 lpszSQL = saklı yordam çağrısı

Önceden tanımlanmış bir sorguyu (örneğin, bir Microsoft SQL Server veritabanında saklı yordam gibi) çağırmanız gerekiyorsa, *lpszSQL*'e geçirdiğiniz dizeye bir **çağrı** bildirisi yazmanız gerekir. Sihirbazlar, önceden tanımlanmış bir sorguyu çağırmak için bir kayıt kümesi sınıfının bildirimini desteklemez. Önceden tanımlanmış tüm sorgular kayıt döndürmez.

Önceden tanımlanmış bir sorgu kayıt döndürmezse, `CDatabase` üye işlevini `ExecuteSQL` doğrudan kullanabilirsiniz. Kayıtları döndüren önceden tanımlanmış bir sorgu için, içindeki RFX çağrılarını `DoFieldExchange` yordamın döndürdüğü herhangi bir sütun için el ile de yazmanız gerekir. RFX çağrıları aynı sırada olmalıdır ve önceden tanımlanmış sorguyla aynı türleri döndürmelidir. Daha fazla bilgi için bkz. [kayıt kümesi: önceden tanımlanmış sorgu için bir sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: doğrudan SQL çağrıları yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
