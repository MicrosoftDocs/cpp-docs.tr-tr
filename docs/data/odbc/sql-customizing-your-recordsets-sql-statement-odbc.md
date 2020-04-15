---
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
ms.openlocfilehash: 083d268d2b2f2eef072809b1afde9d6ea34f6996
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374514"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: Kayıt Kümenizin SQL Deyimini Özelleştirme (ODBC)

Bu konu açıklar:

- Çerçeve bir SQL deyimini nasıl oluşturuyor?

- SQL deyimi geçersiz kılma

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, DAO Help'de "Microsoft Jet Database Engine SQL ve ANSI SQL karşılaştırması" konusuna bakın.

## <a name="sql-statement-construction"></a>SQL Bildirimi İnşaatı

Recordset'iniz, öncelikle bir SQL **SELECT** deyimine kaydedilir. Sınıfınızı bir sihirbazla beyan ettiğinizde, üye işlevin `GetDefaultSQL` buna benzer bir şekilde (çağrılan `CAuthors`kayıt kümesi sınıfı için) geçersiz kılınan bir sürümünü yazar.

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

Varsayılan olarak, bu geçersiz kılma sihirbazı ile belirttiğiniz tablo adını döndürür. Örnekte, tablo adı "YAZARLAR" dır. Daha sonra kayıt kümesinin `Open` üye işlevini `Open` aradiğinizde, formun **son** SELECT deyimini oluşturur:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

nerede `table-name` arayarak `GetDefaultSQL` elde `rfx-field-list` edilir ve RFX fonksiyonu `DoFieldExchange`aramaları elde edilir. Varsayılan ekstresini parametrelerle veya filtreyle değiştirebiliyor sanız, çalışma zamanında geçersiz kılınan bir sürümle değiştirmediğiniz sürece **SELECT** deyimi için elde ettiğiniz budur.

> [!NOTE]
> Boşluklar içeren (veya içerebilecek) bir sütun adı belirtirseniz, adı kare ayraçlara koymanız gerekir. Örneğin, "Ad Adı" adı "[İlk Ad]" olmalıdır.

Varsayılan **SELECT** deyimini geçersiz kılmak için, **tam** select deyimini içeren bir dize yi aradığınızda `Open`. Kayıt kümesi, kendi varsayılan dizesini oluşturmak yerine sağladığınız dizeyi kullanır. Değiştirme ekstrenizde bir **WHERE** yan tümcesi varsa, iki filtre deyiminiz olacağı için içeri filtre `m_strFilter` belirtmeyin. Benzer şekilde, değiştirme ekstreniz bir **ORDER BY** yan `m_strSort` tümcesi içeriyorsa, iki tür deyiminin olmaması için bir sıralama belirtmeyin.

> [!NOTE]
> Filtrelerinizde (veya SQL deyiminin diğer bölümlerinde) gerçek dizeleri kullanıyorsanız, bu dizeleri DBMS'ye özgü bir edebi önek ve gerçek sonek karakteri (veya karakterler) ile "alıntı" (belirtilen sınırdışılara dahil etmek) gerekebilir.

