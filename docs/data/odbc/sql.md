---
title: SQL
ms.date: 05/09/2019
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
ms.openlocfilehash: 68c01623ef97e89623dff3f46a952c75ea31a774
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707823"
---
# <a name="sql"></a>SQL

SQL (yapılandırılmış sorgu dili), tanımlayın, sorgu, değiştirmek ve veri denetimi sağlayan ilişkisel bir veritabanı ile iletişim kurmak için kullanılan bir yoldur. SQL söz dizimini kullanarak, belirttiğiniz ölçütlere göre kayıtlar ayıklar bir deyim oluşturabilirsiniz.

> [!NOTE]
>  Bu bilgiler, MFC ODBC sınıflarına uygulanır. MFC DAO sınıflarına ile çalışıyorsanız, ANSI SQL DAO Yardımı'nda ve konu karşılaştırma Microsoft Jet veritabanı altyapısı SQL bakın.

SQL deyimleri ile anahtar sözcüğü fiili gibi başlayan **Oluştur** veya **seçin**. SQL çok güçlü bir dildir; tek bir deyimde bir tablonun tamamını etkileyebilir.

SQL'ın birçok sürümü mevcut, her biri belirli bir DBMS aklınızda geliştirilmiştir. MFC veritabanı sınıfları bir dizi X / açık karşılık gelen SQL deyimleri ve SQL erişim grubu ortak uygulamaları ortam (CAE) SQL taslak belirtimi (1991) algılar. Bu deyimler sözdizimi hakkında daha fazla bilgi için bkz: Ek C *ODBC SDK'sı* *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki.

Bu konu şunları açıklar:

- [ODBC'ye ve SQL'e arasındaki ilişkiyi](#_core_open_database_connectivity_.28.odbc.29).

- [Veritabanı sınıfları tarafından kullanılan en yaygın SQL anahtar sözcükleri](#_core_the_database_classes).

- [SQL veritabanı sınıflarını kullanma](#_core_how_the_database_classes_use_sql).

##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Açık veritabanı bağlantısı (ODBC)

SQL komutları ekleme kodu yerine bir çağrı düzeyi arabirimi SQL kullanan ODBC ile veritabanı sınıflarını uygulanır. ODBC ile iletişim kurmak için SQL kullanan bir [veri kaynağı](../../data/odbc/data-source-odbc.md) aracılığıyla ODBC sürücüleri. Bu sürücüleri SQL yorumlar ve, gerekirse, bir Microsoft Access gibi belirli veritabanı biçimi ile kullanılmak üzere çevir. ODBC SQL nasıl kullandığı hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve ODBC SDK'sı *Programcının Başvurusu* MSDN Kitaplığı CD'sindeki.

##  <a name="_core_the_database_classes"></a> Veritabanı sınıfları

> [!NOTE] 
> MFC ODBC Tüketici Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil. Bir tüketici yine de el ile oluşturabilirsiniz.

Veritabanı sınıfları işlemek ve mevcut veri güncelleştirme izin vermek için tasarlanmış [veri kaynağı](../../data/odbc/data-source-odbc.md). [MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (aracılığıyla erişilen **sınıfı Ekle**), ve veritabanı sınıfları SQL deyimlerinin çoğu sizin için oluşturur.

Veritabanı sınıfları, SQL veri işleme dili (DML) olarak bilinen bir bölümünü kullanın. Bu komutlar, tüm ya da veri kaynağının bir parçası, yeni kayıtlar ekleme, kayıtlarını düzenleyin ve kayıtları silme olanak tanır. Aşağıdaki tabloda en yaygın SQL anahtar sözcüklerini listeler ve veritabanı sınıfları yollarını kullanabilirsiniz.

### <a name="some-common-sql-keywords"></a>Bazı yaygın SQL anahtar sözcükleri

|SQL anahtar sözcüğü|Sihirbazlar ve veritabanı sınıfları bunu kullanın.|
|-----------------|---------------------------------------------|
|**SELECT**|Tanımlamak için hangi tablolar ve sütunlar veri kaynağında kullanıma yöneliktir.|
|**WHERE**|Bir filtre uygulamak için bu seçimi daraltır.|
|**ORDER BY**|Kayıt kümesi için bir sıralama düzeni uygulamak için.|
|**EKLE**|Yeni kayıtlar için bir kayıt eklemek için.|
|**DELETE**|Bir kayıt kümesinden kayıtları silmek için.|
|**GÜNCELLEŞTİRME**|Bir kaydın alanlarını değiştirmek için.|

Ayrıca, ODBC veritabanı sınıfları tanımak **çağrı** deyimleri, bazı veri kaynakları üzerinde önceden tanımlanmış sorgu (veya saklı yordam) aramak için kullanabilirsiniz. ODBC veritabanı sürücüsü, bu deyimler yorumlar ve her DBMS için uygun komut yerini alır.

> [!NOTE]
>  Tüm DBMS Destek **çağrı** deyimleri.

Sınıfları bir kullanıcı tarafından sağlanan bir deyimde tanıyamaz `CRecordset::Open`, bir tablonun adı olarak yorumlanır.

Nasıl framework SQL deyimleri oluşturan bir açıklaması için bkz [kayıt kümesi: Kayıtları seçme biçimi (ODBC) kayıtları nasıl](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

SQL veritabanları, C ve C++ içinde kullanılan benzer veri türlerini kullanın. Bu benzerlikler bir tartışma için bkz [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).

Desteklenen SQL deyimleri, veri türleri, SQL çekirdek dil bilgisi ve ilgili SQL, önerilen yayınlara okuma listesi listesi dahil olmak üzere, SQL hakkında daha fazla bilgi bulabilirsiniz *ODBC SDK* *Programcının Başvurusu*  MSDN Kitaplığı CD'sindeki.

##  <a name="_core_how_the_database_classes_use_sql"></a> SQL veritabanı sınıflarını kullanma

Veritabanı sınıflarından kayıt kümeleri, veri kaynağı ile iletişim kurmak için ODBC kullanma ve ODBC kayıt veri kaynağından SQL deyimleri göndererek alır. Bu konu, SQL ve veritabanı sınıfları arasındaki ilişkiyi açıklar.

Bir SQL deyiminde parçalarını oluşturarak bir SQL deyimi bir kayıt oluşturur bir `CString`. Dize olarak oluşturulmuş bir **seçin** deyimi kayıt kümesini döndürür.

Kayıt kümesi bir SQL deyimi veri kaynağına göndermek için ODBC çağırdığında, ODBC Sürücü Yöneticisi deyim ODBC sürücüsüne geçer ve isteğe bağlı olarak sürücü için temel alınan DBMS gönderir. DBMS kayıtlarının sonuç kümesi döndürür ve ODBC sürücüsü, uygulamaya kayıtları döndürür. Veritabanı sınıfları sonuç kümesini tür kullanımı uyumlu bir C++ sınıfı türetilen program erişiminizi izin `CRecordset`.

Aşağıdaki konular, SQL veritabanı sınıflarını kullanma hakkında daha fazla bilgi sağlar:

- [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[ODBC Temelleri](../../data/odbc/odbc-basics.md)