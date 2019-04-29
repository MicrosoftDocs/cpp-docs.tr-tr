---
title: 'SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)'
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
ms.openlocfilehash: eabaab019ee94b0c5617573c534d920ec710e9b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329939"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)

Bu konu şunları açıklar:

- Nasıl bir SQL deyimi framework oluşturur

- SQL deyimi geçersiz kılma

> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıflarına uygulanır. MFC DAO sınıflarına ile çalışıyorsanız, "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" DAO Yardım konusuna bakın.

## <a name="sql-statement-construction"></a>SQL deyimi oluşturma

Kümenizin bir SQL öncelikli olarak kayıt seçimi tabanları **seçin** deyimi. Sihirbaz sınıfınıza bildirdiğinizde, bir geçersiz kılma sürümünü Yazar `GetDefaultSQL` şuna benzer bir üye işlevi (kayıt kümesi sınıfı olarak adlandırılan `CAuthors`).

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

Varsayılan olarak, bu geçersiz kılma Sihirbazı ile belirtilen tablo adını döndürür. Örnekte, "Yazarlar." tablo adıdır Daha sonra çağırdığınızda kayıt kümesinin `Open` üye işlevini `Open` bir sonuç oluşturur **seçin** formun deyimi:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

Burada `table-name` çağırılarak alınır `GetDefaultSQL` ve `rfx-field-list` RFX işlev çağrılarında penceresinden `DoFieldExchange`. Bu için size, bir **seçin** deyimi parametreleri veya bir filtre varsayılan deyimiyle değiştirebilirsiniz ancak, bunu bir geçersiz kılma çalışma zamanında bir sürümle sürece.

> [!NOTE]
>  Boşluk içeren (veya içerebilir) bir sütun adı belirtirseniz, adı köşeli parantez içine almalısınız. Örneğin, adı "" "[ad]" olmalıdır.

Varsayılan geçersiz kılmak için **seçin** deyimi, bir dizeyi içeren eksiksiz bir pass **seçin** çağırdığınızda deyimi `Open`. Kayıt, kendi varsayılan dizesini oluşturmak yerine, sağladığınız dizeyi kullanır. Değiştirme deyiminiz varsa bir **burada** yan tümcesi, bir filtre belirtmeyin `m_strFilter` ardından gerekir çünkü iki ifadeleri filtreleme. Benzer şekilde, değiştirme deyiminiz varsa bir **ORDER BY** yan tümcesi bir sıralamada belirtmeyin `m_strSort` iki deyimleri, sahip olacak şekilde Sırala.

> [!NOTE]
>  Değişmez değer dizeleri filtrelerinizi (veya diğer bölümlerini SQL deyimi) kullanırsanız, "Teklif" gerekebilir (içinde belirtilen sınırlayıcılardan alın) gibi dizeleri DBMS özgü sabit değerli önek ve değişmez değerli karakter (veya karakterler) soneki.

Bu gibi durumlarda, dış birleştirme gibi işlemler için özel sözdizimsel gereksinimler de bağlı olarak, DBMS karşılaşabilirsiniz. ODBC işlevleri için DBMS sürücünüzden bu bilgileri almak için kullanın. Örneğin, çağrı `::SQLGetTypeInfo` , belirli veri türü için gibi `SQL_VARCHAR`LITERAL_PREFIX ve LITERAL_SUFFIX karakterleri istemek için. Veritabanı-bağımsız kod yazıyorsanız bkz [ek C: SQL dil bilgisi](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) içinde [ODBC Programcının Başvurusu](/sql/odbc/reference/odbc-programmer-s-reference) ayrıntılı söz dizimi bilgi.

Özel bir SQL deyimi geçirmezseniz kayıtları seçmek için kullandığı SQL deyimi bir kayıt kümesi nesnesi oluşturur. Nasıl yapıldığını çoğunlukla geçirdiğiniz değere bağlıdır. *lpszSQL* parametresinin `Open` üye işlevi.

Bir SQL genel formu **seçin** deyimidir:

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

Yollarından biri **DISTINCT** kayıt kümenizin SQL deyimini sözcüktür anahtar sözcüğü ilk RFX işlev çağrısında katıştırmak için `DoFieldExchange`. Örneğin:

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
>  Yalnızca salt okunur olarak açılan bir kayıt ile bu tekniği kullanın.

## <a name="overriding-the-sql-statement"></a>SQL deyimi geçersiz kılma

Aşağıdaki tabloda olasılıklarını gösterir *lpszSQL* parametresi `Open`. Tablo durumlarda, aşağıdaki tabloda açıklanmıştır.

**Parametre lpszSQL ve sonuçta elde edilen SQL dizesi**

|Servis talebi|LpszSQL'de geçirin|Sonuçta elde edilen SELECT deyimi|
|----------|------------------------------|------------------------------------|
|1.|NULL|**SEÇİN** *rfx alan listesi* **FROM** *tablo adı*<br /><br /> `CRecordset::Open` çağrıları `GetDefaultSQL` tablo adını almak için. Sonuç dizesi ne bağlı olarak 2-5, durumlarından biri olan `GetDefaultSQL` döndürür.|
|2|Tablo adı|**SEÇİN** *rfx alan listesi* **FROM** *tablo adı*<br /><br /> Alan listesi RFX deyimlerinde alınır `DoFieldExchange`. Varsa `m_strFilter` ve `m_strSort` ekler, boş olmayan **burada** ve/veya **ORDER BY** yan tümceleri.|
|3 \*|Eksiksiz bir **seçin** deyimi olmadan bir **burada** veya **ORDER BY** yan tümcesi|Geçirilen olarak. Varsa `m_strFilter` ve `m_strSort` ekler, boş olmayan **burada** ve/veya **ORDER BY** yan tümceleri.|
|4 \*|Eksiksiz bir **seçin** deyimiyle bir **burada** ve/veya **ORDER BY** yan tümcesi|Geçirilen olarak. `m_strFilter` ve/veya `m_strSort` gerekir boş ya da iki filtre kalır ve/veya sıralama ifadeleri oluşturulur.|
|5 \*|Bir saklı yordam çağrısı|Geçirilen olarak.|

