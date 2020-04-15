---
title: SQL
ms.date: 05/09/2019
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
ms.openlocfilehash: e5ab824f850b6050e11c10734dd709330af416b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376435"
---
# <a name="sql"></a>SQL

SQL (Yapılandırılmış Sorgu Dili), verileri tanımlamanızı, sorgulamanızı, değiştirmenizi ve denetlemenizi sağlayan ilişkisel bir veritabanıyla iletişim kurmanın bir yoludur. SQL sözdizimini kullanarak, belirttiğiniz ölçütlere göre kayıtları ayıklayan bir deyim oluşturabilirsiniz.

> [!NOTE]
> Bu bilgiler MFC ODBC sınıfları için geçerlidir. MFC DAO sınıfları ile çalışıyorsanız, DAO Help'de Microsoft Jet Database Engine SQL ve ANSI SQL'in karşılaştırma konusuna bakın.

SQL deyimleri **CREATE** veya **SELECT**gibi bir anahtar kelime fiili ile başlar. SQL çok güçlü bir dildir; tek bir ifade tüm tabloyu etkileyebilir.

SQL'in her biri belirli bir DBMS düşünülarak geliştirilen birçok sürümü vardır. MFC veritabanı sınıfları, X/Open ve SQL Access Group Ortak Uygulamalar Ortamı (CAE) SQL taslak belirtimine (1991) karşılık gelen bir dizi SQL deyimitanır. Bu ifadelerin sözdizimi hakkında bilgi için, MSDN Kitaplığı CD'sindeki *ODBC SDK* *Programcısı* Referansı'ndaki Ek C'ye bakın.

Bu konu açıklar:

