---
title: Visual C++'da Veri Erişimi
ms.date: 03/28/2017
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
ms.openlocfilehash: a1645c1116daa66c578a6d6e697ab168e4006af9
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150959"
---
# <a name="data-access-in-visual-c"></a>Visual C++'da Veri Erişimi

Neredeyse tüm veritabanı ürünleri, SQL ve NoSQL, yerel C++ uygulamalar için bir arabirim sağlar. Endüstri standardı arabirimi, tüm büyük SQL veritabanı ürünleri ve birçok NoSQL ürünü tarafından desteklenen ODBC 'dir. Microsoft dışı ürünler için daha fazla bilgi edinmek üzere satıcıya başvurun. Çeşitli lisans koşullarına sahip üçüncü taraf kitaplıkları da mevcuttur.

2011 Microsoft, yerel uygulamaların hem şirket içinde hem de buluttaki Microsoft SQL Server veritabanlarına bağlanmasına yönelik standart olarak ODBC 'yi hizalamıştır. Daha fazla bilgi için bkz. [veri erişim programlama \(MFC-ATL\)](data-access-programming-mfc-atl.md). C++/CLı kitaplıkları yerel ODBC sürücülerini veya ADO.NET kullanabilir. Daha fazla bilgi için bkz. [ADO.netC++(/CLI) kullanarak veri erişimi](../dotnet/data-access-using-adonet-cpp-cli.md) ve [Visual Studio 'da verilere erişme](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>Bu Bölümde

[Veri erişim programlama (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Tercih edilen yol, Visual Template Class C++LIBRARY (ATL) veya Microsoft Foundation Class (MFC) kitaplığı gibi sınıf kitaplıklarından birini kullanarak veritabanı API 'leriyle çalışmayı kolaylaştıran, Visual ile eski veri erişimi programlamayı açıklar.

[Açık Veritabanı Bağlantısı (ODBC)](odbc/open-database-connectivity-odbc.md)<br/>
Microsoft Foundation Sınıfları (MFC) kitaplığı, açık veritabanı bağlantısı (ODBC) ile programlama için sınıflar sağlar.

[OLE DB Programlama](oledb/ole-db-programming.md)<br/>
Özellikle bağlantılı sunucularla programlama yaparken, bazı senaryolarda hala gerekli olan, genellikle eski bir arabirim.

## <a name="related-topics"></a>İlgili Konular

[C ve kullanarak SQL veritabanı 'na bağlanmaC++](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
C veya C++ UYGULAMALARDAN Azure SQL veritabanı 'na bağlanın.

[İçin Microsoft Azure Depolama Istemci kitaplığıC++](https://github.com/Azure/azure-storage-cpp)<br/>
[Azure depolama](/azure/storage/storage-introduction) , müşterilerinin ihtiyaçlarını karşılamak için dayanıklılık, kullanılabilirlik ve ölçeklenebilirlik kullanan modern uygulamalara yönelik bulut depolama çözümüdür. İçin C++Azure Storage istemci kitaplığı C++ 'Nı kullanarak üzerinden Azure depolama 'ya bağlanın.

[SQL Server için ODBC sürücüsü](/sql/connect/odbc/microsoft-odbc-driver-for-sql-server)<br/>
En son ODBC sürücüsü, C/C++ tabanlı uygulamalara yönelik Microsoft SQL Server ve Microsoft Azure SQL veritabanı güçlü veri erişimi sağlar. Her zaman şifrelenmiş, Azure Active Directory ve AlwaysOn Kullanılabilirlik Grupları dahil olmak üzere Özellikler için destek sağlar. MacOS ve Linux için de kullanılabilir.

[SQL Server için OLE DB sürücüsü](/sql/connect/oledb/oledb-driver-for-sql-server)<br/>
En son OLE DB sürücü, Microsoft SQL Server ve Microsoft Azure SQL Veritabanı destekleyen tek başına bir veri erişim uygulaması programlama arabirimidir (API).

[Microsoft Azure C ve C++ Geliştirici Merkezi](https://azure.microsoft.com/develop/cpp/)<br/>
Azure, sevdiğiniz araçları kullanarak daha C++ fazla esneklik, ölçeklenebilirlik ve güvenilirlik sunan uygulamalar oluşturmayı kolaylaştırır.

[Öğesinden blob depolamayı kullanmaC++](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Azure Blob Storage, bulutta nesne/blob olarak yapılandırılmamış veri depolayan bir hizmettir. Blob Storage belge, medya dosyası veya uygulama yükleyici gibi her tür metin veya ikili veri depolayabilir. Blob Storage aynı zamanda nesne depolama olarak adlandırılır.

[ODBC Programcı başvurusu](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
ODBC arabirimi C programlama diliyle kullanılmak üzere tasarlanmıştır. ODBC arabirimi kullanımı üç alanı kapsar: SQL deyimleri, ODBC işlev çağrıları ve C programlama.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)