\* `m_nFields` Belirtilen sütun sayısı eşit veya ondan daha az olmalıdır **seçin** deyimi. Belirtilen her bir sütunun veri türünü **seçin** deyimi karşılık gelen RFX çıkış sütununun veri türü ile aynı olması gerekir.

### <a name="case-1---lpszsql--null"></a>1 lpszSQL durumda = NULL

Kayıt seçimi ne bağlıdır `GetDefaultSQL` döndürdüğü `CRecordset::Open` çağırır. Çalışmaları 2'den 5 olası dizeleri açıklar.

### <a name="case-2---lpszsql--a-table-name"></a>2. durum lpszSQL bir tablo adı =

Kayıt, kayıt kümesi sınıfın geçersiz kılmasında RFX işlevi sağlanan sütun adlarından sütun listesi oluşturmak için kayıt alanı değişimi (RFX) kullanır. `DoFieldExchange`. Kayıt kümesi sınıfı bildirmek için bir sihirbaz kullandıysanız, bu durumda (sihirbazda belirtilen aynı tablo adı geçmesi şartıyla) 1. durum aynı sonucu vardır. Bir sihirbaz sınıfınıza yazılacak kullanmazsanız, 2. durum SQL deyimi oluşturmak için en basit yoludur.

Aşağıdaki örnek, bir MFC veritabanı uygulamasından kayıtları seçen bir SQL deyimi oluşturur. Framework çağırdığında `GetDefaultSQL` üye işlevi, işlev, tablonun adını döndürür `SECTION`.

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

SQL için sütun adlarını almak için **seçin** deyimi, framework çağrıları `DoFieldExchange` üye işlevi.

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

Tamamlandığında, SQL deyimini şöyle görünür:

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Durum 3 lpszSQL SELECT = buralardan deyimi

Sütun listesi el ile otomatik olarak oluşturmak için RFX'in güvenmek yerine belirttiğiniz. Bu durumda yapmak isteyebilirsiniz:

- Belirlemek istediğiniz **DISTINCT** anahtar sözcüğü aşağıdaki **seçin**.

   Bağlantısında listelendiği gibi sütun listesi sütun adlarını ve türlerini aynı sırayla eşleşmelidir `DoFieldExchange`.

- ODBC işlevi kullanarak sütun değerlerini el ile almanız nedeniniz `::SQLGetData` bağlamak ve sizin için sütunları almak için RFX güvenmek yerine.

   Örneğin, uygulama dağıtıldıktan sonra uygulamanızın bir müşteri veritabanı tablolarına eklenen yeni sütunlar barındırmak isteyebilirsiniz. Sınıf Sihirbazı ile bildirilen zaman bilinmeyen bu ek alan veri üyeleri eklemeniz gerekir.

   Bağlantısında listelendiği gibi sütun listesi sütun adlarını ve türlerini aynı sırayla eşleşmelidir `DoFieldExchange`çizgidir el ile ilişkili sütunların adları. Daha fazla bilgi için [kayıt kümesi: (ODBC) veri sütunlarını dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- Birden çok tablodan belirterek tabloları birleştirme istediğiniz **FROM** yan tümcesi.

   Bilgi ve örnek için bkz. [kayıt kümesi: Birleşim gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Durum 4 lpszSQL SELECT = / FROM + WHERE ve/veya ORDER BY

Her şeyi belirtin: sütun listesi (RFX çağrılarında göre `DoFieldExchange`), Tablo listesini ve içeriğini bir **burada** ve/veya bir **ORDER BY** yan tümcesi. Belirtirseniz, **burada** ve/veya **ORDER BY** yan tümceleri bu şekilde kullanmayın `m_strFilter` ve/veya `m_strSort`.

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Durum 5 lpszSQL bir saklı yordam çağrısı =

Önceden tanımlanmış sorgu (örneğin, bir Microsoft SQL Server veritabanında bir saklı yordam) çağırmak gerekiyorsa, yazmanız gereken bir **çağrı** geçirmek için dize deyiminde *lpszSQL*. Sihirbazlar, önceden tanımlanmış sorgu çağırmak için bir kayıt kümesi sınıf bildirme desteklemez. Tüm önceden tanımlanmış sorguları, kayıtları döndürür.

Önceden tanımlanmış sorgu kayıtları döndürmezse kullanabileceğiniz `CDatabase` üye işlevi `ExecuteSQL` doğrudan. Kayıt döndüren bir önceden tanımlanmış sorgu için el ile de RFX çağrıları yazmanız gereken `DoFieldExchange` yordamı için tüm sütunları döndürür. RFX çağrılarının aynı sırayla ve aynı türlerini, önceden tanımlanmış sorgu dönüş gerekir. Daha fazla bilgi için [kayıt kümesi: Bir sınıf bildirme (ODBC) önceden tanımlanmış sorgu için](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
