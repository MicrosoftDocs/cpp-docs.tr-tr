---
title: SQL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: df1563d8bb3d53bb405fbb0d89b2b26cc964bd44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093249"
---
# <a name="sql"></a>SQL
SQL (yapılandırılmış sorgu dili) tanımlamak, sorgu, değiştirmek ve veri denetimi olanak sağlayan bir ilişkisel veritabanı ile iletişim kurmak için bir yoldur. SQL sözdizimini kullanarak, belirttiğiniz ölçütlere göre kayıtları ayıklar bir deyim oluşturabilirsiniz.  
  
> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, konu karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL DAO Yardımı'nda bkz.  
  
 SQL deyimleri ile anahtar sözcüğü fiili gibi başlamak **oluşturma** veya **seçin**. SQL çok güçlü bir dildir; tek bir deyimde tüm bir tabloyu etkileyebilir.  
  
 SQL pek çok sürümünde mevcut, her biri belirli bir DBMS aklınızda geliştirilmiştir. MFC veritabanı sınıfları X / açık karşılık gelen SQL deyimlerini ve SQL erişim grubu ortak uygulamalar ortamı (CAE) SQL taslak belirtimine (1991) kümesini tanır. Ek C bu deyimleri söz dizimi hakkında daha fazla bilgi için bkz *ODBC SDK* *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki.  
  
 Bu konuda açıklanmaktadır:  
  
-   [ODBC'ye ve SQL'e arasındaki ilişkiyi](#_core_open_database_connectivity_.28.odbc.29).  
  
-   [Veritabanı sınıfları tarafından kullanılan en yaygın SQL anahtar sözcükleri](#_core_the_database_classes).  
  
-   [SQL veritabanı sınıflarını kullanma](#_core_how_the_database_classes_use_sql).  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Açık veritabanı bağlantısı (ODBC)  
 Veritabanı sınıfları SQL kodda SQL komutlarını katıştırma yerine bir çağrı düzeyi arabirimi kullanan ODBC ile uygulanır. ODBC ile iletişim kurmak için SQL kullanan bir [veri kaynağı](../../data/odbc/data-source-odbc.md) ODBC sürücüleri aracılığıyla. Bu sürücüleri SQL yorumlar ve, gerekirse, Microsoft Access gibi bir belirli veritabanı biçimi ile kullanılmak üzere çevir. ODBC SQL nasıl kullandığı hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md) ve ODBC SDK *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki.  
  
##  <a name="_core_the_database_classes"></a> Veritabanı sınıfları  
 Veritabanı sınıfları işlemek ve var olan verileri güncelleştirmenize izin vermek için tasarlanmış [veri kaynağı](../../data/odbc/data-source-odbc.md). [MFC Uygulama Sihirbazı'nı](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (üzerinden erişilen **sınıfı Ekle**), ve veritabanı sınıfları SQL deyimlerini çoğunu sizin için oluşturur.  
  
 Veritabanı sınıfları SQL veri işleme dili (DML) olarak bilinen bir bölümünü kullanın. Bu komutlar bölümünü veya tümünü veri kaynağı ile çalışma, yeni kayıtlar ekleme, kaydını düzenlemek ve kayıtlarını sil olanak tanır. Aşağıdaki tabloda en yaygın SQL anahtar sözcükleri listeler ve veritabanı sınıfları yöntemleri kullanabilirsiniz.  
  
### <a name="some-common-sql-keywords"></a>Bazı yaygın SQL anahtar sözcükleri  
  
|SQL anahtar sözcüğü|Sihirbazlar ve veritabanı sınıflarını kullanma|  
|-----------------|---------------------------------------------|  
|**SELECT**|Hangi tablolar ve sütunlar veri kaynağındaki kullanılacak olan tanımlamak için.|  
|**WHERE**|Seçimi daraltır bir filtre uygulamak için.|  
|**ORDER BY**|Kayıt kümesi için bir sıralama düzeni uygulamak için.|  
|**EKLE**|Yeni kayıtlar için kayıt eklemek için.|  
|**SİL**|Bir kayıt kümesinden kayıtları silmek için.|  
|**GÜNCELLEŞTİRME**|Bir kaydın alanlarını değiştirmek için.|  
  
 Ayrıca, veritabanı sınıfları ODBC tanır **ÇAĞRISI** önceden tanımlanmış sorgu (veya saklı yordam) bazı veri kaynaklarında arama için kullanabileceğiniz ifadeler. ODBC veritabanı sürücü bu deyimleri yorumlar ve her DBMS için uygun komut değiştirir.  
  
> [!NOTE]
>  Tüm DBMS Destek **ÇAĞRISI** deyimleri.  
  
 Sınıfları bir kullanıcı tarafından sağlanan bir deyimde tanıyamıyor `CRecordset::Open`, bir tablo adı olarak yorumlanır.  
  
 SQL deyimleri framework nasıl oluşturur, bir açıklama için bkz [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
 SQL veritabanları C ve C++ kullanılan benzer veri türlerini kullanın. Bu benzerlikler tartışma için bkz [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
 Desteklenen SQL deyimleri, veri türleri, SQL temel dilbilgisi ve SQL, ilgili önerilen yayınlara okuma listesi listesi dahil olmak üzere SQL hakkında daha fazla bilgi bulabilirsiniz *ODBC SDK* *Programcı Başvurusu*  MSDN Kitaplığı CD'sindeki.  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> SQL veritabanı sınıflarını kullanma  
 Veri kaynağı ile iletişim kurmak için ODBC veritabanı sınıflarından kayıt kümelerini kullanma ve ODBC kayıtlarını SQL deyimlerini göndererek veri kaynağından alır. Bu konu veritabanı sınıfları ve SQL arasındaki ilişkiyi açıklar.  
  
 Bir SQL deyimini parçalarını oluşturarak bir SQL deyimi bir kayıt oluşturur bir `CString`. Dize olarak oluşturulan bir **seçin** deyimi bir kayıt kümesini döndürür.  
  
 Kayıt kümesi bir SQL deyimi veri kaynağına göndermek için ODBC çağırdığında ODBC Sürücü Yöneticisi deyimi ODBC sürücüsüne gönderir ve isteğe bağlı olarak sürücü temel DBMS gönderir. DBMS kayıtların sonuç kümesini döndürür ve ODBC sürücüsü kayıtları uygulamaya döndürür. Veritabanı sınıfları sonuç bir tür kullanımı uyumlu C++ sınıfta kümesini türetilen program erişiminizi sağlayan `CRecordset`.  
  
 Aşağıdaki konular SQL veritabanı sınıflarını kullanma hakkında daha fazla bilgi sağlar:  
  
-   [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)  
  
-   [SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [ODBC Temelleri](../../data/odbc/odbc-basics.md)