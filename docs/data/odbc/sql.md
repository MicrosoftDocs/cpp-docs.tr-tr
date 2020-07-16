---
title: SQL
ms.date: 05/09/2019
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
ms.openlocfilehash: cdceec9f4a6a39e9e1a50fc002d4220801e8d15a
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404274"
---
# <a name="sql"></a>SQL

SQL (Yapılandırılmış Sorgu Dili), verileri tanımlamanıza, sorgulamanızı, değiştirmenize ve denetlemenize olanak tanıyan ilişkisel bir veritabanıyla iletişim kurmanın bir yoludur. SQL söz dizimini kullanarak, belirttiğiniz ölçütlere göre kayıtları ayıklayan bir ifade oluşturabilirsiniz.

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıflarıyla çalışıyorsanız, DAO yardımı 'nda Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL ' in karşılaştırması konusuna bakın.

SQL deyimleri **Create** veya **Select**gibi bir anahtar sözcük fiili ile başlar. SQL çok güçlü bir dildir; tek bir ifade, bir tablonun tamamını etkileyebilir.

Her biri göz önünde bulundurularak geliştirilen pek çok SQL sürümü vardır. MFC veritabanı sınıfları, X/Open ve SQL Access Group ortak uygulamalar ortamı (CAE) SQL taslak belirtimine (1991) karşılık gelen bir SQL deyimleri kümesini algılar. Bu deyimlerin sözdizimi hakkında daha fazla bilgi için, bkz. Ek C, [ODBC Programcı Başvuru](/sql/odbc/reference/odbc-programmer-s-reference) belgeleri.

Bu konuda aşağıdakiler açıklanmaktadır:

- [ODBC ve SQL arasındaki ilişki](#_core_open_database_connectivity_.28.odbc.29).

- [Veritabanı sınıfları tarafından kullanılan en YAYGıN SQL anahtar sözcükleri](#_core_the_database_classes).

- [Veritabanı SıNıFLARı SQL 'ı nasıl kullanır](#_core_how_the_database_classes_use_sql).

## <a name="open-database-connectivity-odbc"></a><a name="_core_open_database_connectivity_.28.odbc.29"></a>Açık veritabanı bağlantısı (ODBC)

Veritabanı sınıfları, koda SQL komutları katıştırmak yerine SQL 'yi çağrı düzeyinde bir arabirimde kullanarak ODBC ile uygulanır. ODBC, ODBC sürücüleri aracılığıyla bir [veri kaynağıyla](../../data/odbc/data-source-odbc.md) iletişim kurmak için SQL kullanır. Bu sürücüler, SQL 'i Yorumlar ve gerekirse, Microsoft Access gibi belirli bir veritabanı biçimiyle kullanılmak üzere çevirir. ODBC 'nin SQL 'in nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC Programcı Başvuru](/sql/odbc/reference/odbc-programmer-s-reference) belgeleri.

## <a name="database-classes"></a><a name="_core_the_database_classes"></a>Veritabanı sınıfları

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Veritabanı sınıfları, var olan bir [veri kaynağındaki](../../data/odbc/data-source-odbc.md)verileri değiştirmenize ve güncelleştirmenize olanak sağlayacak şekilde tasarlanmıştır. MFC [Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) ( **Sınıf Ekle**aracılığıyla erişilir) ve veritabanı sınıfları sizin için SQL deyimlerinin çoğunu oluşturur.

Veritabanı sınıfları, veri Işleme dili (DML) olarak bilinen bir SQL bölümünü kullanır. Bu komutlar, veri kaynağının tümü veya bir kısmı ile çalışmanıza, yeni kayıtlar eklemenize, kayıtları düzenlemenize ve kayıtları silmenize olanak sağlar. Aşağıdaki tabloda en yaygın SQL anahtar kelimeleri ve veritabanı sınıflarının bunları kullanma yolları listelenmektedir.

### <a name="some-common-sql-keywords"></a>Bazı yaygın SQL anahtar sözcükleri

|SQL anahtar sözcüğü|Sihirbazlar ve veritabanı sınıfları onu kullanır|
|-----------------|---------------------------------------------|
|**SEÇIN**|Veri kaynağındaki hangi tablo ve sütunların kullanılacağını belirlemek için.|
|**WHERE**|Seçimi daralan bir filtre uygulamak için.|
|**SİPARİŞ VEREN**|Kayıt kümesine bir sıralama düzeni uygulamak için.|
|**EKLEYIN**|Yeni kayıtları bir kayıt kümesine eklemek için.|
|**SILMELI**|Kayıt kümesinden kayıtları silmek için.|
|**UPDATE**|Bir kaydın alanlarını değiştirmek için.|

Ayrıca, veritabanı sınıfları bazı veri kaynaklarında önceden tanımlanmış bir sorguyu (veya saklı yordamı) çağırmak için kullanabileceğiniz ODBC **çağrı** deyimlerini tanır. ODBC veritabanı sürücüsü bu deyimleri Yorumlar ve komutu her DBMS için uygun olarak değiştirir.

> [!NOTE]
> Tüm **Dbcepler çağrı** deyimlerini desteklemez.

Sınıflar içinde Kullanıcı tarafından sağlanan bir ifadeyi tanıyamazsa `CRecordset::Open` tablo adı olarak yorumlanır.

Framework 'ün SQL deyimlerini nasıl geliştirdiğinin açıklaması için bkz. [kayıt kümesi: kayıt kümeleri kayıtları seçme (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [SQL: Kayıt Kümenizin SQL DEYIMINI özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

SQL veritabanları, C ve C++ ' da kullanılanlarla benzer veri türlerini kullanır. Bu benzerlikler hakkında bir tartışma için bkz. [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).

Desteklenen SQL deyimlerinin listesi, veri türleri, SQL Core dilbilgisi ve [MICROSOFT SQL](/sql/) belgelerinde SQL hakkında önerilen yayınların okuma listesi dahil olmak üzere SQL hakkında daha fazla bilgi edinebilirsiniz.

## <a name="how-the-database-classes-use-sql"></a><a name="_core_how_the_database_classes_use_sql"></a>Veritabanı sınıfları SQL 'i nasıl kullanır?

Veritabanı sınıflarından türettiğiniz kayıt kümeleri ODBC 'yi bir veri kaynağıyla iletişim kurmak için kullanır ve ODBC, SQL deyimleri göndererek veri kaynağından kayıtları alır. Bu konu, veritabanı sınıfları ve SQL arasındaki ilişkiyi açıklar.

Bir kayıt kümesi SQL ifadesinin parçalarını ' a oluşturarak bir SQL ifadesini oluşturur `CString` . Dize, bir kayıt kümesi döndüren bir **Select** ifadesiyle oluşturulur.

Kayıt kümesi ODBC 'yi bir SQL ifadesini veri kaynağına göndermek için çağırdığında, ODBC Sürücü Yöneticisi, ifadeyi ODBC sürücüsüne geçirir ve sürücü onu temel DBMS 'ye gönderir. DBMS bir kayıt kümesi döndürür ve ODBC sürücüsü kayıtları uygulamaya döndürür. Veritabanı sınıfları, programınızın öğesinden türetilmiş tür açısından güvenli bir C++ sınıfındaki sonuç kümesine erişmesine olanak sağlar `CRecordset` .

Aşağıdaki konularda, veritabanı sınıflarının SQL kullanımı hakkında daha fazla bilgi sağlanmaktadır:

- [SQL: Kayıt Kümenizin SQL deyiminizi özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: doğrudan SQL çağrıları yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[ODBC temelleri](../../data/odbc/odbc-basics.md)
