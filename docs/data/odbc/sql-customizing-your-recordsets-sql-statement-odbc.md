---
title: 'SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f385127d1b61e1453eb7a079963da727f82f1874
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098595"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: Kayıt Kümenizin SQL Deyimini Özelleştirme (ODBC)
Bu konuda açıklanmaktadır:  
  
-   Çerçeve bir SQL deyimini nasıl oluşturur  
  
-   SQL deyimi geçersiz kılmak nasıl  
  
> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" DAO Yardım konusuna bakın.  
  
## <a name="sql-statement-construction"></a>SQL deyimi oluşturma  
 Öncelikle bir SQL kayıt seçimini kümenizin taban **seçin** deyimi. Sihirbaz sınıfınız bildirirken bir geçersiz kılma sürümünü Yazar `GetDefaultSQL` şuna benzer üye işlevi (kayıt kümesi sınıfı adlı `CAuthors`).  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 Varsayılan olarak, bu geçersiz kılma Sihirbazı'nı kullanarak belirttiğiniz tablo adı döndürür. Örnekte, "Yazar" tablo adıdır Daha sonra çağırdığınızda kayıt kümesinin **açık** üye işlevi **açık** bir son yapıları **seçin** biçiminde ifade:  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 Burada `table-name` çağırılarak alınır `GetDefaultSQL` ve `rfx-field-list` RFX işlev çağrılarını penceresinden `DoFieldExchange`. Bu için aldığınızdır bir **seçin** deyimi parametreleri veya bir filtre varsayılan deyimiyle değiştirebilirsiniz ancak, bunu bir geçersiz kılma çalışma zamanında sürümle sürece.  
  
> [!NOTE]
>  Boşluk içeren (veya içerebilir) bir sütun adı belirtirseniz, adı köşeli parantez içine almanız gerekir. Örneğin, "Ad" ad "[ilk adı]" olmalıdır.  
  
 Varsayılan değer geçersiz kılmak için **seçin** deyimi, bir tam içeren dize bir geçirin **seçin** çağırdığınızda deyimi **açık**. Kendi varsayılan dizesini oluşturmak yerine kayıt kümesi sağladığınız dizeyi kullanır. Değiştirme deyiminizde içeriyorsa bir **nerede** yan tümcesi içinde filtre belirtmeyin **m_strFilter** sonra gerekir çünkü iki deyimleri filtre. Benzer şekilde, değiştirme deyiminizde içeriyorsa bir **ORDER BY** yan tümcesi içinde bir sıralama belirtmeyin `m_strSort` sahip şekilde iki deyimleri Sırala.  
  
> [!NOTE]
>  Değişmez değer dizeleri filtrelerinizi (veya diğer bölümleri SQL deyimi) kullanıyorsanız, teklif"" olabilir (belirtilmiş ayırıcılar içine almanız) karakteri (veya karakterleri) gibi dizeleri DBMS özgü değişmez değer öneki ve değişmez değer soneki.  
  
 Dış birleşimler gibi işlemler için özel sözdizimsel gereksinimlerle bağlı olarak, DBMS da karşılaşabilirsiniz. ODBC işlevlerini sürücünüzden DBMS için bu bilgileri almak için kullanın. Örneğin, arama **:: SQLGetTypeInfo** belirli veri türü için aşağıdaki gibi **SQL_VARCHAR**, istemek için **LITERAL_PREFIX** ve **LITERAL_SUFFIX** karakter. Veritabanı bağımsız kod yazıyorsanız, ek C'de bkz *ODBC SDK ** Programcının Başvurusu* ayrıntılı sözdizimi bilgi için MSDN Kitaplığı CD'sindeki.  
  
 Özel bir SQL deyimi geçirmezseniz kayıtları seçmek için kullandığı SQL deyimi bir kayıt kümesi nesnesi oluşturur. Bunun nasıl yapılacağı çoğunlukla geçirdiğiniz değere bağlıdır. `lpszSQL` parametresinin **açık** üye işlevi.  
  
 Bir SQL genel form **seçin** ifadesi:  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 Tek yönlü eklemek için **DISTINCT** kayıt kümenizin SQL deyimini sözcüktür ilk RFX işlev çağrısında anahtar sözcüğü katıştırılacak `DoFieldExchange`. Örneğin:  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  Salt okunur olarak açılan yalnızca bir kayıt kümesi ile bu tekniği kullanın.  
  
## <a name="overriding-the-sql-statement"></a>SQL deyimi geçersiz kılma  
 Aşağıdaki tabloda olasılıklarını gösterir `lpszSQL` parametresi **açık**. Tablo durumlarda, aşağıdaki tablonun açıklanmıştır.  
  
 **Parametre lpszSQL ve sonuçta elde edilen SQL dizesi**  
  
