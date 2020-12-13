---
description: 'Daha fazla bilgi edinin: veri erişim programlama (MFC/ATL)'
title: Veri erişim programlama (MFC-ATL)
ms.date: 11/16/2018
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: 7785eb65bd26c6c8bf4b60d5a8a919097627f20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136487"
---
# <a name="data-access-programming-mfcatl"></a>Veri erişim programlama (MFC/ATL)

Yıl boyunca, Visual C++ veritabanlarıyla çalışmak için birkaç yol sağlamıştır. 2011 ' de, Microsoft 'un açık veritabanı bağlantısı (ODBC) üzerinde SQL Server ürünlerine yerel koddan erişmek için tercih edilen teknoloji olarak hizalanmasının duyurulduğunu duyurmuştur. ODBC bir sektör standardıdır ve bunu kullanarak birden çok platform ve veri kaynağı üzerinde kodunuzun en fazla taşınabilirliği elde edersiniz. SQL veritabanı ürünlerinin çoğu ve birçok NoSQL ürünü ODBC 'yi destekler. Alt düzey ODBC API 'Lerini çağırarak ODBC 'yi doğrudan kullanabilirsiniz veya MFC ODBC sarmalayıcı sınıflarını veya bir üçüncü taraf C++ sarmalayıcı kitaplığını kullanabilirsiniz.

OLE DB, COM belirtimine dayalı düşük düzeyli ve yüksek performanslı bir API 'dir ve yalnızca Windows 'da desteklenir. Programınız [bağlantılı sunuculara](/sql/relational-databases/linked-servers/linked-servers-database-engine)erişiyorsa OLE DB kullanın. ATL, özel OLE DB sağlayıcıları ve tüketiciler oluşturmayı kolaylaştıran OLE DB şablonlar sağlar. Microsoft SQL Server için en son sağlayıcı, [SQL Server OLE DB sürücüsüne](/sql/connect/oledb/oledb-driver-for-sql-server)yönelik belgelerde bulunabilir.

## <a name="porting-data-applications"></a>Veri Uygulamalarını Taşıma

Eski uygulamanız SQL Server bağlanmak için OLE DB veya daha yüksek düzeyde bir ADO arabirimi kullanıyorsa, en son SQL Server özelliklerinden faydalanmak için SQL Server için en son [OLE DB sürücüsüne](/sql/connect/oledb/oledb-driver-for-sql-server) geçiş yapmayı düşünmelisiniz. Başka bir alternatif olarak, platformlar arası taşınabilirlik veya en son SQL Server özellikler gerektirmiyorsa, ODBC için Microsoft OLE DB sağlayıcısı 'nı (MSDASQL) kullanabilirsiniz.  MSDASQL, bir ODBC sürücüsü aracılığıyla veri kaynaklarına erişmek için OLE DB ve ADO (Şirket içinde OLEDB kullanır) üzerinde oluşturulan uygulamalara izin verir. Tüm çeviri katmanında olduğu gibi, MSDASQL de veritabanı performansını etkileyebilir. Etkinin uygulamanız için önemli olup olmadığını anlamak için test etmelisiniz. MSDASQL Windows işletim sistemiyle birlikte gelir ve Windows Server 2008 & Windows Vista SP1, teknolojinin 64 bit sürümünü içeren ilk Windows sürümlerdir.

C++ uygulamanız ODBC aracılığıyla SQL Server veya Azure SQL veritabanı 'na bağlanırsa, [en son ODBC sürücüsünü](/sql/connect/odbc/download-odbc-driver-for-sql-server)kullanmalıdır.

C++/CLı kullanıyorsanız, her zaman ADO.NET kullanmaya devam edebilirsiniz. Daha fazla bilgi için bkz. [ADO.NET kullanarak veri erişimi (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)ve [Visual Studio 'da verilere erişme](/visualstudio/data-tools/accessing-data-in-visual-studio).

- MFC, ODBC sarmalayıcı sınıflarına ek olarak, Access veritabanlarına bağlanmak için veri erişim nesneleri (DAO) sarmalayıcı sınıfları da sağlar.  Ancak, DAO artık kullanılmıyor. CDaoDatabase veya CDaoRecordset ' i temel alan herhangi bir kod yükseltilmelidir.

Microsoft Windows 'daki veri erişimi teknolojilerinin geçmişi hakkında daha fazla bilgi için bkz. [Microsoft Data Access Components (Vikipedi)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Erişimi](data-access-in-cpp.md)<br/>
[Microsoft açık veritabanı bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
