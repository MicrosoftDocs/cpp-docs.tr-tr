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
ms.openlocfilehash: 4bb7c4ecbeba76dcd5a6f1de64fa468d0b8e0854
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635727"
---
# <a name="data-access-in-visual-c"></a>Visual C++'da Veri Erişimi

Neredeyse tüm veritabanı ürünler, SQL ve NoSQL, yerel C++ uygulamaları için bir arabirim sağlar. Sektörde standart büyük SQL veritabanı ürün ve birçok NoSQL ürünleri tarafından desteklenen ODBC arabirimidir. Microsoft olmayan ürünler için daha fazla bilgi için satıcıya başvurun. Üçüncü taraf kitaplıklar çeşitli lisans koşullarıyla birlikte de kullanılabilir.

2011'den beri Microsoft, Microsoft SQL Server veritabanlarını, hem şirket içinde ve bulutta bağlama için yerel uygulamalar için standart olarak ODBC hizalı. Daha fazla bilgi için [veri erişim programlama \(MFC-ATL\)](data-access-programming-mfc-atl.md). C + +/ CLI kitaplıklar, yerel ODBC sürücüleri ya da ADO.NET kullanabilirsiniz. Daha fazla bilgi için bkz. [veri erişim ADO.NET kullanma (C + +/ CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) ve [Visual Studio'da verilere erişme](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>Bu Bölümde

[Veri erişim programlama (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Eski veri erişimi etkin şablon sınıf kitaplığı (ATL) veya Microsoft Foundation Class (MFC) kitaplığı gibi API'leri veritabanı ile çalışmayı basitleştiren sınıf kitaplıklarının kullanmayı tercih edilen yol olduğu Visual C++ ile programlama açıklar.

[Açık Veritabanı Bağlantısı (ODBC)](odbc/open-database-connectivity-odbc.md)<br/>
Microsoft Foundation sınıfları (MFC) kitaplığı programlama açık veritabanı bağlantısı (ODBC) için sınıflar sağlar.

[OLE DB Programlama](oledb/ole-db-programming.md)<br/>
Özellikle bağlı sunuculara karşı programlama yaparken yine de bazı senaryolarda gereken bir çoğunlukla eski arabirimi.

## <a name="related-topics"></a>İlgili Konular

[C ve C++ kullanarak SQL veritabanına bağlanma](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
C veya C++ uygulamalarından Azure SQL veritabanı'na bağlanın.

[C++ için Microsoft Azure depolama istemci kitaplığı](https://github.com/Azure/azure-storage-cpp)<br/>
[Azure depolama](/azure/storage/storage-introduction) dayanıklılık, kullanılabilirlik ve ölçeklenebilirlik müşterilerinin ihtiyaçlarını karşılamak üzere dayanan modern uygulamalar için bulut depolama çözümüdür. Azure depolama için C++'tan C++ için Azure depolama istemci kitaplığı kullanarak bağlanın.

[Yayımlanan ODBC sürücüsü 13.1 SQL Server - Windows](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server)<br/>
En son ODBC sürücüsü, C/C++ tabanlı uygulamalar için Microsoft SQL Server 2016 Microsoft Azure SQL veritabanı için güçlü veri erişim sağlar. Her zaman şifreli gibi özellikleri için destek, Azure Active Directory ve AlwaysOn Kullanılabilirlik grupları sağlar. Ayrıca, MacOS ve Linux için de kullanılabilir.

[SQL Server yerel istemcisi](/sql/relational-databases/native-client/sql-server-native-client-programming)<br/>
OLE DB hem de SQL Server 2005, SQL Server 2014'e destekleyen ODBC için kullanılan tek başına veri erişim uygulama programlama arabirimi (API), SQL Server Native Client ' dir. Yeni uygulamalar için SQL Server ODBC sürücüsü 13.1 kullanmanız gerekir.

[Microsoft Azure C ve C++ Geliştirici Merkezi](https://azure.microsoft.com/develop/cpp/)<br/>
Azure ile daha fazla esneklik, ölçeklenebilirlik ve güvenilirlik sevdiğiniz araçları kullanarak C++ uygulamaları oluşturmayı kolaylaştırır.

[BLOB depolama alanından C++ kullanma](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Azure Blob Depolama, yapılandırılmamış verileri nesne/BLOB olarak bulutta depolayan bir hizmettir. BLOB Depolama, herhangi bir türde metin veya belge, medya dosyası veya uygulama Yükleyici gibi ikili veri depolayabilir. BLOB storage ayrıca nesne depolama olarak adlandırılır.

[ ODBC Programcının Başvurusu](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
ODBC arabirimi C programlama dilini ile kullanılmak üzere tasarlanmıştır. ODBC arabirimi kullanımını yayılmış üç alandan: SQL deyimleri, ODBC işlev çağrıları ve C programlama.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++](../visual-cpp-in-visual-studio.md)
