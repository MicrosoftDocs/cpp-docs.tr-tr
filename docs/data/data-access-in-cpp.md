---
title: "Visual C++'da veri erişimi | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9bae9c7d8e50ca12767e5baed436912f04daafd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-access-in-visual-c"></a>Visual C++'da Veri Erişimi

Neredeyse tüm veritabanı ürünler, SQL ve NoSQL, yerel C++ uygulamaları için bir arabirim sağlar. Endüstri Standart önde gelen tüm SQL veritabanı ürünleri ve birçok NoSQL ürünleri tarafından desteklenmeyen ODBC arabirimidir. Microsoft olmayan ürünler için daha fazla bilgi için satıcısına başvurun. Üçüncü taraf kitaplıklar çeşitli Lisans Koşulları'nı ile de kullanılabilir.

Bu yana 2011 Microsoft, Microsoft SQL Server veritabanları, her iki şirket içi ve buluttaki bağlamak üzere yerel uygulamalar için standart olarak ODBC hizalı. Daha fazla bilgi için bkz: [veri erişim programlama \(MFC ATL\)](data-access-programming-mfc-atl.md). C + +/ CLI kitaplıkları yerel ODBC sürücüleri ya da ADO.NET kullanabilirsiniz. Daha fazla bilgi için bkz: [veri erişimi kullanarak ADO.NET (C + +/ CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) ve [Visual Studio'da veri erişimi](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>Bu Bölümde
[Veri erişim programlama (MFC/ATL)](data-access-programming-mfc-atl.md) Describes eski veri erişim tercih edilen yol olduğu etkin şablon sınıf kitaplığı (ATL) veya Microsoft Foundation Class (MFC) kitaplığı gibi sınıf kitaplıklarından birini kullanmak için Visual C++ ile programlama hangi veritabanı API'leri ile çalışmayı kolaylaştırır.

[Açık veritabanı bağlantısı (ODBC)](odbc/open-database-connectivity-odbc.md) Microsoft Foundation sınıfları (MFC) kitaplığı programlama açık veritabanı bağlantısı (ODBC) için sınıflar sağlar.

[OLE DB programlama](oledb/ole-db-programming.md) özellikle, karşı programlama yaparken, bazı senaryolarda hala gereken daha çok eski bir arabirim bağlantılı sunucuları.

## <a name="related-topics"></a>İlgili Konular
[C ve C++ kullanarak SQL veritabanına bağlan](/azure/sql-database/sql-database-develop-cplusplus-simple) C veya C++ uygulamaları Azure SQL veritabanına bağlanın.

[C++ için Microsoft Azure Storage istemci Kitaplığı](https://github.com/Azure/azure-storage-cpp)
[Azure Storage](/azure/storage/storage-introduction) bulut depolama çözümüdür dayanıklılık, kullanılabilirlik ve ölçeklenebilirlik gereksinimlerini karşılamak üzere kullanan modern uygulamalar için kendi Müşteriler. C++ için Azure Storage istemci kitaplığı kullanılarak C++ içinden Azure depolama birimine bağlayın.

[ODBC sürücüsü 13,1 SQL Server - Windows yayımlanan](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server) C/C++ tabanlı uygulamaları için son ODBC sürücüsü Microsoft SQL Server 2016 Microsoft Azure SQL veritabanı için sağlam veri erişimi sağlar. Özellikleri dahil olmak üzere her zaman şifreli desteği, Azure Active Directory ve AlwaysOn Kullanılabilirlik grupları sağlar. MacOS ve Linux için de kullanılabilir.     
 
[SQL Server Native Client](https://msdn.microsoft.com/library/ms130892.aspx) SQL Server Native Client olan OLE DB ve SQL Server 2005'te SQL Server 2014 aracılığıyla destekleyen ODBC için kullanılan tek başına veri erişim uygulama programlama arabirimi (API). Yeni uygulamalar için SQL Server ODBC sürücüsü 13,1 kullanmalıdır.

[Microsoft Azure C ve C++ Geliştirme Merkezi](https://azure.microsoft.com/develop/cpp/) Azure artan esneklik, ölçeklenebilirlik ve güvenilirlik sevdiğiniz araçlarını kullanarak C++ uygulamalar oluşturmanızı kolaylaştırır.    

[C++ içinden BLOB Storage kullanma](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs) Azure Blob storage, bulutta nesne/BLOB olarak yapılandırılmamış veri depolayan bir hizmetidir. BLOB Depolama metin veya ikili veriler, belge, ortam dosyası veya uygulama Yükleyici gibi herhangi bir türde depolayabilirsiniz. BLOB storage ayrıca nesne depolama olarak adlandırılır.

[ODBC Programcının Başvurusu](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference) ODBC arabirimi C programlama dili ile kullanılmak üzere tasarlanmıştır. ODBC arabirimi kullanımını yayılan üç alanları: SQL deyimlerini, ODBC işlev çağrılarını ve C programlama.

## <a name="see-also"></a>Ayrıca Bkz.
[Visual C++](../visual-cpp-in-visual-studio.md)