- [ODBC ve SQL arasındaki ilişki.](#_core_open_database_connectivity_.28.odbc.29)

- [Veritabanı sınıfları tarafından kullanılan en yaygın SQL anahtar kelimeleri.](#_core_the_database_classes)

- [Veritabanı sınıfları SQL'i nasıl kullanır?](#_core_how_the_database_classes_use_sql)

## <a name="open-database-connectivity-odbc"></a><a name="_core_open_database_connectivity_.28.odbc.29"></a>Açık Veritabanı Bağlantısı (ODBC)

Veritabanı sınıfları, koda SQL komutları yerleştirmek yerine çağrı düzeyinde bir arabirimde SQL kullanan ODBC ile uygulanır. ODBC, odbc sürücüleri aracılığıyla bir [veri kaynağıyla](../../data/odbc/data-source-odbc.md) iletişim kurmak için SQL kullanır. Bu sürücüler SQL'i yorumlar ve gerekirse Microsoft Access gibi belirli bir veritabanı biçimiyle kullanmak üzere çevirir. ODBC'nin SQL'i nasıl kullandığı hakkında daha fazla bilgi için, [MSDN](../../data/odbc/odbc-basics.md) Kitaplığı CD'sindeki ODBC ve ODBC SDK *Programcısı Referansı'na* bakın.

## <a name="database-classes"></a><a name="_core_the_database_classes"></a>Veritabanı Sınıfları

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Veritabanı sınıfları, varolan bir [veri kaynağındaki](../../data/odbc/data-source-odbc.md)verileri işlemeve güncelleştirmenize izin vermek üzere tasarlanmıştır. [MFC Uygulama Sihirbazı,](../../mfc/reference/database-support-mfc-application-wizard.md) [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) **(Add Class**üzerinden erişilen) ve veritabanı sınıfları sizin için SQL deyimlerinin çoğunu oluşturmak.

Veritabanı sınıfları, Veri Düzenleme Dili (DML) olarak bilinen SQL'in bir bölümünü kullanır. Bu komutlar, veri kaynağının tamamı veya bir kısmıyla çalışmanızı, yeni kayıtlar eklemenizi, kayıtları nızı düzene eklemenizi ve kayıtları silmenizi sağlar. Aşağıdaki tabloda en yaygın SQL anahtar kelimeleri ve veritabanı sınıfları bunları kullanma yöntemleri listelenir.

### <a name="some-common-sql-keywords"></a>Bazı Yaygın SQL Anahtar Kelimeleri

|SQL anahtar kelimesi|Sihirbazlar ve veritabanı sınıfları bunu kullanır|
|-----------------|---------------------------------------------|
|**Seçin**|Veri kaynağındaki tabloların ve sütunların hangilerinin kullanılacağını belirlemek için.|
|**WHERE**|Seçimi daraltan bir filtre uygulamak için.|
|**SİPARİŞ VEREN**|Kayıt kümesine bir sıralama sırası uygulamak için.|
|**Ekle**|Kayıt kümesine yeni kayıtlar eklemek için.|
|**Silmek**|Kayıtları bir kayıt kümesinden silmek için.|
|**Güncelleştirme**|Bir kaydın alanlarını değiştirmek için.|

Ayrıca, veritabanı sınıfları, bazı veri kaynaklarında önceden tanımlanmış bir sorgu (veya depolanan yordam) çağırmak için kullanabileceğiniz ODBC **CALL** deyimlerini tanır. ODBC veritabanı sürücüsü bu ifadeleri yorumlar ve her DBMS için uygun komutu yerine geçer.

> [!NOTE]
> Tüm DBMSs **CALL** deyimlerini desteklemez.

Sınıflar kullanıcı tarafından sağlanan bir deyimi `CRecordset::Open`tanıyamıyorsa, tablo adı olarak yorumlanır.

Çerçevenin SQL deyimlerini nasıl oluşturup oluşturabildiğini açıklayan bir açıklama için bkz: [Recordset: Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) ve [SQL: Recordset'inSQL Bildirimini (ODBC) özelleştirme.](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

SQL veritabanları C ve C++'da kullanılanlara benzer veri türleri kullanır. Bu benzerliklerin tartışılması için [SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)bölümüne bakın.

Desteklenen SQL deyimlerinin, veri türlerinin, SQL çekirdek dilbilgisinin ve SQL hakkında önerilen yayınların okuma listesi de dahil olmak üzere, MSDN Kitaplığı CD'sindeki *ODBC SDK* *Programcısının Başvurusu'nda* SQL hakkında daha fazla bilgi bulabilirsiniz.

## <a name="how-the-database-classes-use-sql"></a><a name="_core_how_the_database_classes_use_sql"></a>Veritabanı Sınıfları SQL'i Nasıl Kullanır?

Veritabanı sınıflarından elde ettiğiniz kayıt kümeleri, bir veri kaynağıyla iletişim kurmak için ODBC'yi kullanır ve ODBC, SQL deyimleri göndererek kayıtları veri kaynağından alır. Bu konu veritabanı sınıfları ve SQL arasındaki ilişkiyi açıklar.

Bir kayıt kümesi, bir SQL deyiminin parçalarını bir `CString`. Dize, bir kayıt kümesini döndüren bir **SELECT** deyimi olarak oluşturulur.

Kayıt kümesi veri kaynağına bir SQL deyimi göndermek için ODBC'yi aradığında, ODBC Sürücü Yöneticisi deyimi ODBC sürücüsüne geçirir ve sürücü bunu altta yatan DBMS'ye gönderir. DBMS bir sonuç kayıt kümesini döndürür ve ODBC sürücüsü kayıtları uygulamaya döndürür. Veritabanı sınıfları, programınızın türetilen tür güvenli bir C++ `CRecordset`sınıfında ki sonuca erişmesini sağlar.

Aşağıdaki konular veritabanı sınıfları SQL kullanımı hakkında daha fazla bilgi sağlar:

- [SQL: Kayıt Setinizin SQL Bildirimini Özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: Doğrudan SQL Çağrıları Yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[ODBC Temelleri](../../data/odbc/odbc-basics.md)