|Durumu|LpszSQL'de geçirin|Elde edilen SELECT deyimi|  
|----------|------------------------------|------------------------------------|  
|1.|**NULL**|**SEÇİN** *rfx alan listesi* **FROM** *tablo adı*<br /><br /> `CRecordset::Open` çağrıları `GetDefaultSQL` tablo adı alınamıyor. Sonuç dizesini durumlar 2-5, ne bağlı olarak biri `GetDefaultSQL` döndürür.|  
|2|Bir tablo adı|**SEÇİN** *rfx alan listesi* **FROM** *tablo adı*<br /><br /> Alan listesini RFX deyimlerinde alınırlar `DoFieldExchange`. Varsa **m_strFilter** ve `m_strSort` boş olmayan, ekler **nerede** ve/veya **ORDER BY** yan tümceleri.|  
|3 *|Bir tam **seçin** deyimi olmadan bir **nerede** veya **ORDER BY** yan tümcesi|Geçirilen gibi. Varsa **m_strFilter** ve `m_strSort` boş olmayan, ekler **nerede** ve/veya **ORDER BY** yan tümceleri.|  
|4 *|Bir tam **seçin** deyimiyle bir **nerede** ve/veya **ORDER BY** yan tümcesi|Geçirilen gibi. **m_strFilter** ve/veya `m_strSort` gerekir boş ya da iki filtre kalır ve/veya sıralama ifadeleri oluşturulur.|  
|5 *|Saklı yordam çağrısı|Geçirilen gibi.|  
  
 \* `m_nFields` Belirtilen sütun sayısı küçük veya buna eşit olmalıdır **seçin** deyimi. Belirtilen her bir sütunun veri türünü **seçin** deyimi ilgili RFX çıktı sütununun veri türü ile aynı olması gerekir.  
  
### <a name="case-1---lpszsql--null"></a>1 lpszSQL case = NULL  
 Kayıt seçimi ne bağlıdır `GetDefaultSQL` döndürdüğü `CRecordset::Open` çağırır. Durumlar 2-5 olası dizeleri açıklar.  
  
### <a name="case-2---lpszsql--a-table-name"></a>Durum 2 lpszSQL = bir tablo adı  
 Kayıt kümesi RFX kayıt kümesi sınıfının geçersiz kılmada işlevi çağırır sağlanan sütun adlarından sütun listesi oluşturmak için kayıt alanı değişimi (RFX) kullanır. `DoFieldExchange`. Kayıt kümesi sınıfınızı bildirmek için bir sihirbaz kullandıysanız, bu durumda (sihirbazda belirttiğiniz aynı tablo adının geçmesi olması koşuluyla) durum 1 olarak aynı sonucu verir. Sınıfınızı yazmak için bir sihirbaz kullanmazsanız 2 SQL deyimi oluşturmak için en basit yolu durumdur.  
  
 Aşağıdaki örnek bir MFC veritabanı uygulamasından kayıtlar seçen bir SQL deyimi oluşturur. Framework çağırdığında `GetDefaultSQL` üye işlevi işlevi, tablo adını döndürür `SECTION`.  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 SQL için sütun adlarını almak için **seçin** deyimi, framework çağrıları `DoFieldExchange` üye işlevi.  
  
```  
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
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Durum 3 lpszSQL = bir SELECT / FROM deyimi  
 Sütun listesi el ile otomatik olarak oluşturmak RFX güvenmek yerine belirttiğiniz. Bu durumda yapmak isteyebilirsiniz:  
  
-   Belirtmek istediğiniz **DISTINCT** anahtar sözcüğünü aşağıdaki **seçin**.  
  
     İçinde listelenen sütun listesi sütun adlarını ve türlerini aynı sırayla eşleşmelidir `DoFieldExchange`.  
  
-   ODBC işlevini kullanarak sütun değerlerini el ile almak için nedeniniz **:: SQLGetData** bağlamak ve sütunları aldığınız RFX güvenmek yerine.  
  
     Örneğin, bir müşteri, uygulamanızın uygulama dağıtıldıktan sonra veritabanı tablolarında eklenen yeni sütunlar uyum sağlamak isteyebilirsiniz. Sınıf Sihirbazı ile bildirilen zaman bilinmeyen bu ek alan veri üyeleri eklemeniz gerekir.  
  
     İçinde listelenen sütun listesi sütun adlarını ve türlerini aynı sırayla eşleşmelidir `DoFieldExchange`, el ile ilişkili sütun adlarını takip eden. Daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Birden fazla tabloya belirterek tabloları katılmasını istediğiniz **FROM** yan tümcesi.  
  
     Bilgi ve bir örnek için bkz: [kayıt kümesi: bir birleştirme (ODBC) gerçekleştirme](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Durum 4 lpszSQL = SELECT / FROM + WHERE ve/veya ORDER BY  
 Her şeyi belirtin: sütun listesi (RFX çağrılarında göre `DoFieldExchange`), Tablo listesini ve içeriğini bir **nerede** ve/veya bir **ORDER BY** yan tümcesi. Belirtirseniz, **nerede** ve/veya **ORDER BY** yan tümceleri bu şekilde kullanmayın **m_strFilter** ve/veya `m_strSort`.  
  
### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Servis talebi 5 lpszSQL bir saklı yordam çağrısı =  
 Önceden tanımlanmış bir sorguyu (örneğin, bir Microsoft SQL Server veritabanında saklı yordam) çağırmak gerekiyorsa, yazmalısınız bir **ÇAĞRISI** geçirmek için dize deyiminde `lpszSQL`. Sihirbazlar, önceden tanımlanmış sorgu çağırmak için bir kayıt kümesi sınıf bildirme desteklemez. Tüm önceden tanımlanmış sorgular kayıtları döndürmez.  
  
 Önceden tanımlanmış sorgu kayıtları döndürmezse kullanabileceğiniz `CDatabase` üye işlevi `ExecuteSQL` doğrudan. Kayıtları döndüren bir önceden tanımlanmış sorgu için el ile de RFX çağrıları yazmalısınız `DoFieldExchange` yordamı için herhangi bir sütundan döndürür. RFX çağrıları aynı sırayla ve aynı türlerine, önceden tanımlanmış sorgu dönmek gerekir. Daha fazla bilgi için bkz: [kayıt kümesi: bir önceden tanımlanmış sorgu (ODBC için) bir sınıf bildirme](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