DBMS'nize bağlı olarak dış birleştirmeler gibi işlemler için özel sözdizim gereksinimleriyle de karşılaşabilirsiniz. DBMS için sürücünüzden bu bilgileri almak için ODBC işlevlerini kullanın. Örneğin, LITERAL_PREFIX `::SQLGetTypeInfo` ve LITERAL_SUFFIX karakterleri istemek `SQL_VARCHAR`için belirli bir veri türünü çağırın. Veritabanından bağımsız kod yazıyorsanız, ayrıntılı sözdizimi bilgileri için [ODBC Programcısının Başvurusu'nda](/sql/odbc/reference/odbc-programmer-s-reference) [Ek C: SQL Grammar'a](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) bakın.

Bir kayıt kümesi nesnesi, özel bir SQL deyimini geçirmediğiniz sürece kayıtları seçmek için kullandığı SQL deyimini yapır. Bunun nasıl yapılacağı esas olarak üye işlevin *lpszSQL* parametresinde `Open` geçtiğiniz değere bağlıdır.

SQL **SELECT** deyiminin genel biçimi:

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

Recordset'inizin SQL deyimine **DISTINCT** anahtar sözcüğü eklemenin bir yolu, anahtar kelimeyi `DoFieldExchange`ilk RFX işlev çağrısına katıştırmaktır. Örneğin:

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> Bu tekniği yalnızca salt okunur olarak açılan bir kayıt kümesiyle kullanın.

## <a name="overriding-the-sql-statement"></a>SQL Deyimini Geçersiz Kılma

Aşağıdaki *tabloda lpszSQL* parametresinin `Open`. Tablodaki olgular tablodan sonra açıklanır.

**lpszSQL Parametresi ve Elde Edilen SQL String**

|Case (Olay)|lpszSQL'de neler geçer|Ortaya çıkan SELECT deyimi|
|----------|------------------------------|------------------------------------|
|1|NULL|**SELECT** *rfx-alan listesi* **FROM** *tablo adı*<br /><br /> `CRecordset::Open`tablo `GetDefaultSQL` adını almak için arar. Elde edilen dize, ne `GetDefaultSQL` döndürdüğüne bağlı olarak 2 ile 5' e kadar olan durumlardan biridir.|
|2|Tablo adı|**SELECT** *rfx-alan listesi* **FROM** *tablo adı*<br /><br /> Alan listesi RFX ifadelerinden `DoFieldExchange`alınmıştır. Boş `m_strFilter` `m_strSort` değilse ve boş değilse, **WHERE** ve/veya **ORDER BY** yan tümcelerini ekler.|
|3\*|Tam bir **SELECT** deyimi ancak **WHERE** veya **ORDER BY** yan tümcesi olmadan|Geçtikçe. Boş `m_strFilter` `m_strSort` değilse ve boş değilse, **WHERE** ve/veya **ORDER BY** yan tümcelerini ekler.|
|4\*|**WHERE** ve/veya **ORDER BY** yan tümcesi içeren tam bir **SELECT** deyimi|Geçtikçe. `m_strFilter`ve/veya `m_strSort` boş kalmalı veya iki filtre ve/veya sıralama tablosu üretilir.|
|5\*|Depolanan yordam için arama|Geçtikçe.|

\*`m_nFields` **SELECT** deyiminde belirtilen sütun sayısından daha az veya eşit olmalıdır. **SELECT** deyiminde belirtilen her sütunun veri türü, ilgili RFX çıkış sütununun veri türüyle aynı olmalıdır.

### <a name="case-1---lpszsql--null"></a>Örnek 1 lpszSQL = NULL

Kayıt kümesi seçimi, ne `GetDefaultSQL` zaman `CRecordset::Open` adedin döndüğüne bağlıdır. 2'den 5'e kadar olan durumlarda olası dizeleri açıklar.

### <a name="case-2---lpszsql--a-table-name"></a>Case 2 lpszSQL = Tablo Adı

Kayıt kümesi, kayıt kümesi sınıfının geçersiz kılmasında RFX işlevinde sağlanan sütun adlarından sütun listesini oluşturmak için `DoFieldExchange`kayıt alanı değişimi (RFX) kullanır. Kayıt kümesi sınıfınızı bildirmek için bir sihirbaz kullandıysanız, bu durumda durum 1 ile aynı sonuca sahiptir (sihirbazda belirttiğiniz aynı tablo adını geçmeniz koşuluyla). Sınıfınızı yazmak için sihirbaz kullanmıyorsanız, büyük/küçük harf 2, SQL deyimini oluşturmanın en basit yoludur.

Aşağıdaki örnek, bir MFC veritabanı uygulamasından kayıtları seçen bir SQL deyimi oluşturuyor. Çerçeve `GetDefaultSQL` üye işlevi aradığında, işlev tablonun adını `SECTION`döndürür.

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

SQL **SELECT** deyimi için sütunların adlarını almak için, çerçeve `DoFieldExchange` üye işlevi çağırır.

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

Tamamlandığında, SQL deyimi aşağıdaki gibi görünür:

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Case 3 lpszSQL = SELECT/FROM Deyimi

Sütun listesini, otomatik olarak oluşturmak için RFX'e güvenmek yerine elle belirtirsiniz. Bunu şu anda yapmak isteyebilirsiniz:

- **SELECT'i**takiben **DISTINCT** anahtar sözcük ünü belirtmek istiyorsunuz.

   Sütun listeniz sütun adlarını ve türlerini listedeki lerle `DoFieldExchange`aynı sırada eşleştirmelidir.

- Sütunları bağlamak ve almak için RFX'e `::SQLGetData` güvenmek yerine ODBC işlevini kullanarak sütun değerlerini el ile almak için nedeniniz vardır.

   Örneğin, uygulama dağıtıldıktan sonra uygulamanızın bir müşterisinin veritabanı tablolarına ekleyen yeni sütunları barındırmak isteyebilirsiniz. Sınıfı sihirbazla beyan ettiğiniz sırada bilinmeyen bu ekstra alan veri üyelerini eklemeniz gerekir.

   Sütun listeniz, sütun adlarını ve türlerini, el `DoFieldExchange`ile bağlanan sütunların adlarını takip eden, listelenen sırayla eşleştirmelidir. Daha fazla bilgi için [Bkz. Kayıt Kümesi: Dinamik Bağlama Veri Sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- **FROM** yan tümcesinde birden çok tablo belirterek tablolara katılmak istiyorsunuz.

   Bilgi ve örnek için bkz: [Recordset: Join (ODBC) gerçekleştirme.](../../data/odbc/recordset-performing-a-join-odbc.md)

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Case 4 lpszSQL = SELECT/FROM Plus WHERE ve/veya ORDER BY

Her şeyi belirtirsiniz: sütun listesi (RFX `DoFieldExchange`çağrılarına göre), tablo listesi ve **WHERE** ve/veya **ORDER BY** yan tümcesinin içeriği. **WHERE** ve/veya ORDER **BY** yan maddelerinizi bu şekilde `m_strFilter` belirtirseniz, kullanmayın ve/veya `m_strSort`.

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Case 5 lpszSQL = Bir Depolanmış Yordam Çağrısı

Önceden tanımlanmış bir sorgu (Microsoft SQL Server veritabanında depolanmış yordam gibi) çağırmanız gerekiyorsa, *lpszSQL'e*geçtiğiniz dize bir **CALL** deyimi yazmanız gerekir. Sihirbazlar, önceden tanımlanmış bir sorguyu çağırmak için kayıt kümesi sınıfını bildirmeyi desteklemez. Tüm önceden tanımlanmış sorgular kayıtları döndürmez.

Önceden tanımlanmış bir sorgu kayıtları döndürmezse, `CDatabase` üye `ExecuteSQL` işlevini doğrudan kullanabilirsiniz. Kayıtları döndüren önceden tanımlanmış bir sorgu `DoFieldExchange` için, yordamın döndürdettiği sütunlar için RFX çağrılarını el ile yazmanız gerekir. RFX çağrıları aynı sırada olmalı ve önceden tanımlanmış sorguyla aynı türleri döndürmelidir. Daha fazla bilgi için [bkz: Kayıt Kümesi: Önceden Tanımlanmış Sorgu (ODBC) için Bir Sınıf Bildirme.](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
