---
title: Veri erişim programlama (MFC-ATL)
ms.date: 11/16/2018
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: e71e16bef29239e0c6a391b2d5e2129042cd52fa
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221851"
---
# <a name="data-access-programming-mfcatl"></a>Veri erişim programlama (MFC/ATL)

Yıllar içinde Visual C++ veritabanlarıyla çalışmak için birkaç yol sağlamıştır. 2011'de, SQL Server ürün yerel kod içinden erişmek için tercih edilen teknolojisi olarak açık veritabanı bağlantısı (ODBC) üzerinde hizalama Microsoft duyurdu. ODBC sektör standardı olan ve bunu kullanarak, kodunuzun en fazla taşınabilirlik birden fazla platform ve veri kaynakları üzerinde elde edin. Çoğu SQL veritabanı ürün ve birçok NoSQL ürünleri ODBC desteği. MFC ODBC sarmalayıcı sınıflar veya bir üçüncü taraf C++ sarmalayıcı kitaplıktır kullanın veya doğrudan alt düzey ODBC API'ları çağırarak ODBC kullanabilirsiniz.

OLE DB COM belirtimine göre alt düzey, yüksek performanslı bir API ve yalnızca Windows üzerinde desteklenir. OLE DB kullanırsanız, programınızın erişme [bağlı sunucuları](/sql/relational-databases/linked-servers/linked-servers-database-engine). ATL OLE DB Şablonları, özel OLE DB sağlayıcıları ve tüketici oluşturmayı daha kolay hale getirmek sağlar. Microsoft SQL Server için en son sağlayıcısı için belgelerinde bulunabilir [OLE DB sürücüsü için SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server).

## <a name="porting-data-applications"></a>Veri uygulamalarını taşıma

Eski uygulamanızı SQL Server'a bağlanmak için OLE DB ya da daha üst düzey ADO arabirimini kullanıyorsa, en son sürüme geçirme düşünmelisiniz [OLE DB sürücüsü için SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server) en son SQL Server özelliklerden yararlanmak için. Platformlar arası taşınabilirlik veya en son SQL Server özelliklerini gerektirmiyorsa başka bir alternatif, büyük olasılıkla Microsoft OLE DB sağlayıcısı ODBC (MSDASQL) kullanabilirsiniz.  MSDASQL ODBC sürücüsü aracılığıyla veri kaynaklarına erişim için OLE DB ve ADO (hangi OLEDB dahili olarak kullanılır) üzerinde oluşturulan uygulamalar sağlar. Tüm çeviri katmanı olduğu gibi ile MSDASQL veritabanı performansını etkileyebilir. Etkisi, uygulamanız için önemli olup olmadığını belirlemek için test etmeniz gerekir. MSDASQL Windows işletim sistemiyle birlikte gelir ve teknoloji 64-bit sürümünü eklemek için ilk Windows sürümleri, Windows Server 2008 ve Windows Vista SP1 değildir.

Varsa, C++ uygulama bağlanır SQL Server ya da ODBC aracılığıyla Azure SQL veritabanı, kullanması gereken [en son ODBC sürücüsü](/sql/connect/odbc/download-odbc-driver-for-sql-server).

C + kullanırsanız +/ CLI, devam edebilirsiniz ADO.NET olarak her zaman kullanın. Daha fazla bilgi için [kullanarak veri erişim ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md), ve [Visual Studio'da verilere erişme](/visualstudio/data-tools/accessing-data-in-visual-studio).

- ODBC sarmalayıcı sınıflarının yanı sıra, MFC ayrıca veri erişim nesneleri (DAO) sarmalayıcı sınıflar Access veritabanına bağlanmak için sağlar.  Ancak, DAO kullanımdan kalkmıştır. CDaoDatabase veya CDaoRecordset göre herhangi bir kod yükseltilmelidir.

Veri erişim teknolojileri üzerinde Microsoft Windows geçmişi hakkında daha fazla bilgi için bkz. [Microsoft Data Access Components (Wikipedia)](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Erişimi](data-access-in-cpp.md)<br/>
[Microsoft açık veritabanı bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
