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
ms.openlocfilehash: 42c36259b14a7f0341e383bb3a7f2760bab165aa
ms.sourcegitcommit: fcc3aeb271449f8be80348740cffef39ba543407
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82538590"
---
# <a name="data-access-in-visual-c"></a>Visual C++'da Veri Erişimi

Neredeyse tüm veritabanı ürünleri, SQL ve NoSQL, yerel C++ uygulamaları için bir arabirim sağlar. Endüstri standardı arabirimi, tüm büyük SQL veritabanı ürünleri ve birçok NoSQL ürünü tarafından desteklenen ODBC 'dir. Microsoft dışı ürünler için daha fazla bilgi edinmek üzere satıcıya başvurun. Çeşitli lisans koşullarına sahip üçüncü taraf kitaplıkları da mevcuttur.

2011 Microsoft, yerel uygulamaların hem şirket içinde hem de buluttaki Microsoft SQL Server veritabanlarına bağlanmasına yönelik standart olarak ODBC 'yi hizalamıştır. Daha fazla bilgi için bkz. [veri erişimi \(programlama MFC-\)ATL](data-access-programming-mfc-atl.md). C++/CLı kitaplıkları yerel ODBC sürücülerini veya ADO.NET kullanabilir. Daha fazla bilgi için bkz. [ADO.NET kullanarak veri erişimi (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) ve [Visual Studio 'da verilere erişme](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>Bu Bölümde

[Veri erişim programlama (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Tercih edilen yol, veritabanı API 'Leriyle çalışmayı kolaylaştıran etkin şablon sınıf kitaplığı (ATL) veya Microsoft Foundation Class (MFC) kitaplığı gibi sınıf kitaplıklarından birini kullanmak Visual C++ ile eski veri erişimi programlamayı açıklar.

[Açık Veritabanı Bağlantısı (ODBC)](odbc/open-database-connectivity-odbc.md)<br/>
Microsoft Foundation Sınıfları (MFC) kitaplığı, açık veritabanı bağlantısı (ODBC) ile programlama için sınıflar sağlar.

[OLE DB Programlama](oledb/ole-db-programming.md)<br/>
Özellikle bağlantılı sunucularla programlama yaparken, bazı senaryolarda hala gerekli olan, genellikle eski bir arabirim.

## <a name="related-topics"></a>İlgili Konular

[C ve C++ kullanarak SQL veritabanı 'na bağlanma](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
C veya C++ uygulamalarından Azure SQL veritabanı 'na bağlanın.

[C++ için Microsoft Azure Depolama Istemci kitaplığı](https://github.com/Azure/azure-storage-cpp)<br/>
[Azure depolama](/azure/storage/common/storage-introduction) , müşterilerinin ihtiyaçlarını karşılamak için dayanıklılık, kullanılabilirlik ve ölçeklenebilirlik kullanan modern uygulamalara yönelik bulut depolama çözümüdür. C++ için Azure Storage Istemci kitaplığını kullanarak C++ ' dan Azure depolama 'ya bağlanın.

[SQL Server için ODBC sürücüsü](/sql/connect/odbc/microsoft-odbc-driver-for-sql-server)<br/>
En son ODBC sürücüsü, C/C++ tabanlı uygulamalar için Microsoft SQL Server ve Microsoft Azure SQL Veritabanı güçlü veri erişimi sağlar. Her zaman şifrelenmiş, Azure Active Directory ve AlwaysOn Kullanılabilirlik Grupları dahil olmak üzere Özellikler için destek sağlar. MacOS ve Linux için de kullanılabilir.

[SQL Server için OLE DB sürücüsü](/sql/connect/oledb/oledb-driver-for-sql-server)<br/>
En son OLE DB sürücü, Microsoft SQL Server ve Microsoft Azure SQL Veritabanı destekleyen tek başına bir veri erişim uygulaması programlama arabirimidir (API).

[Microsoft Azure C ve C++ Geliştirici Merkezi](https://azure.microsoft.com/develop/cpp/)<br/>
Azure, sevdiğiniz araçları kullanarak daha fazla esneklik, ölçeklenebilirlik ve güvenilirlik sayesinde C++ uygulamaları oluşturmayı kolaylaştırır.

[C++ ' dan blob depolamayı kullanma](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Azure Blob Storage, bulutta nesne/blob olarak yapılandırılmamış veri depolayan bir hizmettir. Blob Storage belge, medya dosyası veya uygulama yükleyici gibi her tür metin veya ikili veri depolayabilir. Blob Storage aynı zamanda nesne depolama olarak adlandırılır.

[ODBC Programcı başvurusu](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
ODBC arabirimi C programlama diliyle kullanılmak üzere tasarlanmıştır. ODBC arabirimi kullanımı üç alanı kapsar: SQL deyimleri, ODBC işlev çağrıları ve C programlama.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C++](../overview/visual-cpp-in-visual-studio.md)
